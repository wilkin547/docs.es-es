---
title: "Cómo: Dibujar líneas con el control LineShape (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42e7f01a57a514ad1dc64e3d4451ce38ea199f93
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="dbb02-102">Cómo: Dibujar líneas con el control LineShape (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="dbb02-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="dbb02-103">Puede usar el <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control para dibujar líneas horizontales, verticales o diagonales en un formulario o contenedor, tanto en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dbb02-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="dbb02-104">**Tenga en cuenta** su posible que equipo muestre nombres o ubicaciones para algunos de los usuarios de Visual Studio diferentes elementos de la interfaz en las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="dbb02-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="dbb02-105">La edición de Visual Studio que se tenga y la configuración que se utilice determinan estos elementos.</span><span class="sxs-lookup"><span data-stu-id="dbb02-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="dbb02-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="dbb02-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="dbb02-107">Para dibujar una línea en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="dbb02-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="dbb02-108">Arrastre el <xref:Microsoft.VisualBasic.PowerPacks.LineShape> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** arrastre hasta un formulario o un control contenedor.</span><span class="sxs-lookup"><span data-stu-id="dbb02-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="dbb02-109">Arrastre el ajuste de tamaño y mover los controladores de tamaño y la posición de la línea.</span><span class="sxs-lookup"><span data-stu-id="dbb02-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="dbb02-110">También puede cambiar el tamaño y colocar la línea cambiando el `X1`, `X2`, `Y1`, y `Y2` propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="dbb02-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="dbb02-111">En el **propiedades** ventana, o bien establezca propiedades adicionales como `BorderStyle` o `BorderColor` para cambiar la apariencia de la línea.</span><span class="sxs-lookup"><span data-stu-id="dbb02-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="dbb02-112">Para dibujar una línea en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dbb02-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="dbb02-113">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="dbb02-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="dbb02-114">En el **Agregar referencia** cuadro de diálogo, seleccione **Microsoft.VisualBasic.PowerPacks.VS**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dbb02-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="dbb02-115">En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:</span><span class="sxs-lookup"><span data-stu-id="dbb02-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="dbb02-116">Agregue el código siguiente en un procedimiento `Event`:</span><span class="sxs-lookup"><span data-stu-id="dbb02-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dbb02-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbb02-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="dbb02-118">Introducción a los controles de líneas y formas</span><span class="sxs-lookup"><span data-stu-id="dbb02-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="dbb02-119">Dibujar formas con los controles OvalShape y RectangleShape</span><span class="sxs-lookup"><span data-stu-id="dbb02-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
