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
ms.openlocfilehash: 22b2206067302f621a94a1e9abca1607792b3393
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052890"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="f4747-102">Estilos y plantillas de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="f4747-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="f4747-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span><span class="sxs-lookup"><span data-stu-id="f4747-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="f4747-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="f4747-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f4747-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f4747-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="f4747-106">Partes de la barra de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="f4747-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="f4747-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span><span class="sxs-lookup"><span data-stu-id="f4747-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="f4747-108">Parte</span><span class="sxs-lookup"><span data-stu-id="f4747-108">Part</span></span>|<span data-ttu-id="f4747-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4747-109">Type</span></span>|<span data-ttu-id="f4747-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4747-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f4747-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="f4747-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="f4747-112">El contenedor para el elemento que indica la posición de la <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="f4747-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="f4747-113">Estados de la barra de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="f4747-113">ScrollBar States</span></span>  
 <span data-ttu-id="f4747-114">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span><span class="sxs-lookup"><span data-stu-id="f4747-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="f4747-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="f4747-115">VisualState Name</span></span>|<span data-ttu-id="f4747-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f4747-116">VisualStateGroup Name</span></span>|<span data-ttu-id="f4747-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4747-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f4747-118">Normal</span><span class="sxs-lookup"><span data-stu-id="f4747-118">Normal</span></span>|<span data-ttu-id="f4747-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f4747-119">CommonStates</span></span>|<span data-ttu-id="f4747-120">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f4747-120">The default state.</span></span>|  
|<span data-ttu-id="f4747-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f4747-121">MouseOver</span></span>|<span data-ttu-id="f4747-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f4747-122">CommonStates</span></span>|<span data-ttu-id="f4747-123">El puntero del mouse se coloca sobre el control.</span><span class="sxs-lookup"><span data-stu-id="f4747-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f4747-124">Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f4747-124">Disabled</span></span>|<span data-ttu-id="f4747-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f4747-125">CommonStates</span></span>|<span data-ttu-id="f4747-126">El control está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f4747-126">The control is disabled.</span></span>|  
|<span data-ttu-id="f4747-127">Válido</span><span class="sxs-lookup"><span data-stu-id="f4747-127">Valid</span></span>|<span data-ttu-id="f4747-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4747-128">ValidationStates</span></span>|<span data-ttu-id="f4747-129">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="f4747-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f4747-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f4747-130">InvalidFocused</span></span>|<span data-ttu-id="f4747-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4747-131">ValidationStates</span></span>|<span data-ttu-id="f4747-132">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f4747-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f4747-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f4747-133">InvalidUnfocused</span></span>|<span data-ttu-id="f4747-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4747-134">ValidationStates</span></span>|<span data-ttu-id="f4747-135">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f4747-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="f4747-136">Ejemplo de ControlTemplate de ScrollBar</span><span class="sxs-lookup"><span data-stu-id="f4747-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="f4747-137">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span><span class="sxs-lookup"><span data-stu-id="f4747-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="f4747-138">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f4747-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f4747-139">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f4747-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4747-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4747-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f4747-141">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="f4747-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="f4747-142">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="f4747-142">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="f4747-143">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f4747-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f4747-144">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f4747-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
