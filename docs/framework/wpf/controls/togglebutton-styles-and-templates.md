---
title: Estilos y plantillas de ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 981a487b9935a86595a9caca03b4371326924642
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458222"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="0ae62-102">Estilos y plantillas de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="0ae62-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="0ae62-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="0ae62-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="0ae62-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="0ae62-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0ae62-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="0ae62-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="0ae62-106">Elementos ToggleButton</span><span class="sxs-lookup"><span data-stu-id="0ae62-106">ToggleButton Parts</span></span>

<span data-ttu-id="0ae62-107">El control <xref:System.Windows.Controls.Primitives.ToggleButton> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="0ae62-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="0ae62-108">Estados de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="0ae62-108">ToggleButton States</span></span>

<span data-ttu-id="0ae62-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="0ae62-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="0ae62-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="0ae62-110">VisualState Name</span></span>|<span data-ttu-id="0ae62-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0ae62-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0ae62-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ae62-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="0ae62-113">Normal</span><span class="sxs-lookup"><span data-stu-id="0ae62-113">Normal</span></span>|<span data-ttu-id="0ae62-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-114">CommonStates</span></span>|<span data-ttu-id="0ae62-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ae62-115">The default state.</span></span>|
|<span data-ttu-id="0ae62-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0ae62-116">MouseOver</span></span>|<span data-ttu-id="0ae62-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-117">CommonStates</span></span>|<span data-ttu-id="0ae62-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="0ae62-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="0ae62-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="0ae62-119">Pressed</span></span>|<span data-ttu-id="0ae62-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-120">CommonStates</span></span>|<span data-ttu-id="0ae62-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="0ae62-121">The control is pressed.</span></span>|
|<span data-ttu-id="0ae62-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="0ae62-122">Disabled</span></span>|<span data-ttu-id="0ae62-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-123">CommonStates</span></span>|<span data-ttu-id="0ae62-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ae62-124">The control is disabled.</span></span>|
|<span data-ttu-id="0ae62-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="0ae62-125">Focused</span></span>|<span data-ttu-id="0ae62-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-126">FocusStates</span></span>|<span data-ttu-id="0ae62-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ae62-127">The control has focus.</span></span>|
|<span data-ttu-id="0ae62-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="0ae62-128">Unfocused</span></span>|<span data-ttu-id="0ae62-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-129">FocusStates</span></span>|<span data-ttu-id="0ae62-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ae62-130">The control does not have focus.</span></span>|
|<span data-ttu-id="0ae62-131">Activadas</span><span class="sxs-lookup"><span data-stu-id="0ae62-131">Checked</span></span>|<span data-ttu-id="0ae62-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-132">CheckStates</span></span>|<span data-ttu-id="0ae62-133">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="0ae62-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="0ae62-134">desactivada</span><span class="sxs-lookup"><span data-stu-id="0ae62-134">Unchecked</span></span>|<span data-ttu-id="0ae62-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-135">CheckStates</span></span>|<span data-ttu-id="0ae62-136">El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="0ae62-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="0ae62-137">Determina</span><span class="sxs-lookup"><span data-stu-id="0ae62-137">Indeterminate</span></span>|<span data-ttu-id="0ae62-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-138">CheckStates</span></span>|<span data-ttu-id="0ae62-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true`y se `null`<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ae62-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="0ae62-140">Válido</span><span class="sxs-lookup"><span data-stu-id="0ae62-140">Valid</span></span>|<span data-ttu-id="0ae62-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-141">ValidationStates</span></span>|<span data-ttu-id="0ae62-142">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="0ae62-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="0ae62-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0ae62-143">InvalidFocused</span></span>|<span data-ttu-id="0ae62-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-144">ValidationStates</span></span>|<span data-ttu-id="0ae62-145">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ae62-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="0ae62-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0ae62-146">InvalidUnfocused</span></span>|<span data-ttu-id="0ae62-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ae62-147">ValidationStates</span></span>|<span data-ttu-id="0ae62-148">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ae62-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="0ae62-149">Si el estado visual indeterminado no existe en la plantilla de control, el estado visual desactivado se usará como estado visual predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ae62-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="0ae62-150">Ejemplo de ControlTemplate de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="0ae62-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="0ae62-151">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="0ae62-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="0ae62-152">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0ae62-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="0ae62-153">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0ae62-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ae62-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ae62-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0ae62-155">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="0ae62-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="0ae62-156">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="0ae62-156">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="0ae62-157">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="0ae62-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0ae62-158">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0ae62-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
