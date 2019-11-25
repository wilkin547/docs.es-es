---
title: Estilos y plantillas de StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283374"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="8101a-102">Estilos y plantillas de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8101a-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="8101a-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="8101a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="8101a-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="8101a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8101a-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="8101a-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="8101a-106">Partes de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8101a-106">StatusBar Parts</span></span>  
 <span data-ttu-id="8101a-107">El control <xref:System.Windows.Controls.Primitives.StatusBar> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="8101a-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="8101a-108">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8101a-108">StatusBar States</span></span>  
 <span data-ttu-id="8101a-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="8101a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="8101a-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8101a-110">VisualState Name</span></span>|<span data-ttu-id="8101a-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8101a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="8101a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8101a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8101a-113">Válido</span><span class="sxs-lookup"><span data-stu-id="8101a-113">Valid</span></span>|<span data-ttu-id="8101a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-114">ValidationStates</span></span>|<span data-ttu-id="8101a-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="8101a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8101a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8101a-116">InvalidFocused</span></span>|<span data-ttu-id="8101a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-117">ValidationStates</span></span>|<span data-ttu-id="8101a-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8101a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8101a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8101a-119">InvalidUnfocused</span></span>|<span data-ttu-id="8101a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-120">ValidationStates</span></span>|<span data-ttu-id="8101a-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8101a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="8101a-122">Elementos StatusBarItem</span><span class="sxs-lookup"><span data-stu-id="8101a-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="8101a-123">El control <xref:System.Windows.Controls.Primitives.StatusBarItem> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="8101a-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="8101a-124">Estados de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8101a-124">StatusBar States</span></span>  
 <span data-ttu-id="8101a-125">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.StatusBarItem>.</span><span class="sxs-lookup"><span data-stu-id="8101a-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="8101a-126">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="8101a-126">VisualState Name</span></span>|<span data-ttu-id="8101a-127">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="8101a-127">VisualStateGroup Name</span></span>|<span data-ttu-id="8101a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="8101a-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8101a-129">Válido</span><span class="sxs-lookup"><span data-stu-id="8101a-129">Valid</span></span>|<span data-ttu-id="8101a-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-130">ValidationStates</span></span>|<span data-ttu-id="8101a-131">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="8101a-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8101a-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8101a-132">InvalidFocused</span></span>|<span data-ttu-id="8101a-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-133">ValidationStates</span></span>|<span data-ttu-id="8101a-134">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8101a-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8101a-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8101a-135">InvalidUnfocused</span></span>|<span data-ttu-id="8101a-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8101a-136">ValidationStates</span></span>|<span data-ttu-id="8101a-137">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="8101a-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="8101a-138">Ejemplo de ControlTemplate de StatusBar</span><span class="sxs-lookup"><span data-stu-id="8101a-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="8101a-139">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="8101a-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="8101a-140">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="8101a-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8101a-141">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="8101a-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8101a-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="8101a-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8101a-143">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="8101a-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="8101a-144">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="8101a-144">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="8101a-145">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="8101a-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8101a-146">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="8101a-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
