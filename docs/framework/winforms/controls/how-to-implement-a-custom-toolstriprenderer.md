---
title: 'Cómo: Implementar un control ToolStripRenderer personalizado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 91c04ba41a02c7c620c2f6c621505a19e0302c19
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398120"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="98194-102">Cómo: Implementar un control ToolStripRenderer personalizado</span><span class="sxs-lookup"><span data-stu-id="98194-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="98194-103">Puede personalizar la apariencia de un control <xref:System.Windows.Forms.ToolStrip> implementando una clase que deriva de <xref:System.Windows.Forms.ToolStripRenderer>.</span><span class="sxs-lookup"><span data-stu-id="98194-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="98194-104">Esta opción le da flexibilidad para crear un aspecto diferente al que proporcionan las clases <xref:System.Windows.Forms.ToolStripProfessionalRenderer> y <xref:System.Windows.Forms.ToolStripSystemRenderer>.</span><span class="sxs-lookup"><span data-stu-id="98194-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98194-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98194-105">Example</span></span>  
 <span data-ttu-id="98194-106">En el ejemplo de código siguiente, se muestra cómo implementar una clase <xref:System.Windows.Forms.ToolStripRenderer> personalizada.</span><span class="sxs-lookup"><span data-stu-id="98194-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="98194-107">En este ejemplo, el control `GridStrip` implementa un rompecabezas de mosaicos deslizantes que permite al usuario trasladar mosaicos en un diseño de tabla para formar una imagen.</span><span class="sxs-lookup"><span data-stu-id="98194-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="98194-108">Un control <xref:System.Windows.Forms.ToolStrip> personalizado organiza sus controles <xref:System.Windows.Forms.ToolStripButton> en un diseño de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="98194-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="98194-109">El diseño contiene una celda vacía en la que el usuario puede deslizar un mosaico adyacente mediante una operación de arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="98194-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="98194-110">Se resaltan los mosaicos que el usuario puede mover.</span><span class="sxs-lookup"><span data-stu-id="98194-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="98194-111">La clase `GridStripRenderer` personaliza tres aspectos del aspecto del control `GridStrip`:</span><span class="sxs-lookup"><span data-stu-id="98194-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
-   <span data-ttu-id="98194-112">Borde `GridStrip`</span><span class="sxs-lookup"><span data-stu-id="98194-112">`GridStrip` border</span></span>  
  
-   <span data-ttu-id="98194-113">Borde <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="98194-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
-   <span data-ttu-id="98194-114">Imagen <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="98194-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98194-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="98194-115">Compiling the Code</span></span>  
 <span data-ttu-id="98194-116">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="98194-116">This example requires:</span></span>  
  
-   <span data-ttu-id="98194-117">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="98194-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="98194-118">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="98194-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="98194-119">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="98194-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="98194-120">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="98194-120">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98194-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="98194-121">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="98194-122">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="98194-122">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
