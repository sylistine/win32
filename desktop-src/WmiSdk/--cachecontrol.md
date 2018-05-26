---
Description: Class is the abstract base class for classes that are used to determine when WMI should release a Component Object Model (COM) object.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 32631610-8c0e-4f04-b0b2-62e5f8e23ef4
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: '\_\_CacheControl class'
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# \_\_CacheControl class

The **\_\_CacheControl** system class is the abstract base class for classes that are used to determine when WMI should release a Component Object Model (COM) object. Instances of this class are never created. The **\_\_CacheControl** class is located only in the root namespace. For more information about using this class, see [Unloading a Provider](unloading-a-provider.md).

The following syntax is simplified from Managed Object Format (MOF) code and includes all inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[abstract]
class __CacheControl : __SystemClass
{
};
```

## Members

The **\_\_CacheControl** class does not define any members.

## Remarks

The **\_\_CacheControl** class is derived from [**\_\_SystemClass**](--systemclass.md).

## Requirements



|                                     |                                |
|-------------------------------------|--------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>       |
| Minimum supported server<br/> | Windows Server 2008<br/> |
| Namespace<br/>                | All WMI namespaces<br/>  |



## See also

<dl> <dt>

[**\_\_SystemClass**](https://msdn.microsoft.com/library/aa394675)
</dt> <dt>

[WMI System Classes](wmi-system-classes.md)
</dt> <dt>

[**\_\_EventConsumerProviderCacheControl**](--eventconsumerprovidercachecontrol.md)
</dt> <dt>

[**\_\_EventProviderCacheControl**](--eventprovidercachecontrol.md)
</dt> <dt>

[**\_\_EventSinkCacheControl**](--eventsinkcachecontrol.md)
</dt> <dt>

[**\_\_ObjectProviderCacheControl**](--objectprovidercachecontrol.md)
</dt> <dt>

[\_\_PropertyProviderCacheControl](--propertyprovidercachecontrol.md)
</dt> <dt>

[Unloading a Provider](unloading-a-provider.md)
</dt> </dl>

 

 



