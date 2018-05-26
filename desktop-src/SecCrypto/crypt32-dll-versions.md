---
Description: Crypt32.dll is the module that implements many of the CryptoAPI functions.
ms.assetid: b6063c92-5831-4b78-b2cd-812e55194bc9
title: Crypt32.dll Versions
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Crypt32.dll Versions

Crypt32.dll is the module that implements many of the Certificate and Cryptographic Messaging functions in the CryptoAPI, such as [**CryptSignMessage**](/windows/win32/Wincrypt/nf-wincrypt-cryptsignmessage?branch=master). Crypt32.dll is a module that comes with the Windows and Windows Server operating systems, but different versions of this DLL provide different capabilities. There is no API to determine the version of CryptoAPI that is in use, but you can determine the version of Crypt32.dll that is currently in use by using the [**GetFileVersionInfo**](_win32_getfileversioninfo_cpp) and [**VerQueryValue**](_win32_verqueryvalue_cpp) functions.

In general, the version ranges of Crypt32.dll map to the operating system versions as shown in the following table. However, this table should be used as a guideline only because it is possible, through other update avenues, that the Crypt32.dll version will differ from the one indicated in the table.

| Crypt32.dll version                               | Operating system                                                                                                                                                                |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *version* &gt;= 5.131.3790.0                      | Windows Server 2003                                                                                                                                                             |
| *version* &gt;= 5.131.2600.1243                   | Windows XP with Service Pack 2 (SP2)Windows XP with Service Pack 1 (SP1) with hotfix [Q329433](http://go.microsoft.com/fwlink/p/?linkid=84539)<br/> Windows XP<br/> |
| 5.131.2600.0 &lt;= *version* &lt; 5.131.2600.1243 | Windows XP with SP1Windows XP<br/>                                                                                                                                        |



 

 

 



