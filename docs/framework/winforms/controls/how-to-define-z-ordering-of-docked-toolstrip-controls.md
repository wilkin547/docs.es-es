---
title: Filtrar Definir el orden Z de los controles ToolStrip acoplados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 1ae7e6f63488d2dbb6b408cdf255f111f929298f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722677"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="3d262-102">Filtrar Definir el orden Z de los controles ToolStrip acoplados</span><span class="sxs-lookup"><span data-stu-id="3d262-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="3d262-103">Para colocar correctamente un control <xref:System.Windows.Forms.ToolStrip> con acoplamiento, debe colocar de forma adecuada el control en el orden z del formulario.</span><span class="sxs-lookup"><span data-stu-id="3d262-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d262-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d262-104">Example</span></span>  
 <span data-ttu-id="3d262-105">En el ejemplo de código siguiente, se muestra cómo se organiza un control <xref:System.Windows.Forms.ToolStrip> y un control <xref:System.Windows.Forms.MenuStrip> acoplado especificando el orden z.</span><span class="sxs-lookup"><span data-stu-id="3d262-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="3d262-106">El orden determina el orden z en que los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="3d262-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="3d262-107">se agregan a la colección <xref:System.Windows.Forms.Control.Controls%2A> del formulario.</span><span class="sxs-lookup"><span data-stu-id="3d262-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="3d262-108">vierta el orden de estas llamadas al método <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> y vea el efecto en el diseño.</span><span class="sxs-lookup"><span data-stu-id="3d262-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d262-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3d262-109">Compiling the Code</span></span>  
 <span data-ttu-id="3d262-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3d262-110">This example requires:</span></span>  
  
-   <span data-ttu-id="3d262-111">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3d262-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3d262-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="3d262-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3d262-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="3d262-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d262-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d262-114">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>
- <xref:System.Windows.Forms.Control.Controls%2A>
- <xref:System.Windows.Forms.Control.Dock%2A>
- [<span data-ttu-id="3d262-115">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3d262-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
