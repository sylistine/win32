---
title: IAgentCommand SetEnabled
description: IAgentCommand SetEnabled
ms.assetid: e0a724b4-3613-400f-a801-efc8bf66e355
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IAgentCommand::SetEnabled

\[Microsoft Agent is deprecated as of Windows 7, and may be unavailable in subsequent versions of Windows.\]

``` syntax
HRESULT SetEnabled(
   long bEnabled  // Enabled setting for Command
);
```

Sets the [**Enabled**](enabled-property.md) property for a [**Command**](https://msdn.microsoft.com/library/windows/desktop/ms696441).

-   Returns S\_OK to indicate the operation was successful.

<dl> <dt>

<span id="bEnabled"></span><span id="benabled"></span><span id="BENABLED"></span>*bEnabled*
</dt> <dd>

A Boolean value that sets the value of the [**Enabled**](enabled-property.md) setting of a [**Command**](https://msdn.microsoft.com/library/windows/desktop/ms696441). **True** enables the **Command**; **False** disables it. A disabled **Command** cannot be selected.

</dd> </dl>

A [**Command**](https://msdn.microsoft.com/library/windows/desktop/ms696441) must have its [**Enabled**](enabled-property.md) property set to **True** to be selectable. It also must have its [**Caption**](caption-property.md) property set and its [**Visible**](visible-property.md) property set to **True** to appear in the character's pop-up menu. To make the **Command** appear in the **Voice Commands Window**, you must set its [**Voice**](voice-property.md)property.

## See Also

[**IAgentCommand::GetCaption**](iagentcommand--getcaption.md), [**IAgentCommand::SetVoice**](iagentcommand--setvoice.md), [**IAgentCommands::Add**](iagentcommands--add.md), [**IAgentCommands::Insert**](iagentcommands--insert.md)


 

 



