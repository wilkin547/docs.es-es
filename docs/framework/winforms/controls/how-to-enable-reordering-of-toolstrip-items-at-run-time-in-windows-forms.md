---
title: "C&#243;mo: Habilitar la reordenaci&#243;n de elementos ToolStrip en tiempo de ejecuci&#243;n en un formulario Windows Forms | Microsoft Docs"
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
  - "AllowItemReorder (propiedad)"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "barras de herramientas [Windows Forms], volver a organizar controles"
  - "ToolStrip (control) [Windows Forms], ejemplos"
  - "ToolStrip (control) [Windows Forms], volver a ordenar elementos"
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Habilitar la reordenaci&#243;n de elementos ToolStrip en tiempo de ejecuci&#243;n en un formulario Windows Forms
Se puede permitir al usuario reorganizar los controles <xref:System.Windows.Forms.ToolStripItem> en <xref:System.Windows.Forms.ToolStrip>.  
  
### Para habilitar la reorganización de ToolStripItem en tiempo de ejecución  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> en `true`.  De manera predeterminada, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> es `false`.  
  
     En tiempo de ejecución, el usuario mantiene presionada la tecla ALT y el botón primario del mouse para arrastrar <xref:System.Windows.Forms.ToolStripItem> hacia una ubicación diferente en <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)