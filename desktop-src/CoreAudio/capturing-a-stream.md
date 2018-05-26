---
Description: Capturing a Stream
ms.assetid: 1d9072dc-4f9b-4111-a747-5eb33ad3ae5b
title: Capturing a Stream
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Capturing a Stream

The client calls the methods in the [**IAudioCaptureClient**](/windows/win32/Audioclient/nn-audioclient-iaudiocaptureclient?branch=master) interface to read captured data from an endpoint buffer. The client shares the endpoint buffer with the audio engine in shared mode and with the audio device in exclusive mode. To request an endpoint buffer of a particular size, the client calls the [**IAudioClient::Initialize**](/windows/win32/Audioclient/nf-audioclient-iaudioclient-initialize?branch=master) method. To get the size of the allocated buffer, which might be different from the requested size, the client calls the [**IAudioClient::GetBufferSize**](/windows/win32/Audioclient/nf-audioclient-iaudioclient-getbuffersize?branch=master) method.

To move a stream of captured data through the endpoint buffer, the client alternately calls the [**IAudioCaptureClient::GetBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getbuffer?branch=master) method and the [**IAudioCaptureClient::ReleaseBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-releasebuffer?branch=master) method. The client accesses the data in the endpoint buffer as a series of data packets. The **GetBuffer** call retrieves the next packet of captured data from the buffer. After reading the data from the packet, the client calls **ReleaseBuffer** to release the packet and make it available for more captured data.

The packet size can vary from one [**GetBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getbuffer?branch=master) call to the next. Before calling **GetBuffer**, the client has the option of calling the [**IAudioCaptureClient::GetNextPacketSize**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getnextpacketsize?branch=master) method to get the size of the next packet in advance. In addition, the client can call the [**IAudioClient::GetCurrentPadding**](/windows/win32/Audioclient/nf-audioclient-iaudioclient-getcurrentpadding?branch=master) method to get the total amount of captured data that is available in the buffer. At any instant, the packet size is always less than or equal to the total amount of captured data in the buffer.

During each processing pass, the client has the option of processing the captured data in one of the following ways:

-   The client alternately calls [**GetBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getbuffer?branch=master) and [**ReleaseBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-releasebuffer?branch=master), reading one packet with each pair of calls, until **GetBuffer** returns AUDCNT\_S\_BUFFEREMPTY, indicating that the buffer is empty.
-   The client calls [**GetNextPacketSize**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getnextpacketsize?branch=master) before each pair of calls to [**GetBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-getbuffer?branch=master) and [**ReleaseBuffer**](/windows/win32/Audioclient/nf-audioclient-iaudiocaptureclient-releasebuffer?branch=master) until **GetNextPacketSize** reports a packet size of 0, indicating that the buffer is empty.

The two techniques yield equivalent results.

The following code example shows how to record an audio stream from the default capture device:


```C++
//-----------------------------------------------------------
// Record an audio stream from the default audio capture
// device. The RecordAudioStream function allocates a shared
// buffer big enough to hold one second of PCM audio data.
// The function uses this buffer to stream data from the
// capture device. The main loop runs every 1/2 second.
//-----------------------------------------------------------

// REFERENCE_TIME time units per second and per millisecond
#define REFTIMES_PER_SEC  10000000
#define REFTIMES_PER_MILLISEC  10000

#define EXIT_ON_ERROR(hres)  \
              if (FAILED(hres)) { goto Exit; }
#define SAFE_RELEASE(punk)  \
              if ((punk) != NULL)  \
                { (punk)->Release(); (punk) = NULL; }

const CLSID CLSID_MMDeviceEnumerator = __uuidof(MMDeviceEnumerator);
const IID IID_IMMDeviceEnumerator = __uuidof(IMMDeviceEnumerator);
const IID IID_IAudioClient = __uuidof(IAudioClient);
const IID IID_IAudioCaptureClient = __uuidof(IAudioCaptureClient);

HRESULT RecordAudioStream(MyAudioSink *pMySink)
{
    HRESULT hr;
    REFERENCE_TIME hnsRequestedDuration = REFTIMES_PER_SEC;
    REFERENCE_TIME hnsActualDuration;
    UINT32 bufferFrameCount;
    UINT32 numFramesAvailable;
    IMMDeviceEnumerator *pEnumerator = NULL;
    IMMDevice *pDevice = NULL;
    IAudioClient *pAudioClient = NULL;
    IAudioCaptureClient *pCaptureClient = NULL;
    WAVEFORMATEX *pwfx = NULL;
    UINT32 packetLength = 0;
    BOOL bDone = FALSE;
    BYTE *pData;
    DWORD flags;

    hr = CoCreateInstance(
           CLSID_MMDeviceEnumerator, NULL,
           CLSCTX_ALL, IID_IMMDeviceEnumerator,
           (void**)&amp;pEnumerator);
    EXIT_ON_ERROR(hr)

    hr = pEnumerator->GetDefaultAudioEndpoint(
                        eCapture, eConsole, &amp;pDevice);
    EXIT_ON_ERROR(hr)

    hr = pDevice->Activate(
                    IID_IAudioClient, CLSCTX_ALL,
                    NULL, (void**)&amp;pAudioClient);
    EXIT_ON_ERROR(hr)

    hr = pAudioClient->GetMixFormat(&amp;pwfx);
    EXIT_ON_ERROR(hr)

    hr = pAudioClient->Initialize(
                         AUDCLNT_SHAREMODE_SHARED,
                         0,
                         hnsRequestedDuration,
                         0,
                         pwfx,
                         NULL);
    EXIT_ON_ERROR(hr)

    // Get the size of the allocated buffer.
    hr = pAudioClient->GetBufferSize(&amp;bufferFrameCount);
    EXIT_ON_ERROR(hr)

    hr = pAudioClient->GetService(
                         IID_IAudioCaptureClient,
                         (void**)&amp;pCaptureClient);
    EXIT_ON_ERROR(hr)

    // Notify the audio sink which format to use.
    hr = pMySink->SetFormat(pwfx);
    EXIT_ON_ERROR(hr)

    // Calculate the actual duration of the allocated buffer.
    hnsActualDuration = (double)REFTIMES_PER_SEC *
                     bufferFrameCount / pwfx->nSamplesPerSec;

    hr = pAudioClient->Start();  // Start recording.
    EXIT_ON_ERROR(hr)

    // Each loop fills about half of the shared buffer.
    while (bDone == FALSE)
    {
        // Sleep for half the buffer duration.
        Sleep(hnsActualDuration/REFTIMES_PER_MILLISEC/2);

        hr = pCaptureClient->GetNextPacketSize(&amp;packetLength);
        EXIT_ON_ERROR(hr)

        while (packetLength != 0)
        {
            // Get the available data in the shared buffer.
            hr = pCaptureClient->GetBuffer(
                                   &amp;pData,
                                   &amp;numFramesAvailable,
                                   &amp;flags, NULL, NULL);
            EXIT_ON_ERROR(hr)

            if (flags & AUDCLNT_BUFFERFLAGS_SILENT)
            {
                pData = NULL;  // Tell CopyData to write silence.
            }

            // Copy the available capture data to the audio sink.
            hr = pMySink->CopyData(
                              pData, numFramesAvailable, &amp;bDone);
            EXIT_ON_ERROR(hr)

            hr = pCaptureClient->ReleaseBuffer(numFramesAvailable);
            EXIT_ON_ERROR(hr)

            hr = pCaptureClient->GetNextPacketSize(&amp;packetLength);
            EXIT_ON_ERROR(hr)
        }
    }

    hr = pAudioClient->Stop();  // Stop recording.
    EXIT_ON_ERROR(hr)

Exit:
    CoTaskMemFree(pwfx);
    SAFE_RELEASE(pEnumerator)
    SAFE_RELEASE(pDevice)
    SAFE_RELEASE(pAudioClient)
    SAFE_RELEASE(pCaptureClient)

    return hr;
}
```



In the preceding example, the RecordAudioStream function takes a single parameter, `pMySink`, which is a pointer to an object that belongs to a client-defined class, MyAudioSink, with two functions, CopyData and SetFormat. The example code does not include the implementation of MyAudioSink because:

-   None of the class members communicates directly with any of the methods in the interfaces in WASAPI.
-   The class could be implemented in a variety of ways, depending on the requirements of the client. (For example, it might write the capture data to a WAV file.)

However, information about the operation of the two methods is useful for understanding the example.

The CopyData function copies a specified number of audio frames from a specified buffer location. The RecordAudioStream function uses the CopyData function to read and save the audio data from the shared buffer. The SetFormat function specifies the format for the CopyData function to use for the data.

As long as the MyAudioSink object requires additional data, the CopyData function outputs the value **FALSE** through its third parameter, which, in the preceding code example, is a pointer to the variable `bDone`. When the MyAudioSink object has all the data that it requires, the CopyData function sets `bDone` to **TRUE**, which causes the program to exit the loop in the RecordAudioStream function.

The RecordAudioStream function allocates a shared buffer that has a duration of one second. (The allocated buffer might have a slightly longer duration.) Within the main loop, the call to the Windows [**Sleep**](https://msdn.microsoft.com/library/windows/desktop/ms686298) function causes the program to wait for a half second. At the start of each **Sleep** call, the shared buffer is empty or nearly empty. By the time the **Sleep** call returns, the shared buffer is about half filled with capture data.

Following the call to the [**IAudioClient::Initialize**](/windows/win32/Audioclient/nf-audioclient-iaudioclient-initialize?branch=master) method, the stream remains open until the client releases all of its references to the [**IAudioClient**](/windows/win32/Audioclient/nn-audioclient-iaudioclient?branch=master) interface and to all references to service interfaces that the client obtained through the [**IAudioClient::GetService**](/windows/win32/Audioclient/nf-audioclient-iaudioclient-getservice?branch=master) method. The final [**Release**](https://msdn.microsoft.com/library/windows/desktop/ms682317) call closes the stream.

## Related topics

<dl> <dt>

[Stream Management](stream-management.md)
</dt> </dl>

 

 


