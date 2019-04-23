---
title: Procedimiento para controlar el evento Opening de ContextMenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170723"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="3d534-102">Procedimiento para controlar el evento Opening de ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="3d534-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="3d534-103">Puede personalizar el comportamiento de su <xref:System.Windows.Forms.ContextMenuStrip> control controlando el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.</span><span class="sxs-lookup"><span data-stu-id="3d534-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d534-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d534-104">Example</span></span>  
 <span data-ttu-id="3d534-105">En el ejemplo de código siguiente se muestra cómo controlar el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.</span><span class="sxs-lookup"><span data-stu-id="3d534-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="3d534-106">El controlador de eventos agrega elementos dinámicamente a un <xref:System.Windows.Forms.ContextMenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="3d534-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="3d534-107">El ejemplo de código completo, vea [Cómo: Agregar dinámicamente elementos de ToolStrip](how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="3d534-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="3d534-108">Establecer el <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> propiedad `true` para evitar que se abra el menú.</span><span class="sxs-lookup"><span data-stu-id="3d534-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d534-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d534-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="3d534-110">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="3d534-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
