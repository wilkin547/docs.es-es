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
ms.openlocfilehash: 6b084cfa31efebe2456871a99cd810741aa26609
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131032"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="8d800-102">Estilos y plantillas de Frame</span><span class="sxs-lookup"><span data-stu-id="8d800-102">Frame Styles and Templates</span></span>
<span data-ttu-id="8d800-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="8d800-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="8d800-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="8d800-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8d800-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="8d800-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="8d800-106">Elementos de marco</span><span class="sxs-lookup"><span data-stu-id="8d800-106">Frame Parts</span></span>  
 <span data-ttu-id="8d800-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="8d800-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="8d800-108">Parte</span><span class="sxs-lookup"><span data-stu-id="8d800-108">Part</span></span>|<span data-ttu-id="8d800-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d800-109">Type</span></span>|<span data-ttu-id="8d800-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d800-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8d800-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="8d800-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="8d800-112">El área de contenido.</span><span class="sxs-lookup"><span data-stu-id="8d800-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="8d800-113">Estados de marco</span><span class="sxs-lookup"><span data-stu-id="8d800-113">Frame States</span></span>  
 <span data-ttu-id="8d800-114">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="8d800-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="8d800-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8d800-115">VisualState Name</span></span>|<span data-ttu-id="8d800-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8d800-116">VisualStateGroup Name</span></span>|<span data-ttu-id="8d800-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d800-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8d800-118">Válido</span><span class="sxs-lookup"><span data-stu-id="8d800-118">Valid</span></span>|<span data-ttu-id="8d800-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d800-119">ValidationStates</span></span>|<span data-ttu-id="8d800-120">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="8d800-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8d800-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8d800-121">InvalidFocused</span></span>|<span data-ttu-id="8d800-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d800-122">ValidationStates</span></span>|<span data-ttu-id="8d800-123">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8d800-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8d800-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8d800-124">InvalidUnfocused</span></span>|<span data-ttu-id="8d800-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8d800-125">ValidationStates</span></span>|<span data-ttu-id="8d800-126">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8d800-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="8d800-127">Ejemplo de ControlTemplate de marco</span><span class="sxs-lookup"><span data-stu-id="8d800-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="8d800-128">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="8d800-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="8d800-129">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d800-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8d800-130">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8d800-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d800-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d800-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8d800-132">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="8d800-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8d800-133">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="8d800-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8d800-134">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8d800-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="8d800-135">Personalizar la apariencia de un control existente creando una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8d800-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
