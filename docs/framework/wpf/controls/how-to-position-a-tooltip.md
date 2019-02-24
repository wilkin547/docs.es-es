---
title: Filtrar Situar una información sobre herramientas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 985c9b7737d979937837d7184f9b96f226ec73c3
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746920"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="0241b-102">Procedimiento Situar una información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="0241b-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="0241b-103">En este ejemplo se muestra cómo especificar la posición de una información sobre herramientas en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0241b-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0241b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0241b-104">Example</span></span>  
 <span data-ttu-id="0241b-105">Puede colocar una información sobre herramientas mediante el uso de un conjunto de cinco propiedades que se definen tanto en el <xref:System.Windows.Controls.ToolTip> y <xref:System.Windows.Controls.ToolTipService> clases.</span><span class="sxs-lookup"><span data-stu-id="0241b-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="0241b-106">En la tabla siguiente se muestra estos dos conjuntos de cinco propiedades y proporciona vínculos a documentación de referencia según la clase.</span><span class="sxs-lookup"><span data-stu-id="0241b-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="0241b-107">Propiedades de información sobre herramientas correspondiente según la clase</span><span class="sxs-lookup"><span data-stu-id="0241b-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="0241b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> propiedades de la clase</span><span class="sxs-lookup"><span data-stu-id="0241b-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="0241b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> propiedades de la clase</span><span class="sxs-lookup"><span data-stu-id="0241b-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="0241b-110">Si se define el contenido de una información sobre herramientas con un <xref:System.Windows.Controls.ToolTip> objeto, puede usar las propiedades de cualquier clase; sin embargo, el <xref:System.Windows.Controls.ToolTipService> propiedades tienen prioridad.</span><span class="sxs-lookup"><span data-stu-id="0241b-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="0241b-111">Use la <xref:System.Windows.Controls.ToolTipService> las propiedades de información sobre herramientas que no estén definidas como <xref:System.Windows.Controls.ToolTip> objetos.</span><span class="sxs-lookup"><span data-stu-id="0241b-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="0241b-112">Las ilustraciones siguientes muestran cómo colocar una información sobre herramientas mediante el uso de estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="0241b-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="0241b-113">Aunque, el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos de estas ilustraciones muestran cómo establecer las propiedades definidas por el <xref:System.Windows.Controls.ToolTip> de clases, las propiedades correspondientes de la <xref:System.Windows.Controls.ToolTipService> clase siguen las mismas reglas de diseño.</span><span class="sxs-lookup"><span data-stu-id="0241b-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="0241b-114">Para obtener más información acerca de los valores posibles para la propiedad de colocación, vea [selección de ubicación de un control Popup](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="0241b-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="0241b-115">![Colocación de ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="0241b-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="0241b-116">Colocación de ToolTip mediante el uso de la propiedad de colocación</span><span class="sxs-lookup"><span data-stu-id="0241b-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="0241b-117">![Colocar ToolTip mediante el uso de un rectángulo de selección de ubicación](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="0241b-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="0241b-118">Colocación de ToolTip mediante las propiedades Placement y PlacementRectangle</span><span class="sxs-lookup"><span data-stu-id="0241b-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="0241b-119">![Diagrama de colocación de ToolTip](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="0241b-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="0241b-120">Colocación de ToolTip mediante las propiedades Placement, PlacementRectangle y desplazamiento</span><span class="sxs-lookup"><span data-stu-id="0241b-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="0241b-121">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.ToolTip> propiedades para especificar la posición de una información sobre herramientas cuyo contenido es un <xref:System.Windows.Controls.ToolTip> objeto.</span><span class="sxs-lookup"><span data-stu-id="0241b-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="0241b-122">El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Controls.ToolTipService> propiedades para especificar la posición de una información sobre herramientas cuyo contenido no es un <xref:System.Windows.Controls.ToolTip> objeto.</span><span class="sxs-lookup"><span data-stu-id="0241b-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="0241b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0241b-123">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="0241b-124">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0241b-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="0241b-125">Información general de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="0241b-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
