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
ms.openlocfilehash: 9b87c5c80533e12f5a93e4fc59cb5265a8374a33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521964"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="55e55-102">Estilos y plantillas de ToolTip</span><span class="sxs-lookup"><span data-stu-id="55e55-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="55e55-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="55e55-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="55e55-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="55e55-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="55e55-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="55e55-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="55e55-106">Partes de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="55e55-106">ToolTip Parts</span></span>  
 <span data-ttu-id="55e55-107">El <xref:System.Windows.Controls.ToolTip> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="55e55-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="55e55-108">Estados de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="55e55-108">ToolTip States</span></span>  
 <span data-ttu-id="55e55-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="55e55-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="55e55-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="55e55-110">VisualState Name</span></span>|<span data-ttu-id="55e55-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="55e55-111">VisualStateGroup Name</span></span>|<span data-ttu-id="55e55-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="55e55-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="55e55-113">Cerrado</span><span class="sxs-lookup"><span data-stu-id="55e55-113">Closed</span></span>|<span data-ttu-id="55e55-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="55e55-114">OpenStates</span></span>|<span data-ttu-id="55e55-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="55e55-115">The default state.</span></span>|  
|<span data-ttu-id="55e55-116">Abrir</span><span class="sxs-lookup"><span data-stu-id="55e55-116">Open</span></span>|<span data-ttu-id="55e55-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="55e55-117">OpenStates</span></span>|<span data-ttu-id="55e55-118">El <xref:System.Windows.Controls.ToolTip> está visible.</span><span class="sxs-lookup"><span data-stu-id="55e55-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="55e55-119">Válido</span><span class="sxs-lookup"><span data-stu-id="55e55-119">Valid</span></span>|<span data-ttu-id="55e55-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="55e55-120">ValidationStates</span></span>|<span data-ttu-id="55e55-121">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="55e55-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="55e55-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="55e55-122">InvalidFocused</span></span>|<span data-ttu-id="55e55-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="55e55-123">ValidationStates</span></span>|<span data-ttu-id="55e55-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="55e55-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="55e55-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="55e55-125">InvalidUnfocused</span></span>|<span data-ttu-id="55e55-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="55e55-126">ValidationStates</span></span>|<span data-ttu-id="55e55-127">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="55e55-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="55e55-128">Ejemplo de ControlTemplate de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="55e55-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="55e55-129">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="55e55-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="55e55-130">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="55e55-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="55e55-131">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="55e55-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e55-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="55e55-132">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="55e55-133">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="55e55-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- <span data-ttu-id="55e55-134">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="55e55-134">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>
- [<span data-ttu-id="55e55-135">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="55e55-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="55e55-136">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="55e55-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
