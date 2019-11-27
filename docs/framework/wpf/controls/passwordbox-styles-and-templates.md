---
title: Estilos y plantillas de PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 4ba90182468466773644c7375059f0cc01675b33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283461"
---
# <a name="passwordbox-styles-and-templates"></a><span data-ttu-id="99a35-102">Estilos y plantillas de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="99a35-102">PasswordBox Styles and Templates</span></span>

<span data-ttu-id="99a35-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="99a35-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="99a35-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="99a35-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="99a35-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="99a35-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>

## <a name="passwordbox-parts"></a><span data-ttu-id="99a35-106">Partes de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="99a35-106">PasswordBox Parts</span></span>

<span data-ttu-id="99a35-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="99a35-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="99a35-108">Parte</span><span class="sxs-lookup"><span data-stu-id="99a35-108">Part</span></span>|<span data-ttu-id="99a35-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="99a35-109">Type</span></span>|<span data-ttu-id="99a35-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="99a35-110">Description</span></span>|
|-|-|-|
|<span data-ttu-id="99a35-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="99a35-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="99a35-112">Elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="99a35-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="99a35-113">El texto del <xref:System.Windows.Controls.PasswordBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="99a35-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|

## <a name="passwordbox-states"></a><span data-ttu-id="99a35-114">Estados de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="99a35-114">PasswordBox States</span></span>

<span data-ttu-id="99a35-115">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="99a35-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

|<span data-ttu-id="99a35-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="99a35-116">VisualState Name</span></span>|<span data-ttu-id="99a35-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="99a35-117">VisualStateGroup Name</span></span>|<span data-ttu-id="99a35-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="99a35-118">Description</span></span>|
|-|-|-|
|<span data-ttu-id="99a35-119">Normal</span><span class="sxs-lookup"><span data-stu-id="99a35-119">Normal</span></span>|<span data-ttu-id="99a35-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="99a35-120">CommonStates</span></span>|<span data-ttu-id="99a35-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="99a35-121">The default state.</span></span>|
|<span data-ttu-id="99a35-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="99a35-122">MouseOver</span></span>|<span data-ttu-id="99a35-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="99a35-123">CommonStates</span></span>|<span data-ttu-id="99a35-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="99a35-124">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="99a35-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="99a35-125">Disabled</span></span>|<span data-ttu-id="99a35-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="99a35-126">CommonStates</span></span>|<span data-ttu-id="99a35-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="99a35-127">The control is disabled.</span></span>|
|<span data-ttu-id="99a35-128">Con foco</span><span class="sxs-lookup"><span data-stu-id="99a35-128">Focused</span></span>|<span data-ttu-id="99a35-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="99a35-129">FocusStates</span></span>|<span data-ttu-id="99a35-130">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="99a35-130">The control has focus.</span></span>|
|<span data-ttu-id="99a35-131">Sin foco</span><span class="sxs-lookup"><span data-stu-id="99a35-131">Unfocused</span></span>|<span data-ttu-id="99a35-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="99a35-132">FocusStates</span></span>|<span data-ttu-id="99a35-133">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="99a35-133">The control does not have focus.</span></span>|
|<span data-ttu-id="99a35-134">Válido</span><span class="sxs-lookup"><span data-stu-id="99a35-134">Valid</span></span>|<span data-ttu-id="99a35-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="99a35-135">ValidationStates</span></span>|<span data-ttu-id="99a35-136">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="99a35-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="99a35-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="99a35-137">InvalidFocused</span></span>|<span data-ttu-id="99a35-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="99a35-138">ValidationStates</span></span>|<span data-ttu-id="99a35-139">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="99a35-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="99a35-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="99a35-140">InvalidUnfocused</span></span>|<span data-ttu-id="99a35-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="99a35-141">ValidationStates</span></span>|<span data-ttu-id="99a35-142">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="99a35-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="99a35-143">Ejemplo de ControlTemplate de PasswordBox</span><span class="sxs-lookup"><span data-stu-id="99a35-143">PasswordBox ControlTemplate Example</span></span>

<span data-ttu-id="99a35-144">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.PasswordBox>.</span><span class="sxs-lookup"><span data-stu-id="99a35-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

<span data-ttu-id="99a35-145">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="99a35-145">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="99a35-146">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="99a35-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="99a35-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="99a35-147">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="99a35-148">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="99a35-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="99a35-149">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="99a35-149">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="99a35-150">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="99a35-150">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="99a35-151">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="99a35-151">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
