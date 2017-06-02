---
title: "C&#243;mo: Utilizar la informaci&#243;n sobre herramientas en los controles ToolStrip | Microsoft Docs"
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
  - "barras de herramientas [Windows Forms], agregar información sobre herramientas"
  - "ToolStrip (control) [Windows Forms], agregar información sobre herramientas"
  - "información sobre herramientas [Windows Forms], agregar"
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Utilizar la informaci&#243;n sobre herramientas en los controles ToolStrip
Se puede mostrar una <xref:System.Windows.Forms.ToolTip> para el control <xref:System.Windows.Forms.ToolStrip> que desee, estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> de control en `true`.  
  
### Para mostrar una ToolTip  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> del control en `true`:  
  
     El valor predeterminado de <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=fullName> es `true` y el valor predeterminado de <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=fullName> y <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=fullName> es `false`.  
  
### Para utilizar la propiedad ToolTipText para el texto de información sobre herramientas de ToolStripButton  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> del botón en `true`.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=fullName> del botón en `false`.  
  
     De forma predeterminada, la propiedad `AutoToolTip` es `true` para <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> y <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     De forma predeterminada, <xref:System.Windows.Forms.ToolStripButton> utiliza su propiedad `Text` para el texto <xref:System.Windows.Forms.ToolTip>.  Utilice este procedimiento para mostrar el texto personalizado de una <xref:System.Windows.Forms.ToolTip> del <xref:System.Windows.Forms.ToolStripButton>.  
  
> [!NOTE]
>  Si establece <xref:System.Windows.Forms.ToolStripItemDisplayStyle> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, no se mostrará ningún texto en el botón, pero la información sobre herramientas sí aparece.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>   
 <xref:System.Windows.Forms.ToolStripButton>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 <xref:System.Windows.Forms.ToolStripSplitButton>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)