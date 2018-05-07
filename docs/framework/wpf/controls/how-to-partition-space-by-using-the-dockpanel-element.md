---
title: 'Cómo: Crear una partición del espacio mediante el elemento DockPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 6b10fbcd14236f9259dc5772e7f8763c1602d0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Cómo: Crear una partición del espacio mediante el elemento DockPanel
En el ejemplo siguiente se crea un sencillo [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework usando un <xref:System.Windows.Controls.DockPanel> elemento. El <xref:System.Windows.Controls.DockPanel> particiones espacio disponible en sus elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad, que es una propiedad adjunta para acoplar dos idénticos <xref:System.Windows.Controls.Border> elementos en la <xref:System.Windows.Controls.Dock.Top> del espacio con particiones. Una tercera <xref:System.Windows.Controls.Border> el elemento se acopla a la <xref:System.Windows.Controls.Dock.Left>, con su ancho establecido en 200 píxeles. Un cuarto <xref:System.Windows.Controls.Border> está acoplada a la <xref:System.Windows.Controls.Dock.Bottom> de la pantalla. La última <xref:System.Windows.Controls.Border> elemento rellena automáticamente el espacio restante.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  De forma predeterminada, el último elemento secundario de un <xref:System.Windows.Controls.DockPanel> elemento rellena el espacio sin asignar restantes. Si no desea este comportamiento, establezca `LastChildFill="False"`.  
  
 La aplicación compilada genera una nueva interfaz de usuario que tiene esta apariencia.  
  
 ![Escenario DockPanel típico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.DockPanel>  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
