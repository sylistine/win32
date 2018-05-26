---
Description: The PatchFiles property returns a StringList object that contains a list of files that can be updated by the provided list of patches.
ms.assetid: 14549847-8558-4a9a-9ad5-3575c3f4391e
title: Installer.PatchFiles property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Installer.PatchFiles property

The **PatchFiles** property returns a [**StringList**](stringlist-object.md) object that contains a list of files that can be updated by the provided list of patches. This property calls [**MsiGetPatchFileList**](/windows/win32/Msi/nf-msi-msigetpatchfilelista?branch=master). For more information about using the **PatchFiles** property see [Listing the Files that can be Updated](listing-the-files-that-can-be-updated.md).

This property is read-only.

## Syntax


```JScript
propVal = Installer.PatchFiles
```



## Property value

## Requirements



|                    |                                                                                                                                                                                                                                                              |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Version<br/> | Windows Installer 5.0 on Windows Server 2012, Windows 8, Windows Server 2008 R2 or Windows 7. Windows Installer 4.0 or Windows Installer 4.5 on Windows Server 2008 or Windows Vista. Windows Installer 4.5 on Windows Server 2003 and Windows XP<br/> |
| DLL<br/>     | <dl> <dt>Msi.dll</dt> </dl>                                                                                                                                                                           |
| IID<br/>     | IID\_IInstaller is defined as 000C1090-0000-0000-C000-000000000046<br/>                                                                                                                                                                                |



## See also

<dl> <dt>

[**Installer Object**](installer-object.md)
</dt> <dt>

[Not Supported in Windows Installer 3.1 and earlier versions](not-supported-in-windows-installer-version-3-1.md)
</dt> </dl>

 

 



