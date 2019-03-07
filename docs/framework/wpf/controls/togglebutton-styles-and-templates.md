---
title: ToggleButton estilos y plantillas
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 46fd7d07c3904ee752ae3f467f65af4b0c031c84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509514"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="fea96-102">ToggleButton estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="fea96-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="fea96-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span><span class="sxs-lookup"><span data-stu-id="fea96-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="fea96-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="fea96-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="fea96-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="fea96-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="fea96-106">Partes de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="fea96-106">ToggleButton Parts</span></span>

<span data-ttu-id="fea96-107">El <xref:System.Windows.Controls.Primitives.ToggleButton> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="fea96-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="fea96-108">Estados de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="fea96-108">ToggleButton States</span></span>

<span data-ttu-id="fea96-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span><span class="sxs-lookup"><span data-stu-id="fea96-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="fea96-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="fea96-110">VisualState Name</span></span>|<span data-ttu-id="fea96-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="fea96-111">VisualStateGroup Name</span></span>|<span data-ttu-id="fea96-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fea96-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="fea96-113">Normal</span><span class="sxs-lookup"><span data-stu-id="fea96-113">Normal</span></span>|<span data-ttu-id="fea96-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fea96-114">CommonStates</span></span>|<span data-ttu-id="fea96-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fea96-115">The default state.</span></span>|
|<span data-ttu-id="fea96-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="fea96-116">MouseOver</span></span>|<span data-ttu-id="fea96-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fea96-117">CommonStates</span></span>|<span data-ttu-id="fea96-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="fea96-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="fea96-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="fea96-119">Pressed</span></span>|<span data-ttu-id="fea96-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fea96-120">CommonStates</span></span>|<span data-ttu-id="fea96-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="fea96-121">The control is pressed.</span></span>|
|<span data-ttu-id="fea96-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="fea96-122">Disabled</span></span>|<span data-ttu-id="fea96-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="fea96-123">CommonStates</span></span>|<span data-ttu-id="fea96-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fea96-124">The control is disabled.</span></span>|
|<span data-ttu-id="fea96-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="fea96-125">Focused</span></span>|<span data-ttu-id="fea96-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fea96-126">FocusStates</span></span>|<span data-ttu-id="fea96-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="fea96-127">The control has focus.</span></span>|
|<span data-ttu-id="fea96-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="fea96-128">Unfocused</span></span>|<span data-ttu-id="fea96-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="fea96-129">FocusStates</span></span>|<span data-ttu-id="fea96-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="fea96-130">The control does not have focus.</span></span>|
|<span data-ttu-id="fea96-131">Activado</span><span class="sxs-lookup"><span data-stu-id="fea96-131">Checked</span></span>|<span data-ttu-id="fea96-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fea96-132">CheckStates</span></span>|<span data-ttu-id="fea96-133">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="fea96-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="fea96-134">desactivada</span><span class="sxs-lookup"><span data-stu-id="fea96-134">Unchecked</span></span>|<span data-ttu-id="fea96-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fea96-135">CheckStates</span></span>|<span data-ttu-id="fea96-136">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="fea96-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="fea96-137">Indeterminado</span><span class="sxs-lookup"><span data-stu-id="fea96-137">Indeterminate</span></span>|<span data-ttu-id="fea96-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="fea96-138">CheckStates</span></span>|<span data-ttu-id="fea96-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true`, y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `null`.</span><span class="sxs-lookup"><span data-stu-id="fea96-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="fea96-140">Válido</span><span class="sxs-lookup"><span data-stu-id="fea96-140">Valid</span></span>|<span data-ttu-id="fea96-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fea96-141">ValidationStates</span></span>|<span data-ttu-id="fea96-142">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="fea96-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="fea96-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="fea96-143">InvalidFocused</span></span>|<span data-ttu-id="fea96-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fea96-144">ValidationStates</span></span>|<span data-ttu-id="fea96-145">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="fea96-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="fea96-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="fea96-146">InvalidUnfocused</span></span>|<span data-ttu-id="fea96-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="fea96-147">ValidationStates</span></span>|<span data-ttu-id="fea96-148">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="fea96-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="fea96-149">Si el estado indeterminado visual no existe en la plantilla de control, se usará como el estado visual de forma predeterminada el estado visual desactivado.</span><span class="sxs-lookup"><span data-stu-id="fea96-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="fea96-150">Ejemplo de ControlTemplate de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="fea96-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="fea96-151">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span><span class="sxs-lookup"><span data-stu-id="fea96-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="fea96-152">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="fea96-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="fea96-153">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="fea96-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="fea96-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="fea96-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="fea96-155">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="fea96-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="fea96-156">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="fea96-156">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="fea96-157">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="fea96-157">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="fea96-158">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="fea96-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
