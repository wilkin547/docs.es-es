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
ms.openlocfilehash: b1dd575d58571b845fc849ca432ad440d1ce3ec4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458261"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="eb327-102">Estilos y plantillas de StatusBar</span><span class="sxs-lookup"><span data-stu-id="eb327-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="eb327-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="eb327-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="eb327-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="eb327-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="eb327-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="eb327-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="eb327-106">Partes de StatusBar</span><span class="sxs-lookup"><span data-stu-id="eb327-106">StatusBar Parts</span></span>  
 <span data-ttu-id="eb327-107">El control <xref:System.Windows.Controls.Primitives.StatusBar> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="eb327-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="eb327-108">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="eb327-108">StatusBar States</span></span>  
 <span data-ttu-id="eb327-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="eb327-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="eb327-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="eb327-110">VisualState Name</span></span>|<span data-ttu-id="eb327-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="eb327-111">VisualStateGroup Name</span></span>|<span data-ttu-id="eb327-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb327-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="eb327-113">Válido</span><span class="sxs-lookup"><span data-stu-id="eb327-113">Valid</span></span>|<span data-ttu-id="eb327-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-114">ValidationStates</span></span>|<span data-ttu-id="eb327-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="eb327-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="eb327-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="eb327-116">InvalidFocused</span></span>|<span data-ttu-id="eb327-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-117">ValidationStates</span></span>|<span data-ttu-id="eb327-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="eb327-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="eb327-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="eb327-119">InvalidUnfocused</span></span>|<span data-ttu-id="eb327-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-120">ValidationStates</span></span>|<span data-ttu-id="eb327-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="eb327-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="eb327-122">Elementos StatusBarItem</span><span class="sxs-lookup"><span data-stu-id="eb327-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="eb327-123">El control <xref:System.Windows.Controls.Primitives.StatusBarItem> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="eb327-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="eb327-124">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="eb327-124">StatusBar States</span></span>  
 <span data-ttu-id="eb327-125">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.StatusBarItem>.</span><span class="sxs-lookup"><span data-stu-id="eb327-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="eb327-126">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="eb327-126">VisualState Name</span></span>|<span data-ttu-id="eb327-127">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="eb327-127">VisualStateGroup Name</span></span>|<span data-ttu-id="eb327-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb327-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="eb327-129">Válido</span><span class="sxs-lookup"><span data-stu-id="eb327-129">Valid</span></span>|<span data-ttu-id="eb327-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-130">ValidationStates</span></span>|<span data-ttu-id="eb327-131">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="eb327-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="eb327-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="eb327-132">InvalidFocused</span></span>|<span data-ttu-id="eb327-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-133">ValidationStates</span></span>|<span data-ttu-id="eb327-134">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="eb327-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="eb327-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="eb327-135">InvalidUnfocused</span></span>|<span data-ttu-id="eb327-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="eb327-136">ValidationStates</span></span>|<span data-ttu-id="eb327-137">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="eb327-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="eb327-138">Ejemplo de ControlTemplate de StatusBar</span><span class="sxs-lookup"><span data-stu-id="eb327-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="eb327-139">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="eb327-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="eb327-140">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="eb327-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="eb327-141">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="eb327-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb327-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb327-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="eb327-143">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="eb327-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="eb327-144">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="eb327-144">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="eb327-145">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="eb327-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="eb327-146">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="eb327-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
