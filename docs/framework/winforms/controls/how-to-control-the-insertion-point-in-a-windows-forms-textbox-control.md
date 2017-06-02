---
title: "C&#243;mo: Controlar el punto de inserci&#243;n en un control TextBox de formularios Windows Forms | Microsoft Docs"
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
  - "puntos de inserción, TextBox (controles)"
  - "cuadros de texto, controlar punto de inserción"
  - "TextBox (control) [Windows Forms], punto de inserción"
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Controlar el punto de inserci&#243;n en un control TextBox de formularios Windows Forms
Cuando un control <xref:System.Windows.Forms.TextBox> de formularios Windows Forms recibe el foco por primera vez, el punto de inserción predeterminado dentro del cuadro de texto se encuentra a la izquierda de cualquier texto existente.  El usuario puede mover el punto de inserción con el teclado o el mouse.  Si el cuadro de texto pierde el foco y luego lo vuelve a obtener, el punto de inserción se encontrará donde lo dejó el usuario.  
  
 En algunos casos, este comportamiento puede resultar desconcertante para el usuario.  En una aplicación de procesamiento de textos, es posible que el usuario espere que los caracteres nuevos aparezcan después del texto existente.  En una aplicación de entrada de datos, el usuario podría esperar que los caracteres reemplazaran la entrada existente.  Las propiedades <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> y <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> permiten modificar el comportamiento de modo que se ajuste a las necesidades.  
  
### Para controlar el punto de inserción en un control TextBox  
  
1.  Establezca un valor adecuado en la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>.  El cero sitúa el punto de inserción inmediatamente a la izquierda del primer carácter.  
  
2.  \(Opcional\) Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.  
  
     El código siguiente siempre devuelve el punto de inserción a 0.  El controlador de eventos `TextBox1_Enter` se debe enlazar al control. Para obtener más información, vea [Creating Event Handlers in Windows Forms](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## Hacer que el punto de inserción esté visible de manera predeterminada  
 El punto de inserción de <xref:System.Windows.Forms.TextBox> sólo está visible de manera predeterminada en un nuevo formulario si el control <xref:System.Windows.Forms.TextBox> es el primero en el orden de tabulación.  De lo contrario, el punto de inserción sólo aparece si asigna el foco a <xref:System.Windows.Forms.TextBox> con el teclado o el mouse.  
  
#### Para hacer que el punto de inserción del cuadro de texto sea visible en un nuevo formulario de manera predeterminada  
  
-   Establezca la propiedad <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.TabIndex%2A> en `0`.  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)