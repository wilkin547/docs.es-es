---
title: 'Cómo: elegir las impresoras conectadas al equipo de un usuario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746510"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a>Cómo: Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms
A menudo, los usuarios quieren elegir una impresora que no sea la predeterminada. Para que los usuarios puedan elegir una impresora de entre las que están instaladas, use el componente <xref:System.Windows.Forms.PrintDialog> . Con el componente <xref:System.Windows.Forms.PrintDialog> , se captura el <xref:System.Windows.Forms.DialogResult> del componente <xref:System.Windows.Forms.PrintDialog> y se usa para seleccionar la impresora.  
  
 En el siguiente procedimiento se selecciona un archivo de texto para imprimirlo en la impresora predeterminada y luego se crea una instancia de la clase <xref:System.Windows.Forms.PrintDialog> .  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a>Para elegir una impresora e imprimir un archivo  
  
1. Seleccione la impresora que se va a usar con el componente de <xref:System.Windows.Forms.PrintDialog>.  
  
     En el siguiente ejemplo de código se tratan dos eventos. En el primer caso, se crea <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Button> una instancia de la clase <xref:System.Windows.Forms.PrintDialog> y la impresora seleccionada por el usuario se captura en la propiedad <xref:System.Windows.Forms.DialogResult>.  
  
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
  
     (Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
## <a name="see-also"></a>Vea también

- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
