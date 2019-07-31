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
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671979"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="bc403-102">Estilos y plantillas de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bc403-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="bc403-103">En este tema se describen los estilos y las <xref:System.Windows.Controls.Primitives.ScrollBar> plantillas del control.</span><span class="sxs-lookup"><span data-stu-id="bc403-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="bc403-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="bc403-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="bc403-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="bc403-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="bc403-106">Elementos ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bc403-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="bc403-107">En la tabla siguiente se enumeran las partes <xref:System.Windows.Controls.Primitives.ScrollBar> con nombre para el control.</span><span class="sxs-lookup"><span data-stu-id="bc403-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="bc403-108">Parte</span><span class="sxs-lookup"><span data-stu-id="bc403-108">Part</span></span>|<span data-ttu-id="bc403-109">Type</span><span class="sxs-lookup"><span data-stu-id="bc403-109">Type</span></span>|<span data-ttu-id="bc403-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc403-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="bc403-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="bc403-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="bc403-112">Contenedor del elemento que indica la posición de <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="bc403-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="bc403-113">Estados de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bc403-113">ScrollBar States</span></span>  
 <span data-ttu-id="bc403-114">En la tabla siguiente se enumeran los Estados <xref:System.Windows.Controls.Primitives.ScrollBar> visuales del control.</span><span class="sxs-lookup"><span data-stu-id="bc403-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="bc403-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="bc403-115">VisualState Name</span></span>|<span data-ttu-id="bc403-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="bc403-116">VisualStateGroup Name</span></span>|<span data-ttu-id="bc403-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bc403-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="bc403-118">Normal</span><span class="sxs-lookup"><span data-stu-id="bc403-118">Normal</span></span>|<span data-ttu-id="bc403-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc403-119">CommonStates</span></span>|<span data-ttu-id="bc403-120">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bc403-120">The default state.</span></span>|  
|<span data-ttu-id="bc403-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bc403-121">MouseOver</span></span>|<span data-ttu-id="bc403-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc403-122">CommonStates</span></span>|<span data-ttu-id="bc403-123">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="bc403-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="bc403-124">Disabled</span><span class="sxs-lookup"><span data-stu-id="bc403-124">Disabled</span></span>|<span data-ttu-id="bc403-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="bc403-125">CommonStates</span></span>|<span data-ttu-id="bc403-126">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bc403-126">The control is disabled.</span></span>|  
|<span data-ttu-id="bc403-127">Válido</span><span class="sxs-lookup"><span data-stu-id="bc403-127">Valid</span></span>|<span data-ttu-id="bc403-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc403-128">ValidationStates</span></span>|<span data-ttu-id="bc403-129">El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="bc403-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="bc403-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="bc403-130">InvalidFocused</span></span>|<span data-ttu-id="bc403-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc403-131">ValidationStates</span></span>|<span data-ttu-id="bc403-132">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="bc403-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="bc403-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="bc403-133">InvalidUnfocused</span></span>|<span data-ttu-id="bc403-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="bc403-134">ValidationStates</span></span>|<span data-ttu-id="bc403-135">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="bc403-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="bc403-136">Ejemplo de ControlTemplate de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bc403-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="bc403-137">En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> un para <xref:System.Windows.Controls.Primitives.ScrollBar> el control.</span><span class="sxs-lookup"><span data-stu-id="bc403-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="bc403-138">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="bc403-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="bc403-139">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="bc403-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc403-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc403-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="bc403-141">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="bc403-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="bc403-142">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="bc403-142">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="bc403-143">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="bc403-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="bc403-144">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="bc403-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
