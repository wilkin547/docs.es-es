---
title: Estilos y plantillas de TextBox
description: Obtenga información sobre los estilos y las plantillas del control TextBox Windows Presentation Foundation. Modifique el ControlTemplate para dar al control una apariencia única.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164729"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="46bd9-104">Estilos y plantillas de TextBox</span><span class="sxs-lookup"><span data-stu-id="46bd9-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="46bd9-105">En este tema se describen los estilos y las plantillas del <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="46bd9-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="46bd9-106">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="46bd9-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="46bd9-107">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="46bd9-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="46bd9-108">Elementos de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="46bd9-108">TextBox Parts</span></span>  
 <span data-ttu-id="46bd9-109">En la tabla siguiente se enumeran las partes con nombre para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="46bd9-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="46bd9-110">Parte</span><span class="sxs-lookup"><span data-stu-id="46bd9-110">Part</span></span>|<span data-ttu-id="46bd9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="46bd9-111">Type</span></span>|<span data-ttu-id="46bd9-112">Description</span><span class="sxs-lookup"><span data-stu-id="46bd9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="46bd9-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="46bd9-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="46bd9-114">Elemento visual que puede contener un <xref:System.Windows.FrameworkElement> .</span><span class="sxs-lookup"><span data-stu-id="46bd9-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="46bd9-115">El texto de <xref:System.Windows.Controls.TextBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="46bd9-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="46bd9-116">Estados de TextBox</span><span class="sxs-lookup"><span data-stu-id="46bd9-116">TextBox States</span></span>  
 <span data-ttu-id="46bd9-117">En la tabla siguiente se enumeran los Estados visuales del <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="46bd9-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="46bd9-118">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="46bd9-118">VisualState Name</span></span>|<span data-ttu-id="46bd9-119">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="46bd9-119">VisualStateGroup Name</span></span>|<span data-ttu-id="46bd9-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="46bd9-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="46bd9-121">Normal</span><span class="sxs-lookup"><span data-stu-id="46bd9-121">Normal</span></span>|<span data-ttu-id="46bd9-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-122">CommonStates</span></span>|<span data-ttu-id="46bd9-123">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="46bd9-123">The default state.</span></span>|  
|<span data-ttu-id="46bd9-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="46bd9-124">MouseOver</span></span>|<span data-ttu-id="46bd9-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-125">CommonStates</span></span>|<span data-ttu-id="46bd9-126">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="46bd9-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="46bd9-127">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="46bd9-127">Disabled</span></span>|<span data-ttu-id="46bd9-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-128">CommonStates</span></span>|<span data-ttu-id="46bd9-129">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="46bd9-129">The control is disabled.</span></span>|  
|<span data-ttu-id="46bd9-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="46bd9-130">ReadOnly</span></span>|<span data-ttu-id="46bd9-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-131">CommonStates</span></span>|<span data-ttu-id="46bd9-132">El usuario no puede cambiar el texto en <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="46bd9-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="46bd9-133">Con foco</span><span class="sxs-lookup"><span data-stu-id="46bd9-133">Focused</span></span>|<span data-ttu-id="46bd9-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-134">FocusStates</span></span>|<span data-ttu-id="46bd9-135">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="46bd9-135">The control has focus.</span></span>|  
|<span data-ttu-id="46bd9-136">Sin foco</span><span class="sxs-lookup"><span data-stu-id="46bd9-136">Unfocused</span></span>|<span data-ttu-id="46bd9-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-137">FocusStates</span></span>|<span data-ttu-id="46bd9-138">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="46bd9-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="46bd9-139">Válido</span><span class="sxs-lookup"><span data-stu-id="46bd9-139">Valid</span></span>|<span data-ttu-id="46bd9-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-140">ValidationStates</span></span>|<span data-ttu-id="46bd9-141">El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .</span><span class="sxs-lookup"><span data-stu-id="46bd9-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="46bd9-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="46bd9-142">InvalidFocused</span></span>|<span data-ttu-id="46bd9-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-143">ValidationStates</span></span>|<span data-ttu-id="46bd9-144">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta tiene `true` el foco.</span><span class="sxs-lookup"><span data-stu-id="46bd9-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="46bd9-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="46bd9-145">InvalidUnfocused</span></span>|<span data-ttu-id="46bd9-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46bd9-146">ValidationStates</span></span>|<span data-ttu-id="46bd9-147">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="46bd9-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="46bd9-148">Ejemplo de ControlTemplate de TextBox</span><span class="sxs-lookup"><span data-stu-id="46bd9-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="46bd9-149">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="46bd9-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="46bd9-150">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="46bd9-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="46bd9-151">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="46bd9-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bd9-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="46bd9-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="46bd9-153">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="46bd9-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="46bd9-154">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="46bd9-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="46bd9-155">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="46bd9-155">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="46bd9-156">Creación de una plantilla de un control</span><span class="sxs-lookup"><span data-stu-id="46bd9-156">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
