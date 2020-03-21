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
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="f925b-102">Cómo: Situar una información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="f925b-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="f925b-103">En este ejemplo se muestra cómo especificar la posición de una información sobre herramientas en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f925b-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f925b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f925b-104">Example</span></span>  
 <span data-ttu-id="f925b-105">Puede colocar una información sobre herramientas mediante un conjunto <xref:System.Windows.Controls.ToolTip> de <xref:System.Windows.Controls.ToolTipService> cinco propiedades que se definen en las clases y.</span><span class="sxs-lookup"><span data-stu-id="f925b-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="f925b-106">En la tabla siguiente se muestran estos dos conjuntos de cinco propiedades y se proporcionan vínculos a su documentación de referencia según la clase.</span><span class="sxs-lookup"><span data-stu-id="f925b-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="f925b-107">Propiedades de información sobre herramientas correspondientes según la clase</span><span class="sxs-lookup"><span data-stu-id="f925b-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="f925b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>propiedades de clase</span><span class="sxs-lookup"><span data-stu-id="f925b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="f925b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>propiedades de clase</span><span class="sxs-lookup"><span data-stu-id="f925b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="f925b-110">Si define el contenido de una <xref:System.Windows.Controls.ToolTip> información sobre herramientas mediante un objeto, puede utilizar las propiedades de cualquiera de las clases; sin <xref:System.Windows.Controls.ToolTipService> embargo, las propiedades tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="f925b-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="f925b-111">Utilice <xref:System.Windows.Controls.ToolTipService> las propiedades de información sobre <xref:System.Windows.Controls.ToolTip> herramientas que no están definidas como objetos.</span><span class="sxs-lookup"><span data-stu-id="f925b-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="f925b-112">En las ilustraciones siguientes se muestra cómo colocar una información sobre herramientas mediante estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="f925b-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="f925b-113">Aunque, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] los ejemplos de estas ilustraciones muestran cómo <xref:System.Windows.Controls.ToolTip> establecer las propiedades definidas <xref:System.Windows.Controls.ToolTipService> por la clase, las propiedades correspondientes de la clase siguen las mismas reglas de diseño.</span><span class="sxs-lookup"><span data-stu-id="f925b-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="f925b-114">Para obtener más información acerca de los valores posibles para la propiedad Placement, vea Comportamiento de [ubicación emergente](popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="f925b-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="f925b-115">La siguiente imagen muestra la colocación de información sobre herramientas mediante la propiedad Placement:</span><span class="sxs-lookup"><span data-stu-id="f925b-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Diagrama que muestra la colocación de información sobre herramientas mediante el Placement propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="f925b-117">La siguiente imagen muestra la colocación de información sobre herramientas mediante las propiedades Placement y PlacementRectangle:</span><span class="sxs-lookup"><span data-stu-id="f925b-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![Diagrama que muestra la información sobre herramientas de colocación mediante un PlacementRectangle propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="f925b-119">La siguiente imagen muestra la colocación de información sobre herramientas mediante las propiedades Placement, PlacementRectangle y Offset:</span><span class="sxs-lookup"><span data-stu-id="f925b-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Diagrama que muestra la colocación de información sobre herramientas mediante el Desplazamiento propiedad.](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="f925b-121">En el ejemplo siguiente <xref:System.Windows.Controls.ToolTip> se muestra cómo utilizar las propiedades <xref:System.Windows.Controls.ToolTip> para especificar la posición de una información sobre herramientas cuyo contenido es un objeto.</span><span class="sxs-lookup"><span data-stu-id="f925b-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="f925b-122">En el ejemplo siguiente <xref:System.Windows.Controls.ToolTipService> se muestra cómo utilizar las propiedades para <xref:System.Windows.Controls.ToolTip> especificar la posición de una información sobre herramientas cuyo contenido no es un objeto.</span><span class="sxs-lookup"><span data-stu-id="f925b-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="f925b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f925b-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="f925b-124">Temas de información</span><span class="sxs-lookup"><span data-stu-id="f925b-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="f925b-125">Información general de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="f925b-125">ToolTip Overview</span></span>](tooltip-overview.md)
