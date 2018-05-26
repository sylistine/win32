---
Description: Boolean value that indicates whether the filter is currently dropping frames. If this value is TRUE, the filter continues to drop frames until it reaches the next key frame, or until it receives 30 delta frames in a row without a key frame.
ms.assetid: 1af22879-bf9b-4835-b3b5-06fb52b3140f
title: CVideoTransformFilterm\_bSkipping member
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CVideoTransformFilter::m\_bSkipping member

Boolean value that indicates whether the filter is currently dropping frames. If this value is **TRUE**, the filter continues to drop frames until it reaches the next key frame, or until it receives 30 delta frames in a row without a key frame.

## Syntax


```C++
BOOL m_bSkipping;
```



## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Vtrans.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CVideoTransformFilter Class**](cvideotransformfilter.md)
</dt> </dl>

 

 



