---
title: 'Cómo: Agregar un ToolStripContainer a un formulario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 0e3a766c8238d7388ee95ecda5c60836ed944e05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513190"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="0898c-102">Cómo: Agregar un ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="0898c-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="0898c-103">Puede agregar mediante programación un <xref:System.Windows.Forms.ToolStripContainer> a Windows Forms y rellenarlo con controles.</span><span class="sxs-lookup"><span data-stu-id="0898c-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0898c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0898c-104">Example</span></span>  
 <span data-ttu-id="0898c-105">El ejemplo de código siguiente muestra cómo agregar un panel <xref:System.Windows.Forms.ToolStripContainer> y un control <xref:System.Windows.Forms.ToolStrip> a Windows Forms, cómo agregar elementos al control <xref:System.Windows.Forms.ToolStrip> y cómo agregar el control <xref:System.Windows.Forms.ToolStrip> a la propiedad <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del panel <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="0898c-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0898c-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0898c-106">Compiling the Code</span></span>  
 <span data-ttu-id="0898c-107">Para este ejemplo de código se necesita:</span><span class="sxs-lookup"><span data-stu-id="0898c-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="0898c-108">Referencias a los ensamblados System.Drawing, System.Text y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0898c-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0898c-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0898c-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0898c-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0898c-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="0898c-111">Vea también [Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) o [Tareas de ToolStripContainer (Cuadro de diálogo)](https://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0898c-111">See also [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) or [ToolStripContainer Tasks Dialog Box](https://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0898c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0898c-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="0898c-113">ToolStripContainer (control)</span><span class="sxs-lookup"><span data-stu-id="0898c-113">ToolStripContainer Control</span></span>](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [<span data-ttu-id="0898c-114">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0898c-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
