---
Description: Puts the guest service in a started state.
ms.assetid: 1DC6A5B3-0F91-4AC1-99D5-0E8CF5ED35A2
title: Msvm\_GuestServiceStartService method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Msvm\_GuestService::StartService method

Puts the guest service in a started state.

## Syntax


```C++
uint32 StartService();
```



## Parameters

This method has no parameters.

## Return value

This method returns one of the following values.



| Return code/value                                                                                                                                             | Description         |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| <dl> <dt>**Completed with No Error**</dt> <dt>0</dt> </dl> | Success.<br/> |
| <dl> <dt>**Not supported**</dt> <dt>1</dt> </dl>           |                     |



 

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1 \[desktop apps only\]<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2012 R2 \[desktop apps only\]<br/>                                                 |
| Namespace<br/>                | \\\\Root\\Virtualization\\V2<br/>                                                                 |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



## See also

<dl> <dt>

[**Msvm\_GuestService**](msvm-guestservice.md)
</dt> </dl>

 

 



