---
title: Estilos y plantillas de ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: b782e62500edd14b40b1267c3b7f92758210a5c0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458213"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="83ca7-102">Estilos y plantillas de ToolBar</span><span class="sxs-lookup"><span data-stu-id="83ca7-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="83ca7-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="83ca7-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="83ca7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="83ca7-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="83ca7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="83ca7-106">Elementos de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="83ca7-106">ToolBar Parts</span></span>  
 <span data-ttu-id="83ca7-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="83ca7-108">Parte</span><span class="sxs-lookup"><span data-stu-id="83ca7-108">Part</span></span>|<span data-ttu-id="83ca7-109">Type</span><span class="sxs-lookup"><span data-stu-id="83ca7-109">Type</span></span>|<span data-ttu-id="83ca7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="83ca7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="83ca7-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="83ca7-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="83ca7-112">Objeto que contiene los controles del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="83ca7-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="83ca7-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="83ca7-114">Objeto que contiene los controles que se encuentran en el área de desbordamiento del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="83ca7-115">Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="83ca7-116">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ToolBar>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="83ca7-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="83ca7-117">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="83ca7-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="83ca7-118">Estados de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="83ca7-118">ToolBar States</span></span>  
 <span data-ttu-id="83ca7-119">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="83ca7-120">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="83ca7-120">VisualState Name</span></span>|<span data-ttu-id="83ca7-121">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="83ca7-121">VisualStateGroup Name</span></span>|<span data-ttu-id="83ca7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="83ca7-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="83ca7-123">Válido</span><span class="sxs-lookup"><span data-stu-id="83ca7-123">Valid</span></span>|<span data-ttu-id="83ca7-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="83ca7-124">ValidationStates</span></span>|<span data-ttu-id="83ca7-125">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="83ca7-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="83ca7-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="83ca7-126">InvalidFocused</span></span>|<span data-ttu-id="83ca7-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="83ca7-127">ValidationStates</span></span>|<span data-ttu-id="83ca7-128">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="83ca7-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="83ca7-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="83ca7-129">InvalidUnfocused</span></span>|<span data-ttu-id="83ca7-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="83ca7-130">ValidationStates</span></span>|<span data-ttu-id="83ca7-131">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="83ca7-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="83ca7-132">Ejemplo de ControlTemplate de ToolBar</span><span class="sxs-lookup"><span data-stu-id="83ca7-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="83ca7-133">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="83ca7-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="83ca7-134">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="83ca7-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="83ca7-135">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="83ca7-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ca7-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="83ca7-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="83ca7-137">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="83ca7-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="83ca7-138">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="83ca7-138">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="83ca7-139">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="83ca7-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="83ca7-140">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="83ca7-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
