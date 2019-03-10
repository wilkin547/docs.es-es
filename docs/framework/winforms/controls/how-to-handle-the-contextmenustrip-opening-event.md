---
title: Procedimiento Controlar el evento Opening de ContextMenuStrip
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
ms.openlocfilehash: 179411da96362fd9ba42e2b97682f335beb894c1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715456"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Filtrar Controlar el evento Opening de ContextMenuStrip
Puede personalizar el comportamiento de su <xref:System.Windows.Forms.ContextMenuStrip> control controlando el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo controlar el <xref:System.Windows.Forms.ToolStripDropDown.Opening> eventos. El controlador de eventos agrega elementos dinámicamente a un <xref:System.Windows.Forms.ContextMenuStrip> control. El ejemplo de código completo, vea [Cómo: Agregar dinámicamente elementos de ToolStrip](how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Establecer el <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> propiedad `true` para evitar que se abra el menú.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [Control ToolStrip](toolstrip-control-windows-forms.md)
