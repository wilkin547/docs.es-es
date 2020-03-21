---
title: 'Cómo: Situar una información sobre herramientas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 0f52703e4fe127daa40f220280f084b2026580cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186951"
---
# <a name="how-to-position-a-tooltip"></a>Cómo: Situar una información sobre herramientas
En este ejemplo se muestra cómo especificar la posición de una información sobre herramientas en la pantalla.  
  
## <a name="example"></a>Ejemplo  
 Puede colocar una información sobre herramientas mediante un conjunto <xref:System.Windows.Controls.ToolTip> de <xref:System.Windows.Controls.ToolTipService> cinco propiedades que se definen en las clases y. En la tabla siguiente se muestran estos dos conjuntos de cinco propiedades y se proporcionan vínculos a su documentación de referencia según la clase.  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a>Propiedades de información sobre herramientas correspondientes según la clase  
  
|<xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>propiedades de clase|<xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>propiedades de clase|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 Si define el contenido de una <xref:System.Windows.Controls.ToolTip> información sobre herramientas mediante un objeto, puede utilizar las propiedades de cualquiera de las clases; sin <xref:System.Windows.Controls.ToolTipService> embargo, las propiedades tienen prioridad. Utilice <xref:System.Windows.Controls.ToolTipService> las propiedades de información sobre <xref:System.Windows.Controls.ToolTip> herramientas que no están definidas como objetos.  
  
 En las ilustraciones siguientes se muestra cómo colocar una información sobre herramientas mediante estas propiedades. Aunque, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] los ejemplos de estas ilustraciones muestran cómo <xref:System.Windows.Controls.ToolTip> establecer las propiedades definidas <xref:System.Windows.Controls.ToolTipService> por la clase, las propiedades correspondientes de la clase siguen las mismas reglas de diseño. Para obtener más información acerca de los valores posibles para la propiedad Placement, vea Comportamiento de [ubicación emergente](popup-placement-behavior.md).  

 La siguiente imagen muestra la colocación de información sobre herramientas mediante la propiedad Placement:  
  
 ![Diagrama que muestra la colocación de información sobre herramientas mediante el Placement propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 La siguiente imagen muestra la colocación de información sobre herramientas mediante las propiedades Placement y PlacementRectangle:

 ![Diagrama que muestra la información sobre herramientas de colocación mediante un PlacementRectangle propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 La siguiente imagen muestra la colocación de información sobre herramientas mediante las propiedades Placement, PlacementRectangle y Offset:
  
 ![Diagrama que muestra la colocación de información sobre herramientas mediante el Desplazamiento propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 En el ejemplo siguiente <xref:System.Windows.Controls.ToolTip> se muestra cómo utilizar las propiedades <xref:System.Windows.Controls.ToolTip> para especificar la posición de una información sobre herramientas cuyo contenido es un objeto.  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.ToolTipService> se muestra cómo utilizar las propiedades para <xref:System.Windows.Controls.ToolTip> especificar la posición de una información sobre herramientas cuyo contenido no es un objeto.  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Temas de información](tooltip-how-to-topics.md)
- [Información general de información sobre herramientas](tooltip-overview.md)
