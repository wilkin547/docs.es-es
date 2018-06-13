---
title: 'Cómo: Imprimir áreas de cliente y áreas que no son de cliente de un formulario (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- title bar [Visual Basic], printing
- printing
- borders [Visual Basic], printing
- entire form
- non-client area [Visual Basic], printing
ms.assetid: 856bb0e4-dbc3-47e2-81cd-4b376cf07757
ms.openlocfilehash: 566cf295462945a6bc90bc96f8907de34646bd00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584747"
---
# <a name="how-to-print-client-and-non-client-areas-of-a-form-visual-basic"></a><span data-ttu-id="059b1-102">Cómo: Imprimir áreas de cliente y áreas que no son de cliente de un formulario (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="059b1-102">How to: Print Client and Non-Client Areas of a Form (Visual Basic)</span></span>
<span data-ttu-id="059b1-103">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario, tal y como aparece en pantalla sin usar un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="059b1-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="059b1-104">El siguiente procedimiento muestra cómo imprimir un formulario, incluyendo el área de cliente y el área que no es de cliente.</span><span class="sxs-lookup"><span data-stu-id="059b1-104">The following procedure shows how to print a form, including both the client area and the non-client area.</span></span> <span data-ttu-id="059b1-105">El área que no es de cliente incluye la barra de título, los bordes y las barras de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="059b1-105">The non-client area includes the title bar, borders, and scroll bars.</span></span>  
  
 <span data-ttu-id="059b1-106">Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="059b1-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-both-the-client-and-the-non-client-areas-of-a-form"></a><span data-ttu-id="059b1-107">Para imprimir el área de cliente y el área que no es de cliente de un formulario</span><span class="sxs-lookup"><span data-stu-id="059b1-107">To print both the client and the non-client areas of a form</span></span>  
  
1.  <span data-ttu-id="059b1-108">En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.</span><span class="sxs-lookup"><span data-stu-id="059b1-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="059b1-109">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="059b1-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="059b1-110">En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="059b1-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="059b1-111">Agregue el siguiente código en el controlador de eventos apropiado (por ejemplo, en el controlador de un evento `Click` de un control `Button`Imprimir).</span><span class="sxs-lookup"><span data-stu-id="059b1-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a Print `Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.FullWindow)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="059b1-112">En algunos sistemas operativos, es posible que el texto o los gráficos dibujados por métodos <xref:System.Drawing.Graphics> no se impriman correctamente.</span><span class="sxs-lookup"><span data-stu-id="059b1-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="059b1-113">En este caso, use el método de impresión compatible: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).</span><span class="sxs-lookup"><span data-stu-id="059b1-113">In this case, use the compatible printing method: `PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.CompatibleModeFullWindow`).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="059b1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="059b1-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="059b1-115">PrintForm (componente)</span><span class="sxs-lookup"><span data-stu-id="059b1-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="059b1-116">Imprimir un formulario desplazable</span><span class="sxs-lookup"><span data-stu-id="059b1-116">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)
