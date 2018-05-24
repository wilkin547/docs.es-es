---
title: Estilos y plantillas de etiquetas
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: 9d2f5e4d886d8fc46ecb14dd4f1bda67debdae97
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="33650-102">Estilos y plantillas de etiquetas</span><span class="sxs-lookup"><span data-stu-id="33650-102">Label Styles and Templates</span></span>
<span data-ttu-id="33650-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="33650-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="33650-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="33650-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="33650-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="33650-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="33650-106">Partes de etiqueta</span><span class="sxs-lookup"><span data-stu-id="33650-106">Label Parts</span></span>  
 <span data-ttu-id="33650-107">El <xref:System.Windows.Controls.Label> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="33650-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="33650-108">Estados de etiqueta</span><span class="sxs-lookup"><span data-stu-id="33650-108">Label States</span></span>  
 <span data-ttu-id="33650-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="33650-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="33650-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="33650-110">VisualState Name</span></span>|<span data-ttu-id="33650-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="33650-111">VisualStateGroup Name</span></span>|<span data-ttu-id="33650-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="33650-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33650-113">Válido</span><span class="sxs-lookup"><span data-stu-id="33650-113">Valid</span></span>|<span data-ttu-id="33650-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33650-114">ValidationStates</span></span>|<span data-ttu-id="33650-115">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="33650-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="33650-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="33650-116">InvalidFocused</span></span>|<span data-ttu-id="33650-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33650-117">ValidationStates</span></span>|<span data-ttu-id="33650-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="33650-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="33650-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="33650-119">InvalidUnfocused</span></span>|<span data-ttu-id="33650-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33650-120">ValidationStates</span></span>|<span data-ttu-id="33650-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="33650-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="33650-122">Ejemplo de ControlTemplate de etiqueta</span><span class="sxs-lookup"><span data-stu-id="33650-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="33650-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="33650-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="33650-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="33650-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="33650-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="33650-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33650-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="33650-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="33650-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="33650-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="33650-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="33650-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="33650-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="33650-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="33650-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="33650-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
