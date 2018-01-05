---
title: Estilos y plantillas de Thumb
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 780ddc07c79aab111c17f9e7e551cfde85c68f3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="8bd21-102">Estilos y plantillas de Thumb</span><span class="sxs-lookup"><span data-stu-id="8bd21-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="8bd21-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.Thumb> control.</span><span class="sxs-lookup"><span data-stu-id="8bd21-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="8bd21-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="8bd21-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8bd21-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="8bd21-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="8bd21-106">Elementos de control</span><span class="sxs-lookup"><span data-stu-id="8bd21-106">Thumb Parts</span></span>  
 <span data-ttu-id="8bd21-107">El <xref:System.Windows.Controls.Primitives.Thumb> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="8bd21-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="8bd21-108">Estados de posición</span><span class="sxs-lookup"><span data-stu-id="8bd21-108">Thumb States</span></span>  
 <span data-ttu-id="8bd21-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.Thumb> control.</span><span class="sxs-lookup"><span data-stu-id="8bd21-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="8bd21-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8bd21-110">VisualState Name</span></span>|<span data-ttu-id="8bd21-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8bd21-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8bd21-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bd21-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8bd21-113">Normal</span><span class="sxs-lookup"><span data-stu-id="8bd21-113">Normal</span></span>|<span data-ttu-id="8bd21-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-114">CommonStates</span></span>|<span data-ttu-id="8bd21-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8bd21-115">The default state.</span></span>|  
|<span data-ttu-id="8bd21-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8bd21-116">MouseOver</span></span>|<span data-ttu-id="8bd21-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-117">CommonStates</span></span>|<span data-ttu-id="8bd21-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="8bd21-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="8bd21-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="8bd21-119">Pressed</span></span>|<span data-ttu-id="8bd21-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-120">CommonStates</span></span>|<span data-ttu-id="8bd21-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="8bd21-121">The control is pressed.</span></span>|  
|<span data-ttu-id="8bd21-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="8bd21-122">Disabled</span></span>|<span data-ttu-id="8bd21-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-123">CommonStates</span></span>|<span data-ttu-id="8bd21-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="8bd21-124">The control is disabled.</span></span>|  
|<span data-ttu-id="8bd21-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="8bd21-125">Focused</span></span>|<span data-ttu-id="8bd21-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-126">FocusStates</span></span>|<span data-ttu-id="8bd21-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8bd21-127">The control has focus.</span></span>|  
|<span data-ttu-id="8bd21-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="8bd21-128">Unfocused</span></span>|<span data-ttu-id="8bd21-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-129">FocusStates</span></span>|<span data-ttu-id="8bd21-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8bd21-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="8bd21-131">Válido</span><span class="sxs-lookup"><span data-stu-id="8bd21-131">Valid</span></span>|<span data-ttu-id="8bd21-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-132">ValidationStates</span></span>|<span data-ttu-id="8bd21-133">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd21-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8bd21-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8bd21-134">InvalidFocused</span></span>|<span data-ttu-id="8bd21-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-135">ValidationStates</span></span>|<span data-ttu-id="8bd21-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8bd21-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8bd21-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8bd21-137">InvalidUnfocused</span></span>|<span data-ttu-id="8bd21-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8bd21-138">ValidationStates</span></span>|<span data-ttu-id="8bd21-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8bd21-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="8bd21-140">Ejemplo de ControlTemplate de Thumb</span><span class="sxs-lookup"><span data-stu-id="8bd21-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="8bd21-141">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.Thumb> control.</span><span class="sxs-lookup"><span data-stu-id="8bd21-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="8bd21-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8bd21-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8bd21-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="8bd21-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd21-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bd21-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="8bd21-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="8bd21-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="8bd21-146">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="8bd21-146">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="8bd21-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8bd21-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="8bd21-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8bd21-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
