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
ms.openlocfilehash: 16f087051e438fa0dbe248c46b0ec555c07cc06c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367913"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="04969-102">Estilos y plantillas de TextBox</span><span class="sxs-lookup"><span data-stu-id="04969-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="04969-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="04969-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="04969-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="04969-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="04969-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="04969-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="04969-106">Elementos de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="04969-106">TextBox Parts</span></span>  
 <span data-ttu-id="04969-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="04969-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="04969-108">Parte</span><span class="sxs-lookup"><span data-stu-id="04969-108">Part</span></span>|<span data-ttu-id="04969-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="04969-109">Type</span></span>|<span data-ttu-id="04969-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="04969-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="04969-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="04969-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="04969-112">Un elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="04969-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="04969-113">El texto de la <xref:System.Windows.Controls.TextBox> se muestra en este elemento.</span><span class="sxs-lookup"><span data-stu-id="04969-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="04969-114">Estados del cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="04969-114">TextBox States</span></span>  
 <span data-ttu-id="04969-115">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="04969-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="04969-116">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="04969-116">VisualState Name</span></span>|<span data-ttu-id="04969-117">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="04969-117">VisualStateGroup Name</span></span>|<span data-ttu-id="04969-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="04969-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="04969-119">Normal</span><span class="sxs-lookup"><span data-stu-id="04969-119">Normal</span></span>|<span data-ttu-id="04969-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04969-120">CommonStates</span></span>|<span data-ttu-id="04969-121">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="04969-121">The default state.</span></span>|  
|<span data-ttu-id="04969-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="04969-122">MouseOver</span></span>|<span data-ttu-id="04969-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04969-123">CommonStates</span></span>|<span data-ttu-id="04969-124">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="04969-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="04969-125">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="04969-125">Disabled</span></span>|<span data-ttu-id="04969-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04969-126">CommonStates</span></span>|<span data-ttu-id="04969-127">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="04969-127">The control is disabled.</span></span>|  
|<span data-ttu-id="04969-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="04969-128">ReadOnly</span></span>|<span data-ttu-id="04969-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="04969-129">CommonStates</span></span>|<span data-ttu-id="04969-130">El usuario no puede cambiar el texto en el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="04969-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="04969-131">Con foco</span><span class="sxs-lookup"><span data-stu-id="04969-131">Focused</span></span>|<span data-ttu-id="04969-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="04969-132">FocusStates</span></span>|<span data-ttu-id="04969-133">El control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04969-133">The control has focus.</span></span>|  
|<span data-ttu-id="04969-134">Sin foco</span><span class="sxs-lookup"><span data-stu-id="04969-134">Unfocused</span></span>|<span data-ttu-id="04969-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="04969-135">FocusStates</span></span>|<span data-ttu-id="04969-136">El control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04969-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="04969-137">Válido</span><span class="sxs-lookup"><span data-stu-id="04969-137">Valid</span></span>|<span data-ttu-id="04969-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04969-138">ValidationStates</span></span>|<span data-ttu-id="04969-139">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="04969-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="04969-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="04969-140">InvalidFocused</span></span>|<span data-ttu-id="04969-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04969-141">ValidationStates</span></span>|<span data-ttu-id="04969-142">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04969-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="04969-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="04969-143">InvalidUnfocused</span></span>|<span data-ttu-id="04969-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04969-144">ValidationStates</span></span>|<span data-ttu-id="04969-145">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04969-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="04969-146">Ejemplo de ControlTemplate de cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="04969-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="04969-147">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="04969-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="04969-148">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="04969-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="04969-149">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="04969-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04969-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="04969-150">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="04969-151">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="04969-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="04969-152">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="04969-152">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="04969-153">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="04969-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="04969-154">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="04969-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
