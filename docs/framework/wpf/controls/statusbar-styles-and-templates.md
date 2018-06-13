---
title: Estilos y plantillas de StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 11fa3ab6edd62f0b5484d9ccf76c101d04be353c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457870"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="04069-102">Estilos y plantillas de StatusBar</span><span class="sxs-lookup"><span data-stu-id="04069-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="04069-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="04069-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="04069-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="04069-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="04069-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="04069-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="04069-106">Partes de StatusBar</span><span class="sxs-lookup"><span data-stu-id="04069-106">StatusBar Parts</span></span>  
 <span data-ttu-id="04069-107">El <xref:System.Windows.Controls.Primitives.StatusBar> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="04069-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="04069-108">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="04069-108">StatusBar States</span></span>  
 <span data-ttu-id="04069-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="04069-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="04069-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="04069-110">VisualState Name</span></span>|<span data-ttu-id="04069-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="04069-111">VisualStateGroup Name</span></span>|<span data-ttu-id="04069-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="04069-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="04069-113">Válido</span><span class="sxs-lookup"><span data-stu-id="04069-113">Valid</span></span>|<span data-ttu-id="04069-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-114">ValidationStates</span></span>|<span data-ttu-id="04069-115">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="04069-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="04069-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="04069-116">InvalidFocused</span></span>|<span data-ttu-id="04069-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-117">ValidationStates</span></span>|<span data-ttu-id="04069-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04069-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="04069-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="04069-119">InvalidUnfocused</span></span>|<span data-ttu-id="04069-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-120">ValidationStates</span></span>|<span data-ttu-id="04069-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04069-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="04069-122">StatusBarItem partes</span><span class="sxs-lookup"><span data-stu-id="04069-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="04069-123">El <xref:System.Windows.Controls.Primitives.StatusBarItem> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="04069-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="04069-124">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="04069-124">StatusBar States</span></span>  
 <span data-ttu-id="04069-125">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span><span class="sxs-lookup"><span data-stu-id="04069-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="04069-126">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="04069-126">VisualState Name</span></span>|<span data-ttu-id="04069-127">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="04069-127">VisualStateGroup Name</span></span>|<span data-ttu-id="04069-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="04069-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="04069-129">Válido</span><span class="sxs-lookup"><span data-stu-id="04069-129">Valid</span></span>|<span data-ttu-id="04069-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-130">ValidationStates</span></span>|<span data-ttu-id="04069-131">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="04069-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="04069-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="04069-132">InvalidFocused</span></span>|<span data-ttu-id="04069-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-133">ValidationStates</span></span>|<span data-ttu-id="04069-134">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04069-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="04069-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="04069-135">InvalidUnfocused</span></span>|<span data-ttu-id="04069-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04069-136">ValidationStates</span></span>|<span data-ttu-id="04069-137">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04069-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="04069-138">Ejemplo de ControlTemplate de StatusBar</span><span class="sxs-lookup"><span data-stu-id="04069-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="04069-139">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="04069-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="04069-140">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="04069-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="04069-141">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="04069-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04069-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="04069-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="04069-143">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="04069-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="04069-144">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="04069-144">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="04069-145">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="04069-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="04069-146">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="04069-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
