---
title: "Cómo: Controlar el evento Opening de ContextMenuStrip"
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
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 354631e514d9e2ece39d16bf7f259c36e4f90c32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="b1723-102">Cómo: Controlar el evento Opening de ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b1723-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="b1723-103">Puede personalizar el comportamiento de la <xref:System.Windows.Forms.ContextMenuStrip> control controlando el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.</span><span class="sxs-lookup"><span data-stu-id="b1723-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1723-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1723-104">Example</span></span>  
 <span data-ttu-id="b1723-105">En el ejemplo de código siguiente se muestra cómo controlar la <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.</span><span class="sxs-lookup"><span data-stu-id="b1723-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="b1723-106">El controlador de eventos agrega elementos de forma dinámica a un <xref:System.Windows.Forms.ContextMenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="b1723-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="b1723-107">En el ejemplo de código completo, vea [Cómo: agregar dinámicamente elementos de ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="b1723-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="b1723-108">Establecer el <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> propiedad `true` para evitar que se abra el menú.</span><span class="sxs-lookup"><span data-stu-id="b1723-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1723-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1723-109">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="b1723-110">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b1723-110">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
