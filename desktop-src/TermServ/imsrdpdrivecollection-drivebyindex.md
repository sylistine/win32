---
title: IMsRdpDriveCollection DriveByIndex property
description: Retrieves the drive at the specified index.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 28bb2a44-00ac-4892-881d-fdd3fe6adb6b
ms.prod: windows-server-dev
ms.technology: remote-desktop-services
ms.tgt_platform: multiple
keywords:
- DriveByIndex property Remote Desktop Services
- DriveByIndex property Remote Desktop Services , IMsRdpDriveCollection interface
- IMsRdpDriveCollection interface Remote Desktop Services , DriveByIndex property
topic_type:
- apiref
api_name:
- IMsRdpDriveCollection.DriveByIndex
- IMsRdpDriveCollection.get_DriveByIndex
api_location:
- MsTscAx.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# IMsRdpDriveCollection::DriveByIndex property

Retrieves the drive at the specified index.

This property is read-only.

## Syntax


```C++
HRESULT get_DriveByIndex(
  [in]          ULONG index,
  [out, retval] IMsRdpDrive **ppDevice
);
```



## Property value

An [**IMsRdpDrive**](imsrdpdrive.md) interface pointer.

## Error codes

If the method succeeds, **S\_OK** is returned. Any other **HRESULT** value indicates that the call failed.

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                 |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                           |
| Type library<br/>             | <dl> <dt>MsTscAx.dll</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>MsTscAx.dll</dt> </dl>   |
| IID<br/>                      | IID\_IMsRdpDriveCollection is defined as 7ff17599-da2c-4677-ad35-f60c04fe1585<br/> |



## See also

<dl> <dt>

[**IMsRdpDriveCollection**](imsrdpdrivecollection.md)
</dt> </dl>

 

 




