---
Description: Notfies an application when a selected IME needs information about the candidate window. The application receives this command through the WM\_IME\_REQUEST message with parameter settings as shown below.
ms.assetid: 35849290-a5be-406f-82f5-4a7e2af48586
title: IMR\_CANDIDATEWINDOW notification code
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IMR\_CANDIDATEWINDOW notification code

Notfies an application when a selected IME needs information about the candidate window. The application receives this command through the [**WM\_IME\_REQUEST**](wm-ime-request.md) message with parameter settings as shown below.


```C++
LRESULT IMR_CANDIDATEWINDOW
```



## Parameters

<dl> <dt>

<span id="wParam"></span><span id="wparam"></span><span id="WPARAM"></span>*wParam*
</dt> <dd>

Set to IMR\_CANDIDATEWINDOW.

</dd> <dt>

<span id="lParam"></span><span id="lparam"></span><span id="LPARAM"></span>*lParam*
</dt> <dd>

Pointer to a buffer containing a [**CANDIDATEFORM**](/windows/win32/Imm/ns-imm-tagcandidateform?branch=master) structure. Its **dwIndex** member contains the index to the candidate window referenced.

</dd> </dl>

## Return Value

Returns a nonzero value if the application fills in the [**CANDIDATEFORM**](/windows/win32/Imm/ns-imm-tagcandidateform?branch=master) structure. Otherwise, the command returns 0.

## Remarks

This command can be sent by the IME to a window that has cleared the ISC\_SHOWUICANDIDATEWINDOW flag in the [**WM\_IME\_SETCONTEXT**](wm-ime-setcontext.md) message handler.

## Requirements



|                                     |                                                                                                      |
|-------------------------------------|------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                 |
| Header<br/>                   | <dl> <dt>Imm.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

[Input Method Manager](input-method-manager.md)
</dt> <dt>

[Input Method Manager Commands](input-method-manager-commands.md)
</dt> <dt>

[**CANDIDATEFORM**](/windows/win32/Imm/ns-imm-tagcandidateform?branch=master)
</dt> <dt>

[**WM\_IME\_REQUEST**](wm-ime-request.md)
</dt> <dt>

[**WM\_IME\_SETCONTEXT**](wm-ime-setcontext.md)
</dt> </dl>

 

 



