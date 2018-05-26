---
Description: The ISearchManager interface provides methods that make changes across catalogs.
ms.assetid: e6f4432b-03bf-4711-a79e-1bf9242c5683
title: Using the Search Manager
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Using the Search Manager

The [**ISearchManager**](/windows/win32/Searchapi/nn-searchapi-isearchmanager?branch=master) interface provides methods that make changes across catalogs. Changes made at the **ISearchManager** level apply globally to all catalogs used by the indexer, while changes made at the [**ISearchCatalogManager**](/windows/win32/Searchapi/nn-searchapi-isearchcatalogmanager?branch=master) level apply to specific catalogs. However, currently, Windows Search uses only one catalog, SystemIndex. You can use the Search Manager to do the following:

-   Get an instance of the Catalog Manager for the search catalog.
-   Get version information about the Windows Search engine.

The following methods of the [**ISearchManager**](/windows/win32/Searchapi/nn-searchapi-isearchmanager?branch=master) interface can help you manage your search catalog(s):



| Method                                                                      | Description                                                                                                                                                                                                                          |
|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**GetCatalog**](/windows/win32/Searchapi/nf-searchapi-isearchmanager-getcatalog?branch=master)                     | Gets a catalog by name and returns an instance of [**ISearchCatalogManager**](/windows/win32/Searchapi/nn-searchapi-isearchcatalogmanager?branch=master) for that catalog. This enables you to manage an individual search catalog.                                          |
| [**GetIndexerVersion**](/windows/win32/Searchapi/nf-searchapi-isearchmanager-getindexerversion?branch=master)       | Returns the version of the indexer in two integers: major version and minor version. For example, the major version number for Windows Vista Search and Windows Search 3.0 on Windows XP is "3" and the minor version number is "0". |
| [**GetIndexerVersionStr**](/windows/win32/Searchapi/nf-searchapi-isearchmanager-getindexerversionstr?branch=master) | Returns the complete version number of the indexer as a string: for example, "03.00.5824.280".                                                                                                                                       |



 

For more information about these methods, see the [**ISearchManager**](/windows/win32/Searchapi/nn-searchapi-isearchmanager?branch=master) documentation.

The following [**ISearchManager**](/windows/win32/Searchapi/nn-searchapi-isearchmanager?branch=master) methods are reserved for future use. They are, however, implemented and do not affect the indexer or catalog, as there is only one catalog for Windows Search at this time.

-   **get\_BypassList**
-   **get\_LocalBypass**
-   **get\_PortNumber**
-   **get\_ProxyName**
-   **get\_UseProxy**
-   **get\_UserAgent**
-   **put\_UserAgent**
-   **SetProxy**

**GetParameter** and **SetParameter** are also reserved for future use but are not implemented.

## Related topics

<dl> <dt>

[Managing the Index](-search-3x-wds-mngidx-overview.md)
</dt> <dt>

[Interfaces for Managing the Index](interfaces-for-managing-the-index.md)
</dt> <dt>

[Using the Catalog Manager](-search-3x-wds-mngidx-catalog-manager.md)
</dt> <dt>

[Using the Crawl Scope Manager](-search-3x-wds-extidx-csm.md)
</dt> </dl>

 

 


