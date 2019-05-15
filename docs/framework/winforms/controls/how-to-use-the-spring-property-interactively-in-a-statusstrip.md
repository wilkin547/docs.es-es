---
title: Procedimiento para usar la propiedad Spring de manera interactiva en un control StatusStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 8750c48d08161260a1dba6ab69098980f25a5d55
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589639"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a><span data-ttu-id="3ae5e-102">Procedimiento para usar la propiedad Spring de manera interactiva en un control StatusStrip</span><span class="sxs-lookup"><span data-stu-id="3ae5e-102">How to: Use the Spring Property Interactively in a StatusStrip</span></span>
<span data-ttu-id="3ae5e-103">Puede utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-103">You can use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="3ae5e-104">La propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina si el control <xref:System.Windows.Forms.ToolStripStatusLabel> rellena automáticamente el espacio disponible en el control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-104">The <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property determines whether the <xref:System.Windows.Forms.ToolStripStatusLabel> control automatically fills the available space on the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae5e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ae5e-105">Example</span></span>  
 <span data-ttu-id="3ae5e-106">El ejemplo de código siguiente muestra cómo utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-106">The following code example demonstrates how to use the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property to position a <xref:System.Windows.Forms.ToolStripStatusLabel> control in a <xref:System.Windows.Forms.StatusStrip> control.</span></span> <span data-ttu-id="3ae5e-107">El controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> realiza una operación OR exclusiva (XOR) para cambiar el valor de la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-107">The <xref:System.Windows.Forms.ToolStripItem.Click> event handler performs an exclusive-or (XOR) operation to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 <span data-ttu-id="3ae5e-108">Para usar este ejemplo de código, compilar y ejecutar la aplicación y, a continuación, haga clic en **Middle (Spring)** en el <xref:System.Windows.Forms.StatusStrip> control para cambiar el valor de la <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-108">To use this code example, compile and run the application, and then click **Middle (Spring)** on the <xref:System.Windows.Forms.StatusStrip> control to switch the value of the <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ae5e-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3ae5e-109">Compiling the Code</span></span>  
 <span data-ttu-id="3ae5e-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3ae5e-110">This example requires:</span></span>  
  
- <span data-ttu-id="3ae5e-111">Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="3ae5e-111">References to the System.Design, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae5e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ae5e-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="3ae5e-113">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3ae5e-113">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
