---
title: Estilos y plantillas de TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 41e390c261836909240cc146a48729d48c4a410e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283695"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="1f02d-102">Estilos y plantillas de TextBox</span><span class="sxs-lookup"><span data-stu-id="1f02d-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="1f02d-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="1f02d-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="1f02d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1f02d-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="1f02d-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="1f02d-106">Elementos de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="1f02d-106">TextBox Parts</span></span>  
 <span data-ttu-id="1f02d-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="1f02d-108">Parte</span><span class="sxs-lookup"><span data-stu-id="1f02d-108">Part</span></span>|<span data-ttu-id="1f02d-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="1f02d-109">Type</span></span>|<span data-ttu-id="1f02d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f02d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1f02d-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="1f02d-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="1f02d-112">Elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="1f02d-113">El texto del <xref:System.Windows.Controls.TextBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="1f02d-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="1f02d-114">Estados de TextBox</span><span class="sxs-lookup"><span data-stu-id="1f02d-114">TextBox States</span></span>  
 <span data-ttu-id="1f02d-115">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="1f02d-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="1f02d-116">VisualState Name</span></span>|<span data-ttu-id="1f02d-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="1f02d-117">VisualStateGroup Name</span></span>|<span data-ttu-id="1f02d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f02d-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="1f02d-119">Normal</span><span class="sxs-lookup"><span data-stu-id="1f02d-119">Normal</span></span>|<span data-ttu-id="1f02d-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-120">CommonStates</span></span>|<span data-ttu-id="1f02d-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1f02d-121">The default state.</span></span>|  
|<span data-ttu-id="1f02d-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="1f02d-122">MouseOver</span></span>|<span data-ttu-id="1f02d-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-123">CommonStates</span></span>|<span data-ttu-id="1f02d-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="1f02d-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="1f02d-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="1f02d-125">Disabled</span></span>|<span data-ttu-id="1f02d-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-126">CommonStates</span></span>|<span data-ttu-id="1f02d-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1f02d-127">The control is disabled.</span></span>|  
|<span data-ttu-id="1f02d-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1f02d-128">ReadOnly</span></span>|<span data-ttu-id="1f02d-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-129">CommonStates</span></span>|<span data-ttu-id="1f02d-130">El usuario no puede cambiar el texto en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="1f02d-131">Con foco</span><span class="sxs-lookup"><span data-stu-id="1f02d-131">Focused</span></span>|<span data-ttu-id="1f02d-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-132">FocusStates</span></span>|<span data-ttu-id="1f02d-133">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1f02d-133">The control has focus.</span></span>|  
|<span data-ttu-id="1f02d-134">Sin foco</span><span class="sxs-lookup"><span data-stu-id="1f02d-134">Unfocused</span></span>|<span data-ttu-id="1f02d-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-135">FocusStates</span></span>|<span data-ttu-id="1f02d-136">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1f02d-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="1f02d-137">Válido</span><span class="sxs-lookup"><span data-stu-id="1f02d-137">Valid</span></span>|<span data-ttu-id="1f02d-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-138">ValidationStates</span></span>|<span data-ttu-id="1f02d-139">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="1f02d-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1f02d-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1f02d-140">InvalidFocused</span></span>|<span data-ttu-id="1f02d-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-141">ValidationStates</span></span>|<span data-ttu-id="1f02d-142">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1f02d-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1f02d-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1f02d-143">InvalidUnfocused</span></span>|<span data-ttu-id="1f02d-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1f02d-144">ValidationStates</span></span>|<span data-ttu-id="1f02d-145">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="1f02d-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="1f02d-146">Ejemplo de ControlTemplate de TextBox</span><span class="sxs-lookup"><span data-stu-id="1f02d-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="1f02d-147">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1f02d-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="1f02d-148">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="1f02d-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1f02d-149">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="1f02d-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f02d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f02d-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1f02d-151">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="1f02d-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="1f02d-152">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="1f02d-152">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="1f02d-153">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="1f02d-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1f02d-154">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="1f02d-154">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
