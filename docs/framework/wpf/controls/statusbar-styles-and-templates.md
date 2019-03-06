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
ms.openlocfilehash: 42bf7aa672addadbc4205c796c09914fe8f3054d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372482"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="8ff06-102">Estilos y plantillas de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8ff06-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="8ff06-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="8ff06-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="8ff06-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="8ff06-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8ff06-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8ff06-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="8ff06-106">Partes de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8ff06-106">StatusBar Parts</span></span>  
 <span data-ttu-id="8ff06-107">El <xref:System.Windows.Controls.Primitives.StatusBar> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="8ff06-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="8ff06-108">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8ff06-108">StatusBar States</span></span>  
 <span data-ttu-id="8ff06-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="8ff06-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="8ff06-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8ff06-110">VisualState Name</span></span>|<span data-ttu-id="8ff06-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8ff06-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8ff06-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ff06-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8ff06-113">Válido</span><span class="sxs-lookup"><span data-stu-id="8ff06-113">Valid</span></span>|<span data-ttu-id="8ff06-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-114">ValidationStates</span></span>|<span data-ttu-id="8ff06-115">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="8ff06-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8ff06-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8ff06-116">InvalidFocused</span></span>|<span data-ttu-id="8ff06-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-117">ValidationStates</span></span>|<span data-ttu-id="8ff06-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8ff06-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8ff06-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8ff06-119">InvalidUnfocused</span></span>|<span data-ttu-id="8ff06-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-120">ValidationStates</span></span>|<span data-ttu-id="8ff06-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8ff06-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="8ff06-122">StatusBarItem partes</span><span class="sxs-lookup"><span data-stu-id="8ff06-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="8ff06-123">El <xref:System.Windows.Controls.Primitives.StatusBarItem> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="8ff06-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="8ff06-124">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8ff06-124">StatusBar States</span></span>  
 <span data-ttu-id="8ff06-125">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span><span class="sxs-lookup"><span data-stu-id="8ff06-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="8ff06-126">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8ff06-126">VisualState Name</span></span>|<span data-ttu-id="8ff06-127">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8ff06-127">VisualStateGroup Name</span></span>|<span data-ttu-id="8ff06-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ff06-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8ff06-129">Válido</span><span class="sxs-lookup"><span data-stu-id="8ff06-129">Valid</span></span>|<span data-ttu-id="8ff06-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-130">ValidationStates</span></span>|<span data-ttu-id="8ff06-131">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="8ff06-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8ff06-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8ff06-132">InvalidFocused</span></span>|<span data-ttu-id="8ff06-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-133">ValidationStates</span></span>|<span data-ttu-id="8ff06-134">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8ff06-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8ff06-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8ff06-135">InvalidUnfocused</span></span>|<span data-ttu-id="8ff06-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8ff06-136">ValidationStates</span></span>|<span data-ttu-id="8ff06-137">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8ff06-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="8ff06-138">Ejemplo de ControlTemplate de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8ff06-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="8ff06-139">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.StatusBar> control.</span><span class="sxs-lookup"><span data-stu-id="8ff06-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="8ff06-140">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="8ff06-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8ff06-141">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8ff06-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff06-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ff06-142">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8ff06-143">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="8ff06-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="8ff06-144">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="8ff06-144">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="8ff06-145">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8ff06-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="8ff06-146">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8ff06-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
