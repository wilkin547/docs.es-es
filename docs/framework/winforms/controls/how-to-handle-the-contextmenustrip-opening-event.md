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
ms.workload: dotnet
ms.openlocfilehash: 5de244abd35c83bce329882d679df8303ef3a833
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Cómo: Controlar el evento Opening de ContextMenuStrip
Puede personalizar el comportamiento de la <xref:System.Windows.Forms.ContextMenuStrip> control controlando el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo controlar la <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos. El controlador de eventos agrega elementos de forma dinámica a un <xref:System.Windows.Forms.ContextMenuStrip> control. En el ejemplo de código completo, vea [Cómo: agregar dinámicamente elementos de ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Establecer el <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> propiedad `true` para evitar que se abra el menú.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
