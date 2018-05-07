---
title: 'Cómo: Obtener o establecer un valor de acoplamiento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: b792c8b2342416fb380827b702efa28885145d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-or-set-a-dock-value"></a>Cómo: Obtener o establecer un valor de acoplamiento
En el ejemplo siguiente se muestra cómo asignar un <xref:System.Windows.Controls.Dock> valor para un objeto. El ejemplo se utiliza la <xref:System.Windows.Controls.DockPanel.GetDock%2A> y <xref:System.Windows.Controls.DockPanel.SetDock%2A> métodos de <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se crea una instancia de la <xref:System.Windows.Controls.TextBlock> elemento, `txt1`y le asigna un <xref:System.Windows.Controls.Dock> valo `Top` mediante el uso de la <xref:System.Windows.Controls.DockPanel.SetDock%2A> método de <xref:System.Windows.Controls.DockPanel>. Después, se anexa el valor de la <xref:System.Windows.Controls.Dock> propiedad para el <xref:System.Windows.Controls.TextBlock.Text%2A> de la <xref:System.Windows.Controls.TextBlock> elemento mediante el uso de la <xref:System.Windows.Controls.DockPanel.GetDock%2A> (método). Por último, en el ejemplo se agrega el <xref:System.Windows.Controls.TextBlock> elemento al elemento primario <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
