---
title: Procedimiento Crear una partición del espacio mediante el elemento DockPanel
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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960196"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a>Procedimiento Crear una partición del espacio mediante el elemento DockPanel
En el ejemplo siguiente se crea [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] un marco de <xref:System.Windows.Controls.DockPanel> trabajo simple mediante un elemento. El <xref:System.Windows.Controls.DockPanel> espacio disponible de las particiones en sus elementos secundarios.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se <xref:System.Windows.Controls.DockPanel.Dock%2A> usa la propiedad, que es una propiedad adjunta, para acoplar dos elementos <xref:System.Windows.Controls.Dock.Top> idénticos <xref:System.Windows.Controls.Border> en el espacio con particiones. Un tercer <xref:System.Windows.Controls.Border> elemento está acoplado <xref:System.Windows.Controls.Dock.Left>a, con su ancho establecido en 200 píxeles. Un cuarto <xref:System.Windows.Controls.Border> está acoplado <xref:System.Windows.Controls.Dock.Bottom> al de la pantalla. El último <xref:System.Windows.Controls.Border> elemento rellena automáticamente el espacio restante.  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> De forma predeterminada, el último elemento secundario <xref:System.Windows.Controls.DockPanel> de un elemento rellena el espacio restante sin asignar. Si no desea este comportamiento, establezca `LastChildFill="False"`.  
  
 La aplicación compilada genera una nueva interfaz de usuario que tiene esta apariencia.  
  
 ![Escenario DockPanel típico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.DockPanel>
- [Información general sobre elementos Panel](panels-overview.md)
