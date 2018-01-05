---
title: Estilos y plantillas de StatusBar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 370f8f9bc61ffbdd3b98743d11f61613803e6d98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="3538a-102">Estilos y plantillas de StatusBar</span><span class="sxs-lookup"><span data-stu-id="3538a-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="3538a-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="3538a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="3538a-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="3538a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3538a-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="3538a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="3538a-106">Partes de StatusBar</span><span class="sxs-lookup"><span data-stu-id="3538a-106">StatusBar Parts</span></span>  
 <span data-ttu-id="3538a-107">El <xref:System.Windows.Controls.Primitives.StatusBar> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="3538a-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="3538a-108">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="3538a-108">StatusBar States</span></span>  
 <span data-ttu-id="3538a-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="3538a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="3538a-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="3538a-110">VisualState Name</span></span>|<span data-ttu-id="3538a-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3538a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3538a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3538a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3538a-113">Válido</span><span class="sxs-lookup"><span data-stu-id="3538a-113">Valid</span></span>|<span data-ttu-id="3538a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-114">ValidationStates</span></span>|<span data-ttu-id="3538a-115">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="3538a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3538a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3538a-116">InvalidFocused</span></span>|<span data-ttu-id="3538a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-117">ValidationStates</span></span>|<span data-ttu-id="3538a-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3538a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3538a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3538a-119">InvalidUnfocused</span></span>|<span data-ttu-id="3538a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-120">ValidationStates</span></span>|<span data-ttu-id="3538a-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3538a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="3538a-122">StatusBarItem partes</span><span class="sxs-lookup"><span data-stu-id="3538a-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="3538a-123">El <xref:System.Windows.Controls.Primitives.StatusBarItem> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="3538a-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="3538a-124">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="3538a-124">StatusBar States</span></span>  
 <span data-ttu-id="3538a-125">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span><span class="sxs-lookup"><span data-stu-id="3538a-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="3538a-126">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="3538a-126">VisualState Name</span></span>|<span data-ttu-id="3538a-127">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3538a-127">VisualStateGroup Name</span></span>|<span data-ttu-id="3538a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="3538a-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3538a-129">Válido</span><span class="sxs-lookup"><span data-stu-id="3538a-129">Valid</span></span>|<span data-ttu-id="3538a-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-130">ValidationStates</span></span>|<span data-ttu-id="3538a-131">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="3538a-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3538a-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3538a-132">InvalidFocused</span></span>|<span data-ttu-id="3538a-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-133">ValidationStates</span></span>|<span data-ttu-id="3538a-134">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3538a-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3538a-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3538a-135">InvalidUnfocused</span></span>|<span data-ttu-id="3538a-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3538a-136">ValidationStates</span></span>|<span data-ttu-id="3538a-137">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3538a-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="3538a-138">Ejemplo de ControlTemplate de StatusBar</span><span class="sxs-lookup"><span data-stu-id="3538a-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="3538a-139">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="3538a-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="3538a-140">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="3538a-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3538a-141">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="3538a-141">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3538a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="3538a-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="3538a-143">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="3538a-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="3538a-144">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="3538a-144">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="3538a-145">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="3538a-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="3538a-146">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="3538a-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
