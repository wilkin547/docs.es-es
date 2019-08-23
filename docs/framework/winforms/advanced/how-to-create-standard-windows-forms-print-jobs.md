---
title: Procedimiento para crear trabajos de impresión estándar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938240"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="6bae0-102">Procedimiento para crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6bae0-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="6bae0-103">La base de la impresión en Windows Forms es <xref:System.Drawing.Printing.PrintDocument> el componente, más concretamente <xref:System.Drawing.Printing.PrintDocument.PrintPage> , el evento.</span><span class="sxs-lookup"><span data-stu-id="6bae0-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="6bae0-104">Al escribir código para controlar el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, puede especificar lo que se va a imprimir y cómo imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="6bae0-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="6bae0-105">Para crear un trabajo de impresión</span><span class="sxs-lookup"><span data-stu-id="6bae0-105">To create a print job</span></span>  
  
1. <span data-ttu-id="6bae0-106">Agregue un <xref:System.Drawing.Printing.PrintDocument> componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="6bae0-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="6bae0-107">Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="6bae0-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="6bae0-108">Tendrá que codificar su propia lógica de impresión.</span><span class="sxs-lookup"><span data-stu-id="6bae0-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="6bae0-109">Además, tendrá que especificar el material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="6bae0-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="6bae0-110">En el ejemplo de código siguiente, se crea un gráfico de ejemplo en la forma de un rectángulo rojo <xref:System.Drawing.Printing.PrintDocument.PrintPage> en el controlador de eventos para que actúe como material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="6bae0-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="6bae0-111">(Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="6bae0-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="6bae0-112">También puede escribir código para los <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventos y <xref:System.Drawing.Printing.PrintDocument.EndPrint> , quizás incluir un entero que represente el número total de páginas que se van a imprimir, que se reduce a medida que se imprime cada página.</span><span class="sxs-lookup"><span data-stu-id="6bae0-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6bae0-113">Puede Agregar un <xref:System.Windows.Forms.PrintDialog> componente a su formulario para proporcionar una interfaz de usuario limpia y eficaz a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6bae0-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="6bae0-114">Establecer la <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad <xref:System.Windows.Forms.PrintDialog> del componente le permite establecer las propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario.</span><span class="sxs-lookup"><span data-stu-id="6bae0-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="6bae0-115">Para obtener más información sobre <xref:System.Windows.Forms.PrintDialog> el componente, vea [PrintDialog (componente](../controls/printdialog-component-windows-forms.md)).</span><span class="sxs-lookup"><span data-stu-id="6bae0-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="6bae0-116">Para obtener más información acerca de los detalles de los trabajos de impresión Windows Forms, incluido cómo crear un trabajo de impresión mediante <xref:System.Drawing.Printing.PrintPageEventArgs>programación, vea.</span><span class="sxs-lookup"><span data-stu-id="6bae0-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bae0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bae0-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- <span data-ttu-id="6bae0-118">[Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6bae0-118">[Windows Forms Print Support](windows-forms-print-support.md)</span></span>
