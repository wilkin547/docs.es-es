---
title: Procedimiento Personalizar los colores en las aplicaciones de ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], customizing colors
- colors [Windows Forms], customizing in ToolStrip controls [Windows Forms]
- ToolStrip control [Windows Forms], custom colors
ms.assetid: e2752fe2-1afb-489e-ab96-b7805acd96bc
ms.openlocfilehash: 0a7679624d375fac610f6c74f124881d7235eab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585437"
---
# <a name="how-to-customize-colors-in-toolstrip-applications"></a><span data-ttu-id="d5c38-102">Procedimiento Personalizar los colores en las aplicaciones de ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5c38-102">How to: Customize Colors in ToolStrip Applications</span></span>
<span data-ttu-id="d5c38-103">Puede personalizar la apariencia de <xref:System.Windows.Forms.ToolStrip> usando la clase <xref:System.Windows.Forms.ToolStripProfessionalRenderer> para utilizar colores personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5c38-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> by using the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class to use customized colors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5c38-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5c38-104">Example</span></span>  
 <span data-ttu-id="d5c38-105">El siguiente ejemplo de código muestra cómo utilizar <xref:System.Windows.Forms.ToolStripProfessionalRenderer> para definir colores personalizados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5c38-105">The following code example demonstrates how to use a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> to define custom colors at run time.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5c38-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d5c38-106">Compiling the Code</span></span>  
 <span data-ttu-id="d5c38-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d5c38-107">This example requires:</span></span>  
  
-   <span data-ttu-id="d5c38-108">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d5c38-108">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d5c38-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d5c38-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d5c38-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="d5c38-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="d5c38-111">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="d5c38-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c38-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5c38-112">See also</span></span>
- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.ProfessionalColorTable>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
