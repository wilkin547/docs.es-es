---
title: Seleccionar texto en el control TextBox
description: Obtenga información sobre cómo seleccionar texto mediante programación en el control TextBox Windows Forms. Obtenga también información sobre cómo alertar visualmente al lector de la posición de la cadena encontrada.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621566"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms
Puede seleccionar texto mediante programación en el control Windows Forms <xref:System.Windows.Forms.TextBox> . Por ejemplo, si crea una función que busca en el texto una cadena determinada, puede seleccionar el texto para alertar visualmente al lector de la posición de la cadena encontrada.  
  
### <a name="to-select-text-programmatically"></a>Para seleccionar texto mediante programación  
  
1. Establezca la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad en el principio del texto que desea seleccionar.  
  
     La <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad es un número que indica el punto de inserción dentro de la cadena de texto, donde 0 es la posición más a la izquierda. Si la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> propiedad se establece en un valor igual o mayor que el número de caracteres del cuadro de texto, el punto de inserción se coloca después del último carácter.  
  
2. Establezca la <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad en la longitud del texto que desea seleccionar.  
  
     La <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> propiedad es un valor numérico que establece el ancho del punto de inserción. Si <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> se establece en un número mayor que 0, se seleccionará ese número de caracteres, empezando por el punto de inserción actual.  
  
3. Opta Acceder al texto seleccionado a través de la <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> propiedad.  
  
     El código siguiente selecciona el contenido de un cuadro de texto cuando <xref:System.Windows.Forms.Control.Enter> se produce el evento del control. En este ejemplo se comprueba si el cuadro de texto tiene un valor para la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad que no es `null` o una cadena vacía. Cuando el cuadro de texto recibe el foco, se selecciona el texto actual en el cuadro de texto. El `TextBox1_Enter` controlador de eventos debe estar enlazado al control. para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Para probar este ejemplo, presione la tecla TAB hasta que el cuadro de texto tenga el foco. Si hace clic en el cuadro de texto, se anula la selección del texto.  
  
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

- <xref:System.Windows.Forms.TextBox>
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
- [Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedimiento para crear un cuadro de texto de solo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedimiento para insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
