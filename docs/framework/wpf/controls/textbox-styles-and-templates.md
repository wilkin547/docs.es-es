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
ms.openlocfilehash: ccc89e0e0c8977398ed162b246ff6cdede3b8351
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177949"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="7d308-102">Estilos y plantillas de TextBox</span><span class="sxs-lookup"><span data-stu-id="7d308-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="7d308-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="7d308-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="7d308-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="7d308-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7d308-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="7d308-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="7d308-106">Elementos de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="7d308-106">TextBox Parts</span></span>  
 <span data-ttu-id="7d308-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="7d308-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="7d308-108">Parte</span><span class="sxs-lookup"><span data-stu-id="7d308-108">Part</span></span>|<span data-ttu-id="7d308-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="7d308-109">Type</span></span>|<span data-ttu-id="7d308-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d308-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7d308-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="7d308-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="7d308-112">Un elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="7d308-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="7d308-113">El texto de la <xref:System.Windows.Controls.TextBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="7d308-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="7d308-114">Estados del cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="7d308-114">TextBox States</span></span>  
 <span data-ttu-id="7d308-115">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="7d308-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="7d308-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="7d308-116">VisualState Name</span></span>|<span data-ttu-id="7d308-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="7d308-117">VisualStateGroup Name</span></span>|<span data-ttu-id="7d308-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d308-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="7d308-119">Normal</span><span class="sxs-lookup"><span data-stu-id="7d308-119">Normal</span></span>|<span data-ttu-id="7d308-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d308-120">CommonStates</span></span>|<span data-ttu-id="7d308-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7d308-121">The default state.</span></span>|  
|<span data-ttu-id="7d308-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7d308-122">MouseOver</span></span>|<span data-ttu-id="7d308-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d308-123">CommonStates</span></span>|<span data-ttu-id="7d308-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="7d308-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7d308-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="7d308-125">Disabled</span></span>|<span data-ttu-id="7d308-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d308-126">CommonStates</span></span>|<span data-ttu-id="7d308-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="7d308-127">The control is disabled.</span></span>|  
|<span data-ttu-id="7d308-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="7d308-128">ReadOnly</span></span>|<span data-ttu-id="7d308-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d308-129">CommonStates</span></span>|<span data-ttu-id="7d308-130">El usuario no puede cambiar el texto en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="7d308-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="7d308-131">Con foco</span><span class="sxs-lookup"><span data-stu-id="7d308-131">Focused</span></span>|<span data-ttu-id="7d308-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7d308-132">FocusStates</span></span>|<span data-ttu-id="7d308-133">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d308-133">The control has focus.</span></span>|  
|<span data-ttu-id="7d308-134">Sin foco</span><span class="sxs-lookup"><span data-stu-id="7d308-134">Unfocused</span></span>|<span data-ttu-id="7d308-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7d308-135">FocusStates</span></span>|<span data-ttu-id="7d308-136">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d308-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="7d308-137">Válido</span><span class="sxs-lookup"><span data-stu-id="7d308-137">Valid</span></span>|<span data-ttu-id="7d308-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d308-138">ValidationStates</span></span>|<span data-ttu-id="7d308-139">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="7d308-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7d308-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7d308-140">InvalidFocused</span></span>|<span data-ttu-id="7d308-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d308-141">ValidationStates</span></span>|<span data-ttu-id="7d308-142">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d308-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7d308-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7d308-143">InvalidUnfocused</span></span>|<span data-ttu-id="7d308-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d308-144">ValidationStates</span></span>|<span data-ttu-id="7d308-145">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d308-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="7d308-146">Ejemplo de ControlTemplate de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="7d308-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="7d308-147">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="7d308-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="7d308-148">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7d308-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7d308-149">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="7d308-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d308-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d308-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7d308-151">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="7d308-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7d308-152">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="7d308-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7d308-153">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="7d308-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="7d308-154">Personalizar la apariencia de un control existente creando una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7d308-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
