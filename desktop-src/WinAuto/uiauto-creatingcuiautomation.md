---
title: Creating the CUIAutomation Object
description: This section describes how to get started writing a Microsoft UI Automation client application by instantiating an object that implements IUIAutomation.
ms.assetid: 9b90da60-0204-48c1-bb16-ff4a843bac67
keywords:
- clients,creating CUIAutomation object
- clients,CUIAutomation object
- UI Automation,CUIAutomation object
- UI Automation,creating CUIAutomation object
- creating CUIAutomation object
- CUIAutomation object
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Creating the CUIAutomation Object

This section describes how to get started writing a Microsoft UI Automation client application by instantiating an object that implements [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master).

This topic contains the following sections.

-   [The CUIAutomation Object](#the-cuiautomation-object)
-   [Creating the Object](#creating-the-object)
-   [Related topics](#related-topics)

## The CUIAutomation Object

The first step in using UI Automation is to create an object of the [**CUIAutomation**](/windows/win32/UIAutomationClient/?branch=master) class. This object exposes the [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master) interface, which is the gateway to all the other objects and interfaces that are used by client applications. Among other things, **IUIAutomation** is used for the following tasks:

-   Subscribing to events.
-   Creating conditions. Conditions are objects used to narrow the scope of searches for UI Automation elements.
-   Obtaining UI Automation elements directly from the desktop (the root element), or from screen coordinates or window handles.
-   Creating tree walker objects that can be used to navigate the hierarchy of UI Automation elements.
-   Converting data types.

## Creating the Object

To get started using UI Automation in your application, take the following steps:

-   Include UIAutomation.h in your project headers. UIAutomation.h brings in the other headers that define the API.
-   Declare a pointer to [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master).
-   Initialize the Component Object Model (COM).
-   Create an instance of [**CUIAutomation**](/windows/win32/UIAutomationClient/?branch=master) and retrieve the [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master) interface in your pointer.

The following example function initializes COM, and then creates the [**CUIAutomation**](/windows/win32/UIAutomationClient/?branch=master) object, retrieving the [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master) interface in the *ppAutomation* pointer.


```C++
#include <uiautomation.h>

// CoInitialize must be called before calling this function, and the  
// caller must release the returned pointer when finished with it.
// 
HRESULT InitializeUIAutomation(IUIAutomation **ppAutomation)
{
    return CoCreateInstance(CLSID_CUIAutomation, NULL,
        CLSCTX_INPROC_SERVER, IID_IUIAutomation, 
        reinterpret_cast<void**>(ppAutomation));
}
```



## Related topics

<dl> <dt>

**Conceptual**
</dt> <dt>

[UI Automation Events Overview](uiauto-eventsoverview.md)
</dt> <dt>

[Obtaining UI Automation Elements](uiauto-obtainingelements.md)
</dt> </dl>

 

 



