---
title: Estilos y plantillas de RadioButton
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05b5f2124e6d8817b03171af5308c116e9339ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="a2904-102">Estilos y plantillas de RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2904-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="a2904-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.RadioButton> control.</span><span class="sxs-lookup"><span data-stu-id="a2904-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="a2904-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="a2904-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a2904-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="a2904-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="a2904-106">Partes de RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2904-106">RadioButton Parts</span></span>  
 <span data-ttu-id="a2904-107">El <xref:System.Windows.Controls.RadioButton> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="a2904-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="a2904-108">Estados de RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2904-108">RadioButton States</span></span>  
 <span data-ttu-id="a2904-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.RadioButton> control.</span><span class="sxs-lookup"><span data-stu-id="a2904-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="a2904-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="a2904-110">VisualState Name</span></span>|<span data-ttu-id="a2904-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a2904-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a2904-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2904-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a2904-113">Normal</span><span class="sxs-lookup"><span data-stu-id="a2904-113">Normal</span></span>|<span data-ttu-id="a2904-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2904-114">CommonStates</span></span>|<span data-ttu-id="a2904-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a2904-115">The default state.</span></span>|  
|<span data-ttu-id="a2904-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="a2904-116">MouseOver</span></span>|<span data-ttu-id="a2904-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2904-117">CommonStates</span></span>|<span data-ttu-id="a2904-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="a2904-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="a2904-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="a2904-119">Pressed</span></span>|<span data-ttu-id="a2904-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2904-120">CommonStates</span></span>|<span data-ttu-id="a2904-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="a2904-121">The control is pressed.</span></span>|  
|<span data-ttu-id="a2904-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="a2904-122">Disabled</span></span>|<span data-ttu-id="a2904-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a2904-123">CommonStates</span></span>|<span data-ttu-id="a2904-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a2904-124">The control is disabled.</span></span>|  
|<span data-ttu-id="a2904-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="a2904-125">Focused</span></span>|<span data-ttu-id="a2904-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a2904-126">FocusStates</span></span>|<span data-ttu-id="a2904-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a2904-127">The control has focus.</span></span>|  
|<span data-ttu-id="a2904-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="a2904-128">Unfocused</span></span>|<span data-ttu-id="a2904-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="a2904-129">FocusStates</span></span>|<span data-ttu-id="a2904-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a2904-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="a2904-131">Activado</span><span class="sxs-lookup"><span data-stu-id="a2904-131">Checked</span></span>|<span data-ttu-id="a2904-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a2904-132">CheckStates</span></span>|<span data-ttu-id="a2904-133">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="a2904-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="a2904-134">No está activada</span><span class="sxs-lookup"><span data-stu-id="a2904-134">Unchecked</span></span>|<span data-ttu-id="a2904-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a2904-135">CheckStates</span></span>|<span data-ttu-id="a2904-136">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="a2904-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="a2904-137">Indeterminado</span><span class="sxs-lookup"><span data-stu-id="a2904-137">Indeterminate</span></span>|<span data-ttu-id="a2904-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="a2904-138">CheckStates</span></span>|<span data-ttu-id="a2904-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span><span class="sxs-lookup"><span data-stu-id="a2904-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="a2904-140">Válido</span><span class="sxs-lookup"><span data-stu-id="a2904-140">Valid</span></span>|<span data-ttu-id="a2904-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2904-141">ValidationStates</span></span>|<span data-ttu-id="a2904-142">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="a2904-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a2904-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a2904-143">InvalidFocused</span></span>|<span data-ttu-id="a2904-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2904-144">ValidationStates</span></span>|<span data-ttu-id="a2904-145">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a2904-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a2904-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a2904-146">InvalidUnfocused</span></span>|<span data-ttu-id="a2904-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a2904-147">ValidationStates</span></span>|<span data-ttu-id="a2904-148">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a2904-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="a2904-149">Ejemplo de ControlTemplate de RadioButton</span><span class="sxs-lookup"><span data-stu-id="a2904-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="a2904-150">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.RadioButton> control.</span><span class="sxs-lookup"><span data-stu-id="a2904-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="a2904-151">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a2904-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a2904-152">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a2904-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2904-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2904-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a2904-154">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="a2904-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="a2904-155">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="a2904-155">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="a2904-156">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a2904-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a2904-157">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a2904-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
