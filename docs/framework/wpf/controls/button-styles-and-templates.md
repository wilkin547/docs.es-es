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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912488"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="ad8ff-102">Estilos y plantillas de Button</span><span class="sxs-lookup"><span data-stu-id="ad8ff-102">Button Styles and Templates</span></span>
<span data-ttu-id="ad8ff-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="ad8ff-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ad8ff-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ad8ff-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="ad8ff-106">Elementos de botón</span><span class="sxs-lookup"><span data-stu-id="ad8ff-106">Button Parts</span></span>  
 <span data-ttu-id="ad8ff-107">El <xref:System.Windows.Controls.Button> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="ad8ff-108">Estados del botón</span><span class="sxs-lookup"><span data-stu-id="ad8ff-108">Button States</span></span>  
 <span data-ttu-id="ad8ff-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="ad8ff-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="ad8ff-110">VisualState Name</span></span>|<span data-ttu-id="ad8ff-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ad8ff-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ad8ff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad8ff-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ad8ff-113">Normal</span><span class="sxs-lookup"><span data-stu-id="ad8ff-113">Normal</span></span>|<span data-ttu-id="ad8ff-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-114">CommonStates</span></span>|<span data-ttu-id="ad8ff-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-115">The default state.</span></span>|  
|<span data-ttu-id="ad8ff-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ad8ff-116">MouseOver</span></span>|<span data-ttu-id="ad8ff-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-117">CommonStates</span></span>|<span data-ttu-id="ad8ff-118">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ad8ff-119">Presionado</span><span class="sxs-lookup"><span data-stu-id="ad8ff-119">Pressed</span></span>|<span data-ttu-id="ad8ff-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-120">CommonStates</span></span>|<span data-ttu-id="ad8ff-121">El control está presionado.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ad8ff-122">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="ad8ff-122">Disabled</span></span>|<span data-ttu-id="ad8ff-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-123">CommonStates</span></span>|<span data-ttu-id="ad8ff-124">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ad8ff-125">Con foco</span><span class="sxs-lookup"><span data-stu-id="ad8ff-125">Focused</span></span>|<span data-ttu-id="ad8ff-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-126">FocusStates</span></span>|<span data-ttu-id="ad8ff-127">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-127">The control has focus.</span></span>|  
|<span data-ttu-id="ad8ff-128">Sin foco</span><span class="sxs-lookup"><span data-stu-id="ad8ff-128">Unfocused</span></span>|<span data-ttu-id="ad8ff-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-129">FocusStates</span></span>|<span data-ttu-id="ad8ff-130">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ad8ff-131">Válido</span><span class="sxs-lookup"><span data-stu-id="ad8ff-131">Valid</span></span>|<span data-ttu-id="ad8ff-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-132">ValidationStates</span></span>|<span data-ttu-id="ad8ff-133">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ad8ff-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ad8ff-134">InvalidFocused</span></span>|<span data-ttu-id="ad8ff-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-135">ValidationStates</span></span>|<span data-ttu-id="ad8ff-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="ad8ff-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ad8ff-137">InvalidUnfocused</span></span>|<span data-ttu-id="ad8ff-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad8ff-138">ValidationStates</span></span>|<span data-ttu-id="ad8ff-139">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="ad8ff-140">Ejemplo de ControlTemplate de Button</span><span class="sxs-lookup"><span data-stu-id="ad8ff-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="ad8ff-141">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Button> control.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="ad8ff-142">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad8ff-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ad8ff-143">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ad8ff-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad8ff-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad8ff-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ad8ff-145">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="ad8ff-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="ad8ff-146">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="ad8ff-146">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="ad8ff-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ad8ff-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="ad8ff-148">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ad8ff-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
