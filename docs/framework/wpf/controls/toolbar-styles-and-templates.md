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
ms.openlocfilehash: a984311234386cb205d5db35f18a743ca535ff05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283656"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="5d110-102">Estilos y plantillas de ToolBar</span><span class="sxs-lookup"><span data-stu-id="5d110-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="5d110-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="5d110-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="5d110-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5d110-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="5d110-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="5d110-106">Elementos de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="5d110-106">ToolBar Parts</span></span>  
 <span data-ttu-id="5d110-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="5d110-108">Parte</span><span class="sxs-lookup"><span data-stu-id="5d110-108">Part</span></span>|<span data-ttu-id="5d110-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d110-109">Type</span></span>|<span data-ttu-id="5d110-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d110-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5d110-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="5d110-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="5d110-112">Objeto que contiene los controles del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="5d110-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="5d110-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="5d110-114">Objeto que contiene los controles que se encuentran en el área de desbordamiento del <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="5d110-115">Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="5d110-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="5d110-116">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ToolBar>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="5d110-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="5d110-117">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="5d110-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="5d110-118">Estados de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="5d110-118">ToolBar States</span></span>  
 <span data-ttu-id="5d110-119">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="5d110-120">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="5d110-120">VisualState Name</span></span>|<span data-ttu-id="5d110-121">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="5d110-121">VisualStateGroup Name</span></span>|<span data-ttu-id="5d110-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d110-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5d110-123">Válido</span><span class="sxs-lookup"><span data-stu-id="5d110-123">Valid</span></span>|<span data-ttu-id="5d110-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5d110-124">ValidationStates</span></span>|<span data-ttu-id="5d110-125">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="5d110-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5d110-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5d110-126">InvalidFocused</span></span>|<span data-ttu-id="5d110-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5d110-127">ValidationStates</span></span>|<span data-ttu-id="5d110-128">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="5d110-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5d110-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5d110-129">InvalidUnfocused</span></span>|<span data-ttu-id="5d110-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5d110-130">ValidationStates</span></span>|<span data-ttu-id="5d110-131">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="5d110-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="5d110-132">Ejemplo de ControlTemplate de ToolBar</span><span class="sxs-lookup"><span data-stu-id="5d110-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="5d110-133">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="5d110-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="5d110-134">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="5d110-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5d110-135">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="5d110-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d110-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d110-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5d110-137">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="5d110-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="5d110-138">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="5d110-138">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="5d110-139">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="5d110-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="5d110-140">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="5d110-140">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
