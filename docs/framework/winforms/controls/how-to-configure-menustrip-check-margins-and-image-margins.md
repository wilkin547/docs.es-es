---
title: Procedimiento Configuración de la comprobación de MenuStrip los márgenes e imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins [Windows Forms], setting in MenuStrip controls
- menus [Windows Forms], setting margins
- MenuStrip control [Windows Forms], configuring check and image margins
ms.assetid: 45a9075d-4bea-4ce2-9b2c-7619aa39f8ce
ms.openlocfilehash: 49c228fef387a7c2a18cf8cecd5081e7b5519ab3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530780"
---
# <a name="how-to-configure-menustrip-check-margins-and-image-margins"></a><span data-ttu-id="40841-102">Procedimiento Configuración de la comprobación de MenuStrip los márgenes e imagen</span><span class="sxs-lookup"><span data-stu-id="40841-102">How to: Configure MenuStrip Check Margins and Image Margins</span></span>
<span data-ttu-id="40841-103">Puede personalizar un <xref:System.Windows.Forms.MenuStrip> estableciendo las propiedades <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> y <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> en diversas combinaciones.</span><span class="sxs-lookup"><span data-stu-id="40841-103">You can customize a <xref:System.Windows.Forms.MenuStrip> by setting the <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowImageMargin%2A> and <xref:System.Windows.Forms.ToolStripDropDownMenu.ShowCheckMargin%2A> properties in various combinations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40841-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40841-104">Example</span></span>  
 <span data-ttu-id="40841-105">En el ejemplo de código siguiente, se muestra cómo establecer y personalizar los márgenes de comprobación y los márgenes de imagen <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="40841-105">The following code example demonstrates how to set and customize the <xref:System.Windows.Forms.ContextMenuStrip> check margins and image margins.</span></span> <span data-ttu-id="40841-106">El procedimiento es el mismo para <xref:System.Windows.Forms.ContextMenuStrip> o <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="40841-106">The procedure is the same for a <xref:System.Windows.Forms.ContextMenuStrip> or a <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#60)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40841-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="40841-107">Compiling the Code</span></span>  
 <span data-ttu-id="40841-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="40841-108">This example requires:</span></span>  
  
-   <span data-ttu-id="40841-109">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="40841-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="40841-110">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="40841-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="40841-111">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="40841-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="40841-112">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="40841-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40841-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="40841-113">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="40841-114">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="40841-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
- [<span data-ttu-id="40841-115">Cómo: Habilitar los márgenes de comprobación y de imagen en los controles ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="40841-115">How to: Enable Check Margins and Image Margins in ContextMenuStrip Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-check-margins-and-image-margins-in-contextmenustrip-controls.md)
