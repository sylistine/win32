---
Description: Given a list of media types, the TryMediaTypes method tries to complete a connection using one of those types.
ms.assetid: cc437e44-bc59-494e-8669-7f539353a794
title: CBasePin.TryMediaTypes method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBasePin.TryMediaTypes method

Given a list of media types, the `TryMediaTypes` method tries to complete a connection using one of those types.

## Syntax


```C++
virtual HRESULT TryMediaTypes(
         IPin            *pReceivePin,
   const CMediaType      *pmt,
         IEnumMediaTypes *pEnum
);
```



## Parameters

<dl> <dt>

*pReceivePin* 
</dt> <dd>

Pointer to the receiving pin's [**IPin**](/windows/win32/Strmif/nn-strmif-ipin?branch=master) interface.

</dd> <dt>

*pmt* 
</dt> <dd>

Pointer to a [**CMediaType**](cmediatype.md) object that limits the possible media types, or **NULL**.

</dd> <dt>

*pEnum* 
</dt> <dd>

Pointer to an [**IEnumMediaTypes**](/windows/win32/Strmif/nn-strmif-ienummediatypes?branch=master) interface, used to enumerate the list of media types.

</dd> </dl>

## Return value

Returns an **HRESULT** value. Possible values include those in the following table.



| Return code                                                                                                  | Description                                       |
|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>                         | Success.<br/>                               |
| <dl> <dt>**VFW\_E\_NO\_ACCEPTABLE\_TYPES**</dt> </dl> | Did not find an acceptable media type.<br/> |



 

## Remarks

For each media type returned by the **IEnumMediaTypes** interface, this method attempts a connection by calling the [**CBasePin::AttemptConnection**](cbasepin-attemptconnection.md) method.

If the *pmt* parameter is non-**NULL**, the pin skips media types that do not match this type. The *pmt* parameter can specify a partial media type. A partial media type has a value of GUID\_NULL for either the major type, the subtype, or the format. The GUID\_NULL value matches any type, similar to a "wildcard" value.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBasePin Class**](cbasepin.md)
</dt> </dl>

 

 



