---
Description: The TrustedDomain object stores information about a trust relationship with a domain.
ms.assetid: fab69367-2143-49ef-a1b9-9c1d846fd4e1
title: TrustedDomain Object
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# TrustedDomain Object

The **TrustedDomain** object stores information about a trust relationship with a domain. A **TrustedDomain** object is created on the trusting system to identify an account within the trusted domain that can be used to submit authentication requests and to perform other operations, such as name and [*security identifier*](https://msdn.microsoft.com/library/windows/desktop/ms721625#-security-security-identifier-gly) (SID) translations.

The information stored in a **TrustedDomain** object includes:

-   The SID of the trusted domain. This information is not modifiable and must be unique among all **TrustedDomain** objects.
-   The name of the trusted domain. This information is not modifiable and must be unique among all **TrustedDomain** objects.
-   The name of the account in the trusted domain used to submit authentication requests and to perform name and SID translations. This name is not modifiable.
-   The password used to submit authentication requests and perform name and SID translations.

For more information, see [The TrustedDomain Object Type](the-trusteddomain-object-type.md).

 

 


