---
Description: Re-enumerates all the scan profiles in the system.
ms.assetid: f5e49645-e81a-4750-8ea5-f0c698a61752
title: IScanProfileMgrRefresh method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IScanProfileMgr::Refresh method

Re-enumerates all the scan profiles in the system.

## Syntax


```C++
HRESULT Refresh();
```



## Parameters

This method has no parameters.

## Return value

Type: **HRESULT**

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

Use this method when more than one [**IScanProfileMgr**](-wia-iscanprofilemgr.md) object might be creating or deleting profiles at the same time.

## Requirements



|                                     |                                                                                             |
|-------------------------------------|---------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                        |
| Header<br/>                   | <dl> <dt>Scanprofilemgr.h</dt> </dl> |
| IDL<br/>                      | <dl> <dt>Scanprofiles.idl</dt> </dl> |



## See also

<dl> <dt>

[**IScanProfileMgr**](-wia-iscanprofilemgr.md)
</dt> <dt>

[Scan Profile Schema](-wia-scan-profile-schema.md)
</dt> </dl>

 

 



