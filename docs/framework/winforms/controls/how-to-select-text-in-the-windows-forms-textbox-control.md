---
title: Seleccionar texto en el control TextBox
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
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745312"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a>Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms
Puede seleccionar texto mediante programación en el control Windows Forms <xref:System.Windows.Forms.TextBox>. Por ejemplo, si crea una función que busca en el texto una cadena determinada, puede seleccionar el texto para alertar visualmente al lector de la posición de la cadena encontrada.  
  
### <a name="to-select-text-programmatically"></a>Para seleccionar texto mediante programación  
  
1. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> en el principio del texto que desea seleccionar.  
  
     La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> es un número que indica el punto de inserción dentro de la cadena de texto, donde 0 es la posición más a la izquierda. Si la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> está establecida en un valor igual o mayor que el número de caracteres del cuadro de texto, el punto de inserción se coloca después del último carácter.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en la longitud del texto que desea seleccionar.  
  
     La propiedad <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> es un valor numérico que establece el ancho del punto de inserción. Al establecer el <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> en un número mayor que 0, se selecciona ese número de caracteres, empezando por el punto de inserción actual.  
  
3. Opta Acceder al texto seleccionado a través de la propiedad <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A>.  
  
     El código siguiente selecciona el contenido de un cuadro de texto cuando se produce el evento <xref:System.Windows.Forms.Control.Enter> del control. En este ejemplo se comprueba si el cuadro de texto tiene un valor para la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> que no es `null` o una cadena vacía. Cuando el cuadro de texto recibe el foco, se selecciona el texto actual en el cuadro de texto. El controlador de eventos `TextBox1_Enter` debe estar enlazado al control; para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
- [Controlar el punto de inserción en un control TextBox de Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de contraseña con el control TextBox de Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Crear un cuadro de texto de sólo lectura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Insertar comillas en una cadena](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Ver múltiples líneas en el control TextBox de Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Control TextBox](textbox-control-windows-forms.md)
