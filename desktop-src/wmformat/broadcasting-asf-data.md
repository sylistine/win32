---
title: Broadcasting ASF Data
description: Broadcasting ASF Data
ms.assetid: 1b04f361-8147-4f6a-8c9d-d8eeed28550a
keywords:
- Windows Media Format SDK,broadcasting ASF data
- Advanced Systems Format (ASF),broadcasting data
- ASF (Advanced Systems Format),broadcasting data
- Windows Media Format SDK,sending ASF data
- Advanced Systems Format (ASF),sending data
- ASF (Advanced Systems Format),sending data
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Broadcasting ASF Data

This topic describes how to send ASF data across a network using the HTTP protocol. Sending files over a network requires the use of the writer object, so you should have a general understanding of this object before reading this topic. For more information, see [Writing ASF Files](writing-asf-files.md).

If you are starting with uncompressed data, do the following:

1.  Create the writer object by calling the [**WMCreateWriter**](/windows/win32/Wmsdkidl/nf-wmsdkidl-wmcreatewriter?branch=master) function. This function returns an **IWMWriter** pointer.
    ```C++
    IWMWriter *pWriter;
    hr = WMCreateWriter(NULL, &amp;pWriter);
    ```

    

2.  Create the network sink object by calling the [**WMCreateWriterNetworkSink**](/windows/win32/Wmsdkidl/nf-wmsdkidl-wmcreatewriternetworksink?branch=master) function, which returns an **IWMWriterNetworkSink** pointer.
    ```C++
    IWMWriterNetworkSink *pNetSink;
    hr = WMCreateWriterNetworkSink(&amp;pNetSink);
    ```

    

3.  Call [**IWMWriterNetworkSink::Open**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriternetworksink-open?branch=master) on the network sink and specify the port number to open; for example, 8080. Optionally, call [**IWMWriterNetworkSink::GetHostURL**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriternetworksink-gethosturl?branch=master) to get the URL of the host. Clients will access the content from this URL. You can also call [**IWMWriterNetworkSink::SetMaximumClients**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriternetworksink-setmaximumclients?branch=master) to restrict the number of clients.
    ```C++
    DWORD dwPortNum = 8080;
    hr = pNetSink->Open( &amp;dwPortNum)
    ```

    

4.  Attach the network sink to the writer by calling [**IWMWriterAdvanced::AddSink**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriteradvanced-addsink?branch=master) on the writer, with a pointer to the network sink's **IWMWriterNetworkSink** interface.
    ```C++
    IWMWriterAdvanced *pWriterAdvanced;
    hr = pWriter->QueryInterface(IID_IWMWriterAdvanced, ( void** ) pWriterAdvanced );
    if (SUCCEEDED(hr))
    {
        pWriterAdvanced->AddSink(pNetSink);
    }
    ```

    

5.  Set the ASF profile by calling the [**IWMWriter::SetProfile**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-setprofile?branch=master) method on the writer object, with an [**IWMProfile**](iwmprofile.md) pointer. For information about creating a profile, see [Working with Profiles](working-with-profiles.md).
6.  Optionally, specify metadata using the [**IWMHeaderInfo**](/windows/win32/wmsdkidl/nn-wmsdkidl-iwmheaderinfo?branch=master) interface on the writer.
7.  Call [**IWMWriter::BeginWriting**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-beginwriting?branch=master) on the writer.
    ```C++
    hr = pWriter->BeginWriting();
    ```

    

8.  For each sample, call the [**IWMWriter::WriteSample**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-writesample?branch=master) method. Specify the stream number, the presentation time, the duration of the sample, and a pointer to the sample buffer. The **WriteSample** method compresses the samples.
9.  When you are done, call [**IWMWriter::EndWriting**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-endwriting?branch=master) on the writer.
    ```C++
    hr = pWriter->EndWriting();
    ```

    

10. Call [**IWMWriterAdvanced::RemoveSink**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriteradvanced-removesink?branch=master) on the writer to detach the network sink object.
    ```C++
    hr = pWriterAdvanced->RemoveSink(pNetSink);
    ```

    

11. Call [**IWMWriterNetworkSink::Close**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriternetworksink-close?branch=master) on the network sink to release the port.
    ```C++
    hr = pNetSink->Close();
    ```

    

Another way to stream ASF content over a network is to read it from an existing ASF file. The WMVNetWrite sample provided in the SDK demonstrates this approach. In addition to the steps listed previously, do the following:

1.  Create a reader object and call the **Open** method with the name of the file.
2.  Call [**IWMReaderAdvanced::SetManualStreamSelection**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreaderadvanced-setmanualstreamselection?branch=master) on the reader object, with the value **TRUE**. This enables the application to read every stream in the file, including streams with mutual exclusion.
3.  Query the reader for the [**IWMProfile**](iwmprofile.md) interface. Use this pointer when you call [**IWMWriter::SetProfile**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-setprofile?branch=master) on the writer object (step 5 in the previous procedure).
4.  For every stream defined in the profile, call [**IWMProfile::GetStream**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmprofile-getstream?branch=master) to get the stream number. Pass this stream number to the reader's [**IWMReaderAdvanced::SetReceiveStreamSamples**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreaderadvanced-setreceivestreamsamples?branch=master) method. This method informs the reader to deliver compressed samples, rather than decoding them. The samples will be delivered to the application through the application's [**IWMReaderCallbackAdvanced::OnStreamSample**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreadercallbackadvanced-onstreamsample?branch=master) callback method.

    You must obtain codec information for every stream that you read uncompressed and add it to the header before broadcast. To obtain the codec information, call [**IWMHeaderInfo2::GetCodecInfoCount**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmheaderinfo2-getcodecinfocount?branch=master) and [**IWMHeaderInfo2::GetCodecInfo**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmheaderinfo2-getcodecinfo?branch=master) to enumerate the codecs associated with the file in the reader. Select the codec information that matches the stream configuration. Then set the codec information in the writer by calling [**IWMHeaderInfo3::AddCodecInfo**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmheaderinfo3-addcodecinfo?branch=master), passing the information obtained from the reader.

5.  After you set the profile on the writer, call [**IWMWriter::GetInputCount**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-getinputcount?branch=master) on the writer to get the number of inputs. For each input, call [**IWMWriter::SetInputProps**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriter-setinputprops?branch=master) with the value **NULL**. This indicates to the writer object that the application will deliver compressed samples, so the writer does not have to use any codecs to compress the data. Make sure to call **SetInputProps** before calling **BeginWriting**.
6.  Optionally, copy the metadata attributes from the reader to the writer
7.  Because the samples from the reader are already compressed, use the [**IWMWriterAdvanced::WriteStreamSample**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmwriteradvanced-writestreamsample?branch=master) method to write the samples, instead of the **WriteSample** method. The **WriteStreamSample** method bypasses the writer object's usual compression procedures.
8.  When the reader reaches the end of the file, it sends a WMT\_EOF notification to the application.

In addition, the application should drive the clock on the reader object, so that the reader pulls data from the file as quickly as possible. To do this, call the [**IWMReaderAdvanced::SetUserProvidedClock**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreaderadvanced-setuserprovidedclock?branch=master) method on the reader, with the value **TRUE**. After the reader sends the WMT\_STARTED notification, call [**IWMReaderAdvanced::DeliverTime**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreaderadvanced-delivertime?branch=master) and specify the time interval that the reader should deliver. After the reader is done reading this time interval, it calls the application's [**IWMReaderCallbackAdvanced::OnTime**](/windows/win32/Wmsdkidl/nf-wmsdkidl-iwmreadercallbackadvanced-ontime?branch=master) callback method. The application should call **DeliverTime** again to read the next time interval. For example, to read from the file in one-second intervals:


```C++
// Initial call to DeliverTime.
QWORD m_qwTime = 10000000; // 1 second.
hr = m_pReaderAdvanced->DeliverTime(m_qwTime);

// In the callback:
HRESULT CNetWrite::OnTime(QWORD cnsCurrentTime, void *pvContext)
{
    HRESULT hr = S_OK;
    // Continue calling DeliverTime until the end of the file.
    if(!m_bEOF)
    {
        m_qwTime += 10000000; // 1 second.
        hr = m_pReaderAdvanced->DeliverTime(m_qwTime);
    }
    return S_OK;
}
```



## Related topics

<dl> <dt>

[**Sending ASF Data Over a Network**](sending-asf-data-over-a-network.md)
</dt> <dt>

[**Working with Writer Sinks**](working-with-writer-sinks.md)
</dt> </dl>

 

 



