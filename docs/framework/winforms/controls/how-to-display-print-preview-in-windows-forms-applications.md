---
title: "C&#243;mo: Mostrar la vista preliminar en aplicaciones de Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], vista previa de impresión"
  - "vista previa de impresión, mostrar"
  - "imprimir [Windows Forms], vista previa de impresión"
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Mostrar la vista preliminar en aplicaciones de Windows Forms
Se puede utilizar el control <xref:System.Windows.Forms.PrintPreviewDialog> para permitir a los usuarios mostrar un documento, con frecuencia antes de ser impreso.  
  
 Para ello, debe especificar una instancia de la clase <xref:System.Drawing.Printing.PrintDocument>; éste es el documento que se imprimirá.  Para obtener más información sobre cómo usar la vista previa de impresión con el componente <xref:System.Drawing.Printing.PrintDocument>, vea [Cómo: Imprimir en Windows Forms a través de la vista previa de impresión](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Para utilizar el control <xref:System.Windows.Forms.PrintPreviewDialog> en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea localmente o a través de una red, ya que esto influye parcialmente en cómo determina el componente <xref:System.Windows.Forms.PrintPreviewDialog> el aspecto que tendrá el documento al imprimirlo.  
  
 El control <xref:System.Windows.Forms.PrintPreviewDialog> utiliza la clase <xref:System.Drawing.Printing.PrinterSettings>.  Además, el control <xref:System.Windows.Forms.PrintPreviewDialog> utiliza la clase <xref:System.Drawing.Printing.PageSettings>, del mismo modo que el componente <xref:System.Windows.Forms.PrintPreviewDialog>.  El documento de impresión especificado en la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del control <xref:System.Windows.Forms.PrintPreviewDialog> hace referencia a instancias de las dos clases <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings>, y se utilizan para representar el documento en la ventana de vista previa.  
  
### Para ver páginas con el control PrintPreviewDialog  
  
-   Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el componente <xref:System.Drawing.Printing.PrintDocument> que se utilizará.  
  
     En el ejemplo siguiente, el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button> abre una instancia del control <xref:System.Windows.Forms.PrintPreviewDialog>.  El documento para imprimir se especifica en la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A>.  Observe que, en el ejemplo siguiente, no se especifica ningún documento para imprimirlo.  
  
     En el ejemplo requiere que el formulario tiene un control <xref:System.Windows.Forms.Button>, un componente <xref:System.Drawing.Printing.PrintDocument> denominado `myDocument` y un control <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Vea también  
 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)   
 [PrintPreviewDialog \(Control\)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)