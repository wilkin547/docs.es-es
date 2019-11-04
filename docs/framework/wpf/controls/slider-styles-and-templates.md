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
ms.openlocfilehash: 334cb4a44788980262110eadac3305283bb61a92
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458392"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="af65e-102">Estilos y plantillas de Slider</span><span class="sxs-lookup"><span data-stu-id="af65e-102">Slider Styles and Templates</span></span>
<span data-ttu-id="af65e-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="af65e-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="af65e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="af65e-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="af65e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="af65e-106">Elementos deslizantes</span><span class="sxs-lookup"><span data-stu-id="af65e-106">Slider Parts</span></span>  
 <span data-ttu-id="af65e-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="af65e-108">Parte</span><span class="sxs-lookup"><span data-stu-id="af65e-108">Part</span></span>|<span data-ttu-id="af65e-109">Type</span><span class="sxs-lookup"><span data-stu-id="af65e-109">Type</span></span>|<span data-ttu-id="af65e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="af65e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="af65e-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="af65e-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="af65e-112">Contenedor del elemento que indica la posición del <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="af65e-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="af65e-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="af65e-114">Elemento que muestra un intervalo de selección a lo largo del <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="af65e-115">El intervalo de selección solo es visible si la propiedad <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="af65e-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="af65e-116">Estados de control deslizante</span><span class="sxs-lookup"><span data-stu-id="af65e-116">Slider States</span></span>  
 <span data-ttu-id="af65e-117">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="af65e-118">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="af65e-118">VisualState Name</span></span>|<span data-ttu-id="af65e-119">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="af65e-119">VisualStateGroup Name</span></span>|<span data-ttu-id="af65e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="af65e-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="af65e-121">Normal</span><span class="sxs-lookup"><span data-stu-id="af65e-121">Normal</span></span>|<span data-ttu-id="af65e-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="af65e-122">CommonStates</span></span>|<span data-ttu-id="af65e-123">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="af65e-123">The default state.</span></span>|  
|<span data-ttu-id="af65e-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="af65e-124">MouseOver</span></span>|<span data-ttu-id="af65e-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="af65e-125">CommonStates</span></span>|<span data-ttu-id="af65e-126">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="af65e-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="af65e-127">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="af65e-127">Disabled</span></span>|<span data-ttu-id="af65e-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="af65e-128">CommonStates</span></span>|<span data-ttu-id="af65e-129">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="af65e-129">The control is disabled.</span></span>|  
|<span data-ttu-id="af65e-130">Con foco</span><span class="sxs-lookup"><span data-stu-id="af65e-130">Focused</span></span>|<span data-ttu-id="af65e-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="af65e-131">FocusStates</span></span>|<span data-ttu-id="af65e-132">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="af65e-132">The control has focus.</span></span>|  
|<span data-ttu-id="af65e-133">Sin foco</span><span class="sxs-lookup"><span data-stu-id="af65e-133">Unfocused</span></span>|<span data-ttu-id="af65e-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="af65e-134">FocusStates</span></span>|<span data-ttu-id="af65e-135">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="af65e-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="af65e-136">Válido</span><span class="sxs-lookup"><span data-stu-id="af65e-136">Valid</span></span>|<span data-ttu-id="af65e-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="af65e-137">ValidationStates</span></span>|<span data-ttu-id="af65e-138">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="af65e-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="af65e-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="af65e-139">InvalidFocused</span></span>|<span data-ttu-id="af65e-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="af65e-140">ValidationStates</span></span>|<span data-ttu-id="af65e-141">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="af65e-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="af65e-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="af65e-142">InvalidUnfocused</span></span>|<span data-ttu-id="af65e-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="af65e-143">ValidationStates</span></span>|<span data-ttu-id="af65e-144">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="af65e-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="af65e-145">Ejemplo de ControlTemplate de slider</span><span class="sxs-lookup"><span data-stu-id="af65e-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="af65e-146">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="af65e-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="af65e-147">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="af65e-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="af65e-148">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="af65e-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af65e-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="af65e-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="af65e-150">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="af65e-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="af65e-151">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="af65e-151">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="af65e-152">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="af65e-152">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="af65e-153">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="af65e-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
