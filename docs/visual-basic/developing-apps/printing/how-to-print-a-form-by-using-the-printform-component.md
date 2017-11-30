---
title: "Cómo: Imprimir un formulario mediante el componente PrintForm (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: Form [Visual Basic], printing
ms.assetid: df963bf6-3ee1-49f4-8b2e-1d95d1beb0be
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5edad4f04b98dcf0dfa328f111db5dcb423036e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-form-by-using-the-printform-component-visual-basic"></a><span data-ttu-id="f53a5-102">Cómo: Imprimir un formulario mediante el componente PrintForm (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f53a5-102">How to: Print a Form by Using the PrintForm Component (Visual Basic)</span></span>
<span data-ttu-id="f53a5-103">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> permite imprimir rápidamente una imagen de un formulario, tal y como aparece en pantalla sin usar un componente <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="f53a5-103">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component enables you to quickly print an image of a form exactly as it appears on screen without using a <xref:System.Drawing.Printing.PrintDocument> component.</span></span> <span data-ttu-id="f53a5-104">Los procedimientos siguientes muestran cómo imprimir un formulario en una impresora, una ventana de vista previa de impresión y un archivo PostScript encapsulado.</span><span class="sxs-lookup"><span data-stu-id="f53a5-104">The following procedures show how to print a form to a printer, to a print preview window, and to an Encapsulated PostScript file.</span></span>  
  
 <span data-ttu-id="f53a5-105">Los controles PowerPack ya no están incluidos en Visual Studio, pero puede descargarlos desde el [Centro de descarga](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span><span class="sxs-lookup"><span data-stu-id="f53a5-105">The PowerPack controls are no longer included in Visual Studio, but you can download them from the [Download Center](http://www.microsoft.com/en-us/download/details.aspx?id=25169).</span></span>  
  
### <a name="to-print-a-form-to-the-default-printer"></a><span data-ttu-id="f53a5-106">Para imprimir un formulario en la impresora predeterminada</span><span class="sxs-lookup"><span data-stu-id="f53a5-106">To print a form to the default printer</span></span>  
  
1.  <span data-ttu-id="f53a5-107">En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.</span><span class="sxs-lookup"><span data-stu-id="f53a5-107">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="f53a5-108">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="f53a5-108">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="f53a5-109">En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span><span class="sxs-lookup"><span data-stu-id="f53a5-109">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>.</span></span>  
  
3.  <span data-ttu-id="f53a5-110">Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).</span><span class="sxs-lookup"><span data-stu-id="f53a5-110">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-display-a-form-in-a-print-preview-window"></a><span data-ttu-id="f53a5-111">Para visualizar un formulario en una ventana de vista previa de impresión</span><span class="sxs-lookup"><span data-stu-id="f53a5-111">To display a form in a print preview window</span></span>  
  
1.  <span data-ttu-id="f53a5-112">En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.</span><span class="sxs-lookup"><span data-stu-id="f53a5-112">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="f53a5-113">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="f53a5-113">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="f53a5-114">En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span><span class="sxs-lookup"><span data-stu-id="f53a5-114">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToPreview>.</span></span>  
  
3.  <span data-ttu-id="f53a5-115">Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).</span><span class="sxs-lookup"><span data-stu-id="f53a5-115">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
### <a name="to-print-a-form-to-a-file"></a><span data-ttu-id="f53a5-116">Para imprimir un formulario en un archivo</span><span class="sxs-lookup"><span data-stu-id="f53a5-116">To print a form to a file</span></span>  
  
1.  <span data-ttu-id="f53a5-117">En el **Cuadro de herramientas**, haga clic en la pestaña **Visual Basic PowerPacks** y, después, arrastre el componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> al formulario.</span><span class="sxs-lookup"><span data-stu-id="f53a5-117">In the **Toolbox**, click the **Visual Basic PowerPacks** tab and then drag the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component onto the form.</span></span>  
  
     <span data-ttu-id="f53a5-118">El componente <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> se agrega a la bandeja de componentes.</span><span class="sxs-lookup"><span data-stu-id="f53a5-118">The <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> component is added to the component tray.</span></span>  
  
2.  <span data-ttu-id="f53a5-119">En la ventana **Propiedades** , establezca la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> en <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span><span class="sxs-lookup"><span data-stu-id="f53a5-119">In the **Properties** window, set the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> property to <xref:System.Drawing.Printing.PrintAction.PrintToFile>.</span></span>  
  
3.  <span data-ttu-id="f53a5-120">Opcionalmente, seleccione la propiedad <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> y escriba la ruta de acceso completa y nombre del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="f53a5-120">Optionally, select the <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A> property and type the full path and file name for the destination file.</span></span>  
  
     <span data-ttu-id="f53a5-121">Si omite este paso, se pedirá al usuario un nombre de archivo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f53a5-121">If you skip this step, the user will be prompted for a file name at run time.</span></span>  
  
4.  <span data-ttu-id="f53a5-122">Agregue el siguiente código al controlador de eventos adecuado (por ejemplo, al controlador de eventos `Click` de un botón **Imprimir**`Button`).</span><span class="sxs-lookup"><span data-stu-id="f53a5-122">Add the following code in the appropriate event handler (for example, in the `Click` event handler for a **Print**`Button`).</span></span>  
  
    ```  
    PrintForm1.Print()  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f53a5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53a5-123">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintFileName%2A>  
 [<span data-ttu-id="f53a5-124">Imprimir el área de cliente de un formulario</span><span class="sxs-lookup"><span data-stu-id="f53a5-124">How to: Print the Client Area of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [<span data-ttu-id="f53a5-125">Imprimir áreas de cliente y áreas que no son de cliente de un formulario</span><span class="sxs-lookup"><span data-stu-id="f53a5-125">How to: Print Client and Non-Client Areas of a Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)  
 [<span data-ttu-id="f53a5-126">Imprimir un formulario desplazable</span><span class="sxs-lookup"><span data-stu-id="f53a5-126">How to: Print a Scrollable Form</span></span>](../../../visual-basic/developing-apps/printing/how-to-print-a-scrollable-form.md)  
 [<span data-ttu-id="f53a5-127">PrintForm (componente)</span><span class="sxs-lookup"><span data-stu-id="f53a5-127">PrintForm Component</span></span>](../../../visual-basic/developing-apps/printing/printform-component.md)
