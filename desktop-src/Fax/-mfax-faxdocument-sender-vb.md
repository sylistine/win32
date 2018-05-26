---
Description: Retrieves an object containing information about the sender of the fax document.
ms.assetid: f5489323-3c91-4de9-963b-0a1d3ae5f01a
title: FaxDocument.Sender property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxDocument.Sender property

Retrieves an object containing information about the sender of the fax document.

This property is read-only.

## Syntax


```VB
Property Sender As IFaxSender
```



## Property value

A variable of type [**IFaxSender**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxsender?branch=master) that receives a [**FaxSender**](-mfax-faxsender.md) object.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-sending-a-fax.md)
</dt> <dt>

[**FaxDocument**](-mfax-faxdocument.md)
</dt> <dt>

[**IFaxDocument**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxdocument?branch=master)
</dt> </dl>

 

 



