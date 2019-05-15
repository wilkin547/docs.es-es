---
title: Procedimiento para agregar un control ToolStripContainer a un formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582582"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="c88c4-102">Procedimiento para agregar un control ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="c88c4-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="c88c4-103">Puede agregar mediante programación un <xref:System.Windows.Forms.ToolStripContainer> a Windows Forms y rellenarlo con controles.</span><span class="sxs-lookup"><span data-stu-id="c88c4-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c88c4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c88c4-104">Example</span></span>  
 <span data-ttu-id="c88c4-105">El ejemplo de código siguiente muestra cómo agregar un panel <xref:System.Windows.Forms.ToolStripContainer> y un control <xref:System.Windows.Forms.ToolStrip> a Windows Forms, cómo agregar elementos al control <xref:System.Windows.Forms.ToolStrip> y cómo agregar el control <xref:System.Windows.Forms.ToolStrip> a la propiedad <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del panel <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="c88c4-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c88c4-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c88c4-106">Compiling the Code</span></span>  
 <span data-ttu-id="c88c4-107">Para este ejemplo de código se necesita:</span><span class="sxs-lookup"><span data-stu-id="c88c4-107">This code example requires:</span></span>  
  
- <span data-ttu-id="c88c4-108">Referencias a los ensamblados System.Drawing, System.Text y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="c88c4-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88c4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c88c4-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="c88c4-110">ToolStripContainer (control)</span><span class="sxs-lookup"><span data-stu-id="c88c4-110">ToolStripContainer Control</span></span>](toolstripcontainer-control.md)
- [<span data-ttu-id="c88c4-111">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c88c4-111">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
