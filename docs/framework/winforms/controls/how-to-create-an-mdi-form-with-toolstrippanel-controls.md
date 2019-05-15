---
title: Procedimiento para crear un formulario MDI con controles ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms [Windows Forms]
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
ms.assetid: d198ef8e-f7c4-4b3f-a7f5-ce858cb90cec
ms.openlocfilehash: 4dae528d69c6c08c2005fd30d7d16fafa67afb53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590553"
---
# <a name="how-to-create-an-mdi-form-with-toolstrippanel-controls"></a><span data-ttu-id="2df3a-102">Procedimiento para crear un formulario MDI con controles ToolStripPanel</span><span class="sxs-lookup"><span data-stu-id="2df3a-102">How to: Create an MDI Form with ToolStripPanel Controls</span></span>
<span data-ttu-id="2df3a-103">Puede crear un formulario de interfaz de múltiples documentos (MDI) que tenga controles <xref:System.Windows.Forms.ToolStrip> que lo enmarquen por los cuatro lados.</span><span class="sxs-lookup"><span data-stu-id="2df3a-103">You can create a multiple document interface (MDI) form that has <xref:System.Windows.Forms.ToolStrip> controls framing it on all four sides.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df3a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2df3a-104">Example</span></span>  
 <span data-ttu-id="2df3a-105">El ejemplo de código siguiente muestra cómo utilizar controles <xref:System.Windows.Forms.ToolStripPanel> acoplados para enmarcar una ventana MDI con cuatro controles <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="2df3a-105">The following code example demonstrates how to use docked <xref:System.Windows.Forms.ToolStripPanel> controls to frame an MDI window with four <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="2df3a-106">En el ejemplo, el método <xref:System.Windows.Forms.ToolStripPanel.Join%2A> asocia los controles <xref:System.Windows.Forms.ToolStrip> a los controles <xref:System.Windows.Forms.ToolStripPanel> correspondientes.</span><span class="sxs-lookup"><span data-stu-id="2df3a-106">In the example, the <xref:System.Windows.Forms.ToolStripPanel.Join%2A> method attaches the <xref:System.Windows.Forms.ToolStrip> controls to the corresponding <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2df3a-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2df3a-107">Compiling the Code</span></span>  
 <span data-ttu-id="2df3a-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2df3a-108">This example requires:</span></span>  
  
- <span data-ttu-id="2df3a-109">Referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2df3a-109">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df3a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df3a-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- <xref:System.Windows.Forms.ToolStripPanel.Join%2A>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="2df3a-111">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="2df3a-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
