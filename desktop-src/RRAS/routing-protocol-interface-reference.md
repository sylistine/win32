---
title: Routing Protocol Interface Reference
description: This documentation describes the functions and structures that are used to implement a routing protocol as a user-mode DLL.
ms.assetid: 0429f5ca-6574-48f5-85ab-70b4677ca539
keywords:
- Routing and Remote Access Service RRAS , Routing Protocol Interface, reference
- Routing Protocol Interface RRAS , reference
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Routing Protocol Interface Reference

This documentation describes the functions and structures that are used to implement a routing protocol as a user-mode DLL.

MPR50 should be defined in the make file for the routing protocol.

The **SIZEOF\_IP\_BINDING(x)** macro computes the size, in bytes, of an [**IP\_ADAPTER\_BINDING\_INFO**](/windows/win32/Routprot/ns-routprot-ip_adapter_binding_info?branch=master) structure that contains the number of IP addresses.

These reference elements are described in the following topics:

-   [Routing Protocol Interface Functions](routing-protocol-interface-functions.md)
-   [Routing Protocol Interface Structures](routing-protocol-interface-structures.md)
-   [IPX Service Table Management](ipx-service-table-management.md)

 

 



