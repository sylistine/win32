---
Description: COM+ provides an administration object model that exposes all of the functionality of the Component Services administrative tool, itself a graphical front end written on top of the administrative objects.
ms.assetid: f302eb02-2ef5-42ee-a18f-59f7e60b38df
title: Automating COM+ Administration
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Automating COM+ Administration

COM+ provides an administration object model that exposes all of the functionality of the Component Services administrative tool, itself a graphical front end written on top of the administrative objects. You can use these objects, supplied by the Component Services Administration (COMAdmin) Library, to automate all tasks in the administration of COM+ applications and services.

The COMAdmin objects enable you to read and write information that is stored on the COM+ catalog, the underlying data store that holds all COM+ configuration data.

You can use these objects to do the following:

-   Create and configure COM+ applications.
-   Install and export existing COM+ applications.
-   Manage installed COM+ applications.
-   Manage and configure services.
-   Remotely administer Component Services on a different machine.

You can use the scriptable COMAdmin objects with any Automation-compatible language, such as Microsoft Visual Basic and Visual Basic Script. You can develop either lightweight scripts or general-purpose administration tools. For example, you can do the following:

-   Write scripts to perform routine administrative tasks.
-   Write scripts to automate processes in the development of COM+ applications.
-   Develop general-purpose tools for administering and monitoring Component Services.
-   Develop setup executables to install and deploy your COM+ application.

The COMAdmin Library provides backward compatibility with the MTS 2.0 Administration Library. Most existing MTS 2.0 administration code will still work, although with some exceptions. (See [MTS Administration Library](mts-administration-library.md).)

To automate administration effectively, you should be familiar with administration tasks as performed with the Component Services administrative tool.

For full descriptions of the COMAdmin objects and the corresponding interfaces, see the COM+ Reference documentation for the following classes and interfaces:

-   [**COMAdminCatalog**](/windows/win32/ComAdmin/?branch=master)
-   [**COMAdminCatalogCollection**](/windows/win32/ComAdmin/?branch=master)
-   [**COMAdminCatalogObject**](/windows/win32/ComAdmin/?branch=master)
-   [**ICOMAdminCatalog**](/windows/win32/ComAdmin/nn-comadmin-icomadmincatalog?branch=master)
-   [**ICOMAdminCatalog2**](/windows/win32/ComAdmin/nn-comadmin-icomadmincatalog2?branch=master)
-   [**ICatalogCollection**](/windows/win32/ComAdmin/nn-comadmin-icatalogcollection?branch=master)
-   [**ICatalogObject**](/windows/win32/ComAdmin/nn-comadmin-icatalogobject?branch=master)

The following topics in this section provide an overview for automating administration using the COMAdmin objects:

-   [Overview of the COMAdmin Objects](overview-of-the-comadmin-objects.md)
-   [Retrieving Collections on the COM+ Catalog](retrieving-collections-on-the-com--catalog.md)
-   [Setting Properties and Saving Changes to the COM+ Catalog](setting-properties-and-saving-changes-to-the-com--catalog.md)
-   [Handling COM+ Administration Errors](handling-com--administration-errors.md)
-   [COM+ Administration Operations Within Transactions](com--administration-operations-within-transactions.md)
-   [Introductory Example Using the COM+ Administration Catalog](introductory-example-using-the-com--administration-catalog.md)

 

 


