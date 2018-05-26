---
Description: A trustee is the user account, group account, or logon session to which an access control entry (ACE) applies. Each ACE in an access control list (ACL) has one security identifier (SID) that identifies a trustee.
ms.assetid: 1c34faa0-936a-433a-9280-a94033f3f815
title: Trustees
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Trustees

A trustee is the user account, group account, or [*logon session*](https://msdn.microsoft.com/library/windows/desktop/ms721592#-security-logon-session-gly) to which an [*access control entry*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-control-entry-gly) (ACE) applies. Each ACE in an [*access control list*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-control-list-gly) (ACL) has one [*security identifier*](https://msdn.microsoft.com/library/windows/desktop/ms721625#-security-security-identifier-gly) (SID) that identifies a trustee.

User accounts include accounts that human users or programs such as Windows Services use to log on to the local computer.

Group accounts cannot be used to log on to a computer, but they are useful in ACEs to allow or deny a set of access rights to one or more user accounts.

A [*logon SID*](https://msdn.microsoft.com/library/windows/desktop/ms721592#-security-logon-sid-gly) that identifies the current logon session is useful to allow or deny access rights only until the user logs off.

The access control functions use the [**TRUSTEE**](/windows/win32/AccCtrl/ns-accctrl-_trustee_a?branch=master) structure to identify a trustee. The **TRUSTEE** structure enables you to use a name string or a SID to identify a trustee. If you use a name, the functions that create an ACE from the **TRUSTEE** structure perform the task of allocating the SID buffers and looking up the SID that corresponds to the account name. There are two helper functions, [**BuildTrusteeWithSid**](/windows/win32/Aclapi/nf-aclapi-buildtrusteewithsida?branch=master) and [**BuildTrusteeWithName**](/windows/win32/Aclapi/nf-aclapi-buildtrusteewithnamea?branch=master), that initialize a **TRUSTEE** structure with a specified SID or name. [**BuildTrusteeWithObjectsAndSid**](/windows/win32/Aclapi/nf-aclapi-buildtrusteewithobjectsandsida?branch=master) and [**BuildTrusteeWithObjectsAndName**](/windows/win32/Aclapi/nf-aclapi-buildtrusteewithobjectsandnamea?branch=master) allow you to initialize a **TRUSTEE** structure with object-specific ACE information. Three other helper functions, [**GetTrusteeForm**](/windows/win32/Aclapi/nf-aclapi-gettrusteeforma?branch=master), [**GetTrusteeName**](/windows/win32/Aclapi/nf-aclapi-gettrusteenamea?branch=master), and [**GetTrusteeType**](/windows/win32/Aclapi/nf-aclapi-gettrusteetypea?branch=master), retrieve the values of the various members of a **TRUSTEE** structure.

The **ptstrName** member of the [**TRUSTEE**](/windows/win32/AccCtrl/ns-accctrl-_trustee_a?branch=master) structure can be a pointer to an [**OBJECTS\_AND\_NAME**](/windows/win32/AccCtrl/ns-accctrl-_objects_and_name_a?branch=master) or [**OBJECTS\_AND\_SID**](/windows/win32/AccCtrl/ns-accctrl-_objects_and_sid?branch=master) structure. These structures specify information about an [object-specific ACE](object-specific-aces.md) in addition to a trustee name or SID. This enables functions such as [**SetEntriesInAcl**](/windows/win32/Aclapi/nf-aclapi-setentriesinacla?branch=master) and [**GetExplicitEntriesFromAcl**](/windows/win32/Aclapi/nf-aclapi-getexplicitentriesfromacla?branch=master) to store object-specific ACE information in the **Trustee** member of the [**EXPLICIT\_ACCESS**](/windows/win32/AccCtrl/ns-accctrl-_explicit_access_a?branch=master) structure.

 

 


