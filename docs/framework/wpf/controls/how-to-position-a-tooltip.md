---
title: Procedimiento Situar una información sobre herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: d20eea0890708eb2ec2ada503f5c871d54ccc035
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364542"
---
# <a name="how-to-position-a-tooltip"></a>Procedimiento Situar una información sobre herramientas
En este ejemplo se muestra cómo especificar la posición de una información sobre herramientas en la pantalla.  
  
## <a name="example"></a>Ejemplo  
 Puede colocar una información sobre herramientas mediante el uso de un conjunto de cinco propiedades que se definen tanto en el <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService> clases. En la tabla siguiente se muestra estos dos conjuntos de cinco propiedades y proporciona vínculos a documentación de referencia según la clase.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Propiedades de información sobre herramientas correspondiente según la clase  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> propiedades de la clase|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> propiedades de la clase|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Si se define el contenido de una información sobre herramientas con un <xref:System.Windows.Controls.ToolTip> objeto, puede usar las propiedades de cualquier clase; sin embargo, el <xref:System.Windows.Controls.ToolTipService> propiedades tienen prioridad. Use la <xref:System.Windows.Controls.ToolTipService> las propiedades de información sobre herramientas que no estén definidas como <xref:System.Windows.Controls.ToolTip> objetos.  
  
 Las ilustraciones siguientes muestran cómo colocar una información sobre herramientas mediante el uso de estas propiedades. Aunque, el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos de estas ilustraciones muestran cómo establecer las propiedades definidas por el <xref:System.Windows.Controls.ToolTip> de clases, las propiedades correspondientes de la <xref:System.Windows.Controls.ToolTipService> clase siguen las mismas reglas de diseño. Para obtener más información acerca de los valores posibles para la propiedad de colocación, vea [selección de ubicación de un control Popup](popup-placement-behavior.md).  
  
 ![Colocación de ToolTip](./media/tooltipplacement.png "ToolTipPlacement")  
Colocación de ToolTip mediante el uso de la propiedad de colocación  
  
 ![Colocar ToolTip mediante el uso de un rectángulo de selección de ubicación](./media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")  
Colocación de ToolTip mediante las propiedades Placement y PlacementRectangle  
  
 ![Diagrama de colocación de ToolTip](./media/tooltipplacementprhv.png "ToolTipPlacementPRHV")  
Colocación de ToolTip mediante las propiedades Placement, PlacementRectangle y desplazamiento  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.ToolTip> propiedades para especificar la posición de una información sobre herramientas cuyo contenido es un <xref:System.Windows.Controls.ToolTip> objeto.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.ToolTipService> propiedades para especificar la posición de una información sobre herramientas cuyo contenido no es un <xref:System.Windows.Controls.ToolTip> objeto.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Temas "Cómo..."](tooltip-how-to-topics.md)
- [Información general de información sobre herramientas](tooltip-overview.md)
