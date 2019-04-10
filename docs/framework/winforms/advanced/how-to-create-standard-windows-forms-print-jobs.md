---
title: Filtrar para crear trabajos de impresión estándar de formularios Windows Forms
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
ms.openlocfilehash: 816da93218e20f73f16c14769ed1a549dd3d8eb3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335412"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="3608b-102">Filtrar para crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3608b-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="3608b-103">La base de la impresión en Windows Forms es la <xref:System.Drawing.Printing.PrintDocument> componente, más concretamente, el <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos.</span><span class="sxs-lookup"><span data-stu-id="3608b-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="3608b-104">Al escribir código para controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos, puede especificar lo que desea imprimir y cómo imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="3608b-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="3608b-105">Para crear un trabajo de impresión</span><span class="sxs-lookup"><span data-stu-id="3608b-105">To create a print job</span></span>  
  
1. <span data-ttu-id="3608b-106">Agregar un <xref:System.Drawing.Printing.PrintDocument> al formulario.</span><span class="sxs-lookup"><span data-stu-id="3608b-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="3608b-107">Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="3608b-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="3608b-108">Tendrá que codificar su propia lógica de impresión.</span><span class="sxs-lookup"><span data-stu-id="3608b-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="3608b-109">Además, tendrá que especificar el material que se imprimen.</span><span class="sxs-lookup"><span data-stu-id="3608b-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="3608b-110">En el ejemplo de código siguiente se crea un gráfico de ejemplo en la forma de un rectángulo rojo en el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos para que actúe como material para imprimirse.</span><span class="sxs-lookup"><span data-stu-id="3608b-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="3608b-111">(Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3608b-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="3608b-112">También puede escribir código para el <xref:System.Drawing.Printing.PrintDocument.BeginPrint> y <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos, quizá para incluir un entero que representa el número total de páginas para imprimir que cada página se imprime.</span><span class="sxs-lookup"><span data-stu-id="3608b-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3608b-113">Puede agregar un <xref:System.Windows.Forms.PrintDialog> al formulario para proporcionar una interfaz limpia y eficiente de usuario (UI) a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3608b-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="3608b-114">Establecer el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad de la <xref:System.Windows.Forms.PrintDialog> habilita componente establecer las propiedades relacionadas con la impresión del documento que está trabajando en el formulario.</span><span class="sxs-lookup"><span data-stu-id="3608b-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="3608b-115">Para obtener más información sobre la <xref:System.Windows.Forms.PrintDialog> componente, vea [componente PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3608b-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="3608b-116">Para obtener más información sobre las características de Windows Forms, los trabajos de impresión, incluido cómo crear un trabajo de impresión mediante programación, vea <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3608b-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3608b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3608b-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="3608b-118">Funcionalidad para imprimir en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3608b-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
