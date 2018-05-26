---
Description: Specifies the low-level boost when the decoder performs dynamic range control on a Dolby AC-3 audio stream.
ms.assetid: d723c825-f2f1-4ba0-a667-8285009764fd
title: AVDecDDDynamicRangeScaleLow property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# AVDecDDDynamicRangeScaleLow property

Specifies the low-level boost when the decoder performs dynamic range control on a Dolby AC-3 audio stream.

This property is read/write.

## Data type

**UINT32** (**VT\_UI4**)

## Property GUID

**CODECAPI\_AVDecDDDynamicRangeScaleLow**

## Property value

The value of this property has the following range.



| Value | Description                                                    |
|-------|----------------------------------------------------------------|
| 0     | No dynamic range compression. Preserve the full dynamic range. |
| 100   | Apply full dynamic range compression.                          |



 

## Remarks

This property applies only when the value of the [**AVDecDDOperationalMode**](avdecddoperationalmode-property.md) property is eAVDecDDOperationalMode\_LINE.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps \| UWP apps\]<br/>                     |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Codec API Properties](codec-api-properties.md)
</dt> <dt>

[**ICodecAPI Interface**](/windows/win32/Strmif/nn-strmif-icodecapi?branch=master)
</dt> </dl>

 

 



