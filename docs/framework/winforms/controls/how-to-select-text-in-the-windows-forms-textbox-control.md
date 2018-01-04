---
title: "Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 535ee9e7359782f24d48d895f094afbe47e1023b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms
Puede seleccionar texto mediante programación en Windows Forms <xref:System.Windows.Forms.TextBox> control. Por ejemplo, si crea una función que se busca en el texto de una cadena concreta, puede seleccionar el texto para alertar visualmente al usuario de la posición de la cadena se encuentra.  
  
### <a name="to-select-text-programmatically"></a>Para seleccionar texto mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad al principio del texto que desea seleccionar.  
  
     El <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad es un número que indica el punto de inserción dentro de la cadena de texto, siendo 0 la posición más a la izquierda. Si el <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad se establece en un valor igual o mayor que el número de caracteres en el cuadro de texto, el punto de inserción se coloca después del último carácter.  
  
2.  Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad a la longitud del texto que desea seleccionar.  
  
     El <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad es un valor numérico que establece el ancho del punto de inserción. Establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en un número mayor que 0, ese número de caracteres que se seleccione, desde el punto de inserción actual.  
  
3.  (Opcional) Tener acceso al texto seleccionado a través de la <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> propiedad.  
  
     El código siguiente selecciona el contenido de un texto de cuadro cuando el control <xref:System.Windows.Forms.Control.Enter> se produce el evento. Este ejemplo se comprueba si el cuadro de texto tiene un valor para el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad que no es `null` o una cadena vacía. Cuando el cuadro de texto recibe el foco, se selecciona el texto actual en el cuadro de texto. El `TextBox1_Enter` controlador de eventos debe estar enlazado al control; para obtener más información, consulte [Cómo: crear controladores de eventos en tiempo de ejecución para formularios Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Para probar este ejemplo, presione la tecla Tab hasta que el cuadro de texto tiene el foco. Si hace clic en el cuadro de texto, el texto se anula la selección.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TextBox>  
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Controlar el punto de inserción en un control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Ver múltiples líneas en el control TextBox de Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Control TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
