---
title: Crear trabajos de impresión estándar
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741522"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="83d8d-102">Cómo: Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83d8d-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="83d8d-103">La base de la impresión en Windows Forms es el componente <xref:System.Drawing.Printing.PrintDocument>, más concretamente, el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="83d8d-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="83d8d-104">Al escribir código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>, puede especificar lo que se va a imprimir y cómo imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="83d8d-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="83d8d-105">Para crear un trabajo de impresión</span><span class="sxs-lookup"><span data-stu-id="83d8d-105">To create a print job</span></span>  
  
1. <span data-ttu-id="83d8d-106">Agregue un componente de <xref:System.Drawing.Printing.PrintDocument> al formulario.</span><span class="sxs-lookup"><span data-stu-id="83d8d-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="83d8d-107">Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="83d8d-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="83d8d-108">Tendrá que codificar su propia lógica de impresión.</span><span class="sxs-lookup"><span data-stu-id="83d8d-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="83d8d-109">Además, tendrá que especificar el material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="83d8d-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="83d8d-110">En el ejemplo de código siguiente, se crea un gráfico de ejemplo en la forma de un rectángulo rojo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage> para que actúe como material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="83d8d-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="83d8d-111">(Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="83d8d-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="83d8d-112">También puede que desee escribir código para los eventos <xref:System.Drawing.Printing.PrintDocument.BeginPrint> y <xref:System.Drawing.Printing.PrintDocument.EndPrint>, quizás incluir un entero que represente el número total de páginas que se van a imprimir, que se reduce a medida que se imprime cada página.</span><span class="sxs-lookup"><span data-stu-id="83d8d-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="83d8d-113">Puede Agregar un componente de <xref:System.Windows.Forms.PrintDialog> a su formulario para proporcionar una interfaz de usuario limpia y eficaz a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="83d8d-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="83d8d-114">El establecimiento de la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A> del componente <xref:System.Windows.Forms.PrintDialog> le permite establecer propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario.</span><span class="sxs-lookup"><span data-stu-id="83d8d-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="83d8d-115">Para obtener más información sobre el componente de <xref:System.Windows.Forms.PrintDialog>, vea [PrintDialog (componente](../controls/printdialog-component-windows-forms.md)).</span><span class="sxs-lookup"><span data-stu-id="83d8d-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="83d8d-116">Para obtener más información acerca de los detalles de los trabajos de impresión Windows Forms, incluido cómo crear un trabajo de impresión mediante programación, vea <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="83d8d-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d8d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83d8d-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- <span data-ttu-id="83d8d-118">[Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="83d8d-118">[Windows Forms Print Support](windows-forms-print-support.md)</span></span>
