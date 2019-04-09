---
title: Filtrar para crear un control ToolStrip de estilo profesional
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 6da6e113867efed79dfcd02f3b89ee1f9ae13c4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104598"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="dfea4-102">Filtrar para crear un control ToolStrip de estilo profesional</span><span class="sxs-lookup"><span data-stu-id="dfea4-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="dfea4-103">Puede dar a los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación un aspecto y comportamiento profesional escribiendo su propia clase derivada del tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="dfea4-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="dfea4-104">Hay una amplia compatibilidad para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dfea4-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="dfea4-105">Vea [Tutorial: Crear un Control ToolStrip de estilo profesional](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="dfea4-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfea4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfea4-106">Example</span></span>  
 <span data-ttu-id="dfea4-107">En el ejemplo de código siguiente se muestra cómo usar <xref:System.Windows.Forms.ToolStrip> controles para crear un control compuesto que imite el **panel de navegación** proporcionado por Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="dfea4-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dfea4-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dfea4-108">Compiling the Code</span></span>  
 <span data-ttu-id="dfea4-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="dfea4-109">This example requires:</span></span>  
  
-   <span data-ttu-id="dfea4-110">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="dfea4-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="dfea4-111">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="dfea4-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="dfea4-112">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="dfea4-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="dfea4-113">Consulte también [Tutorial: Crear un Control ToolStrip de estilo profesional](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="dfea4-113">Also see [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfea4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfea4-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="dfea4-115">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="dfea4-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="dfea4-116">Filtrar para proporcionar elementos de menú estándar a un formulario</span><span class="sxs-lookup"><span data-stu-id="dfea4-116">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
