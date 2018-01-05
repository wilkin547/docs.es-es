---
title: Estilos y plantillas de PasswordBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f22b73704d21fa719a678799c1d95fc266c661e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="4d9bf-102">Estilos y plantillas de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4d9bf-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="4d9bf-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="4d9bf-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4d9bf-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="4d9bf-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="4d9bf-106">PasswordBox partes</span><span class="sxs-lookup"><span data-stu-id="4d9bf-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="4d9bf-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="4d9bf-108">Parte</span><span class="sxs-lookup"><span data-stu-id="4d9bf-108">Part</span></span>|<span data-ttu-id="4d9bf-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="4d9bf-109">Type</span></span>|<span data-ttu-id="4d9bf-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d9bf-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4d9bf-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="4d9bf-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="4d9bf-112">Elemento visual que puede contener una <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4d9bf-113">El texto de la <xref:System.Windows.Controls.PasswordBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="4d9bf-114">Estados de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4d9bf-114">PasswordBox States</span></span>  
 <span data-ttu-id="4d9bf-115">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="4d9bf-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="4d9bf-116">VisualState Name</span></span>|<span data-ttu-id="4d9bf-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4d9bf-117">VisualStateGroup Name</span></span>|<span data-ttu-id="4d9bf-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d9bf-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4d9bf-119">Normal</span><span class="sxs-lookup"><span data-stu-id="4d9bf-119">Normal</span></span>|<span data-ttu-id="4d9bf-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-120">CommonStates</span></span>|<span data-ttu-id="4d9bf-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-121">The default state.</span></span>|  
|<span data-ttu-id="4d9bf-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4d9bf-122">MouseOver</span></span>|<span data-ttu-id="4d9bf-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-123">CommonStates</span></span>|<span data-ttu-id="4d9bf-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4d9bf-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4d9bf-125">Disabled</span></span>|<span data-ttu-id="4d9bf-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-126">CommonStates</span></span>|<span data-ttu-id="4d9bf-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-127">The control is disabled.</span></span>|  
|<span data-ttu-id="4d9bf-128">Con foco</span><span class="sxs-lookup"><span data-stu-id="4d9bf-128">Focused</span></span>|<span data-ttu-id="4d9bf-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-129">FocusStates</span></span>|<span data-ttu-id="4d9bf-130">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-130">The control has focus.</span></span>|  
|<span data-ttu-id="4d9bf-131">Sin foco</span><span class="sxs-lookup"><span data-stu-id="4d9bf-131">Unfocused</span></span>|<span data-ttu-id="4d9bf-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-132">FocusStates</span></span>|<span data-ttu-id="4d9bf-133">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="4d9bf-134">Válido</span><span class="sxs-lookup"><span data-stu-id="4d9bf-134">Valid</span></span>|<span data-ttu-id="4d9bf-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-135">ValidationStates</span></span>|<span data-ttu-id="4d9bf-136">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4d9bf-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4d9bf-137">InvalidFocused</span></span>|<span data-ttu-id="4d9bf-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-138">ValidationStates</span></span>|<span data-ttu-id="4d9bf-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4d9bf-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4d9bf-140">InvalidUnfocused</span></span>|<span data-ttu-id="4d9bf-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4d9bf-141">ValidationStates</span></span>|<span data-ttu-id="4d9bf-142">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="4d9bf-143">Ejemplo de ControlTemplate de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="4d9bf-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="4d9bf-144">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.PasswordBox> control.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="4d9bf-145">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4d9bf-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4d9bf-146">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="4d9bf-146">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9bf-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d9bf-147">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="4d9bf-148">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="4d9bf-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="4d9bf-149">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="4d9bf-149">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="4d9bf-150">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4d9bf-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="4d9bf-151">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4d9bf-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
