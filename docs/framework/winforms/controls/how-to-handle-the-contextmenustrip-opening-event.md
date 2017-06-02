---
title: "C&#243;mo: Controlar el evento Opening de ContextMenuStrip | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "menús contextuales, control de eventos"
  - "ContextMenuStrip (control) [Windows Forms]"
  - "control de eventos, menús contextuales"
  - "menús contextuales, control de eventos"
  - "ToolStrip (control) [Windows Forms]"
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Controlar el evento Opening de ContextMenuStrip
Puede personalizar el comportamiento del control <xref:System.Windows.Forms.ContextMenuStrip> controlando el evento <xref:System.Windows.Forms.ToolStripDropDown.Opening>.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo se controla el evento <xref:System.Windows.Forms.ToolStripDropDown.Opening>.  El controlador de eventos agrega dinámicamente elementos a un control <xref:System.Windows.Forms.ContextMenuStrip>.  Para obtener el ejemplo de código completo, vea [Cómo: Agregar dinámicamente elementos de ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Establezca la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=fullName> en `true` para impedir que el menú se abra.  
  
## Vea también  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>   
 <xref:System.Windows.Forms.ToolStripDropDown>   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)