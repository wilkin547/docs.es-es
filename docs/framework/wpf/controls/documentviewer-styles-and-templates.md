---
title: Estilos y plantillas de DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 7a812ff913703e3aa8408da8a11d28ee5adfa7fd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460350"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="a1e48-102">Estilos y plantillas de DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="a1e48-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="a1e48-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="a1e48-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="a1e48-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="a1e48-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a1e48-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="a1e48-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="a1e48-106">Elementos DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="a1e48-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="a1e48-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="a1e48-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="a1e48-108">Parte</span><span class="sxs-lookup"><span data-stu-id="a1e48-108">Part</span></span>|<span data-ttu-id="a1e48-109">Type</span><span class="sxs-lookup"><span data-stu-id="a1e48-109">Type</span></span>|<span data-ttu-id="a1e48-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e48-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a1e48-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="a1e48-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="a1e48-112">El contenido y el área de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="a1e48-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="a1e48-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="a1e48-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="a1e48-114">El cuadro de búsqueda, en la parte inferior de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a1e48-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="a1e48-115">Estados de DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="a1e48-115">DocumentViewer States</span></span>  
 <span data-ttu-id="a1e48-116">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="a1e48-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="a1e48-117">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="a1e48-117">VisualState Name</span></span>|<span data-ttu-id="a1e48-118">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a1e48-118">VisualStateGroup Name</span></span>|<span data-ttu-id="a1e48-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e48-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a1e48-120">Válido</span><span class="sxs-lookup"><span data-stu-id="a1e48-120">Valid</span></span>|<span data-ttu-id="a1e48-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1e48-121">ValidationStates</span></span>|<span data-ttu-id="a1e48-122">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="a1e48-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a1e48-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a1e48-123">InvalidFocused</span></span>|<span data-ttu-id="a1e48-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1e48-124">ValidationStates</span></span>|<span data-ttu-id="a1e48-125">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a1e48-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a1e48-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a1e48-126">InvalidUnfocused</span></span>|<span data-ttu-id="a1e48-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a1e48-127">ValidationStates</span></span>|<span data-ttu-id="a1e48-128">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a1e48-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="a1e48-129">Ejemplo de ControlTemplate de DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="a1e48-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="a1e48-130">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DocumentViewer>.</span><span class="sxs-lookup"><span data-stu-id="a1e48-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="a1e48-131">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a1e48-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a1e48-132">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a1e48-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e48-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e48-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a1e48-134">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="a1e48-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="a1e48-135">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="a1e48-135">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="a1e48-136">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a1e48-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a1e48-137">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a1e48-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
