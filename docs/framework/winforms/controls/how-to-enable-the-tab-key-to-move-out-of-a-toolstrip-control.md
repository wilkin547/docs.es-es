---
title: "C&#243;mo: Habilitar la tecla TAB para salir de un control ToolStrip | Microsoft Docs"
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
  - "controles [Windows Forms], mover entre"
  - "tecla TAB, habilitar"
  - "ToolStrip (control) [Windows Forms], mover desde"
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Habilitar la tecla TAB para salir de un control ToolStrip
Utilice el siguiente procedimiento para permitir al usuario presionar la tecla TAB para desplazarse de <xref:System.Windows.Forms.ToolStrip> al control siguiente en el orden de tabulación.  
  
 <xref:System.Windows.Forms.ToolStrip> acepta la primera vez que se presiona la tecla TAB y las teclas de dirección seleccionan los elementos dentro de <xref:System.Windows.Forms.ToolStrip>.  Cuando el usuario presiona la tecla TAB una segunda vez, lleva al usuario al control siguiente en el orden de tabulación.  
  
### Para permitir al usuario presionar la tecla TAB para desplazarse de un control ToolStrip al control siguiente  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.TabStop%2A> del <xref:System.Windows.Forms.ToolStrip> en `true`.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)