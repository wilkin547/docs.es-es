---
title: Estilos y plantillas de ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 7041a5497355a806894b0a0e0363fffde134aadb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377256"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="3b538-102">Estilos y plantillas de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="3b538-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="3b538-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="3b538-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="3b538-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="3b538-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3b538-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="3b538-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="3b538-106">Partes de la barra de progreso</span><span class="sxs-lookup"><span data-stu-id="3b538-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="3b538-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="3b538-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="3b538-108">Parte</span><span class="sxs-lookup"><span data-stu-id="3b538-108">Part</span></span>|<span data-ttu-id="3b538-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b538-109">Type</span></span>|<span data-ttu-id="3b538-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b538-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3b538-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="3b538-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3b538-112">El objeto que indica el progreso.</span><span class="sxs-lookup"><span data-stu-id="3b538-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="3b538-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="3b538-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3b538-114">El objeto que define la ruta de acceso del indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="3b538-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="3b538-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="3b538-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3b538-116">Objeto que embellishes la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="3b538-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="3b538-117">Estados de la barra de progreso</span><span class="sxs-lookup"><span data-stu-id="3b538-117">ProgressBar States</span></span>  
 <span data-ttu-id="3b538-118">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="3b538-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="3b538-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="3b538-119">VisualState Name</span></span>|<span data-ttu-id="3b538-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3b538-120">VisualStateGroup Name</span></span>|<span data-ttu-id="3b538-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b538-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3b538-122">Determinada</span><span class="sxs-lookup"><span data-stu-id="3b538-122">Determinate</span></span>|<span data-ttu-id="3b538-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3b538-123">CommonStates</span></span>|<span data-ttu-id="3b538-124"><xref:System.Windows.Controls.ProgressBar> informa del progreso según el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b538-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="3b538-125">Indeterminado</span><span class="sxs-lookup"><span data-stu-id="3b538-125">Indeterminate</span></span>|<span data-ttu-id="3b538-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3b538-126">CommonStates</span></span>|<span data-ttu-id="3b538-127"><xref:System.Windows.Controls.ProgressBar> indica el progreso general con un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="3b538-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="3b538-128">Válido</span><span class="sxs-lookup"><span data-stu-id="3b538-128">Valid</span></span>|<span data-ttu-id="3b538-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b538-129">ValidationStates</span></span>|<span data-ttu-id="3b538-130">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="3b538-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3b538-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3b538-131">InvalidFocused</span></span>|<span data-ttu-id="3b538-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b538-132">ValidationStates</span></span>|<span data-ttu-id="3b538-133">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3b538-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3b538-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3b538-134">InvalidUnfocused</span></span>|<span data-ttu-id="3b538-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3b538-135">ValidationStates</span></span>|<span data-ttu-id="3b538-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="3b538-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="3b538-137">Ejemplo de ControlTemplate para ProgressBar</span><span class="sxs-lookup"><span data-stu-id="3b538-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="3b538-138">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="3b538-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="3b538-139">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="3b538-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3b538-140">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="3b538-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b538-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b538-141">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3b538-142">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="3b538-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="3b538-143">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="3b538-143">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="3b538-144">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="3b538-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="3b538-145">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="3b538-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
