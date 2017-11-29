---
title: Estilos y plantillas de Button
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 27d68cd4102e8ba8502f1be5a9709082fa3d9ff3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="312c1-102">Estilos y plantillas de Button</span><span class="sxs-lookup"><span data-stu-id="312c1-102">Button Styles and Templates</span></span>
<span data-ttu-id="312c1-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="312c1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="312c1-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="312c1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="312c1-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="312c1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="312c1-106">Elementos de botón</span><span class="sxs-lookup"><span data-stu-id="312c1-106">Button Parts</span></span>  
 <span data-ttu-id="312c1-107">El <xref:System.Windows.Controls.Button> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="312c1-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="312c1-108">Estados de botones</span><span class="sxs-lookup"><span data-stu-id="312c1-108">Button States</span></span>  
 <span data-ttu-id="312c1-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="312c1-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="312c1-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="312c1-110">VisualState Name</span></span>|<span data-ttu-id="312c1-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="312c1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="312c1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="312c1-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="312c1-113">Normal</span><span class="sxs-lookup"><span data-stu-id="312c1-113">Normal</span></span>|<span data-ttu-id="312c1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="312c1-114">CommonStates</span></span>|<span data-ttu-id="312c1-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="312c1-115">The default state.</span></span>|  
|<span data-ttu-id="312c1-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="312c1-116">MouseOver</span></span>|<span data-ttu-id="312c1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="312c1-117">CommonStates</span></span>|<span data-ttu-id="312c1-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="312c1-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="312c1-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="312c1-119">Pressed</span></span>|<span data-ttu-id="312c1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="312c1-120">CommonStates</span></span>|<span data-ttu-id="312c1-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="312c1-121">The control is pressed.</span></span>|  
|<span data-ttu-id="312c1-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="312c1-122">Disabled</span></span>|<span data-ttu-id="312c1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="312c1-123">CommonStates</span></span>|<span data-ttu-id="312c1-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="312c1-124">The control is disabled.</span></span>|  
|<span data-ttu-id="312c1-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="312c1-125">Focused</span></span>|<span data-ttu-id="312c1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="312c1-126">FocusStates</span></span>|<span data-ttu-id="312c1-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="312c1-127">The control has focus.</span></span>|  
|<span data-ttu-id="312c1-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="312c1-128">Unfocused</span></span>|<span data-ttu-id="312c1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="312c1-129">FocusStates</span></span>|<span data-ttu-id="312c1-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="312c1-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="312c1-131">Válido</span><span class="sxs-lookup"><span data-stu-id="312c1-131">Valid</span></span>|<span data-ttu-id="312c1-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="312c1-132">ValidationStates</span></span>|<span data-ttu-id="312c1-133">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="312c1-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="312c1-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="312c1-134">InvalidFocused</span></span>|<span data-ttu-id="312c1-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="312c1-135">ValidationStates</span></span>|<span data-ttu-id="312c1-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="312c1-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="312c1-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="312c1-137">InvalidUnfocused</span></span>|<span data-ttu-id="312c1-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="312c1-138">ValidationStates</span></span>|<span data-ttu-id="312c1-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="312c1-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="312c1-140">Ejemplo de ControlTemplate de Button</span><span class="sxs-lookup"><span data-stu-id="312c1-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="312c1-141">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="312c1-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="312c1-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="312c1-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="312c1-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="312c1-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312c1-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="312c1-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="312c1-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="312c1-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="312c1-146">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="312c1-146">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="312c1-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="312c1-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="312c1-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="312c1-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
