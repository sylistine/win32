---
Description: The PID\_MAP structure contains identifies the contents of an MPEG-2 transport stream packet ID.
ms.assetid: c247ec75-483d-4587-a82f-07bbf6d277b4
title: PID\_MAP structure
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# PID\_MAP structure

The `PID_MAP` structure contains identifies the contents of an MPEG-2 transport stream packet ID.

## Syntax


```C++
typedef struct {
  ULONG                ulPID;
  MEDIA_SAMPLE_CONTENT MediaSampleContent;
} PID_MAP;
```



## Members

<dl> <dt>

**ulPID**
</dt> <dd>

Specifies the packet ID (PID)

</dd> <dt>

**MediaSampleContent**
</dt> <dd>

Specifies the contents of the packet payload, as a [**MEDIA\_SAMPLE\_CONTENT**](media-sample-content.md) enumeration type.

</dd> </dl>

## Requirements



|                   |                                                                                                            |
|-------------------|------------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Bdatypes.h (include Bdaiface.h)</dt> </dl> |



## See also

<dl> <dt>

[DirectShow Structures](directshow-structures.md)
</dt> <dt>

[**IEnumPIDMap Interface**](/windows/win32/Bdaiface/nn-bdaiface-ienumpidmap?branch=master)
</dt> </dl>

 

 



