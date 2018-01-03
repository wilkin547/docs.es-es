---
title: "Cómo: Habilitar la tabulación entre las formas (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0b1e8b0378e65becd80324491632ecd8dbffdbbf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="134e6-102">Cómo: Habilitar la tabulación entre las formas (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="134e6-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="134e6-103">No tiene controles Line y shape `TabStop` o `TabIndex` propiedades, pero todavía puede habilitar la tabulación entre ellos.</span><span class="sxs-lookup"><span data-stu-id="134e6-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="134e6-104">En el siguiente ejemplo, al presionar la tecla CTRL y las teclas TAB se pestaña entre formas; solo la tecla TAB se pestaña entre los botones.</span><span class="sxs-lookup"><span data-stu-id="134e6-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="134e6-105">Es posible que el equipo muestre nombres o ubicaciones diferentes para algunos de los elementos de la interfaz de usuario de Visual Studio en las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="134e6-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="134e6-106">La edición de Visual Studio que se tenga y la configuración que se utilice determinan estos elementos.</span><span class="sxs-lookup"><span data-stu-id="134e6-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="134e6-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="134e6-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="134e6-108">Para habilitar la tabulación entre las formas</span><span class="sxs-lookup"><span data-stu-id="134e6-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="134e6-109">Arrastre tres <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controles y dos <xref:System.Windows.Forms.Button> controla desde el **cuadro de herramientas** a un formulario.</span><span class="sxs-lookup"><span data-stu-id="134e6-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="134e6-110">En el **Editor de código**, agregue un `Imports` o `using` instrucción en la parte superior del módulo:</span><span class="sxs-lookup"><span data-stu-id="134e6-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="134e6-111">Agregue el código siguiente en un procedimiento de evento:</span><span class="sxs-lookup"><span data-stu-id="134e6-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="134e6-112">Agregue el código siguiente en el `Button1_PreviewKeyDown` procedimiento de evento:</span><span class="sxs-lookup"><span data-stu-id="134e6-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="134e6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="134e6-113">See Also</span></span>  
 [<span data-ttu-id="134e6-114">Dibujar formas con los controles OvalShape y RectangleShape</span><span class="sxs-lookup"><span data-stu-id="134e6-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="134e6-115">Dibujar líneas con el control LineShape</span><span class="sxs-lookup"><span data-stu-id="134e6-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="134e6-116">Introducción a los controles de líneas y formas</span><span class="sxs-lookup"><span data-stu-id="134e6-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
