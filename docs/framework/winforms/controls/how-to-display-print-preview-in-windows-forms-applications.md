---
title: Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154367"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms
Puede usar el <xref:System.Windows.Forms.PrintPreviewDialog> control para permitir que los usuarios mostrar un documento, a menudo antes de que se imprimen.  
  
 Para ello, deberá especificar una instancia de la <xref:System.Drawing.Printing.PrintDocument> clase; se trata de imprimir el documento. Para obtener más información sobre el uso de vista previa de impresión con la <xref:System.Drawing.Printing.PrintDocument> componente, vea [Cómo: Impresión en Windows Forms a través de la vista previa de impresión](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Para usar el <xref:System.Windows.Forms.PrintPreviewDialog> control en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea localmente o a través de una red, ya que es parcialmente la <xref:System.Windows.Forms.PrintPreviewDialog> componente determina el aspecto de un documento cuando se imprima.  
  
 El <xref:System.Windows.Forms.PrintPreviewDialog> control usa el <xref:System.Drawing.Printing.PrinterSettings> clase. Además, el <xref:System.Windows.Forms.PrintPreviewDialog> control usa el <xref:System.Drawing.Printing.PageSettings> (clase), al igual que el <xref:System.Windows.Forms.PrintPreviewDialog> componente. El documento de impresión especificado en el <xref:System.Windows.Forms.PrintPreviewDialog> del control <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> propiedad hace referencia a las instancias de ambos el <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y estos se utilizan para representar el documento en la ventana Vista previa.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Para ver las páginas mediante el control PrintPreviewDialog  
  
-   Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.  
  
     En el ejemplo de código siguiente, la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos abre una instancia de la <xref:System.Windows.Forms.PrintPreviewDialog> control. El documento de impresión se especifica en el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad. En el ejemplo siguiente, no se especifica ningún documento para imprimirlo.  
  
     El ejemplo requiere que el formulario tiene un <xref:System.Windows.Forms.Button> (control), un <xref:System.Drawing.Printing.PrintDocument> componente denominado `myDocument`y un <xref:System.Windows.Forms.PrintPreviewDialog> control.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vea también

- [PrintDocument (Componente, Windows Forms)](printdocument-component-windows-forms.md)
- [PrintPreviewDialog (control)](printpreviewdialog-control-windows-forms.md)
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [Windows Forms](../index.md)
