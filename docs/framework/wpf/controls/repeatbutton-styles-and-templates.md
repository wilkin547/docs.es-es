---
title: RepeatButton estilos y plantillas
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509594"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="81bb9-102">RepeatButton estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="81bb9-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="81bb9-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span><span class="sxs-lookup"><span data-stu-id="81bb9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="81bb9-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="81bb9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="81bb9-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="81bb9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="81bb9-106">Elementos RepeatButton</span><span class="sxs-lookup"><span data-stu-id="81bb9-106">RepeatButton Parts</span></span>

<span data-ttu-id="81bb9-107">El <xref:System.Windows.Controls.Primitives.RepeatButton> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="81bb9-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="81bb9-108">Estados de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="81bb9-108">RepeatButton States</span></span>

<span data-ttu-id="81bb9-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span><span class="sxs-lookup"><span data-stu-id="81bb9-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="81bb9-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="81bb9-110">VisualState Name</span></span>|<span data-ttu-id="81bb9-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="81bb9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="81bb9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="81bb9-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="81bb9-113">Normal</span><span class="sxs-lookup"><span data-stu-id="81bb9-113">Normal</span></span>|<span data-ttu-id="81bb9-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-114">CommonStates</span></span>|<span data-ttu-id="81bb9-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="81bb9-115">The default state.</span></span>|
|<span data-ttu-id="81bb9-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="81bb9-116">MouseOver</span></span>|<span data-ttu-id="81bb9-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-117">CommonStates</span></span>|<span data-ttu-id="81bb9-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="81bb9-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="81bb9-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="81bb9-119">Pressed</span></span>|<span data-ttu-id="81bb9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-120">CommonStates</span></span>|<span data-ttu-id="81bb9-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="81bb9-121">The control is pressed.</span></span>|
|<span data-ttu-id="81bb9-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="81bb9-122">Disabled</span></span>|<span data-ttu-id="81bb9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-123">CommonStates</span></span>|<span data-ttu-id="81bb9-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="81bb9-124">The control is disabled.</span></span>|
|<span data-ttu-id="81bb9-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="81bb9-125">Focused</span></span>|<span data-ttu-id="81bb9-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-126">FocusStates</span></span>|<span data-ttu-id="81bb9-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="81bb9-127">The control has focus.</span></span>|
|<span data-ttu-id="81bb9-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="81bb9-128">Unfocused</span></span>|<span data-ttu-id="81bb9-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-129">FocusStates</span></span>|<span data-ttu-id="81bb9-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="81bb9-130">The control does not have focus.</span></span>|
|<span data-ttu-id="81bb9-131">Válido</span><span class="sxs-lookup"><span data-stu-id="81bb9-131">Valid</span></span>|<span data-ttu-id="81bb9-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-132">ValidationStates</span></span>|<span data-ttu-id="81bb9-133">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="81bb9-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="81bb9-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="81bb9-134">InvalidFocused</span></span>|<span data-ttu-id="81bb9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-135">ValidationStates</span></span>|<span data-ttu-id="81bb9-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="81bb9-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="81bb9-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="81bb9-137">InvalidUnfocused</span></span>|<span data-ttu-id="81bb9-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="81bb9-138">ValidationStates</span></span>|<span data-ttu-id="81bb9-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="81bb9-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="81bb9-140">Ejemplo de ControlTemplate de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="81bb9-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="81bb9-141">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span><span class="sxs-lookup"><span data-stu-id="81bb9-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="81bb9-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="81bb9-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="81bb9-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="81bb9-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="81bb9-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="81bb9-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="81bb9-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="81bb9-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="81bb9-146">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="81bb9-146">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="81bb9-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="81bb9-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="81bb9-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="81bb9-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
