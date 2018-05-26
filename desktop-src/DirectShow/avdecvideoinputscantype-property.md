---
Description: Specifies how the decoded video stream is interlaced.
ms.assetid: a2b95b90-1c58-47f3-b6a8-0f3f6f1a416c
title: AVDecVideoInputScanType property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# AVDecVideoInputScanType property

Specifies how the decoded video stream is interlaced.

This property is read-only.

## Data type

**UINT32** (**VT\_UI4**)

## Property GUID

**CODECAPI\_AVDecVideoInputScanType**

## Property value

The value of this property is a member of the [**eAVDecVideoInputScanType**](/windows/win32/codecapi/?branch=master) enumeration.

## Remarks

The upper 16 bits of the value contain the width, and the lower 16 bits contain the height.

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

 

 



