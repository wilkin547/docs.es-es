---
title: "C&#243;mo: Habilitar AutoComplete en los controles ToolStrip de formularios Windows Forms | Microsoft Docs"
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
  - "AutoComplete, habilitar en barras de herramientas"
  - "AutoComplete, ejemplos"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "barras de herramientas [Windows Forms], AutoComplete"
  - "ToolStrip (control) [Windows Forms], AutoComplete"
  - "ToolStripComboBox (clase), ejemplos"
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Habilitar AutoComplete en los controles ToolStrip de formularios Windows Forms
El procedimiento siguiente combina un <xref:System.Windows.Forms.ToolStripLabel> con un <xref:System.Windows.Forms.ToolStripComboBox> que puede desplegar para mostrar una lista de elementos, como los sitios Web recientemente visitados.  Si el usuario escribe un carácter que coincide con el primer carácter de uno de los elementos en la lista, inmediatamente se muestra el elemento.  
  
> [!NOTE]
>  La realización automática funciona con controles `ToolStrip` del mismo modo que funciona con controles tradicionales como <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.TextBox>.  
  
### Para habilitar AutoComplete en un control ToolStrip  
  
1.  Cree un control <xref:System.Windows.Forms.ToolStrip> y agréguele los elementos.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
  
    ```  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> de la etiqueta y del cuadro combinado en <xref:System.Windows.Forms.ToolStripItemOverflow>, de modo que la lista esté siempre disponible independientemente del tamaño del formulario.  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
  
    ```  
  
3.  Agregue las palabras a la colección Elementos del control <xref:System.Windows.Forms.ToolStripComboBox>.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
  
    ```  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> del cuadro combinado en <xref:System.Windows.Forms.AutoCompleteMode>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
  
    ```  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> del cuadro combinado en <xref:System.Windows.Forms.AutoCompleteSource>.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripLabel>   
 <xref:System.Windows.Forms.ToolStripComboBox>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>   
 <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)