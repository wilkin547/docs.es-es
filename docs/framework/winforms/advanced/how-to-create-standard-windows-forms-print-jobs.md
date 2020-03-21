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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182567"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="0bbe2-102">Cómo: Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0bbe2-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="0bbe2-103">La base de la impresión en formularios Windows Forms es el <xref:System.Drawing.Printing.PrintDocument> componente, más específicamente, el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="0bbe2-104">Al escribir código <xref:System.Drawing.Printing.PrintDocument.PrintPage> para controlar el evento, puede especificar qué imprimir y cómo imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="0bbe2-105">Para crear un trabajo de impresión</span><span class="sxs-lookup"><span data-stu-id="0bbe2-105">To create a print job</span></span>  
  
1. <span data-ttu-id="0bbe2-106">Agregue <xref:System.Drawing.Printing.PrintDocument> un componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="0bbe2-107">Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="0bbe2-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="0bbe2-108">Tendrá que codificar su propia lógica de impresión.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="0bbe2-109">Además, tendrá que especificar el material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="0bbe2-110">En el ejemplo de código siguiente, se crea un gráfico <xref:System.Drawing.Printing.PrintDocument.PrintPage> de ejemplo con la forma de un rectángulo rojo en el controlador de eventos para que actúe como material que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="0bbe2-111">(Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="0bbe2-112">También es posible que desee escribir código para los <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventos y, <xref:System.Drawing.Printing.PrintDocument.EndPrint> tal vez, incluido un entero que representa el número total de páginas para imprimir que se reduce a medida que se imprime cada página.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0bbe2-113">Puede agregar <xref:System.Windows.Forms.PrintDialog> un componente al formulario para proporcionar una interfaz de usuario (UI) limpia y eficaz a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="0bbe2-114">Establecer <xref:System.Windows.Forms.PrintDialog.Document%2A> la propiedad <xref:System.Windows.Forms.PrintDialog> del componente le permite establecer propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario.</span><span class="sxs-lookup"><span data-stu-id="0bbe2-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="0bbe2-115">Para obtener más <xref:System.Windows.Forms.PrintDialog> información sobre el componente, vea [Componente PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0bbe2-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="0bbe2-116">Para obtener más información acerca de los detalles de los trabajos <xref:System.Drawing.Printing.PrintPageEventArgs>de impresión de formularios Windows Forms, incluido cómo crear un trabajo de impresión mediante programación, vea .</span><span class="sxs-lookup"><span data-stu-id="0bbe2-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbe2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bbe2-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="0bbe2-118">Funcionalidad para imprimir en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0bbe2-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
