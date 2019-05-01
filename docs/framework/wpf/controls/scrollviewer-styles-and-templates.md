---
title: Estilos y plantillas de ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971033"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="253ce-102">Estilos y plantillas de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="253ce-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="253ce-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="253ce-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="253ce-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="253ce-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="253ce-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="253ce-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="253ce-106">Partes de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="253ce-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="253ce-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="253ce-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="253ce-108">Parte</span><span class="sxs-lookup"><span data-stu-id="253ce-108">Part</span></span>|<span data-ttu-id="253ce-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="253ce-109">Type</span></span>|<span data-ttu-id="253ce-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="253ce-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="253ce-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="253ce-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="253ce-112">El marcador de posición para el contenido de la <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="253ce-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="253ce-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="253ce-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="253ce-114">El <xref:System.Windows.Controls.Primitives.ScrollBar> utilizado para desplazar el contenido horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="253ce-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="253ce-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="253ce-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="253ce-116">El <xref:System.Windows.Controls.Primitives.ScrollBar> utilizado para desplazar el contenido verticalmente.</span><span class="sxs-lookup"><span data-stu-id="253ce-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="253ce-117">Estados de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="253ce-117">ScrollViewer States</span></span>  
 <span data-ttu-id="253ce-118">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="253ce-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="253ce-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="253ce-119">VisualState Name</span></span>|<span data-ttu-id="253ce-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="253ce-120">VisualStateGroup Name</span></span>|<span data-ttu-id="253ce-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="253ce-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="253ce-122">Válido</span><span class="sxs-lookup"><span data-stu-id="253ce-122">Valid</span></span>|<span data-ttu-id="253ce-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="253ce-123">ValidationStates</span></span>|<span data-ttu-id="253ce-124">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="253ce-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="253ce-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="253ce-125">InvalidFocused</span></span>|<span data-ttu-id="253ce-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="253ce-126">ValidationStates</span></span>|<span data-ttu-id="253ce-127">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="253ce-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="253ce-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="253ce-128">InvalidUnfocused</span></span>|<span data-ttu-id="253ce-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="253ce-129">ValidationStates</span></span>|<span data-ttu-id="253ce-130">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="253ce-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="253ce-131">Ejemplo de ControlTemplate de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="253ce-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="253ce-132">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="253ce-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="253ce-133">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="253ce-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="253ce-134">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="253ce-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253ce-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="253ce-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="253ce-136">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="253ce-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="253ce-137">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="253ce-137">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="253ce-138">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="253ce-138">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="253ce-139">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="253ce-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
