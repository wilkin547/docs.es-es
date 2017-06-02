---
title: "C&#243;mo: Cambiar la apariencia del texto y las im&#225;genes de ToolStrip en formularios Windows Forms | Microsoft Docs"
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
  - "barras de herramientas [Windows Forms], apariencia"
  - "barras de herramientas [Windows Forms], imágenes"
  - "barras de herramientas [Windows Forms], texto"
  - "ToolStrip (control) [Windows Forms], apariencia"
  - "ToolStrip (control) [Windows Forms], imágenes"
  - "ToolStrip (control) [Windows Forms], texto"
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Cambiar la apariencia del texto y las im&#225;genes de ToolStrip en formularios Windows Forms
Se puede controlar si el texto y las imágenes se muestran en <xref:System.Windows.Forms.ToolStripItem> y cómo son alinean entre sí y con <xref:System.Windows.Forms.ToolStrip>.  
  
### Para definir lo que se muestra en un ToolStripItem  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> en el valor que desee.  Las posibilidades son `Image`, `ImageAndText`, `None` y `Text`.  El valor predeterminado es `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
  
    ```  
  
### Para alinear el texto de un ToolStripItem  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> en el valor que desee.  Las posibilidades son cualquier combinación de parte superior, media y parte inferior con izquierda, centro y derecha.  El valor predeterminado es `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### Para alinear una imagen en un ToolStripItem  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> en el valor que desee.  Las posibilidades son cualquier combinación de parte superior, media y parte inferior con izquierda, centro y derecha.  El valor predeterminado es `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
  
    ```  
  
### Para definir cómo se muestra el texto y las imágenes de ToolStripItem entre sí  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> en el valor que desee.  Las posibilidades son `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` y `TextBeforeImage`.  El valor predeterminado es `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)