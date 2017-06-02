---
title: "C&#243;mo: Detectar cu&#225;ndo est&#225; el puntero del mouse (rat&#243;n) en un elemento ToolStripItem | Microsoft Docs"
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
  - "mouse, detectar movimiento en barras de herramientas"
  - "barras de herramientas [Windows Forms], detectar el movimiento del mouse"
  - "ToolStrip (control) [Windows Forms], detectar el movimiento del mouse"
  - "ToolStripItem (clase), detectar el movimiento del mouse"
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Detectar cu&#225;ndo est&#225; el puntero del mouse (rat&#243;n) en un elemento ToolStripItem
Utilice el siguiente procedimiento para detectar cuándo se encuentra el puntero del mouse encima de <xref:System.Windows.Forms.ToolStripItem>.  
  
### Para detectar cuándo se encuentra el puntero encima de ToolStripItem  
  
-   Utilice la propiedad <xref:System.Windows.Forms.ToolStripItem.Selected%2A> para elementos en los que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.  
  
     Esto evitará que tenga que sincronizar los eventos <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave>.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)