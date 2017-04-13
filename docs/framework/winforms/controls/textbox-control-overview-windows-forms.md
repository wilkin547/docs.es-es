---
title: "Informaci&#243;n general sobre el control TextBox (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadros de texto, agregar"
  - "TextBox (control) [Windows Forms], acerca de los controles TextBox"
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre el control TextBox (formularios Windows Forms)
Los cuadros de texto de formularios Windows Forms se utilizan para obtener entradas del usuario o para mostrar texto.  El control <xref:System.Windows.Forms.TextBox> se utiliza generalmente para el texto que se puede editar, aunque también puede configurarse como control de sólo lectura.  Los cuadros de texto pueden mostrar varias líneas, ajustar el texto al tamaño del control y agregar formato básico.  El control <xref:System.Windows.Forms.TextBox> proporciona un único estilo de formato para el texto mostrado o escrito en el control.  Para mostrar varios tipos de texto con formato, se debe usar el control <xref:System.Windows.Forms.RichTextBox>.  Para obtener más información, vea [Información general sobre el control RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## Trabajar con el control TextBox  
 El texto que se muestra en el control se encuentra almacenado en la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  De forma predeterminada, en un cuadro de texto se puede escribir 2048 caracteres como máximo.  Si establece la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`, podrá escribir un máximo de 32 KB de texto.  La propiedad <xref:System.Windows.Forms.TextBox.Text%2A> puede establecerse en tiempo de diseño con la ventana Propiedades, en tiempo de ejecución mediante código o por medio de la introducción de datos por el usuario en tiempo de ejecución.  El contenido actual de un cuadro de texto puede recuperarse en tiempo de ejecución mediante la lectura de la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
 En el ejemplo de código siguiente se establece texto en el control en tiempo de ejecución.  El procedimiento `InitializeMyControl`  no se ejecutará automáticamente; es necesario llamarlo.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)