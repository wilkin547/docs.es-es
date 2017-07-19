---
title: "C&#243;mo: Crear botones de alternancia en los controles ToolStrip | Microsoft Docs"
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
  - "ejemplos [Windows Forms], barras de herramientas"
  - "botones de alternancia, crear"
  - "ToolStrip (control) [Windows Forms], crear botones de alternancia"
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear botones de alternancia en los controles ToolStrip
Cuando un usuario hace clic en un botón de alternancia, se muestra en bajo relieve y retiene ese aspecto hasta que el usuario haga clic de nuevo en el botón.  
  
### Para crear un ToolStripButton con alternancia  
  
-   Utilice código como el siguiente código de ejemplo:  Este código da por supuesto que el formulario contiene un control <xref:System.Windows.Forms.ToolStrip> y que su colección <xref:System.Windows.Forms.ToolStrip.Items%2A> contiene un objeto <xref:System.Windows.Forms.ToolStripButton> denominado `toolStripButton1`.  También da por supuesto que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.  
  
     \[Visual Basic\]  
  
    ```  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripButton>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)