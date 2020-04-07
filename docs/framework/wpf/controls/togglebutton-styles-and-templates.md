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
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805912"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="d62a5-102">Estilos y plantillas de ToggleButton</span><span class="sxs-lookup"><span data-stu-id="d62a5-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="d62a5-103">En este tema se describen <xref:System.Windows.Controls.Primitives.ToggleButton> los estilos y plantillas para el control.</span><span class="sxs-lookup"><span data-stu-id="d62a5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="d62a5-104">Puede modificar el <xref:System.Windows.Controls.ControlTemplate> valor predeterminado para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="d62a5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d62a5-105">Para obtener más información, vea [Crear una plantilla para un control.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="d62a5-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="d62a5-106">Piezas ToggleButton</span><span class="sxs-lookup"><span data-stu-id="d62a5-106">ToggleButton Parts</span></span>

<span data-ttu-id="d62a5-107">El <xref:System.Windows.Controls.Primitives.ToggleButton> control no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="d62a5-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="d62a5-108">Estados ToggleButton</span><span class="sxs-lookup"><span data-stu-id="d62a5-108">ToggleButton States</span></span>

<span data-ttu-id="d62a5-109">En la tabla siguiente se <xref:System.Windows.Controls.Primitives.ToggleButton> enumeran los estados visuales del control.</span><span class="sxs-lookup"><span data-stu-id="d62a5-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="d62a5-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="d62a5-110">VisualState Name</span></span>|<span data-ttu-id="d62a5-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d62a5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d62a5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d62a5-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="d62a5-113">Normal</span><span class="sxs-lookup"><span data-stu-id="d62a5-113">Normal</span></span>|<span data-ttu-id="d62a5-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-114">CommonStates</span></span>|<span data-ttu-id="d62a5-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d62a5-115">The default state.</span></span>|
|<span data-ttu-id="d62a5-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d62a5-116">MouseOver</span></span>|<span data-ttu-id="d62a5-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-117">CommonStates</span></span>|<span data-ttu-id="d62a5-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="d62a5-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="d62a5-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="d62a5-119">Pressed</span></span>|<span data-ttu-id="d62a5-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-120">CommonStates</span></span>|<span data-ttu-id="d62a5-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="d62a5-121">The control is pressed.</span></span>|
|<span data-ttu-id="d62a5-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="d62a5-122">Disabled</span></span>|<span data-ttu-id="d62a5-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-123">CommonStates</span></span>|<span data-ttu-id="d62a5-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="d62a5-124">The control is disabled.</span></span>|
|<span data-ttu-id="d62a5-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="d62a5-125">Focused</span></span>|<span data-ttu-id="d62a5-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-126">FocusStates</span></span>|<span data-ttu-id="d62a5-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d62a5-127">The control has focus.</span></span>|
|<span data-ttu-id="d62a5-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="d62a5-128">Unfocused</span></span>|<span data-ttu-id="d62a5-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-129">FocusStates</span></span>|<span data-ttu-id="d62a5-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d62a5-130">The control does not have focus.</span></span>|
|<span data-ttu-id="d62a5-131">Activado</span><span class="sxs-lookup"><span data-stu-id="d62a5-131">Checked</span></span>|<span data-ttu-id="d62a5-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-132">CheckStates</span></span>|<span data-ttu-id="d62a5-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="d62a5-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="d62a5-134">No activado</span><span class="sxs-lookup"><span data-stu-id="d62a5-134">Unchecked</span></span>|<span data-ttu-id="d62a5-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-135">CheckStates</span></span>|<span data-ttu-id="d62a5-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="d62a5-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="d62a5-137">Indeterminado</span><span class="sxs-lookup"><span data-stu-id="d62a5-137">Indeterminate</span></span>|<span data-ttu-id="d62a5-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-138">CheckStates</span></span>|<span data-ttu-id="d62a5-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true` y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `null`.</span><span class="sxs-lookup"><span data-stu-id="d62a5-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="d62a5-140">Válido</span><span class="sxs-lookup"><span data-stu-id="d62a5-140">Valid</span></span>|<span data-ttu-id="d62a5-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-141">ValidationStates</span></span>|<span data-ttu-id="d62a5-142">El control <xref:System.Windows.Controls.Validation> utiliza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> clase `false`y la propiedad adjunta es .</span><span class="sxs-lookup"><span data-stu-id="d62a5-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="d62a5-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d62a5-143">InvalidFocused</span></span>|<span data-ttu-id="d62a5-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-144">ValidationStates</span></span>|<span data-ttu-id="d62a5-145">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d62a5-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="d62a5-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d62a5-146">InvalidUnfocused</span></span>|<span data-ttu-id="d62a5-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d62a5-147">ValidationStates</span></span>|<span data-ttu-id="d62a5-148">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d62a5-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="d62a5-149">Si el estado visual Indeterminado no existe en la plantilla de control, el estado visual Desmarcado se usará como estado visual predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d62a5-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="d62a5-150">Ejemplo de ToggleButton ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d62a5-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="d62a5-151">En el ejemplo siguiente <xref:System.Windows.Controls.ControlTemplate> se <xref:System.Windows.Controls.Primitives.ToggleButton> muestra cómo definir a para el control.</span><span class="sxs-lookup"><span data-stu-id="d62a5-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="d62a5-152">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d62a5-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="d62a5-153">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d62a5-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="d62a5-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d62a5-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d62a5-155">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="d62a5-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d62a5-156">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="d62a5-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d62a5-157">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="d62a5-157">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d62a5-158">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="d62a5-158">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
