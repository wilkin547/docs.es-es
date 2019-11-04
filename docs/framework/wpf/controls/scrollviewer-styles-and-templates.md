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
ms.openlocfilehash: 70a2002ab114f2bbd6a4e550ae9006e214ee27a5
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458418"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="16aa7-102">Estilos y plantillas de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="16aa7-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="16aa7-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="16aa7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="16aa7-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="16aa7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="16aa7-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="16aa7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="16aa7-106">Elementos ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="16aa7-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="16aa7-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="16aa7-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="16aa7-108">Parte</span><span class="sxs-lookup"><span data-stu-id="16aa7-108">Part</span></span>|<span data-ttu-id="16aa7-109">Type</span><span class="sxs-lookup"><span data-stu-id="16aa7-109">Type</span></span>|<span data-ttu-id="16aa7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="16aa7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="16aa7-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="16aa7-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="16aa7-112">Marcador de posición para el contenido de la <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="16aa7-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="16aa7-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="16aa7-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="16aa7-114"><xref:System.Windows.Controls.Primitives.ScrollBar> que se utiliza para desplazar el contenido horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="16aa7-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="16aa7-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="16aa7-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="16aa7-116"><xref:System.Windows.Controls.Primitives.ScrollBar> que se utiliza para desplazar el contenido verticalmente.</span><span class="sxs-lookup"><span data-stu-id="16aa7-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="16aa7-117">Estados de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="16aa7-117">ScrollViewer States</span></span>  
 <span data-ttu-id="16aa7-118">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="16aa7-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="16aa7-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="16aa7-119">VisualState Name</span></span>|<span data-ttu-id="16aa7-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="16aa7-120">VisualStateGroup Name</span></span>|<span data-ttu-id="16aa7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="16aa7-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="16aa7-122">Válido</span><span class="sxs-lookup"><span data-stu-id="16aa7-122">Valid</span></span>|<span data-ttu-id="16aa7-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16aa7-123">ValidationStates</span></span>|<span data-ttu-id="16aa7-124">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="16aa7-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="16aa7-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="16aa7-125">InvalidFocused</span></span>|<span data-ttu-id="16aa7-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16aa7-126">ValidationStates</span></span>|<span data-ttu-id="16aa7-127">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="16aa7-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="16aa7-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="16aa7-128">InvalidUnfocused</span></span>|<span data-ttu-id="16aa7-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="16aa7-129">ValidationStates</span></span>|<span data-ttu-id="16aa7-130">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="16aa7-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="16aa7-131">Ejemplo de ControlTemplate de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="16aa7-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="16aa7-132">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="16aa7-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="16aa7-133">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="16aa7-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="16aa7-134">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="16aa7-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aa7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="16aa7-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="16aa7-136">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="16aa7-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="16aa7-137">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="16aa7-137">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="16aa7-138">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="16aa7-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="16aa7-139">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="16aa7-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
