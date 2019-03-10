---
title: Filtrar Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms
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
ms.openlocfilehash: 0800acc955ff8cf9efa7bc183f10d2b5cc87aac6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713725"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="e02b3-102">Procedimiento Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e02b3-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="e02b3-103">Puede permitir que el usuario desea reorganizar <xref:System.Windows.Forms.ToolStripItem> controla en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="e02b3-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="e02b3-104">Para habilitar la reorganización de ToolStripItem en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e02b3-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="e02b3-105">Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="e02b3-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="e02b3-106">De forma predeterminada, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="e02b3-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="e02b3-107">En tiempo de ejecución, el usuario mantiene presionada la tecla ALT y el botón primario del mouse para arrastrar un <xref:System.Windows.Forms.ToolStripItem> a una ubicación diferente en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="e02b3-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e02b3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e02b3-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="e02b3-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e02b3-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="e02b3-110">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e02b3-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="e02b3-111">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="e02b3-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
