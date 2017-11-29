---
title: "Cómo: Definir el orden Z de los controles ToolStrip acoplados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71de03fa0a4c3b0d53da29709cc38f50179bed24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a><span data-ttu-id="0ee29-102">Cómo: Definir el orden Z de los controles ToolStrip acoplados</span><span class="sxs-lookup"><span data-stu-id="0ee29-102">How to: Define Z-Ordering of Docked ToolStrip Controls</span></span>
<span data-ttu-id="0ee29-103">Para colocar correctamente un control <xref:System.Windows.Forms.ToolStrip> con acoplamiento, debe colocar de forma adecuada el control en el orden z del formulario.</span><span class="sxs-lookup"><span data-stu-id="0ee29-103">To position a <xref:System.Windows.Forms.ToolStrip> control correctly with docking, you must position the control correctly in the form's z-order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ee29-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ee29-104">Example</span></span>  
 <span data-ttu-id="0ee29-105">En el ejemplo de código siguiente, se muestra cómo se organiza un control <xref:System.Windows.Forms.ToolStrip> y un control <xref:System.Windows.Forms.MenuStrip> acoplado especificando el orden z.</span><span class="sxs-lookup"><span data-stu-id="0ee29-105">The following code example demonstrates how to arrange a <xref:System.Windows.Forms.ToolStrip> control and a docked <xref:System.Windows.Forms.MenuStrip> control by specifying the z-order.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 <span data-ttu-id="0ee29-106">El orden determina el orden z en que los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="0ee29-106">The z-order is determined by the order in which the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip></span></span>  
  
 <span data-ttu-id="0ee29-107">se agregan a la colección <xref:System.Windows.Forms.Control.Controls%2A> del formulario.</span><span class="sxs-lookup"><span data-stu-id="0ee29-107">controls are added to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 <span data-ttu-id="0ee29-108">vierta el orden de estas llamadas al método <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> y vea el efecto en el diseño.</span><span class="sxs-lookup"><span data-stu-id="0ee29-108">Reverse the order of these calls to the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method and view the effect on the layout.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ee29-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0ee29-109">Compiling the Code</span></span>  
 <span data-ttu-id="0ee29-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0ee29-110">This example requires:</span></span>  
  
-   <span data-ttu-id="0ee29-111">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0ee29-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0ee29-112">Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0ee29-112">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0ee29-113">También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ee29-113">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="0ee29-114">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="0ee29-114">Also se [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee29-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ee29-115">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [<span data-ttu-id="0ee29-116">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0ee29-116">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
