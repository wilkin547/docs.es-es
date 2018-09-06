---
title: 'Cómo: Imprimir un formulario con desplazamiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 4a509b7c48f2bff705bc95e58fb88252cb8ca4b9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779424"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a><span data-ttu-id="f4593-102">Cómo: Imprimir un formulario con desplazamiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4593-102">How to: Print a Scrollable Form (Visual Basic)</span></span>
<span data-ttu-id="f4593-103">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario sin usar un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="f4593-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="f4593-104">De forma predeterminada, se imprime solo la parte visible del formulario; si un usuario cambió el tamaño del formulario en tiempo de ejecución, es posible que la imagen no se imprima según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="f4593-104">By default, only the currently visible part of the form is printed; if a user has resized the form at run time, the image may not print as intended.</span></span> <span data-ttu-id="f4593-105">El siguiente procedimiento muestra cómo imprimir el área de cliente completa de un formulario con desplazamiento, aunque se haya cambiado el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="f4593-105">The following procedure shows how to print the complete client area of a scrollable form, even if the form has been resized.</span></span>  
  
 <span data-ttu-id="f4593-106">Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [centro de descarga de](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="f4593-106">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a><span data-ttu-id="f4593-107">Para imprimir el área de cliente completa de un formulario con desplazamiento</span><span class="sxs-lookup"><span data-stu-id="f4593-107">To print the complete client area of a scrollable form</span></span>  
  
1.  <span data-ttu-id="f4593-108">En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.</span><span class="sxs-lookup"><span data-stu-id="f4593-108">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="f4593-109">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agregará a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="f4593-109">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component will be added to the component tray.</span></span>  
  
2.  <span data-ttu-id="f4593-110">En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="f4593-110">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="f4593-111">Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).</span><span class="sxs-lookup"><span data-stu-id="f4593-111">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f4593-112">En algunos sistemas operativos, es posible que el texto o los gráficos dibujados por métodos <xref:System.Drawing.Graphics> no se impriman correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4593-112">On some operating systems, text or graphics drawn by <xref:System.Drawing.Graphics> methods may not print correctly.</span></span> <span data-ttu-id="f4593-113">En este caso, no podrá imprimir con el parámetro `Scrollable` .</span><span class="sxs-lookup"><span data-stu-id="f4593-113">In this case, you will not be able to print with the `Scrollable` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4593-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4593-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [<span data-ttu-id="f4593-115">PrintForm (componente)</span><span class="sxs-lookup"><span data-stu-id="f4593-115">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [<span data-ttu-id="f4593-116">Imprimir el área de cliente de un formulario</span><span class="sxs-lookup"><span data-stu-id="f4593-116">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="f4593-117">Imprimir áreas de cliente y áreas que no son de cliente de un formulario</span><span class="sxs-lookup"><span data-stu-id="f4593-117">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
