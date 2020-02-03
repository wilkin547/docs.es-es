---
title: Completar trabajos de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: b8ef4fa05b2107247181e82b72389f9503507135
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746493"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Cómo: Completar trabajos de impresión de formularios Windows Forms
Con frecuencia, los procesadores de texto y otras aplicaciones que impliquen impresión proporcionarán la opción de mostrar un mensaje a los usuarios de que se ha completado un trabajo de impresión. Puede proporcionar esta funcionalidad en el Windows Forms controlando el evento de <xref:System.Drawing.Printing.PrintDocument.EndPrint> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 El procedimiento siguiente requiere que se haya creado una aplicación basada en Windows con un <xref:System.Drawing.Printing.PrintDocument> componente, que es la manera estándar de habilitar la impresión desde una aplicación basada en Windows. Para obtener más información acerca de la impresión desde Windows Forms mediante el componente <xref:System.Drawing.Printing.PrintDocument>, consulte [Cómo: crear trabajos de impresión estándar de Windows Forms](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Para completar un trabajo de impresión  
  
1. Establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     En el ejemplo de código siguiente, se muestra un cuadro de mensaje que indica que el documento ha finalizado la impresión.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
