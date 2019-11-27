---
title: Estilos y plantillas de ToolTip
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: c7a14034d665c124d01e8a4b43c5d42968241925
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283645"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="1535f-102">Estilos y plantillas de ToolTip</span><span class="sxs-lookup"><span data-stu-id="1535f-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="1535f-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="1535f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="1535f-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="1535f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1535f-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="1535f-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="1535f-106">Elementos de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="1535f-106">ToolTip Parts</span></span>  
 <span data-ttu-id="1535f-107">El control <xref:System.Windows.Controls.ToolTip> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="1535f-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="1535f-108">Estados de la información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="1535f-108">ToolTip States</span></span>  
 <span data-ttu-id="1535f-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="1535f-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="1535f-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="1535f-110">VisualState Name</span></span>|<span data-ttu-id="1535f-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1535f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="1535f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1535f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1535f-113">Cerrado</span><span class="sxs-lookup"><span data-stu-id="1535f-113">Closed</span></span>|<span data-ttu-id="1535f-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="1535f-114">OpenStates</span></span>|<span data-ttu-id="1535f-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1535f-115">The default state.</span></span>|  
|<span data-ttu-id="1535f-116">Abrir</span><span class="sxs-lookup"><span data-stu-id="1535f-116">Open</span></span>|<span data-ttu-id="1535f-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="1535f-117">OpenStates</span></span>|<span data-ttu-id="1535f-118">El <xref:System.Windows.Controls.ToolTip> es visible.</span><span class="sxs-lookup"><span data-stu-id="1535f-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="1535f-119">Válido</span><span class="sxs-lookup"><span data-stu-id="1535f-119">Valid</span></span>|<span data-ttu-id="1535f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1535f-120">ValidationStates</span></span>|<span data-ttu-id="1535f-121">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="1535f-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1535f-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1535f-122">InvalidFocused</span></span>|<span data-ttu-id="1535f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1535f-123">ValidationStates</span></span>|<span data-ttu-id="1535f-124">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1535f-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1535f-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1535f-125">InvalidUnfocused</span></span>|<span data-ttu-id="1535f-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1535f-126">ValidationStates</span></span>|<span data-ttu-id="1535f-127">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1535f-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="1535f-128">Ejemplo de ControlTemplate de ToolTip</span><span class="sxs-lookup"><span data-stu-id="1535f-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="1535f-129">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="1535f-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="1535f-130">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1535f-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1535f-131">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1535f-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1535f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1535f-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1535f-133">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="1535f-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="1535f-134">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="1535f-134">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="1535f-135">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="1535f-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1535f-136">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="1535f-136">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
