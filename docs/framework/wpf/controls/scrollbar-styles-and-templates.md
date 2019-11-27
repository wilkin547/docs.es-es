---
title: Estilos y plantillas de ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283412"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="0ab77-102">Estilos y plantillas de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0ab77-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="0ab77-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0ab77-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="0ab77-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="0ab77-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0ab77-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="0ab77-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="0ab77-106">Elementos ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0ab77-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="0ab77-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0ab77-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0ab77-108">Parte</span><span class="sxs-lookup"><span data-stu-id="0ab77-108">Part</span></span>|<span data-ttu-id="0ab77-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ab77-109">Type</span></span>|<span data-ttu-id="0ab77-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ab77-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0ab77-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="0ab77-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="0ab77-112">Contenedor del elemento que indica la posición del <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0ab77-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="0ab77-113">Estados de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0ab77-113">ScrollBar States</span></span>  
 <span data-ttu-id="0ab77-114">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0ab77-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0ab77-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="0ab77-115">VisualState Name</span></span>|<span data-ttu-id="0ab77-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0ab77-116">VisualStateGroup Name</span></span>|<span data-ttu-id="0ab77-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ab77-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0ab77-118">Normal</span><span class="sxs-lookup"><span data-stu-id="0ab77-118">Normal</span></span>|<span data-ttu-id="0ab77-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-119">CommonStates</span></span>|<span data-ttu-id="0ab77-120">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ab77-120">The default state.</span></span>|  
|<span data-ttu-id="0ab77-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0ab77-121">MouseOver</span></span>|<span data-ttu-id="0ab77-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-122">CommonStates</span></span>|<span data-ttu-id="0ab77-123">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="0ab77-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0ab77-124">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="0ab77-124">Disabled</span></span>|<span data-ttu-id="0ab77-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-125">CommonStates</span></span>|<span data-ttu-id="0ab77-126">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ab77-126">The control is disabled.</span></span>|  
|<span data-ttu-id="0ab77-127">Válido</span><span class="sxs-lookup"><span data-stu-id="0ab77-127">Valid</span></span>|<span data-ttu-id="0ab77-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-128">ValidationStates</span></span>|<span data-ttu-id="0ab77-129">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="0ab77-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0ab77-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0ab77-130">InvalidFocused</span></span>|<span data-ttu-id="0ab77-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-131">ValidationStates</span></span>|<span data-ttu-id="0ab77-132">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ab77-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="0ab77-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0ab77-133">InvalidUnfocused</span></span>|<span data-ttu-id="0ab77-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0ab77-134">ValidationStates</span></span>|<span data-ttu-id="0ab77-135">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="0ab77-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="0ab77-136">Ejemplo de ControlTemplate de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0ab77-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0ab77-137">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0ab77-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="0ab77-138">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="0ab77-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0ab77-139">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0ab77-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab77-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ab77-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0ab77-141">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="0ab77-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="0ab77-142">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="0ab77-142">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="0ab77-143">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="0ab77-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0ab77-144">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="0ab77-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
