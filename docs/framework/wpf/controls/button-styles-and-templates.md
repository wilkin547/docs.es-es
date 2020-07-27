---
title: Estilos y plantillas de Button
description: Obtenga información sobre los estilos y las plantillas del control de botón de Windows Presentation Foundation. Modifique el ControlTemplate para dar al control una apariencia única.
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 11509adeef397f26eb040e6e98d0edb333b2515f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166265"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="d9fd0-104">Estilos y plantillas de Button</span><span class="sxs-lookup"><span data-stu-id="d9fd0-104">Button Styles and Templates</span></span>
<span data-ttu-id="d9fd0-105">En este tema se describen los estilos y las plantillas del <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="d9fd0-106">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d9fd0-107">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="d9fd0-107">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="d9fd0-108">Elementos de botón</span><span class="sxs-lookup"><span data-stu-id="d9fd0-108">Button Parts</span></span>  
 <span data-ttu-id="d9fd0-109">El <xref:System.Windows.Controls.Button> control no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="d9fd0-110">Estados del botón</span><span class="sxs-lookup"><span data-stu-id="d9fd0-110">Button States</span></span>  
 <span data-ttu-id="d9fd0-111">En la tabla siguiente se enumeran los Estados visuales del <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="d9fd0-112">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="d9fd0-112">VisualState Name</span></span>|<span data-ttu-id="d9fd0-113">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d9fd0-113">VisualStateGroup Name</span></span>|<span data-ttu-id="d9fd0-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9fd0-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d9fd0-115">Normal</span><span class="sxs-lookup"><span data-stu-id="d9fd0-115">Normal</span></span>|<span data-ttu-id="d9fd0-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-116">CommonStates</span></span>|<span data-ttu-id="d9fd0-117">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-117">The default state.</span></span>|  
|<span data-ttu-id="d9fd0-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d9fd0-118">MouseOver</span></span>|<span data-ttu-id="d9fd0-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-119">CommonStates</span></span>|<span data-ttu-id="d9fd0-120">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d9fd0-121">Presionado</span><span class="sxs-lookup"><span data-stu-id="d9fd0-121">Pressed</span></span>|<span data-ttu-id="d9fd0-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-122">CommonStates</span></span>|<span data-ttu-id="d9fd0-123">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-123">The control is pressed.</span></span>|  
|<span data-ttu-id="d9fd0-124">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="d9fd0-124">Disabled</span></span>|<span data-ttu-id="d9fd0-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-125">CommonStates</span></span>|<span data-ttu-id="d9fd0-126">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-126">The control is disabled.</span></span>|  
|<span data-ttu-id="d9fd0-127">Con foco</span><span class="sxs-lookup"><span data-stu-id="d9fd0-127">Focused</span></span>|<span data-ttu-id="d9fd0-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-128">FocusStates</span></span>|<span data-ttu-id="d9fd0-129">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-129">The control has focus.</span></span>|  
|<span data-ttu-id="d9fd0-130">Sin foco</span><span class="sxs-lookup"><span data-stu-id="d9fd0-130">Unfocused</span></span>|<span data-ttu-id="d9fd0-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-131">FocusStates</span></span>|<span data-ttu-id="d9fd0-132">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="d9fd0-133">Válido</span><span class="sxs-lookup"><span data-stu-id="d9fd0-133">Valid</span></span>|<span data-ttu-id="d9fd0-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-134">ValidationStates</span></span>|<span data-ttu-id="d9fd0-135">El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .</span><span class="sxs-lookup"><span data-stu-id="d9fd0-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d9fd0-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d9fd0-136">InvalidFocused</span></span>|<span data-ttu-id="d9fd0-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-137">ValidationStates</span></span>|<span data-ttu-id="d9fd0-138">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="d9fd0-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d9fd0-139">InvalidUnfocused</span></span>|<span data-ttu-id="d9fd0-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d9fd0-140">ValidationStates</span></span>|<span data-ttu-id="d9fd0-141">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="d9fd0-142">Ejemplo de ControlTemplate de Button</span><span class="sxs-lookup"><span data-stu-id="d9fd0-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="d9fd0-143">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="d9fd0-144">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d9fd0-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d9fd0-145">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d9fd0-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9fd0-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9fd0-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d9fd0-147">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="d9fd0-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d9fd0-148">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="d9fd0-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d9fd0-149">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="d9fd0-149">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d9fd0-150">Creación de una plantilla de un control</span><span class="sxs-lookup"><span data-stu-id="d9fd0-150">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
