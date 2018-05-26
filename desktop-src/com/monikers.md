---
title: Monikers
description: A moniker in COM is not only a way to identify an object \ 8212;a moniker is also implemented as an object.
ms.assetid: 3b52d3bd-8375-4463-a0e3-5117fa96a1c1
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Monikers

A moniker in COM is not only a way to identify an object—a moniker is also implemented as an object. This object provides services allowing a component to obtain a pointer to the object identified by the moniker. This process is referred to as *binding*.

Monikers are objects that implement the [**IMoniker**](/windows/win32/ObjIdl/nn-objidl-imoniker?branch=master) interface and are generally implemented in DLLs as component objects. There are two ways of viewing the use of monikers: as a moniker client, a component that uses a moniker to get a pointer to another object; and as a moniker provider, a component that supplies monikers identifying its objects to moniker clients.

OLE uses monikers to connect to and activate objects, whether they are in the same machine or across a network. A very important use is for network connections. They are also used to identify, connect to, and run OLE compound document link objects. In this case, the link source acts as the moniker provider and the container holding the link object acts as the moniker client.

For more information, see the following topics:

-   [Moniker Clients](moniker-clients.md)
-   [Moniker Providers](moniker-providers.md)
-   [OLE Moniker Implementations](ole-moniker-implementations.md)

## Related topics

<dl> <dt>

[The Component Object Model](the-component-object-model.md)
</dt> </dl>

 

 



