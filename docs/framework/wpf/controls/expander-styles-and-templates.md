---
title: Estilos y plantillas de Expander
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Expander
- ControlTemplate [WPF], Expander
- templates [WPF], Expander
- Expander [WPF], styles and templates
- states [WPF], Expander
- parts [WPF], Expander
ms.assetid: da2e5a1c-5230-4c21-98a5-59c7895facd7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 04225458e9889c511b7aaa359239512e316cbb26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="expander-styles-and-templates"></a><span data-ttu-id="9f34b-102">Estilos y plantillas de Expander</span><span class="sxs-lookup"><span data-stu-id="9f34b-102">Expander Styles and Templates</span></span>
<span data-ttu-id="9f34b-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Expander> control.</span><span class="sxs-lookup"><span data-stu-id="9f34b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Expander> control.</span></span> <span data-ttu-id="9f34b-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="9f34b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9f34b-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="9f34b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="expander-parts"></a><span data-ttu-id="9f34b-106">Partes de Expander</span><span class="sxs-lookup"><span data-stu-id="9f34b-106">Expander Parts</span></span>  
 <span data-ttu-id="9f34b-107">El <xref:System.Windows.Controls.Expander> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="9f34b-107">The <xref:System.Windows.Controls.Expander> control does not have any named parts.</span></span>  
  
## <a name="expander-states"></a><span data-ttu-id="9f34b-108">Estados de Expander</span><span class="sxs-lookup"><span data-stu-id="9f34b-108">Expander States</span></span>  
 <span data-ttu-id="9f34b-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Expander> control.</span><span class="sxs-lookup"><span data-stu-id="9f34b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
|<span data-ttu-id="9f34b-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="9f34b-110">VisualState Name</span></span>|<span data-ttu-id="9f34b-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="9f34b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9f34b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f34b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f34b-113">Normal</span><span class="sxs-lookup"><span data-stu-id="9f34b-113">Normal</span></span>|<span data-ttu-id="9f34b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-114">CommonStates</span></span>|<span data-ttu-id="9f34b-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9f34b-115">The default state.</span></span>|  
|<span data-ttu-id="9f34b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9f34b-116">MouseOver</span></span>|<span data-ttu-id="9f34b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-117">CommonStates</span></span>|<span data-ttu-id="9f34b-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="9f34b-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="9f34b-119">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="9f34b-119">Disabled</span></span>|<span data-ttu-id="9f34b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-120">CommonStates</span></span>|<span data-ttu-id="9f34b-121">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="9f34b-121">The control is disabled.</span></span>|  
|<span data-ttu-id="9f34b-122">Con foco</span><span class="sxs-lookup"><span data-stu-id="9f34b-122">Focused</span></span>|<span data-ttu-id="9f34b-123">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-123">FocusStates</span></span>|<span data-ttu-id="9f34b-124">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f34b-124">The control has focus.</span></span>|  
|<span data-ttu-id="9f34b-125">Sin foco</span><span class="sxs-lookup"><span data-stu-id="9f34b-125">Unfocused</span></span>|<span data-ttu-id="9f34b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-126">FocusStates</span></span>|<span data-ttu-id="9f34b-127">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f34b-127">The control does not have focus.</span></span>|  
|<span data-ttu-id="9f34b-128">Expandido</span><span class="sxs-lookup"><span data-stu-id="9f34b-128">Expanded</span></span>|<span data-ttu-id="9f34b-129">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-129">ExpansionStates</span></span>|<span data-ttu-id="9f34b-130">El control está expandido.</span><span class="sxs-lookup"><span data-stu-id="9f34b-130">The control is expanded.</span></span>|  
|<span data-ttu-id="9f34b-131">Collapsed</span><span class="sxs-lookup"><span data-stu-id="9f34b-131">Collapsed</span></span>|<span data-ttu-id="9f34b-132">ExpansionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-132">ExpansionStates</span></span>|<span data-ttu-id="9f34b-133">El control no está expandido.</span><span class="sxs-lookup"><span data-stu-id="9f34b-133">The control is not expanded.</span></span>|  
|<span data-ttu-id="9f34b-134">ExpandDown</span><span class="sxs-lookup"><span data-stu-id="9f34b-134">ExpandDown</span></span>|<span data-ttu-id="9f34b-135">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-135">ExpandDirectionStates</span></span>|<span data-ttu-id="9f34b-136">El control se expande hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="9f34b-136">The control expands down.</span></span>|  
|<span data-ttu-id="9f34b-137">ExpandUp</span><span class="sxs-lookup"><span data-stu-id="9f34b-137">ExpandUp</span></span>|<span data-ttu-id="9f34b-138">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-138">ExpandDirectionStates</span></span>|<span data-ttu-id="9f34b-139">El control se expande una.</span><span class="sxs-lookup"><span data-stu-id="9f34b-139">The control expands up.</span></span>|  
|<span data-ttu-id="9f34b-140">ExpandLeft</span><span class="sxs-lookup"><span data-stu-id="9f34b-140">ExpandLeft</span></span>|<span data-ttu-id="9f34b-141">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-141">ExpandDirectionStates</span></span>|<span data-ttu-id="9f34b-142">El control se expande izquierda.</span><span class="sxs-lookup"><span data-stu-id="9f34b-142">The control expands left.</span></span>|  
|<span data-ttu-id="9f34b-143">ExpandRight</span><span class="sxs-lookup"><span data-stu-id="9f34b-143">ExpandRight</span></span>|<span data-ttu-id="9f34b-144">ExpandDirectionStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-144">ExpandDirectionStates</span></span>|<span data-ttu-id="9f34b-145">El control se expande derecha.</span><span class="sxs-lookup"><span data-stu-id="9f34b-145">The control expands right.</span></span>|  
|<span data-ttu-id="9f34b-146">Válido</span><span class="sxs-lookup"><span data-stu-id="9f34b-146">Valid</span></span>|<span data-ttu-id="9f34b-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-147">ValidationStates</span></span>|<span data-ttu-id="9f34b-148">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="9f34b-148">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9f34b-149">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9f34b-149">InvalidFocused</span></span>|<span data-ttu-id="9f34b-150">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-150">ValidationStates</span></span>|<span data-ttu-id="9f34b-151">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f34b-151">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9f34b-152">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9f34b-152">InvalidUnfocused</span></span>|<span data-ttu-id="9f34b-153">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f34b-153">ValidationStates</span></span>|<span data-ttu-id="9f34b-154">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f34b-154">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="expander-controltemplate-example"></a><span data-ttu-id="9f34b-155">Ejemplo de ControlTemplate de Expander</span><span class="sxs-lookup"><span data-stu-id="9f34b-155">Expander ControlTemplate Example</span></span>  
 <span data-ttu-id="9f34b-156">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Expander> control.</span><span class="sxs-lookup"><span data-stu-id="9f34b-156">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Expander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/expander.xaml#expander)]  
  
 <span data-ttu-id="9f34b-157">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="9f34b-157">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9f34b-158">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="9f34b-158">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f34b-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f34b-159">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="9f34b-160">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="9f34b-160">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="9f34b-161">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="9f34b-161">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="9f34b-162">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="9f34b-162">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="9f34b-163">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9f34b-163">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
