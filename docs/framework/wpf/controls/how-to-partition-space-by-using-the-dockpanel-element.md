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
ms.locfileid: "33553889"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="d84c3-102">Cómo: Crear una partición del espacio mediante el elemento DockPanel</span><span class="sxs-lookup"><span data-stu-id="d84c3-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="d84c3-103">En el ejemplo siguiente se crea un sencillo [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework usando un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="d84c3-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="d84c3-104">El <xref:System.Windows.Controls.DockPanel> particiones espacio disponible en sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d84c3-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d84c3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d84c3-105">Example</span></span>  
 <span data-ttu-id="d84c3-106">Este ejemplo se utiliza la <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad, que es una propiedad adjunta para acoplar dos idénticos <xref:System.Windows.Controls.Border> elementos en la <xref:System.Windows.Controls.Dock.Top> del espacio con particiones.</span><span class="sxs-lookup"><span data-stu-id="d84c3-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="d84c3-107">Una tercera <xref:System.Windows.Controls.Border> el elemento se acopla a la <xref:System.Windows.Controls.Dock.Left>, con su ancho establecido en 200 píxeles.</span><span class="sxs-lookup"><span data-stu-id="d84c3-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="d84c3-108">Un cuarto <xref:System.Windows.Controls.Border> está acoplada a la <xref:System.Windows.Controls.Dock.Bottom> de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="d84c3-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="d84c3-109">La última <xref:System.Windows.Controls.Border> elemento rellena automáticamente el espacio restante.</span><span class="sxs-lookup"><span data-stu-id="d84c3-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="d84c3-110">De forma predeterminada, el último elemento secundario de un <xref:System.Windows.Controls.DockPanel> elemento rellena el espacio sin asignar restantes.</span><span class="sxs-lookup"><span data-stu-id="d84c3-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="d84c3-111">Si no desea este comportamiento, establezca `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="d84c3-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="d84c3-112">La aplicación compilada genera una nueva interfaz de usuario que tiene esta apariencia.</span><span class="sxs-lookup"><span data-stu-id="d84c3-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="d84c3-113">![Escenario DockPanel típico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="d84c3-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84c3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d84c3-114">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="d84c3-115">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="d84c3-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
