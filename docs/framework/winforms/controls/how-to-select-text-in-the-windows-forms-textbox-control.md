---
title: "C&#243;mo: Seleccionar texto en el control TextBox de formularios Windows Forms | Microsoft Docs"
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
  - "cuadros de texto, seleccionar texto mediante programación"
  - "texto, seleccionar texto en cuadros de texto mediante programación"
  - "TextBox (control) [Windows Forms], seleccionar texto mediante programación"
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# C&#243;mo: Seleccionar texto en el control TextBox de formularios Windows Forms
Puede seleccionar texto en el control <xref:System.Windows.Forms.TextBox> de formularios Windows Forms mediante programación.  Por ejemplo, si crea una función que busque cadenas en el texto, podría seleccionar el texto para alertar visualmente al usuario de la posición de la cadena encontrada.  
  
### Para seleccionar texto mediante programación  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en el principio del texto que desea seleccionar.  
  
     La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> es un número que indica el punto de inserción dentro de la cadena de texto, siendo 0 la posición más a la izquierda.  Si se establece la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en un valor igual o mayor que el número de caracteres del cuadro de texto, el punto de inserción se situará después del último carácter.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.  
  
     La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> es un valor numérico que establece el ancho del punto de inserción.  Al establecer <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en un número mayor que 0, se selecciona este número de caracteres, empezando en el punto de inserción actual.  
  
3.  \(Opcional\) Utilice la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> para tener acceso al texto seleccionado.  
  
     El código que se muestra a continuación selecciona el contenido de un cuadro de texto cuando se produce el evento <xref:System.Windows.Forms.Control.Enter> del control.  En este ejemplo se comprueba si el cuadro de texto tiene un valor para la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> que no es `null` ni una cadena vacía.  Cuando el cuadro de texto recibe el foco, se selecciona el texto actual del cuadro de texto.  El controlador de eventos `TextBox1_Enter` se debe enlazar al control. Para obtener más información, vea [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Para probar este ejemplo, presione la tecla Tabulador hasta que el cuadro de texto tenga el foco.  Si hace clic en el cuadro de texto, se anula la selección del texto.  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)