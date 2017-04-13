---
title: "C&#243;mo: Crear texto de tama&#241;o variable en un control ComboBox | Microsoft Docs"
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
  - "cuadros combinados, dibujar texto"
  - "ComboBox (control) [Windows Forms], dibujar texto personalizado"
  - "ComboBox (control) [Windows Forms], ejemplos [C#]"
  - "ejemplos [Windows Forms], ComboBox (control)"
  - "texto, dibujar en cuadros combinados"
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear texto de tama&#241;o variable en un control ComboBox
En este ejemplo se muestra el dibujo personalizado de texto en un control <xref:System.Windows.Forms.ComboBox>.  Cuando un elemento cumple un determinado criterio, se dibuja en una fuente mayor y se vuelve color rojo.  
  
## Ejemplo  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un formulario Windows Forms.  
  
-   Un control <xref:System.Windows.Forms.ComboBox> denominado  `ListBox1`  con tres elementos en la propiedad <xref:System.Windows.Forms.ComboBox.Items%2A>.  En este ejemplo, los tres elementos se denominan  `"One", Two", and Three"`.  La propiedad <xref:System.Windows.Forms.ComboBox.DrawMode%2A> de  `ComboBox1`  se debe establecer en <xref:System.Windows.Forms.DrawMode>.  
  
    > [!NOTE]
    >  Esta técnica también se aplica al control <xref:System.Windows.Forms.ListBox>: puede sustituir <xref:System.Windows.Forms.ListBox> para el <xref:System.Windows.Forms.ComboBox>.  
  
-   Referencias a los espacios de nombres <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Drawing?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox.DrawItem>   
 <xref:System.Windows.Forms.DrawItemEventArgs>   
 <xref:System.Windows.Forms.ComboBox.MeasureItem>   
 [Controles compatibles con dibujos propietarios integrados](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [ListBox \(Control\)](../../../../docs/framework/winforms/controls/listbox-control-windows-forms.md)   
 [ComboBox \(Control\)](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)