---
title: Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054268"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="7eec7-102">Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="7eec7-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="7eec7-103">Utilice el procedimiento siguiente para detectar cuando el puntero del mouse se sitúa sobre un <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="7eec7-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="7eec7-104">Para detectar cuando el puntero está sobre un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="7eec7-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="7eec7-105">Use la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propiedad para los elementos en el que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="7eec7-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="7eec7-106">Esto impedirá tener que sincronizar el <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="7eec7-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eec7-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eec7-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="7eec7-108">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7eec7-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
