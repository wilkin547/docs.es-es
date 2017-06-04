---
title: "C&#243;mo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms | Microsoft Docs"
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
  - ".rtf (archivos), aplicar formato en el control RichTextBox"
  - "fuentes, cambiar atributos en el control RichTextBox"
  - "dar formato [Windows Forms]"
  - "RichTextBox (control) [Windows Forms], establecer atributos de fuente"
  - "RTF (archivos), aplicar formato en el control RichTextBox"
  - "texto [Windows Forms]"
  - "cuadros de texto, aplicar formato a texto"
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms tiene numerosas opciones para dar formato al texto que muestra.  Puede mostrar los caracteres seleccionados en negrita, subrayados o en cursiva mediante la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.  También puede utilizar esta propiedad para cambiar el tamaño y el tipo de letra de los caracteres seleccionados.  La propiedad <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> permite cambiar el color de los caracteres seleccionados.  
  
### Para cambiar la apariencia de los caracteres  
  
1.  Establezca una fuente adecuada en la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.  
  
     Para permitir que los usuarios establezcan la familia de fuente, el tamaño y el tipo de letra en una aplicación, utilice el componente <xref:System.Windows.Forms.FontDialog>.  Para obtener información general, vea [Información general sobre el componente FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Establezca un color adecuado en la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>.  
  
     Para permitir que los usuarios establezcan el color en una aplicación, lo más habitual es utilizar el componente <xref:System.Windows.Forms.ColorDialog>.  Para obtener información general, vea [Información general sobre el componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Estas propiedades sólo afectan al texto seleccionado o, si no hay ningún texto seleccionado, al texto que se escribe en la posición actual del punto de inserción.  Para obtener información sobre cómo seleccionar texto mediante programación, vea [TextBoxBase.Select \(Método\)](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)