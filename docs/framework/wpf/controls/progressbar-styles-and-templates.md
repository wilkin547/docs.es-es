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
ms.openlocfilehash: 3a1bea39ba9b6d2cff9937a3fee1d1de41daf16b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459872"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="8d30a-102">Estilos y plantillas de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d30a-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="8d30a-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="8d30a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="8d30a-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="8d30a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8d30a-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="8d30a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="8d30a-106">Elementos ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d30a-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="8d30a-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="8d30a-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="8d30a-108">Parte</span><span class="sxs-lookup"><span data-stu-id="8d30a-108">Part</span></span>|<span data-ttu-id="8d30a-109">Type</span><span class="sxs-lookup"><span data-stu-id="8d30a-109">Type</span></span>|<span data-ttu-id="8d30a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d30a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8d30a-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="8d30a-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="8d30a-112">Objeto que indica el progreso.</span><span class="sxs-lookup"><span data-stu-id="8d30a-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="8d30a-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="8d30a-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="8d30a-114">Objeto que define la ruta de acceso del indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="8d30a-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="8d30a-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="8d30a-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="8d30a-116">Objeto que adorna la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="8d30a-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="8d30a-117">Estados de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d30a-117">ProgressBar States</span></span>  
 <span data-ttu-id="8d30a-118">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="8d30a-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="8d30a-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8d30a-119">VisualState Name</span></span>|<span data-ttu-id="8d30a-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8d30a-120">VisualStateGroup Name</span></span>|<span data-ttu-id="8d30a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d30a-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="8d30a-122">Determinada</span><span class="sxs-lookup"><span data-stu-id="8d30a-122">Determinate</span></span>|<span data-ttu-id="8d30a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d30a-123">CommonStates</span></span>|<span data-ttu-id="8d30a-124"><xref:System.Windows.Controls.ProgressBar> informa del progreso en función de la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="8d30a-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="8d30a-125">Determina</span><span class="sxs-lookup"><span data-stu-id="8d30a-125">Indeterminate</span></span>|<span data-ttu-id="8d30a-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8d30a-126">CommonStates</span></span>|<span data-ttu-id="8d30a-127"><xref:System.Windows.Controls.ProgressBar> informa del progreso genérico con un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="8d30a-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="8d30a-128">Válido</span><span class="sxs-lookup"><span data-stu-id="8d30a-128">Valid</span></span>|<span data-ttu-id="8d30a-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d30a-129">ValidationStates</span></span>|<span data-ttu-id="8d30a-130">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="8d30a-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8d30a-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8d30a-131">InvalidFocused</span></span>|<span data-ttu-id="8d30a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d30a-132">ValidationStates</span></span>|<span data-ttu-id="8d30a-133">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8d30a-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8d30a-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8d30a-134">InvalidUnfocused</span></span>|<span data-ttu-id="8d30a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d30a-135">ValidationStates</span></span>|<span data-ttu-id="8d30a-136">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8d30a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="8d30a-137">Ejemplo de ControlTemplate de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8d30a-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="8d30a-138">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="8d30a-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="8d30a-139">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d30a-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8d30a-140">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8d30a-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d30a-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d30a-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8d30a-142">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="8d30a-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="8d30a-143">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="8d30a-143">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="8d30a-144">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8d30a-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8d30a-145">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8d30a-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
