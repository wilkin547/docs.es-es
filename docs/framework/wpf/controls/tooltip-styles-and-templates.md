---
title: Estilos y plantillas de ToolTip
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 424cfc196474d342f1efdc049350acb71b8fb1eb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375368"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="6f855-102">Estilos y plantillas de ToolTip</span><span class="sxs-lookup"><span data-stu-id="6f855-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="6f855-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="6f855-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="6f855-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="6f855-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6f855-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6f855-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="6f855-106">Partes de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6f855-106">ToolTip Parts</span></span>  
 <span data-ttu-id="6f855-107">El <xref:System.Windows.Controls.ToolTip> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="6f855-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="6f855-108">Estados de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6f855-108">ToolTip States</span></span>  
 <span data-ttu-id="6f855-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="6f855-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="6f855-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="6f855-110">VisualState Name</span></span>|<span data-ttu-id="6f855-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6f855-111">VisualStateGroup Name</span></span>|<span data-ttu-id="6f855-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f855-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6f855-113">Cerrado</span><span class="sxs-lookup"><span data-stu-id="6f855-113">Closed</span></span>|<span data-ttu-id="6f855-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="6f855-114">OpenStates</span></span>|<span data-ttu-id="6f855-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f855-115">The default state.</span></span>|  
|<span data-ttu-id="6f855-116">Abrir</span><span class="sxs-lookup"><span data-stu-id="6f855-116">Open</span></span>|<span data-ttu-id="6f855-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="6f855-117">OpenStates</span></span>|<span data-ttu-id="6f855-118">El <xref:System.Windows.Controls.ToolTip> está visible.</span><span class="sxs-lookup"><span data-stu-id="6f855-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="6f855-119">Válido</span><span class="sxs-lookup"><span data-stu-id="6f855-119">Valid</span></span>|<span data-ttu-id="6f855-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f855-120">ValidationStates</span></span>|<span data-ttu-id="6f855-121">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="6f855-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6f855-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6f855-122">InvalidFocused</span></span>|<span data-ttu-id="6f855-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f855-123">ValidationStates</span></span>|<span data-ttu-id="6f855-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6f855-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6f855-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6f855-125">InvalidUnfocused</span></span>|<span data-ttu-id="6f855-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6f855-126">ValidationStates</span></span>|<span data-ttu-id="6f855-127">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="6f855-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="6f855-128">Ejemplo de ControlTemplate de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="6f855-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="6f855-129">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="6f855-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="6f855-130">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6f855-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6f855-131">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="6f855-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f855-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f855-132">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="6f855-133">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="6f855-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="6f855-134">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="6f855-134">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="6f855-135">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="6f855-135">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="6f855-136">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6f855-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
