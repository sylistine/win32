---
Description: Defines the pan/scan aperture, which is the 4&\#215;3 region of video that should be displayed in pan/scan mode.
ms.assetid: faa577fd-6572-46b9-9c6c-f91c47832cb5
title: MF\_MT\_PAN\_SCAN\_APERTURE attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MF\_MT\_PAN\_SCAN\_APERTURE attribute

Defines the pan/scan aperture, which is the 4×3 region of video that should be displayed in pan/scan mode.

## Data type

Byte array

## Remarks

The attribute value is an [**MFVideoArea**](/windows/win32/mfobjects/ns-mfobjects-_mfvideoarea?branch=master) structure.

This attribute is used to crop widescreen video to a 4:3 aspect ratio. The pan/scan aperture is used only in pan/scan mode, which is enabled by setting the [**MF\_MT\_PAN\_SCAN\_ENABLED**](mf-mt-pan-scan-enabled-attribute.md) attribute to **TRUE**.

If pan/scan mode is not enabled, use the display aperture, specified by the [**MF\_MT\_MINIMUM\_DISPLAY\_APERTURE**](mf-mt-minimum-display-aperture-attribute.md) attribute.

If this attribute is not set, the pan/scan aperture is assumed to be the entire video frame.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps \| UWP apps\]<br/>                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps \| UWP apps\]<br/>                        |
| Header<br/>                   | <dl> <dt>Mfapi.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[Media Type Attributes](media-type-attributes.md)
</dt> <dt>

[Picture Aspect Ratio](picture-aspect-ratio.md)
</dt> <dt>

[Video Media Types](video-media-types.md)
</dt> <dt>

[**IMFAttributes::GetBlob**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-getblob?branch=master)
</dt> <dt>

[**IMFAttributes::SetBlob**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-setblob?branch=master)
</dt> <dt>

[**IMFMediaType**](/windows/win32/mfobjects/nn-mfobjects-imfmediatype?branch=master)
</dt> <dt>

[**MF\_MT\_GEOMETRIC\_APERTURE**](mf-mt-geometric-aperture-attribute.md)
</dt> <dt>

[**MF\_MT\_MINIMUM\_DISPLAY\_APERTURE**](mf-mt-minimum-display-aperture-attribute.md)
</dt> <dt>

[**MF\_MT\_PAN\_SCAN\_ENABLED**](mf-mt-pan-scan-enabled-attribute.md)
</dt> </dl>

 

 



