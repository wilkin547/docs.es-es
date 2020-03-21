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
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="6c835-102">Cómo: Completar trabajos de impresión de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c835-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="6c835-103">Con frecuencia, los procesadores de texto y otras aplicaciones que implican la impresión proporcionarán la opción de mostrar un mensaje a los usuarios de que se ha completado un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="6c835-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="6c835-104">Puede proporcionar esta funcionalidad en los formularios <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows <xref:System.Drawing.Printing.PrintDocument> Forms controlando el evento del componente.</span><span class="sxs-lookup"><span data-stu-id="6c835-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="6c835-105">El siguiente procedimiento requiere que haya creado una <xref:System.Drawing.Printing.PrintDocument> aplicación basada en Windows con un componente en ella, que es la forma estándar de habilitar la impresión desde una aplicación basada en Windows.</span><span class="sxs-lookup"><span data-stu-id="6c835-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="6c835-106">Para obtener más información acerca <xref:System.Drawing.Printing.PrintDocument> de la impresión desde formularios Windows Forms mediante el componente, vea [Cómo: crear trabajos](how-to-create-standard-windows-forms-print-jobs.md)de impresión de formularios Windows Forms estándar .</span><span class="sxs-lookup"><span data-stu-id="6c835-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="6c835-107">Para completar un trabajo de impresión</span><span class="sxs-lookup"><span data-stu-id="6c835-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="6c835-108">Establezca <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> la propiedad <xref:System.Drawing.Printing.PrintDocument> del componente.</span><span class="sxs-lookup"><span data-stu-id="6c835-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="6c835-109">Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .</span><span class="sxs-lookup"><span data-stu-id="6c835-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="6c835-110">En el ejemplo de código siguiente, se muestra un cuadro de mensaje que indica que el documento ha terminado de imprimir.</span><span class="sxs-lookup"><span data-stu-id="6c835-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
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
  
     <span data-ttu-id="6c835-111">(Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="6c835-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c835-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c835-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="6c835-113">Funcionalidad para imprimir en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6c835-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
