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
ms.openlocfilehash: f30a0abb3e4252737e513b531b8d5f49a0d47f0b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458445"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="4a6bc-102">Estilos y plantillas de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4a6bc-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="4a6bc-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="4a6bc-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4a6bc-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="4a6bc-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="4a6bc-106">Elementos ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4a6bc-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="4a6bc-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4a6bc-108">Parte</span><span class="sxs-lookup"><span data-stu-id="4a6bc-108">Part</span></span>|<span data-ttu-id="4a6bc-109">Type</span><span class="sxs-lookup"><span data-stu-id="4a6bc-109">Type</span></span>|<span data-ttu-id="4a6bc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a6bc-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4a6bc-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="4a6bc-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="4a6bc-112">Contenedor del elemento que indica la posición del <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="4a6bc-113">Estados de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4a6bc-113">ScrollBar States</span></span>  
 <span data-ttu-id="4a6bc-114">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4a6bc-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="4a6bc-115">VisualState Name</span></span>|<span data-ttu-id="4a6bc-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4a6bc-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4a6bc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a6bc-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4a6bc-118">Normal</span><span class="sxs-lookup"><span data-stu-id="4a6bc-118">Normal</span></span>|<span data-ttu-id="4a6bc-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-119">CommonStates</span></span>|<span data-ttu-id="4a6bc-120">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-120">The default state.</span></span>|  
|<span data-ttu-id="4a6bc-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4a6bc-121">MouseOver</span></span>|<span data-ttu-id="4a6bc-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-122">CommonStates</span></span>|<span data-ttu-id="4a6bc-123">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4a6bc-124">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="4a6bc-124">Disabled</span></span>|<span data-ttu-id="4a6bc-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-125">CommonStates</span></span>|<span data-ttu-id="4a6bc-126">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-126">The control is disabled.</span></span>|  
|<span data-ttu-id="4a6bc-127">Válido</span><span class="sxs-lookup"><span data-stu-id="4a6bc-127">Valid</span></span>|<span data-ttu-id="4a6bc-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-128">ValidationStates</span></span>|<span data-ttu-id="4a6bc-129">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4a6bc-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4a6bc-130">InvalidFocused</span></span>|<span data-ttu-id="4a6bc-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-131">ValidationStates</span></span>|<span data-ttu-id="4a6bc-132">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="4a6bc-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4a6bc-133">InvalidUnfocused</span></span>|<span data-ttu-id="4a6bc-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a6bc-134">ValidationStates</span></span>|<span data-ttu-id="4a6bc-135">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="4a6bc-136">Ejemplo de ControlTemplate de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4a6bc-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="4a6bc-137">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="4a6bc-138">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4a6bc-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4a6bc-139">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4a6bc-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6bc-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a6bc-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4a6bc-141">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="4a6bc-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="4a6bc-142">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="4a6bc-142">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="4a6bc-143">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4a6bc-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4a6bc-144">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4a6bc-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
