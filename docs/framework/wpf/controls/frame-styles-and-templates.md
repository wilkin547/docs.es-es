---
title: Estilos y plantillas de Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: de853198c97c99319bea4a816c9a6eca5dc5d917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283739"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="cafc5-102">Estilos y plantillas de Frame</span><span class="sxs-lookup"><span data-stu-id="cafc5-102">Frame Styles and Templates</span></span>
<span data-ttu-id="cafc5-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="cafc5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="cafc5-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="cafc5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="cafc5-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="cafc5-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="cafc5-106">Elementos de marco</span><span class="sxs-lookup"><span data-stu-id="cafc5-106">Frame Parts</span></span>  
 <span data-ttu-id="cafc5-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="cafc5-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="cafc5-108">Parte</span><span class="sxs-lookup"><span data-stu-id="cafc5-108">Part</span></span>|<span data-ttu-id="cafc5-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="cafc5-109">Type</span></span>|<span data-ttu-id="cafc5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cafc5-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cafc5-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="cafc5-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="cafc5-112">Área de contenido.</span><span class="sxs-lookup"><span data-stu-id="cafc5-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="cafc5-113">Estados de marco</span><span class="sxs-lookup"><span data-stu-id="cafc5-113">Frame States</span></span>  
 <span data-ttu-id="cafc5-114">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="cafc5-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="cafc5-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="cafc5-115">VisualState Name</span></span>|<span data-ttu-id="cafc5-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="cafc5-116">VisualStateGroup Name</span></span>|<span data-ttu-id="cafc5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cafc5-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cafc5-118">Válido</span><span class="sxs-lookup"><span data-stu-id="cafc5-118">Valid</span></span>|<span data-ttu-id="cafc5-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafc5-119">ValidationStates</span></span>|<span data-ttu-id="cafc5-120">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="cafc5-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="cafc5-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="cafc5-121">InvalidFocused</span></span>|<span data-ttu-id="cafc5-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafc5-122">ValidationStates</span></span>|<span data-ttu-id="cafc5-123">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="cafc5-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="cafc5-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="cafc5-124">InvalidUnfocused</span></span>|<span data-ttu-id="cafc5-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafc5-125">ValidationStates</span></span>|<span data-ttu-id="cafc5-126">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="cafc5-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="cafc5-127">Ejemplo de ControlTemplate de Frame</span><span class="sxs-lookup"><span data-stu-id="cafc5-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="cafc5-128">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Frame>.</span><span class="sxs-lookup"><span data-stu-id="cafc5-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="cafc5-129">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="cafc5-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="cafc5-130">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="cafc5-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafc5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="cafc5-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="cafc5-132">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="cafc5-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="cafc5-133">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="cafc5-133">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="cafc5-134">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="cafc5-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="cafc5-135">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="cafc5-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
