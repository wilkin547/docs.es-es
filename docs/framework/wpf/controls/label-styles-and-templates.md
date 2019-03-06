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
ms.openlocfilehash: e77c27546f4575fb6fae1081ec5a64e904721586
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377539"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="bac51-102">Estilos y plantillas de etiquetas</span><span class="sxs-lookup"><span data-stu-id="bac51-102">Label Styles and Templates</span></span>
<span data-ttu-id="bac51-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="bac51-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="bac51-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="bac51-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bac51-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="bac51-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="bac51-106">Elementos de etiqueta</span><span class="sxs-lookup"><span data-stu-id="bac51-106">Label Parts</span></span>  
 <span data-ttu-id="bac51-107">El <xref:System.Windows.Controls.Label> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="bac51-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="bac51-108">Estados de etiqueta</span><span class="sxs-lookup"><span data-stu-id="bac51-108">Label States</span></span>  
 <span data-ttu-id="bac51-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="bac51-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="bac51-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="bac51-110">VisualState Name</span></span>|<span data-ttu-id="bac51-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="bac51-111">VisualStateGroup Name</span></span>|<span data-ttu-id="bac51-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bac51-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bac51-113">Válido</span><span class="sxs-lookup"><span data-stu-id="bac51-113">Valid</span></span>|<span data-ttu-id="bac51-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bac51-114">ValidationStates</span></span>|<span data-ttu-id="bac51-115">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="bac51-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bac51-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bac51-116">InvalidFocused</span></span>|<span data-ttu-id="bac51-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bac51-117">ValidationStates</span></span>|<span data-ttu-id="bac51-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="bac51-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="bac51-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bac51-119">InvalidUnfocused</span></span>|<span data-ttu-id="bac51-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bac51-120">ValidationStates</span></span>|<span data-ttu-id="bac51-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="bac51-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="bac51-122">Ejemplo de ControlTemplate de etiqueta</span><span class="sxs-lookup"><span data-stu-id="bac51-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="bac51-123">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Label> control.</span><span class="sxs-lookup"><span data-stu-id="bac51-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="bac51-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="bac51-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bac51-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="bac51-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac51-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="bac51-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bac51-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="bac51-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="bac51-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="bac51-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="bac51-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="bac51-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="bac51-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="bac51-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
