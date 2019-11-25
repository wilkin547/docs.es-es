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
ms.openlocfilehash: 35fcd9c15bf44d15a08c16d58847698c5ec6e574
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283500"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="ef2cc-102">Estilos y plantillas de etiquetas</span><span class="sxs-lookup"><span data-stu-id="ef2cc-102">Label Styles and Templates</span></span>
<span data-ttu-id="ef2cc-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="ef2cc-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ef2cc-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="ef2cc-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="ef2cc-106">Elementos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="ef2cc-106">Label Parts</span></span>  
 <span data-ttu-id="ef2cc-107">El control <xref:System.Windows.Controls.Label> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="ef2cc-108">Estados de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="ef2cc-108">Label States</span></span>  
 <span data-ttu-id="ef2cc-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="ef2cc-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="ef2cc-110">VisualState Name</span></span>|<span data-ttu-id="ef2cc-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ef2cc-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ef2cc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef2cc-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ef2cc-113">Válido</span><span class="sxs-lookup"><span data-stu-id="ef2cc-113">Valid</span></span>|<span data-ttu-id="ef2cc-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef2cc-114">ValidationStates</span></span>|<span data-ttu-id="ef2cc-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ef2cc-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ef2cc-116">InvalidFocused</span></span>|<span data-ttu-id="ef2cc-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef2cc-117">ValidationStates</span></span>|<span data-ttu-id="ef2cc-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ef2cc-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ef2cc-119">InvalidUnfocused</span></span>|<span data-ttu-id="ef2cc-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef2cc-120">ValidationStates</span></span>|<span data-ttu-id="ef2cc-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="ef2cc-122">Ejemplo de etiqueta ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ef2cc-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="ef2cc-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="ef2cc-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="ef2cc-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ef2cc-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ef2cc-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2cc-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef2cc-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ef2cc-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="ef2cc-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="ef2cc-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="ef2cc-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="ef2cc-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ef2cc-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ef2cc-130">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="ef2cc-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
