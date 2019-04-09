---
title: Estilos y plantillas de GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 5ef8e4b44bc2b6072fa730f33c10191b64954f7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078998"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="662f4-102">Estilos y plantillas de GroupBox</span><span class="sxs-lookup"><span data-stu-id="662f4-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="662f4-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="662f4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="662f4-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="662f4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="662f4-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="662f4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="662f4-106">Partes de GroupBox</span><span class="sxs-lookup"><span data-stu-id="662f4-106">GroupBox Parts</span></span>  
 <span data-ttu-id="662f4-107">El <xref:System.Windows.Controls.GroupBox> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="662f4-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="662f4-108">Estados de GroupBox</span><span class="sxs-lookup"><span data-stu-id="662f4-108">GroupBox States</span></span>  
 <span data-ttu-id="662f4-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="662f4-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="662f4-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="662f4-110">VisualState Name</span></span>|<span data-ttu-id="662f4-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="662f4-111">VisualStateGroup Name</span></span>|<span data-ttu-id="662f4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="662f4-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="662f4-113">Válido</span><span class="sxs-lookup"><span data-stu-id="662f4-113">Valid</span></span>|<span data-ttu-id="662f4-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="662f4-114">ValidationStates</span></span>|<span data-ttu-id="662f4-115">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="662f4-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="662f4-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="662f4-116">InvalidFocused</span></span>|<span data-ttu-id="662f4-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="662f4-117">ValidationStates</span></span>|<span data-ttu-id="662f4-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="662f4-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="662f4-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="662f4-119">InvalidUnfocused</span></span>|<span data-ttu-id="662f4-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="662f4-120">ValidationStates</span></span>|<span data-ttu-id="662f4-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="662f4-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="662f4-122">Ejemplo de ControlTemplate de GroupBox</span><span class="sxs-lookup"><span data-stu-id="662f4-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="662f4-123">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="662f4-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="662f4-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="662f4-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="662f4-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="662f4-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="662f4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="662f4-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="662f4-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="662f4-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="662f4-128">Personalización de controles</span><span class="sxs-lookup"><span data-stu-id="662f4-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="662f4-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="662f4-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="662f4-130">Personalizar la apariencia de un control existente creando una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="662f4-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
