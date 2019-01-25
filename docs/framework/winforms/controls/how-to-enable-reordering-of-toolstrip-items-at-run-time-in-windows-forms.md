---
title: Procedimiento Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 0b3662a700d897607780e8d5032c498faff97753
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577024"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="ff55e-102">Procedimiento Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff55e-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="ff55e-103">Puede permitir que el usuario desea reorganizar <xref:System.Windows.Forms.ToolStripItem> controla en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ff55e-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="ff55e-104">Para habilitar la reorganización de ToolStripItem en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ff55e-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="ff55e-105">Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="ff55e-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="ff55e-106">De forma predeterminada, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="ff55e-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="ff55e-107">En tiempo de ejecución, el usuario mantiene presionada la tecla ALT y el botón primario del mouse para arrastrar un <xref:System.Windows.Forms.ToolStripItem> a una ubicación diferente en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="ff55e-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ff55e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff55e-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="ff55e-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ff55e-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="ff55e-110">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ff55e-110">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [<span data-ttu-id="ff55e-111">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ff55e-111">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
