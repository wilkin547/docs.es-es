---
title: Estilos y plantillas de Button
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ef9f85848ebdda9dc4ae15d0f54847eacd46e24d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283583"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="96e30-102">Estilos y plantillas de Button</span><span class="sxs-lookup"><span data-stu-id="96e30-102">Button Styles and Templates</span></span>
<span data-ttu-id="96e30-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="96e30-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="96e30-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="96e30-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="96e30-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="96e30-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="96e30-106">Elementos de botón</span><span class="sxs-lookup"><span data-stu-id="96e30-106">Button Parts</span></span>  
 <span data-ttu-id="96e30-107">El control <xref:System.Windows.Controls.Button> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="96e30-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="96e30-108">Estados del botón</span><span class="sxs-lookup"><span data-stu-id="96e30-108">Button States</span></span>  
 <span data-ttu-id="96e30-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="96e30-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="96e30-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="96e30-110">VisualState Name</span></span>|<span data-ttu-id="96e30-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="96e30-111">VisualStateGroup Name</span></span>|<span data-ttu-id="96e30-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96e30-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="96e30-113">Normal</span><span class="sxs-lookup"><span data-stu-id="96e30-113">Normal</span></span>|<span data-ttu-id="96e30-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96e30-114">CommonStates</span></span>|<span data-ttu-id="96e30-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="96e30-115">The default state.</span></span>|  
|<span data-ttu-id="96e30-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="96e30-116">MouseOver</span></span>|<span data-ttu-id="96e30-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96e30-117">CommonStates</span></span>|<span data-ttu-id="96e30-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="96e30-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="96e30-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="96e30-119">Pressed</span></span>|<span data-ttu-id="96e30-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96e30-120">CommonStates</span></span>|<span data-ttu-id="96e30-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="96e30-121">The control is pressed.</span></span>|  
|<span data-ttu-id="96e30-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="96e30-122">Disabled</span></span>|<span data-ttu-id="96e30-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="96e30-123">CommonStates</span></span>|<span data-ttu-id="96e30-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="96e30-124">The control is disabled.</span></span>|  
|<span data-ttu-id="96e30-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="96e30-125">Focused</span></span>|<span data-ttu-id="96e30-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="96e30-126">FocusStates</span></span>|<span data-ttu-id="96e30-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="96e30-127">The control has focus.</span></span>|  
|<span data-ttu-id="96e30-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="96e30-128">Unfocused</span></span>|<span data-ttu-id="96e30-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="96e30-129">FocusStates</span></span>|<span data-ttu-id="96e30-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="96e30-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="96e30-131">Válido</span><span class="sxs-lookup"><span data-stu-id="96e30-131">Valid</span></span>|<span data-ttu-id="96e30-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96e30-132">ValidationStates</span></span>|<span data-ttu-id="96e30-133">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="96e30-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="96e30-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="96e30-134">InvalidFocused</span></span>|<span data-ttu-id="96e30-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96e30-135">ValidationStates</span></span>|<span data-ttu-id="96e30-136">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="96e30-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="96e30-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="96e30-137">InvalidUnfocused</span></span>|<span data-ttu-id="96e30-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="96e30-138">ValidationStates</span></span>|<span data-ttu-id="96e30-139">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="96e30-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="96e30-140">Ejemplo de ControlTemplate de Button</span><span class="sxs-lookup"><span data-stu-id="96e30-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="96e30-141">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="96e30-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="96e30-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="96e30-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="96e30-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="96e30-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e30-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="96e30-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="96e30-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="96e30-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="96e30-146">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="96e30-146">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="96e30-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="96e30-147">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="96e30-148">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="96e30-148">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
