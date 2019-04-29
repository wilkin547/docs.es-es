---
title: Procedimiento para crear un formulario MDI con combinación de menús y controles ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: a67298614b1985152c42577de14d2c5d295f672f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746621"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="a4507-102">Procedimiento para crear un formulario MDI con combinación de menús y controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a4507-102">How to: Create an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="a4507-103">El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.</span><span class="sxs-lookup"><span data-stu-id="a4507-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="a4507-104">Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a4507-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="a4507-105">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a4507-105">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="a4507-106">Consulte también [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a4507-106">Also see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4507-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4507-107">Example</span></span>  
 <span data-ttu-id="a4507-108">En el siguiente ejemplo de código, se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="a4507-108">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="a4507-109">El formulario también admite la combinación de menús con menús secundarios.</span><span class="sxs-lookup"><span data-stu-id="a4507-109">The form also supports menu merging with child menus.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4507-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a4507-110">Compiling the Code</span></span>  
 <span data-ttu-id="a4507-111">Para este ejemplo de código se necesita:</span><span class="sxs-lookup"><span data-stu-id="a4507-111">This code example requires:</span></span>  
  
- <span data-ttu-id="a4507-112">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a4507-112">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a4507-113">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a4507-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a4507-114">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4507-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4507-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4507-115">See also</span></span>

- [<span data-ttu-id="a4507-116">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a4507-116">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
