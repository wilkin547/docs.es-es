---
title: Habilitar operaciones de arrastrar y soltar con RichTextBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 27e5c18598552c465ef17f5e58069bc10e401c09
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182350"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a>Cómo: Habilitar operaciones de arrastrar y colocar con el control RichTextBox de formularios Windows Forms
Las operaciones de arrastrar y colocar con el control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms se realizan mediante el control de los eventos <xref:System.Windows.Forms.RichTextBox.DragEnter> y <xref:System.Windows.Forms.RichTextBox.DragDrop> . Por lo tanto, las operaciones de arrastrar y colocar son extremadamente sencillas con el control <xref:System.Windows.Forms.RichTextBox> .  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a>Para habilitar las operaciones de arrastre en un control RichTextBox  
  
1. Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> del control <xref:System.Windows.Forms.RichTextBox> en `true`.  
  
2. Escriba código en el controlador de eventos del evento <xref:System.Windows.Forms.RichTextBox.DragEnter> . Use una declaración `if` para asegurarse de que los datos que se arrastran son de un tipo aceptable (en este caso, texto). La propiedad <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> se puede establecer en cualquier valor de la enumeración <xref:System.Windows.Forms.DragDropEffects> .  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     (Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. Escriba código para controlar el evento <xref:System.Windows.Forms.RichTextBox.DragDrop> . Utilice el método <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> para recuperar los datos que se están arrastrando.  
  
     En el ejemplo siguiente, el código establece la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox> igual a los datos que se están arrastrando. Si ya hay texto en el control <xref:System.Windows.Forms.RichTextBox> , el texto arrastrado se inserta en el punto de inserción.  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragDrop  
       Dim i As Int16
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     (Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a>Para probar la funcionalidad de arrastrar y colocar en la aplicación  
  
1. Guarde y compile la aplicación. Mientras se esté ejecutando, ejecute WordPad.  
  
     WordPad es un editor de texto instalado por Windows que permite operaciones de arrastrar y colocar. Para acceder a este, haga clic en el botón **Inicio** , seleccione **Ejecutar**, escriba `WordPad` en el cuadro de texto del cuadro de diálogo **Ejecutar** y, después, haga clic en **Aceptar**.  
  
2. Una vez abierto WordPad, escriba una cadena de texto en esta aplicación. Use el mouse para seleccionar el texto y, después, arrastre el texto seleccionado al control <xref:System.Windows.Forms.RichTextBox> de la aplicación Windows.  
  
     Observe que, cuando el mouse señala el control <xref:System.Windows.Forms.RichTextBox> (y, por consiguiente, genera el evento <xref:System.Windows.Forms.RichTextBox.DragEnter> ), el cursor cambia y puede colocar el texto seleccionado en el control <xref:System.Windows.Forms.RichTextBox> .  
  
     Al soltar el botón del mouse, se quita el texto seleccionado (es decir, se genera el evento <xref:System.Windows.Forms.RichTextBox.DragDrop> ) y se inserta en el control <xref:System.Windows.Forms.RichTextBox> .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.RichTextBox>
- [Cómo: Llevar a cabo operaciones de arrastrar y colocar entre aplicaciones](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [Control RichTextBox](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md)
