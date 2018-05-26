---
Description: The EndFlush method informs the owning filter to end a flush operation. The derived class must implement this method.
ms.assetid: 5b178b09-019c-4b5b-9794-5176b5402e1c
title: CPullPin.EndFlush method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CPullPin.EndFlush method

The `EndFlush` method informs the owning filter to end a flush operation. The derived class must implement this method.

## Syntax


```C++
virtual HRESULT EndFlush() = 0;
```



## Parameters

This method has no parameters.

## Return value

Returns an **HRESULT** value.

## Remarks

The [**CPullPin::Seek**](cpullpin-seek.md) method calls this method. Implement this method to call the [**IPin::EndFlush**](/windows/win32/Strmif/nf-strmif-ipin-endflush?branch=master) method on each downstream input pin that receives data from this object. If your filter's output pin(s) derive from **CBaseOutputPin**, call the **CBaseOutputPin::DeliverEndFlush** method.

This design enables the filter to seek the stream simply by calling **Seek** on the **CPullPin** object.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Pullpin.h</dt> </dl>                                                                                                       |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CPullPin Class**](cpullpin.md)
</dt> </dl>

 

 



