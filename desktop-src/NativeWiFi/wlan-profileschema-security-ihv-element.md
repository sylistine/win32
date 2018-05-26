---
Description: Contains various security settings used by independent hardware vendors.
ms.assetid: 237c5d98-3f3c-4279-b2ad-b0d05df041f9
title: security (IHV) Element
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# security (IHV) Element

The security (IHV) element contains various security settings used by independent hardware vendors.

Microsoft security settings and IHV security settings are mutually exclusive. If both sets of security settings are present in the same profile, the profile is invalid.

**Windows XP with SP3 and Wireless LAN API for Windows XP with SP2:** This element is not supported.

``` syntax
<xs:element name="security">
    <xs:complexType>
        <xs:sequence>
            <xs:any
                processContents="lax"
                namespace="##other"
             />
        </xs:sequence>
    </xs:complexType>
</xs:element>
```

The **security** element is defined by the [**IHV**](wlan-profileschema-ihv-wlanprofile-element.md) element.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

**Definition context of element in schema**
</dt> <dt>

[**IHV**](wlan-profileschema-ihv-wlanprofile-element.md)
</dt> <dt>

**Possible immediate parent element in schema instance**
</dt> <dt>

[**IHV (WLANProfile)**](wlan-profileschema-ihv-wlanprofile-element.md)
</dt> </dl>

 

 



