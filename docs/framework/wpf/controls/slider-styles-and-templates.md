---
title: Estilos y plantillas de Slider
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ffbc5d2aa6e401dffb06f1695a5299a99ef90a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="c49b3-102">Estilos y plantillas de Slider</span><span class="sxs-lookup"><span data-stu-id="c49b3-102">Slider Styles and Templates</span></span>
<span data-ttu-id="c49b3-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Slider> control.</span><span class="sxs-lookup"><span data-stu-id="c49b3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="c49b3-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="c49b3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c49b3-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="c49b3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="c49b3-106">Elementos de control deslizante</span><span class="sxs-lookup"><span data-stu-id="c49b3-106">Slider Parts</span></span>  
 <span data-ttu-id="c49b3-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Slider> control.</span><span class="sxs-lookup"><span data-stu-id="c49b3-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="c49b3-108">Parte</span><span class="sxs-lookup"><span data-stu-id="c49b3-108">Part</span></span>|<span data-ttu-id="c49b3-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="c49b3-109">Type</span></span>|<span data-ttu-id="c49b3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c49b3-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c49b3-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="c49b3-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="c49b3-112">El contenedor para el elemento que indica la posición de la <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="c49b3-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="c49b3-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="c49b3-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c49b3-114">El elemento que muestra un intervalo de selección a lo largo de la <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="c49b3-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="c49b3-115">El intervalo de selección esté visible solo si la <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> propiedad es `true`.</span><span class="sxs-lookup"><span data-stu-id="c49b3-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="c49b3-116">Estados de control deslizante</span><span class="sxs-lookup"><span data-stu-id="c49b3-116">Slider States</span></span>  
 <span data-ttu-id="c49b3-117">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Slider> control.</span><span class="sxs-lookup"><span data-stu-id="c49b3-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="c49b3-118">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="c49b3-118">VisualState Name</span></span>|<span data-ttu-id="c49b3-119">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="c49b3-119">VisualStateGroup Name</span></span>|<span data-ttu-id="c49b3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c49b3-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="c49b3-121">Normal</span><span class="sxs-lookup"><span data-stu-id="c49b3-121">Normal</span></span>|<span data-ttu-id="c49b3-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-122">CommonStates</span></span>|<span data-ttu-id="c49b3-123">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c49b3-123">The default state.</span></span>|  
|<span data-ttu-id="c49b3-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c49b3-124">MouseOver</span></span>|<span data-ttu-id="c49b3-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-125">CommonStates</span></span>|<span data-ttu-id="c49b3-126">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="c49b3-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="c49b3-127">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="c49b3-127">Disabled</span></span>|<span data-ttu-id="c49b3-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-128">CommonStates</span></span>|<span data-ttu-id="c49b3-129">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="c49b3-129">The control is disabled.</span></span>|  
|<span data-ttu-id="c49b3-130">Con foco</span><span class="sxs-lookup"><span data-stu-id="c49b3-130">Focused</span></span>|<span data-ttu-id="c49b3-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-131">FocusStates</span></span>|<span data-ttu-id="c49b3-132">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c49b3-132">The control has focus.</span></span>|  
|<span data-ttu-id="c49b3-133">Sin foco</span><span class="sxs-lookup"><span data-stu-id="c49b3-133">Unfocused</span></span>|<span data-ttu-id="c49b3-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-134">FocusStates</span></span>|<span data-ttu-id="c49b3-135">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c49b3-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="c49b3-136">Válido</span><span class="sxs-lookup"><span data-stu-id="c49b3-136">Valid</span></span>|<span data-ttu-id="c49b3-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-137">ValidationStates</span></span>|<span data-ttu-id="c49b3-138">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="c49b3-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c49b3-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c49b3-139">InvalidFocused</span></span>|<span data-ttu-id="c49b3-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-140">ValidationStates</span></span>|<span data-ttu-id="c49b3-141">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c49b3-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c49b3-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c49b3-142">InvalidUnfocused</span></span>|<span data-ttu-id="c49b3-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c49b3-143">ValidationStates</span></span>|<span data-ttu-id="c49b3-144">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c49b3-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="c49b3-145">Ejemplo de ControlTemplate de control deslizante</span><span class="sxs-lookup"><span data-stu-id="c49b3-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="c49b3-146">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Slider> control.</span><span class="sxs-lookup"><span data-stu-id="c49b3-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="c49b3-147">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c49b3-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c49b3-148">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="c49b3-148">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49b3-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="c49b3-149">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="c49b3-150">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="c49b3-150">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="c49b3-151">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="c49b3-151">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="c49b3-152">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="c49b3-152">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="c49b3-153">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="c49b3-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
