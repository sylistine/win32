---
Description: The CopyMediaType function copies an AM\_MEDIA\_TYPE structure into another structure, including the format block
ms.assetid: 5b47e197-abb5-4b2c-ad65-a506c5e239be
title: CopyMediaType function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CopyMediaType function

The **CopyMediaType** function copies an [**AM\_MEDIA\_TYPE**](/windows/win32/strmif/ns-strmif-_ammediatype?branch=master) structure into another structure, including the format block

## Syntax


```C++
HRESULT WINAPI CopyMediaType(
         AM_MEDIA_TYPE *pmtTarget,
   const AM_MEDIA_TYPE *pmtSource
);
```



## Parameters

<dl> <dt>

*pmtTarget* 
</dt> <dd>

Pointer to an [**AM\_MEDIA\_TYPE**](/windows/win32/strmif/ns-strmif-_ammediatype?branch=master) structure. The method copies the media type into this structure.

</dd> <dt>

*pmtSource* 
</dt> <dd>

Pointer to a source [**AM\_MEDIA\_TYPE**](/windows/win32/strmif/ns-strmif-_ammediatype?branch=master) structure to copy.

</dd> </dl>

## Return value

Returns S\_OK or E\_OUTOFMEMORY.

## Remarks

This function allocates the memory for the format block. If the *pmtTarget* parameter already contains an allocated format block, a memory leak will occur. To avoid a memory leak, call [**FreeMediaType**](freemediatype.md) before calling this function.

After the method returns, call [**FreeMediaType**](freemediatype.md) on *pmtTarget* to free the format block.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Mtype.h (include Streams.h)</dt> </dl>                                                                                     |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**Media Type Functions**](media-type-functions.md)
</dt> </dl>

 

 



