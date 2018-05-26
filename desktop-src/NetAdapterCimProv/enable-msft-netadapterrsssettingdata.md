---
Description: Enables the Receive Side Scaling (RSS) properties on the network adapter.
ms.assetid: ecd9527c-db06-43b1-9437-722584da4c59
title: Enable method of the MSFT\_NetAdapterRssSettingData class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Enable method of the MSFT\_NetAdapterRssSettingData class

Enables the Receive Side Scaling (RSS) properties on the network adapter.

## Syntax


```mof
uint32 Enable(
  [out] string cmdletOutput
);
```



## Parameters

<dl> <dt>

*cmdletOutput* \[out\]
</dt> <dd>

Returns an embedded instance of the [**MSFT\_NetAdapterRssSettingData**](msft-netadapterrsssettingdata.md) class.

</dd> </dl>

## Requirements



|                                     |                                                                                              |
|-------------------------------------|----------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                    |
| Minimum supported server<br/> | Windows Server 2012<br/>                                                               |
| Namespace<br/>                | Root\\StandardCimv2<br/>                                                               |
| MOF<br/>                      | <dl> <dt>NetAdapterCim.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>NetAdapterCim.dll</dt> </dl> |



## See also

<dl> <dt>

[**MSFT\_NetAdapterRssSettingData**](msft-netadapterrsssettingdata.md)
</dt> </dl>

 

 



