---
title: Estilos y plantillas de Slider
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: f533142d5ba202bd4aaf628487eaaa2a18a535d0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283385"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="48ed9-102">Estilos y plantillas de Slider</span><span class="sxs-lookup"><span data-stu-id="48ed9-102">Slider Styles and Templates</span></span>
<span data-ttu-id="48ed9-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="48ed9-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="48ed9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="48ed9-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="48ed9-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="48ed9-106">Elementos deslizantes</span><span class="sxs-lookup"><span data-stu-id="48ed9-106">Slider Parts</span></span>  
 <span data-ttu-id="48ed9-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="48ed9-108">Parte</span><span class="sxs-lookup"><span data-stu-id="48ed9-108">Part</span></span>|<span data-ttu-id="48ed9-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="48ed9-109">Type</span></span>|<span data-ttu-id="48ed9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="48ed9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="48ed9-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="48ed9-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="48ed9-112">Contenedor del elemento que indica la posición del <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="48ed9-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="48ed9-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="48ed9-114">Elemento que muestra un intervalo de selección a lo largo del <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="48ed9-115">El intervalo de selección solo es visible si la propiedad <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="48ed9-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="48ed9-116">Estados de control deslizante</span><span class="sxs-lookup"><span data-stu-id="48ed9-116">Slider States</span></span>  
 <span data-ttu-id="48ed9-117">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="48ed9-118">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="48ed9-118">VisualState Name</span></span>|<span data-ttu-id="48ed9-119">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="48ed9-119">VisualStateGroup Name</span></span>|<span data-ttu-id="48ed9-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="48ed9-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="48ed9-121">Normal</span><span class="sxs-lookup"><span data-stu-id="48ed9-121">Normal</span></span>|<span data-ttu-id="48ed9-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-122">CommonStates</span></span>|<span data-ttu-id="48ed9-123">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="48ed9-123">The default state.</span></span>|  
|<span data-ttu-id="48ed9-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="48ed9-124">MouseOver</span></span>|<span data-ttu-id="48ed9-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-125">CommonStates</span></span>|<span data-ttu-id="48ed9-126">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="48ed9-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="48ed9-127">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="48ed9-127">Disabled</span></span>|<span data-ttu-id="48ed9-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-128">CommonStates</span></span>|<span data-ttu-id="48ed9-129">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="48ed9-129">The control is disabled.</span></span>|  
|<span data-ttu-id="48ed9-130">Con foco</span><span class="sxs-lookup"><span data-stu-id="48ed9-130">Focused</span></span>|<span data-ttu-id="48ed9-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-131">FocusStates</span></span>|<span data-ttu-id="48ed9-132">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="48ed9-132">The control has focus.</span></span>|  
|<span data-ttu-id="48ed9-133">Sin foco</span><span class="sxs-lookup"><span data-stu-id="48ed9-133">Unfocused</span></span>|<span data-ttu-id="48ed9-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-134">FocusStates</span></span>|<span data-ttu-id="48ed9-135">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="48ed9-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="48ed9-136">Válido</span><span class="sxs-lookup"><span data-stu-id="48ed9-136">Valid</span></span>|<span data-ttu-id="48ed9-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-137">ValidationStates</span></span>|<span data-ttu-id="48ed9-138">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="48ed9-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="48ed9-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="48ed9-139">InvalidFocused</span></span>|<span data-ttu-id="48ed9-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-140">ValidationStates</span></span>|<span data-ttu-id="48ed9-141">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="48ed9-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="48ed9-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="48ed9-142">InvalidUnfocused</span></span>|<span data-ttu-id="48ed9-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="48ed9-143">ValidationStates</span></span>|<span data-ttu-id="48ed9-144">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="48ed9-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="48ed9-145">Ejemplo de ControlTemplate de slider</span><span class="sxs-lookup"><span data-stu-id="48ed9-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="48ed9-146">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="48ed9-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="48ed9-147">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="48ed9-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="48ed9-148">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="48ed9-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ed9-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="48ed9-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="48ed9-150">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="48ed9-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="48ed9-151">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="48ed9-151">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="48ed9-152">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="48ed9-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="48ed9-153">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="48ed9-153">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
