---
title: Working with IComponentData
description: The section discusses how to implement the IComponentData interface.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 6b07f5aa-171c-486a-a7b2-c625985785b2
ms.prod: windows-server-dev
ms.technology: microsoft-management-console
ms.tgt_platform: multiple
keywords:
- working with IComponentData MMC
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Working with IComponentData

The section discusses how to implement the [**IComponentData**](/windows/win32/Mmc/nn-mmc-icomponentdata?branch=master) interface.

## Cocreating an IComponentData Object

A snap-in is an in-process server DLL, and the instance of MMC that loads it is its client. For a discussion of how in-process servers are loaded into a caller's process space, refer to the Microsoft Developer Network (MSDN) Library. For a discussion of registering snap-ins, see [Registering and Unregistering a Snap-in](registering-and-unregistering-a-snap-in.md).

For this example, assume that the [**CreateInstance**](_com_iclassfactory_createinstance) method of the snap-in's [**IClassFactory**](_com_iclassfactory) implementation is called and that the snap-in creates an instance of the [**IComponentData**](/windows/win32/Mmc/nn-mmc-icomponentdata?branch=master) interface in response. As a result, the console now has a pointer to the snap-in's **IComponentData** implementation.

Here is the constructor for the [**IComponentData**](/windows/win32/Mmc/nn-mmc-icomponentdata?branch=master) implementation, **CComponentData**:


```C++
CComponentData::CComponentData()
: m_cref(0), m_ipConsoleNameSpace(NULL), m_ipConsole(NULL)
{
    OBJECT_CREATED
    m_pStaticNode = new CStaticNode;
}
```



In the constructor, the **CComponentData** object's reference count is initialized to zero. **CComponentData** caches pointers to the console's [**IConsoleNameSpace**](/windows/win32/Mmc/nn-mmc-iconsolenamespace2?branch=master) and [**IConsole**](/windows/win32/Mmc/nn-mmc-iconsole2?branch=master) interfaces; these pointers are set during the initialization of **CComponentData** in its [**Initialize**](/windows/win32/Mmc/nf-mmc-icomponentdata-initialize?branch=master) method.

OBJECT\_CREATED is a macro that is defined as follows:


```C++
#define OBJECT_CREATED InterlockedIncrement((long *)&amp;g_uObjects);
```



The *g\_uObjects* global variable keeps a global count of the number of snap-in-provided interfaces that MMC is holding at any moment during the lifetime of the snap-in instance.

The constructor also creates an instance of the **CStaticNode** object.

**CStaticNode** inherits from **CDelegationBase**.

## Initializing an IComponentData Object

MMC initializes a snap-in by calling the [**Initialize**](/windows/win32/Mmc/nf-mmc-icomponentdata-initialize?branch=master) method of the [**IComponentData**](/windows/win32/Mmc/nn-mmc-icomponentdata?branch=master) object. During initialization, **IComponentData** should query the console for its [**IConsoleNamespace**](/windows/win32/Mmc/nn-mmc-iconsolenamespace2?branch=master) and [**IConsole**](/windows/win32/Mmc/nn-mmc-iconsole2?branch=master) interfaces using the console's [**IUnknown**](_com_iunknown) interface pointer that is passed into the call to **Initialize**. The snap-in should then cache the returned pointers and use them for calling **IConsoleNamespace** and **IConsole** interface methods.

Initialization is also the correct time for a snap-in to add a strip of icons to the image list using the [**IImageList::ImageListSetStrip**](/windows/win32/Mmc/nf-mmc-iimagelist-imagelistsetstrip?branch=master) method.

## Creating an IComponent Object

When the [**CreateComponent**](/windows/win32/Mmc/nf-mmc-icomponentdata-createcomponent?branch=master) method of the [**IComponentData**](/windows/win32/Mmc/nn-mmc-icomponentdata?branch=master) object is called, the snap-in can create an instance of the [**IComponent**](/windows/win32/Mmc/ns-wmidata-_msmcaevent_pcicomponenterror?branch=master) interface. Typically, the newly created **IComponent** object caches a pointer to its parent **IComponentData** object in its constructor.

Be aware that MMC calls [**CreateComponent**](/windows/win32/Mmc/nf-mmc-icomponentdata-createcomponent?branch=master) each time a new view (a new MDI child window) is created; thus each view is associated with a different [**IComponent**](/windows/win32/Mmc/ns-wmidata-_msmcaevent_pcicomponenterror?branch=master) object.

## Sending Notifications to the IComponentData Object

The console calls the [**Notify**](/windows/win32/Mmc/nf-mmc-icomponentdata-notify?branch=master) method to notify the snap-in of an event that occurs, for example, when the user clicks the mouse.

## Querying the IComponentData Object for a Data Object

MMC calls the snap-in's implementation of the [**QueryDataObject**](/windows/win32/Mmc/nf-mmc-icomponentdata-querydataobject?branch=master) method to request a data object for a specific [cookie](cookies.md), including the static folder (NULL cookie). The data object type is taken from the [**DATA\_OBJECT\_TYPES**](/windows/win32/Mmc/ne-mmc-_data_object_types?branch=master) enumeration and determines the context in which MMC requests the data object. A CCT\_SCOPE flag is set to indicate that the data object is for the scope pane. CCT\_RESULT is set to indicate that it is for the result pane, and CCT\_SNAPIN\_MANAGER indicates that the [Add/Remove Snap-in dialog box](add-remove-snap-in-dialog-box.md) is being used. CCT\_UNINITIALIZED indicates that the data object has an invalid type. Given context information, the snap-in can determine the context in which a data object is requested.

As noted earlier, [**IConsole2**](/windows/win32/Mmc/nn-mmc-iconsole2?branch=master) is the snap-in's interface to the console, and objects that expose the [**IDataObject**](_ole_idataobject) interface are used to pass context information from the snap-in to the console or between snap-ins.

## Getting Display Information

The [**GetDisplayInfo**](/windows/win32/Mmc/nf-mmc-icomponentdata-getdisplayinfo?branch=master) method retrieves display information for a namespace item in the scope pane.

## Destroying the Object

The [**Destroy**](/windows/win32/Mmc/nf-mmc-icomponentdata-destroy?branch=master) method releases all interfaces to the console, such as [**IConsole**](/windows/win32/Mmc/nn-mmc-iconsole2?branch=master) and [**IConsoleNamespace2**](/windows/win32/Mmc/nn-mmc-iconsolenamespace2?branch=master). You should be aware that MMC remains in a state in which everything can be queried during the call to **Destroy** so the snap-in can get information from the console. On return from **Destroy**, however, data integrity cannot be guaranteed.

## Comparing Data Objects

The [**CompareObjects**](/windows/win32/Mmc/nf-mmc-icomponentdata-compareobjects?branch=master) method provides a way for a snap-in component to compare two data objects and determine whether they refer to the same physical object. This method is used, for example, to detect duplicate property sheets.

## Related topics

<dl> <dt>

[Working with IComponent](working-with-icomponent.md)
</dt> <dt>

[Working with IDataObject](working-with-idataobject.md)
</dt> <dt>

[Working with IConsole](working-with-iconsole.md)
</dt> <dt>

[Registering and Unregistering a Snap-in](registering-and-unregistering-a-snap-in.md)
</dt> </dl>

 

 



