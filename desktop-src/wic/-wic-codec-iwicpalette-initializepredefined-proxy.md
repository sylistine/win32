---
Description: Proxy function for the InitializePredefined method.
ms.assetid: 78137d43-c32f-4d60-b289-2e2154cf4d1e
title: IWICPalette\_InitializePredefined\_Proxy function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWICPalette\_InitializePredefined\_Proxy function

Proxy function for the [**InitializePredefined**](/windows/win32/Wincodec/nf-wincodec-iwicpalette-initializepredefined?branch=master) method.

## Syntax


```C++
HRESULT IWICPalette_InitializePredefined_Proxy(
  _In_ IWICPalette          *THIS_PTR,
  _In_ WICBitmapPaletteType ePaletteType,
  _In_ BOOL                 fAddTransparentColor
);
```



## Parameters

<dl> <dt>

*THIS\_PTR* \[in\]
</dt> <dd>

Type: **[**IWICPalette**](/windows/win32/Wincodec/nn-wincodec-iwicpalette?branch=master)\***

Pointer to this [**IWICPalette**](/windows/win32/Wincodec/nn-wincodec-iwicpalette?branch=master) object.

</dd> <dt>

*ePaletteType* \[in\]
</dt> <dd>

Type: **[**WICBitmapPaletteType**](/windows/win32/Wincodec/ne-wincodec-wicbitmappalettetype?branch=master)**

The desired pre-defined palette type.

</dd> <dt>

*fAddTransparentColor* \[in\]
</dt> <dd>

Type: **BOOL**

The optional tranparent color to add to the palette. If no transparent color is needed, use 0.

</dd> </dl>

## Return value

Type: **HRESULT**

If this function succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

## Requirements



|                                     |                                                                                                                                                                  |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP with SP2, Windows Vista \[desktop apps only\]<br/>                                                                                              |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                                                                             |
| DLL<br/>                      | <dl> <dt>Windowscodecs.dll; </dt> <dt>Wincodec.lib</dt> </dl> |



 

 



