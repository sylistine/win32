---
Description: Retrieves the capabilities of the recognizer.
ms.assetid: 9014bd9b-54fb-4735-9eb8-56a6188a5fc0
title: IInkAnalysisRecognizerGetCapabilities method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IInkAnalysisRecognizer::GetCapabilities method

Retrieves the capabilities of the recognizer.

## Syntax


```C++
HRESULT GetCapabilities(
  [out] InkAnalysisRecognizerCapabilities *pCapabilities
);
```



## Parameters

<dl> <dt>

*pCapabilities* \[out\]
</dt> <dd>

A bitwise combination of [**RecognizerCapabilities**](recognizercapabilities.md) values.

</dd> </dl>

## Return value

For a description of the return values, see [Classes and Interfaces - Ink Analysis](classes-and-interfaces---ink-analysis.md).

## Remarks

This value is constant for each [**IInkAnalysisRecognizer**](iinkanalysisrecognizer.md)

## Requirements



|                                     |                                                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP Tablet PC Edition \[desktop apps only\]<br/>                                                 |
| Minimum supported server<br/> | None supported<br/>                                                                                     |
| Header<br/>                   | <dl> <dt>IACom.h (also requires IACom\_i.c)</dt> </dl> |
| DLL<br/>                      | <dl> <dt>IACom.dll</dt> </dl>                          |



## See also

<dl> <dt>

[**IInkAnalysisRecognizer**](iinkanalysisrecognizer.md)
</dt> <dt>

[**RecognizerCapabilities**](recognizercapabilities.md)
</dt> <dt>

[Ink Analysis Reference](ink-analysis-reference.md)
</dt> </dl>

 

 



