---
title: Visualización de la vista previa de impresión en Windows Forms aplicaciones
titleSuffix: ''
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
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745572"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Cómo: Mostrar la vista preliminar en aplicaciones de Windows Forms
Puede usar el control <xref:System.Windows.Forms.PrintPreviewDialog> para permitir que los usuarios muestren un documento, a menudo antes de que se imprima.  
  
 Para ello, debe especificar una instancia de la clase <xref:System.Drawing.Printing.PrintDocument>; Este es el documento que se va a imprimir. Para obtener más información acerca del uso de la vista previa de impresión con el componente de <xref:System.Drawing.Printing.PrintDocument>, consulte [Cómo: imprimir en Windows Forms con la vista previa de impresión](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
> Para usar el control <xref:System.Windows.Forms.PrintPreviewDialog> en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea de forma local o a través de una red, ya que esto es en parte el modo en que el componente <xref:System.Windows.Forms.PrintPreviewDialog> determina el aspecto que tendrá un documento cuando se imprima.  
  
 El control <xref:System.Windows.Forms.PrintPreviewDialog> utiliza la clase <xref:System.Drawing.Printing.PrinterSettings>. Además, el control <xref:System.Windows.Forms.PrintPreviewDialog> utiliza la clase <xref:System.Drawing.Printing.PageSettings>, del mismo modo que el componente <xref:System.Windows.Forms.PrintPreviewDialog>. El documento de impresión especificado en la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del control <xref:System.Windows.Forms.PrintPreviewDialog> hace referencia a las instancias de las clases <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings>, y se usan para representar el documento en la ventana de vista previa.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Para ver páginas mediante el control PrintPreviewDialog  
  
- Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.  
  
     En el ejemplo de código siguiente, el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button> abre una instancia del control <xref:System.Windows.Forms.PrintPreviewDialog>. El documento de impresión se especifica en la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A>. En el ejemplo siguiente, no se especifica ningún documento de impresión.  
  
     El ejemplo requiere que el formulario tenga un control <xref:System.Windows.Forms.Button>, un componente <xref:System.Drawing.Printing.PrintDocument> denominado `myDocument`y un control <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
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
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Consulte también

- [PrintDocument (componente)](printdocument-component-windows-forms.md)
- [PrintPreviewDialog (control)](printpreviewdialog-control-windows-forms.md)
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [Windows Forms](../index.md)
