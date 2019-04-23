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
ms.openlocfilehash: ec64c7c2051b12cba01135054a90e54864b7386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116342"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="ef8fc-102">Estilos y plantillas de Button</span><span class="sxs-lookup"><span data-stu-id="ef8fc-102">Button Styles and Templates</span></span>
<span data-ttu-id="ef8fc-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="ef8fc-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ef8fc-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ef8fc-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="ef8fc-106">Elementos de botón</span><span class="sxs-lookup"><span data-stu-id="ef8fc-106">Button Parts</span></span>  
 <span data-ttu-id="ef8fc-107">El <xref:System.Windows.Controls.Button> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="ef8fc-108">Estados del botón</span><span class="sxs-lookup"><span data-stu-id="ef8fc-108">Button States</span></span>  
 <span data-ttu-id="ef8fc-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="ef8fc-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="ef8fc-110">VisualState Name</span></span>|<span data-ttu-id="ef8fc-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ef8fc-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ef8fc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef8fc-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ef8fc-113">Normal</span><span class="sxs-lookup"><span data-stu-id="ef8fc-113">Normal</span></span>|<span data-ttu-id="ef8fc-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-114">CommonStates</span></span>|<span data-ttu-id="ef8fc-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-115">The default state.</span></span>|  
|<span data-ttu-id="ef8fc-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ef8fc-116">MouseOver</span></span>|<span data-ttu-id="ef8fc-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-117">CommonStates</span></span>|<span data-ttu-id="ef8fc-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ef8fc-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="ef8fc-119">Pressed</span></span>|<span data-ttu-id="ef8fc-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-120">CommonStates</span></span>|<span data-ttu-id="ef8fc-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ef8fc-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="ef8fc-122">Disabled</span></span>|<span data-ttu-id="ef8fc-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-123">CommonStates</span></span>|<span data-ttu-id="ef8fc-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ef8fc-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="ef8fc-125">Focused</span></span>|<span data-ttu-id="ef8fc-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-126">FocusStates</span></span>|<span data-ttu-id="ef8fc-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-127">The control has focus.</span></span>|  
|<span data-ttu-id="ef8fc-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="ef8fc-128">Unfocused</span></span>|<span data-ttu-id="ef8fc-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-129">FocusStates</span></span>|<span data-ttu-id="ef8fc-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ef8fc-131">Válido</span><span class="sxs-lookup"><span data-stu-id="ef8fc-131">Valid</span></span>|<span data-ttu-id="ef8fc-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-132">ValidationStates</span></span>|<span data-ttu-id="ef8fc-133">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ef8fc-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ef8fc-134">InvalidFocused</span></span>|<span data-ttu-id="ef8fc-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-135">ValidationStates</span></span>|<span data-ttu-id="ef8fc-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="ef8fc-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ef8fc-137">InvalidUnfocused</span></span>|<span data-ttu-id="ef8fc-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef8fc-138">ValidationStates</span></span>|<span data-ttu-id="ef8fc-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="ef8fc-140">Ejemplo de ControlTemplate de Button</span><span class="sxs-lookup"><span data-stu-id="ef8fc-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="ef8fc-141">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="ef8fc-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ef8fc-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ef8fc-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ef8fc-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8fc-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef8fc-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ef8fc-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="ef8fc-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="ef8fc-146">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="ef8fc-146">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="ef8fc-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ef8fc-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="ef8fc-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ef8fc-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
