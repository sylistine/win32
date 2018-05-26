---
Description: Activates the specified IP-HTTPs profile manually.
ms.assetid: 3a000ab7-c239-48a3-98bf-ef8beccaf67a
title: EnableProfile method of the MSFT\_NetIPHttpsConfiguration class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# EnableProfile method of the MSFT\_NetIPHttpsConfiguration class

Activates the specified IP-HTTPs profile manually.

## Syntax


```mof
uint32 EnableProfile(
  [in] string Profile
);
```



## Parameters

<dl> <dt>

*Profile* \[in\]
</dt> <dd>

Specifies the name of the IP-HTTPs profile that you want to activate.

</dd> </dl>

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8<br/>                                                                    |
| Minimum supported server<br/> | Windows Server 2012<br/>                                                          |
| Namespace<br/>                | Root\\StandardCimv2<br/>                                                          |
| Header<br/>                   | <dl> <dt>Rtccore.h</dt> </dl>    |
| MOF<br/>                      | <dl> <dt>NetTtCim.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>NetTtCim.dll</dt> </dl> |



## See also

<dl> <dt>

[**MSFT\_NetIPHttpsConfiguration**](msft-netiphttpsconfiguration.md)
</dt> </dl>

 

 



