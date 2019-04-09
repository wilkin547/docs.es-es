---
title: Filtrar para completar trabajos de impresión de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: f8d0f1f067efbae6e2b667328e75996179b91737
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159827"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Filtrar para completar trabajos de impresión de formularios Windows Forms
Con frecuencia, los procesadores de textos y otras aplicaciones que implican impresión proporcionará la opción para mostrar un mensaje a los usuarios que un trabajo de impresión está completado. Puede proporcionar esta funcionalidad en los formularios Windows Forms controlando el <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos de la <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 El procedimiento siguiente requiere que se haya creado una aplicación basada en Windows con un <xref:System.Drawing.Printing.PrintDocument> componente en este, que es la manera estándar de habilitar la impresión desde una aplicación basada en Windows. Para obtener más información acerca de la impresión de Windows Forms mediante el <xref:System.Drawing.Printing.PrintDocument> componente, vea [Cómo: Crear trabajos de impresión estándar de Windows Forms](how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Para completar un trabajo de impresión  
  
1.  Establecer el <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> propiedad de la <xref:System.Drawing.Printing.PrintDocument> componente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .  
  
     En el ejemplo de código siguiente se muestra un cuadro de mensaje que indica que ha terminado de imprimir el documento.  
  
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
  
     (Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Printing.PrintDocument>
- [Funcionalidad para imprimir en formularios Windows Forms](windows-forms-print-support.md)
