---
title: "Estilos y plantillas de menú"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e007ae09e57353446feb13b3693e62c985f522d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="90b77-102">Estilos y plantillas de menú</span><span class="sxs-lookup"><span data-stu-id="90b77-102">Menu Styles and Templates</span></span>
<span data-ttu-id="90b77-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Menu> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="90b77-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="90b77-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="90b77-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="90b77-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="90b77-106">Elementos de menú</span><span class="sxs-lookup"><span data-stu-id="90b77-106">Menu Parts</span></span>  
 <span data-ttu-id="90b77-107">El <xref:System.Windows.Controls.Menu> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="90b77-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="90b77-108">Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Menu>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="90b77-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="90b77-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.Menu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).</span><span class="sxs-lookup"><span data-stu-id="90b77-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="90b77-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="90b77-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="90b77-111">Estados de menús</span><span class="sxs-lookup"><span data-stu-id="90b77-111">Menu States</span></span>  
 <span data-ttu-id="90b77-112">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Menu> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="90b77-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="90b77-113">VisualState Name</span></span>|<span data-ttu-id="90b77-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="90b77-114">VisualStateGroup Name</span></span>|<span data-ttu-id="90b77-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="90b77-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="90b77-116">Válido</span><span class="sxs-lookup"><span data-stu-id="90b77-116">Valid</span></span>|<span data-ttu-id="90b77-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-117">ValidationStates</span></span>|<span data-ttu-id="90b77-118">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="90b77-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="90b77-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="90b77-119">InvalidFocused</span></span>|<span data-ttu-id="90b77-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-120">ValidationStates</span></span>|<span data-ttu-id="90b77-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="90b77-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="90b77-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="90b77-122">InvalidUnfocused</span></span>|<span data-ttu-id="90b77-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-123">ValidationStates</span></span>|<span data-ttu-id="90b77-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="90b77-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="90b77-125">Partes de MenuItem</span><span class="sxs-lookup"><span data-stu-id="90b77-125">MenuItem Parts</span></span>  
 <span data-ttu-id="90b77-126">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Menu> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="90b77-127">Parte</span><span class="sxs-lookup"><span data-stu-id="90b77-127">Part</span></span>|<span data-ttu-id="90b77-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="90b77-128">Type</span></span>|<span data-ttu-id="90b77-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="90b77-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="90b77-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="90b77-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="90b77-131">El área para el submenú.</span><span class="sxs-lookup"><span data-stu-id="90b77-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="90b77-132">Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.MenuItem>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="90b77-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="90b77-133">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.MenuItem>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).</span><span class="sxs-lookup"><span data-stu-id="90b77-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="90b77-134">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="90b77-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="90b77-135">Estados de MenuItem</span><span class="sxs-lookup"><span data-stu-id="90b77-135">MenuItem States</span></span>  
 <span data-ttu-id="90b77-136">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.MenuItem> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="90b77-137">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="90b77-137">VisualState Name</span></span>|<span data-ttu-id="90b77-138">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="90b77-138">VisualStateGroup Name</span></span>|<span data-ttu-id="90b77-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="90b77-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="90b77-140">Válido</span><span class="sxs-lookup"><span data-stu-id="90b77-140">Valid</span></span>|<span data-ttu-id="90b77-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-141">ValidationStates</span></span>|<span data-ttu-id="90b77-142">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="90b77-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="90b77-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="90b77-143">InvalidFocused</span></span>|<span data-ttu-id="90b77-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-144">ValidationStates</span></span>|<span data-ttu-id="90b77-145">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="90b77-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="90b77-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="90b77-146">InvalidUnfocused</span></span>|<span data-ttu-id="90b77-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90b77-147">ValidationStates</span></span>|<span data-ttu-id="90b77-148">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="90b77-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="90b77-149">Ejemplo de ControlTemplate de MenuItem y menú</span><span class="sxs-lookup"><span data-stu-id="90b77-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="90b77-150">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Menu> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="90b77-151">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.MenuItem> control.</span><span class="sxs-lookup"><span data-stu-id="90b77-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="90b77-152">En el ejemplo siguiente se define la `MenuScrollViewer`, que se usa en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="90b77-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="90b77-153">El <xref:System.Windows.Controls.ControlTemplate> ejemplos utilizan uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="90b77-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="90b77-154">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="90b77-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b77-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="90b77-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="90b77-156">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="90b77-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="90b77-157">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="90b77-157">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="90b77-158">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="90b77-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="90b77-159">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="90b77-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
