---
Description: Forces the encoder to code the next frame as a key frame.
ms.assetid: 1E252967-6C28-4DA3-9E64-BD276E475753
title: CODECAPI\_AVEncVideoForceKeyFrame property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CODECAPI\_AVEncVideoForceKeyFrame property

Forces the encoder to code the next frame as a key frame.

## Data type

**ULONG** (VT\_UI4)

## Property GUID

**CODECAPI\_AVEncVideoForceKeyFrame**

## Property value

If the value is nonzero, the encoder will code the next frame as a key frame. If the value is zero, the encoder selects whether to encode the next frame as a key frame.

This property applies to the next frame that the encoder receives as input. For a Media Foundation transform (MFT), this is the next frame that is passed to the [**IMFTransform::ProcessInput**](/windows/win32/mftransform/nf-mftransform-imftransform-processinput?branch=master) method. The setting resets to zero after the next frame.

## Remarks

This property is also used with [H.264 UVC 1.5 camera encoders](camera-encoder-h264-uvc-1-5.md).

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps \| UWP apps\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2012 \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> <dt>

[**ICodecAPI**](https://msdn.microsoft.com/library/windows/desktop/dd311953)
</dt> </dl>

 

 



