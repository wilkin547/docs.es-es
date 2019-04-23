---
title: Procedimiento para agregar dinámicamente elementos de ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: d84b62005554479d227778f513e72594322791a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124935"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="565d2-102">Procedimiento para agregar dinámicamente elementos de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="565d2-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="565d2-103">Puede rellenar dinámicamente la colección de elementos de menú de un control <xref:System.Windows.Forms.ToolStrip> cuando se abre el menú.</span><span class="sxs-lookup"><span data-stu-id="565d2-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="565d2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="565d2-104">Example</span></span>  
 <span data-ttu-id="565d2-105">En el ejemplo de código siguiente, se muestra cómo agregar dinámicamente elementos al control <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="565d2-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="565d2-106">El ejemplo también muestra cómo reutilizar el mismo <xref:System.Windows.Forms.ContextMenuStrip> para tres controles diferentes del formulario.</span><span class="sxs-lookup"><span data-stu-id="565d2-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="565d2-107">En el ejemplo, un controlador de eventos <xref:System.Windows.Forms.ToolStripDropDown.Opening> rellena la colección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="565d2-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="565d2-108">El controlador de eventos <xref:System.Windows.Forms.ToolStripDropDown.Opening> examina las propiedades <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType>, y agrega un <xref:System.Windows.Forms.ToolStripItem> que describe el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="565d2-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="565d2-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="565d2-109">Compiling the Code</span></span>  
 <span data-ttu-id="565d2-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="565d2-110">This example requires:</span></span>  
  
-   <span data-ttu-id="565d2-111">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="565d2-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="565d2-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="565d2-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="565d2-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="565d2-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565d2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="565d2-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="565d2-115">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="565d2-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
