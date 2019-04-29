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
ms.openlocfilehash: 1cbb8d54a544b70b4a484c06c6bb2e9ca25029da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790746"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="badd1-102">Estilos y plantillas de ToolBar</span><span class="sxs-lookup"><span data-stu-id="badd1-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="badd1-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="badd1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="badd1-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="badd1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="badd1-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="badd1-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="badd1-106">Partes de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="badd1-106">ToolBar Parts</span></span>  
 <span data-ttu-id="badd1-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="badd1-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="badd1-108">Parte</span><span class="sxs-lookup"><span data-stu-id="badd1-108">Part</span></span>|<span data-ttu-id="badd1-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="badd1-109">Type</span></span>|<span data-ttu-id="badd1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="badd1-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="badd1-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="badd1-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="badd1-112">El objeto que contiene los controles en el <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="badd1-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="badd1-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="badd1-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="badd1-114">El objeto que contiene los controles que se encuentran en el área de desbordamiento de la <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="badd1-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="badd1-115">Cuando creas un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="badd1-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="badd1-116">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento en el <xref:System.Windows.Controls.ToolBar>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="badd1-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="badd1-117">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> el nombre, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="badd1-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="badd1-118">Estados de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="badd1-118">ToolBar States</span></span>  
 <span data-ttu-id="badd1-119">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="badd1-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="badd1-120">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="badd1-120">VisualState Name</span></span>|<span data-ttu-id="badd1-121">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="badd1-121">VisualStateGroup Name</span></span>|<span data-ttu-id="badd1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="badd1-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="badd1-123">Válido</span><span class="sxs-lookup"><span data-stu-id="badd1-123">Valid</span></span>|<span data-ttu-id="badd1-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="badd1-124">ValidationStates</span></span>|<span data-ttu-id="badd1-125">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="badd1-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="badd1-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="badd1-126">InvalidFocused</span></span>|<span data-ttu-id="badd1-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="badd1-127">ValidationStates</span></span>|<span data-ttu-id="badd1-128">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="badd1-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="badd1-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="badd1-129">InvalidUnfocused</span></span>|<span data-ttu-id="badd1-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="badd1-130">ValidationStates</span></span>|<span data-ttu-id="badd1-131">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="badd1-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="badd1-132">Ejemplo de ControlTemplate de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="badd1-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="badd1-133">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="badd1-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="badd1-134">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="badd1-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="badd1-135">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="badd1-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badd1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="badd1-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="badd1-137">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="badd1-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="badd1-138">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="badd1-138">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="badd1-139">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="badd1-139">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="badd1-140">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="badd1-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
