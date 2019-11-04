---
title: Estilos y plantillas de RepeatButton
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 9c6a8ad0a954d244fb693e25965ab52dda114068
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459851"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="11a1b-102">Estilos y plantillas de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="11a1b-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="11a1b-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="11a1b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="11a1b-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="11a1b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="11a1b-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="11a1b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="11a1b-106">Elementos RepeatButton</span><span class="sxs-lookup"><span data-stu-id="11a1b-106">RepeatButton Parts</span></span>

<span data-ttu-id="11a1b-107">El control <xref:System.Windows.Controls.Primitives.RepeatButton> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="11a1b-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="11a1b-108">Estados de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="11a1b-108">RepeatButton States</span></span>

<span data-ttu-id="11a1b-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="11a1b-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="11a1b-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="11a1b-110">VisualState Name</span></span>|<span data-ttu-id="11a1b-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="11a1b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="11a1b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="11a1b-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="11a1b-113">Normal</span><span class="sxs-lookup"><span data-stu-id="11a1b-113">Normal</span></span>|<span data-ttu-id="11a1b-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-114">CommonStates</span></span>|<span data-ttu-id="11a1b-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="11a1b-115">The default state.</span></span>|
|<span data-ttu-id="11a1b-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="11a1b-116">MouseOver</span></span>|<span data-ttu-id="11a1b-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-117">CommonStates</span></span>|<span data-ttu-id="11a1b-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="11a1b-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="11a1b-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="11a1b-119">Pressed</span></span>|<span data-ttu-id="11a1b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-120">CommonStates</span></span>|<span data-ttu-id="11a1b-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="11a1b-121">The control is pressed.</span></span>|
|<span data-ttu-id="11a1b-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="11a1b-122">Disabled</span></span>|<span data-ttu-id="11a1b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-123">CommonStates</span></span>|<span data-ttu-id="11a1b-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="11a1b-124">The control is disabled.</span></span>|
|<span data-ttu-id="11a1b-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="11a1b-125">Focused</span></span>|<span data-ttu-id="11a1b-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-126">FocusStates</span></span>|<span data-ttu-id="11a1b-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="11a1b-127">The control has focus.</span></span>|
|<span data-ttu-id="11a1b-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="11a1b-128">Unfocused</span></span>|<span data-ttu-id="11a1b-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-129">FocusStates</span></span>|<span data-ttu-id="11a1b-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="11a1b-130">The control does not have focus.</span></span>|
|<span data-ttu-id="11a1b-131">Válido</span><span class="sxs-lookup"><span data-stu-id="11a1b-131">Valid</span></span>|<span data-ttu-id="11a1b-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-132">ValidationStates</span></span>|<span data-ttu-id="11a1b-133">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="11a1b-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="11a1b-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="11a1b-134">InvalidFocused</span></span>|<span data-ttu-id="11a1b-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-135">ValidationStates</span></span>|<span data-ttu-id="11a1b-136">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="11a1b-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="11a1b-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="11a1b-137">InvalidUnfocused</span></span>|<span data-ttu-id="11a1b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11a1b-138">ValidationStates</span></span>|<span data-ttu-id="11a1b-139">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="11a1b-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="11a1b-140">Ejemplo de ControlTemplate de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="11a1b-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="11a1b-141">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.RepeatButton>.</span><span class="sxs-lookup"><span data-stu-id="11a1b-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="11a1b-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="11a1b-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="11a1b-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="11a1b-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="11a1b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a1b-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="11a1b-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="11a1b-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="11a1b-146">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="11a1b-146">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="11a1b-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="11a1b-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="11a1b-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="11a1b-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
