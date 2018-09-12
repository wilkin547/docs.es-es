---
title: 'Cómo: Establecer la representación de ToolStrip en tiempo de ejecución'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripManager class [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 525e2347-0804-49aa-b9a3-9b2cabbf1c35
ms.openlocfilehash: 98a027cb8cd913e3e2d00db16fc2f527159a1c87
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706432"
---
# <a name="how-to-set-the-toolstrip-renderer-at-run-time"></a><span data-ttu-id="6a8ac-102">Cómo: Establecer la representación de ToolStrip en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6a8ac-102">How to: Set the ToolStrip Renderer at Run Time</span></span>
<span data-ttu-id="6a8ac-103">Puede personalizar la apariencia de su control <xref:System.Windows.Forms.ToolStrip> creando una clase `ProfessionalColorTable` personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-103">You can customize the appearance of your <xref:System.Windows.Forms.ToolStrip> control by creating a custom `ProfessionalColorTable` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a8ac-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6a8ac-104">Example</span></span>  
 <span data-ttu-id="6a8ac-105">En el siguiente ejemplo se muestra cómo crear una clase `ProfessionalColorTable` personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-105">The following code example demonstrates how to create a custom `ProfessionalColorTable` class.</span></span> <span data-ttu-id="6a8ac-106">Esta clase define los degradados para controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-106">This class defines gradients for a <xref:System.Windows.Forms.MenuStrip> and a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
 <span data-ttu-id="6a8ac-107">Para utilizar este ejemplo de código, compile y ejecute la aplicación y, a continuación, haga clic en **Cambiar colores** para aplicar los degradados definidos en la clase `ProfessionalColorTable` personalizada.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-107">To use this code example, compile and run the application, and then click **Change Colors** to apply the gradients defined in the custom `ProfessionalColorTable` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#20)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#20)]  
  
## <a name="defining-a-custom-professionalcolortable-class"></a><span data-ttu-id="6a8ac-108">Definir una clase ProfessionalColorTable personalizada</span><span class="sxs-lookup"><span data-stu-id="6a8ac-108">Defining a Custom ProfessionalColorTable class</span></span>  
 <span data-ttu-id="6a8ac-109">Los degradados personalizados se definen en la clase `CustomProfessionalColors`.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-109">The custom gradients are defined in the `CustomProfessionalColors` class.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#30)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#30)]  
  
## <a name="assigning-a-custom-renderer"></a><span data-ttu-id="6a8ac-110">Asignar un representador personalizado</span><span class="sxs-lookup"><span data-stu-id="6a8ac-110">Assigning a Custom Renderer</span></span>  
 <span data-ttu-id="6a8ac-111">Cree un nuevo `ToolStripProfessionalRenderer` con una clase `CustomProfessionalColors` y asígnelo a la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-111">Create a new `ToolStripProfessionalRenderer` with a `CustomProfessionalColors` class, and assign it to the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#22)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6a8ac-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6a8ac-112">Compiling the Code</span></span>  
 <span data-ttu-id="6a8ac-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="6a8ac-113">This example requires:</span></span>  
  
-   <span data-ttu-id="6a8ac-114">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-114">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="6a8ac-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6a8ac-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6a8ac-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="6a8ac-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="6a8ac-117">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6a8ac-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a8ac-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a8ac-118">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.ProfessionalColorTable>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [<span data-ttu-id="6a8ac-119">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="6a8ac-119">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
