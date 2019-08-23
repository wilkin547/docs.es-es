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
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929004"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms
Puede usar el <xref:System.Windows.Forms.PrintPreviewDialog> control para permitir que los usuarios muestren un documento, a menudo antes de que se imprima.  
  
 Para ello, debe especificar una instancia de la <xref:System.Drawing.Printing.PrintDocument> clase; este es el documento que se va a imprimir. Para obtener más información acerca del uso de la <xref:System.Drawing.Printing.PrintDocument> vista previa de [impresión con el componente, consulte Cómo: Imprimir en Windows Forms con la vista](../advanced/how-to-print-in-windows-forms-using-print-preview.md)previa de impresión.  
  
> [!NOTE]
> Para usar el <xref:System.Windows.Forms.PrintPreviewDialog> control en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea de forma local o a través de una red, <xref:System.Windows.Forms.PrintPreviewDialog> ya que esto es en parte cómo el componente determina la apariencia de un documento cuando se imprime.  
  
 El <xref:System.Windows.Forms.PrintPreviewDialog> control utiliza la <xref:System.Drawing.Printing.PrinterSettings> clase. Además, el <xref:System.Windows.Forms.PrintPreviewDialog> control utiliza la <xref:System.Drawing.Printing.PageSettings> clase, del mismo modo <xref:System.Windows.Forms.PrintPreviewDialog> que el componente. El documento de impresión especificado en <xref:System.Windows.Forms.PrintPreviewDialog> la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del control hace referencia a las instancias <xref:System.Drawing.Printing.PrinterSettings> de <xref:System.Drawing.Printing.PageSettings> las clases y, y se usan para representar el documento en la ventana de vista previa.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Para ver páginas mediante el control PrintPreviewDialog  
  
- Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.  
  
     En el ejemplo de código siguiente, <xref:System.Windows.Forms.Button> el controlador <xref:System.Windows.Forms.Control.Click> de eventos del control <xref:System.Windows.Forms.PrintPreviewDialog> abre una instancia del control. El documento de impresión se especifica en <xref:System.Windows.Forms.PrintDialog.Document%2A> la propiedad. En el ejemplo siguiente, no se especifica ningún documento de impresión.  
  
     El ejemplo requiere que el formulario tenga un <xref:System.Windows.Forms.Button> control, un <xref:System.Drawing.Printing.PrintDocument> componente denominado `myDocument`y un <xref:System.Windows.Forms.PrintPreviewDialog> control.  
  
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
  
## <a name="see-also"></a>Vea también

- [PrintDocument (Componente, Windows Forms)](printdocument-component-windows-forms.md)
- [PrintPreviewDialog (control)](printpreviewdialog-control-windows-forms.md)
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [Windows Forms](../index.md)
