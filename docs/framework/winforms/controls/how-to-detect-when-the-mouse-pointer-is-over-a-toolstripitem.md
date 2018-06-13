---
title: 'Cómo: Detectar cuándo está el puntero del mouse (ratón) en un elemento ToolStripItem'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 15a7562efd9a86a029754610ffd9e77c372d1ac2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530502"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ea391-102">Cómo: Detectar cuándo está el puntero del mouse (ratón) en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="ea391-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="ea391-103">Utilice el procedimiento siguiente para detectar cuando el puntero del mouse está sobre un <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="ea391-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ea391-104">Detectar cuando el puntero está sobre un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="ea391-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="ea391-105">Use la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propiedad para los elementos en el que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="ea391-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="ea391-106">Esto evitará tener que sincronizar el <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="ea391-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea391-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea391-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="ea391-108">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ea391-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
