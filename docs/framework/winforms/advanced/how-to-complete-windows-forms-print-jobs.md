---
title: Trabajos de impresión completos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182596"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Cómo: Completar trabajos de impresión de formularios Windows Forms
Con frecuencia, los procesadores de texto y otras aplicaciones que implican la impresión proporcionarán la opción de mostrar un mensaje a los usuarios de que se ha completado un trabajo de impresión. Puede proporcionar esta funcionalidad en los formularios <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows <xref:System.Drawing.Printing.PrintDocument> Forms controlando el evento del componente.  
  
 El siguiente procedimiento requiere que haya creado una <xref:System.Drawing.Printing.PrintDocument> aplicación basada en Windows con un componente en ella, que es la forma estándar de habilitar la impresión desde una aplicación basada en Windows. Para obtener más información acerca <xref:System.Drawing.Printing.PrintDocument> de la impresión desde formularios Windows Forms mediante el componente, vea [Cómo: crear trabajos](how-to-create-standard-windows-forms-print-jobs.md)de impresión de formularios Windows Forms estándar .  
  
### <a name="to-complete-a-print-job"></a>Para completar un trabajo de impresión  
  
1. Establezca <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> la propiedad <xref:System.Drawing.Printing.PrintDocument> del componente.  
  
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
  
     En el ejemplo de código siguiente, se muestra un cuadro de mensaje que indica que el documento ha terminado de imprimir.  
  
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
  
     (Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
- [Funcionalidad para imprimir en formularios Windows Forms](windows-forms-print-support.md)
