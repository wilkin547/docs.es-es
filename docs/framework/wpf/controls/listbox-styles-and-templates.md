---
title: Estilos y plantillas de ListBox
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edf8c50424a9694c4e00f5bf319d3122999bda85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="listbox-styles-and-templates"></a><span data-ttu-id="6af48-102">Estilos y plantillas de ListBox</span><span class="sxs-lookup"><span data-stu-id="6af48-102">ListBox Styles and Templates</span></span>
<span data-ttu-id="6af48-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="6af48-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="6af48-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="6af48-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6af48-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6af48-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listbox-parts"></a><span data-ttu-id="6af48-106">Elementos de ListBox</span><span class="sxs-lookup"><span data-stu-id="6af48-106">ListBox Parts</span></span>  
 <span data-ttu-id="6af48-107">El <xref:System.Windows.Controls.ListBox> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="6af48-107">The <xref:System.Windows.Controls.ListBox> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="6af48-108">Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ListBox>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="6af48-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListBox>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="6af48-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.ListBox>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).</span><span class="sxs-lookup"><span data-stu-id="6af48-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListBox>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="6af48-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="6af48-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listbox-states"></a><span data-ttu-id="6af48-111">Estados de ListBox</span><span class="sxs-lookup"><span data-stu-id="6af48-111">ListBox States</span></span>  
 <span data-ttu-id="6af48-112">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="6af48-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="6af48-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="6af48-113">VisualState Name</span></span>|<span data-ttu-id="6af48-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6af48-114">VisualStateGroup Name</span></span>|<span data-ttu-id="6af48-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6af48-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6af48-116">Válido</span><span class="sxs-lookup"><span data-stu-id="6af48-116">Valid</span></span>|<span data-ttu-id="6af48-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-117">ValidationStates</span></span>|<span data-ttu-id="6af48-118">El control es válido.</span><span class="sxs-lookup"><span data-stu-id="6af48-118">The control is valid.</span></span>|  
|<span data-ttu-id="6af48-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6af48-119">InvalidFocused</span></span>|<span data-ttu-id="6af48-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-120">ValidationStates</span></span>|<span data-ttu-id="6af48-121">El control no es válido y tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-121">The control is not valid and has focus.</span></span>|  
|<span data-ttu-id="6af48-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6af48-122">InvalidUnfocused</span></span>|<span data-ttu-id="6af48-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-123">ValidationStates</span></span>|<span data-ttu-id="6af48-124">El control no es válido y no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-124">The control is not valid and does not have focus.</span></span>|  
  
## <a name="listboxitem-parts"></a><span data-ttu-id="6af48-125">Elementos ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="6af48-125">ListBoxItem Parts</span></span>  
 <span data-ttu-id="6af48-126">El <xref:System.Windows.Controls.ListBoxItem> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="6af48-126">The <xref:System.Windows.Controls.ListBoxItem> control does not have any named parts.</span></span>  
  
## <a name="listboxitem-states"></a><span data-ttu-id="6af48-127">Estados de ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="6af48-127">ListBoxItem States</span></span>  
 <span data-ttu-id="6af48-128">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ListBox> control.</span><span class="sxs-lookup"><span data-stu-id="6af48-128">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="6af48-129">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="6af48-129">VisualState Name</span></span>|<span data-ttu-id="6af48-130">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6af48-130">VisualStateGroup Name</span></span>|<span data-ttu-id="6af48-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="6af48-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6af48-132">Normal</span><span class="sxs-lookup"><span data-stu-id="6af48-132">Normal</span></span>|<span data-ttu-id="6af48-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6af48-133">CommonStates</span></span>|<span data-ttu-id="6af48-134">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6af48-134">The default state.</span></span>|  
|<span data-ttu-id="6af48-135">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6af48-135">MouseOver</span></span>|<span data-ttu-id="6af48-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6af48-136">CommonStates</span></span>|<span data-ttu-id="6af48-137">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="6af48-137">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="6af48-138">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6af48-138">Disabled</span></span>|<span data-ttu-id="6af48-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6af48-139">CommonStates</span></span>|<span data-ttu-id="6af48-140">El elemento está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6af48-140">The item is disabled.</span></span>|  
|<span data-ttu-id="6af48-141">Con foco</span><span class="sxs-lookup"><span data-stu-id="6af48-141">Focused</span></span>|<span data-ttu-id="6af48-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6af48-142">FocusStates</span></span>|<span data-ttu-id="6af48-143">El elemento tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-143">The item has focus.</span></span>|  
|<span data-ttu-id="6af48-144">Sin foco</span><span class="sxs-lookup"><span data-stu-id="6af48-144">Unfocused</span></span>|<span data-ttu-id="6af48-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6af48-145">FocusStates</span></span>|<span data-ttu-id="6af48-146">El elemento no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-146">The item does not have focus.</span></span>|  
|<span data-ttu-id="6af48-147">No seleccionado</span><span class="sxs-lookup"><span data-stu-id="6af48-147">Unselected</span></span>|<span data-ttu-id="6af48-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6af48-148">SelectionStates</span></span>|<span data-ttu-id="6af48-149">El elemento no está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6af48-149">The item is not selected.</span></span>|  
|<span data-ttu-id="6af48-150">Seleccionado</span><span class="sxs-lookup"><span data-stu-id="6af48-150">Selected</span></span>|<span data-ttu-id="6af48-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6af48-151">SelectionStates</span></span>|<span data-ttu-id="6af48-152">El elemento está seleccionado actualmente.</span><span class="sxs-lookup"><span data-stu-id="6af48-152">The item is currentlyplate selected.</span></span>|  
|<span data-ttu-id="6af48-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="6af48-153">SelectedUnfocused</span></span>|<span data-ttu-id="6af48-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6af48-154">SelectionStates</span></span>|<span data-ttu-id="6af48-155">El elemento está seleccionado, pero no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="6af48-156">Válido</span><span class="sxs-lookup"><span data-stu-id="6af48-156">Valid</span></span>|<span data-ttu-id="6af48-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-157">ValidationStates</span></span>|<span data-ttu-id="6af48-158">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="6af48-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6af48-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6af48-159">InvalidFocused</span></span>|<span data-ttu-id="6af48-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-160">ValidationStates</span></span>|<span data-ttu-id="6af48-161">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6af48-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6af48-162">InvalidUnfocused</span></span>|<span data-ttu-id="6af48-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6af48-163">ValidationStates</span></span>|<span data-ttu-id="6af48-164">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6af48-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listbox-controltemplate-example"></a><span data-ttu-id="6af48-165">Ejemplo de ControlTemplate de ListBox</span><span class="sxs-lookup"><span data-stu-id="6af48-165">ListBox ControlTemplate Example</span></span>  
 <span data-ttu-id="6af48-166">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ListBoxItem> controles.</span><span class="sxs-lookup"><span data-stu-id="6af48-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListBox> and <xref:System.Windows.Controls.ListBoxItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 <span data-ttu-id="6af48-167">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6af48-167">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6af48-168">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="6af48-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af48-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="6af48-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="6af48-170">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="6af48-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="6af48-171">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="6af48-171">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="6af48-172">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="6af48-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="6af48-173">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6af48-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
