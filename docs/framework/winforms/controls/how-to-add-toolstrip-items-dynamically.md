---
title: Filtrar Agregar dinámicamente elementos de ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- toolbars [Windows Forms], adding items dynamically
- ToolStrip control [Windows Forms]
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
ms.openlocfilehash: 557d1c11c93a4ebedd7098568eeda4be86951647
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702703"
---
# <a name="how-to-add-toolstrip-items-dynamically"></a><span data-ttu-id="4b8d1-102">Filtrar Agregar dinámicamente elementos de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4b8d1-102">How to: Add ToolStrip Items Dynamically</span></span>
<span data-ttu-id="4b8d1-103">Puede rellenar dinámicamente la colección de elementos de menú de un control <xref:System.Windows.Forms.ToolStrip> cuando se abre el menú.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-103">You can dynamically populate the menu item collection of a <xref:System.Windows.Forms.ToolStrip> control when the menu opens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b8d1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b8d1-104">Example</span></span>  
 <span data-ttu-id="4b8d1-105">En el ejemplo de código siguiente, se muestra cómo agregar dinámicamente elementos al control <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-105">The following code example demonstrates how to dynamically add items to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="4b8d1-106">El ejemplo también muestra cómo reutilizar el mismo <xref:System.Windows.Forms.ContextMenuStrip> para tres controles diferentes del formulario.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-106">The example also shows how to reuse the same <xref:System.Windows.Forms.ContextMenuStrip> for three different controls on the form.</span></span>  
  
 <span data-ttu-id="4b8d1-107">En el ejemplo, un controlador de eventos <xref:System.Windows.Forms.ToolStripDropDown.Opening> rellena la colección de elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-107">In the example, an <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler populates the menu item collection.</span></span> <span data-ttu-id="4b8d1-108">El controlador de eventos <xref:System.Windows.Forms.ToolStripDropDown.Opening> examina las propiedades <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType>, y agrega un <xref:System.Windows.Forms.ToolStripItem> que describe el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-108">The <xref:System.Windows.Forms.ToolStripDropDown.Opening> event handler examines the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=nameWithType> properties and adds a <xref:System.Windows.Forms.ToolStripItem> describing the source control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b8d1-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4b8d1-109">Compiling the Code</span></span>  
 <span data-ttu-id="4b8d1-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4b8d1-110">This example requires:</span></span>  
  
-   <span data-ttu-id="4b8d1-111">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-111">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4b8d1-112">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4b8d1-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4b8d1-113">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b8d1-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8d1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b8d1-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- [<span data-ttu-id="4b8d1-115">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4b8d1-115">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
