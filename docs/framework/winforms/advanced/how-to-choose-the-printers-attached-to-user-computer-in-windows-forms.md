---
title: "C&#243;mo: Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "impresión [Windows Forms], elegir impresoras"
  - "impresoras, elegir"
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms
A menudo, los usuarios quieren elegir una impresora que no sea la predeterminada. Para que los usuarios puedan elegir una impresora de entre las que están instaladas, use el componente <xref:System.Windows.Forms.PrintDialog>. Con el componente <xref:System.Windows.Forms.PrintDialog>, se captura el <xref:System.Windows.Forms.DialogResult> del componente <xref:System.Windows.Forms.PrintDialog> y se usa para seleccionar la impresora.  
  
 En el siguiente procedimiento se selecciona un archivo de texto para imprimirlo en la impresora predeterminada y luego se crea una instancia de la clase <xref:System.Windows.Forms.PrintDialog>.  
  
### Para elegir una impresora e imprimir un archivo  
  
1.  Seleccione la impresora que se va a usar con el componente <xref:System.Windows.Forms.PrintDialog>.  
  
     En el siguiente ejemplo de código se tratan dos eventos. En el primero, el evento <xref:System.Windows.Forms.Control.Click> de un control <xref:System.Windows.Forms.Button>, se crea una instancia de la clase <xref:System.Windows.Forms.PrintDialog> y la impresora seleccionada por el usuario se captura en la propiedad <xref:System.Windows.Forms.DialogResult>.  
  
     En el segundo evento, el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> del componente <xref:System.Drawing.Printing.PrintDocument>, se imprime un documento de ejemplo en la impresora especificada.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Vea también  
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)