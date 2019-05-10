---
title: Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623638"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="eb4ea-102">Procedimiento para detectar cuándo está el puntero del mouse en un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="eb4ea-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="eb4ea-103">Utilice el procedimiento siguiente para detectar cuando el puntero del mouse se sitúa sobre un <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="eb4ea-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="eb4ea-104">Para detectar cuando el puntero está sobre un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="eb4ea-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="eb4ea-105">Use la <xref:System.Windows.Forms.ToolStripItem.Selected%2A> propiedad para los elementos en el que <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="eb4ea-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="eb4ea-106">Esto impedirá tener que sincronizar el <xref:System.Windows.Forms.ToolStripItem.MouseEnter> y <xref:System.Windows.Forms.ToolStripItem.MouseLeave> eventos.</span><span class="sxs-lookup"><span data-stu-id="eb4ea-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4ea-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb4ea-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="eb4ea-108">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="eb4ea-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
