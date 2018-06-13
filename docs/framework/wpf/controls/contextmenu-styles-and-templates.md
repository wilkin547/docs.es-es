---
title: Estilos y plantillas de ContextMenu
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 671fb0a4f178c9e16149f6d47945670ea0e64d48
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457418"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="002a6-102">Estilos y plantillas de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="002a6-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="002a6-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="002a6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="002a6-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="002a6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="002a6-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="002a6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="002a6-106">Partes de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="002a6-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="002a6-107">El <xref:System.Windows.Controls.ContextMenu> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="002a6-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="002a6-108">Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ContextMenu>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="002a6-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="002a6-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.ContextMenu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).</span><span class="sxs-lookup"><span data-stu-id="002a6-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="002a6-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="002a6-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="002a6-111">Estados de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="002a6-111">ContextMenu States</span></span>  
 <span data-ttu-id="002a6-112">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="002a6-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="002a6-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="002a6-113">VisualState Name</span></span>|<span data-ttu-id="002a6-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="002a6-114">VisualStateGroup Name</span></span>|<span data-ttu-id="002a6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="002a6-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="002a6-116">Válido</span><span class="sxs-lookup"><span data-stu-id="002a6-116">Valid</span></span>|<span data-ttu-id="002a6-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="002a6-117">ValidationStates</span></span>|<span data-ttu-id="002a6-118">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="002a6-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="002a6-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="002a6-119">InvalidFocused</span></span>|<span data-ttu-id="002a6-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="002a6-120">ValidationStates</span></span>|<span data-ttu-id="002a6-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="002a6-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="002a6-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="002a6-122">InvalidUnfocused</span></span>|<span data-ttu-id="002a6-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="002a6-123">ValidationStates</span></span>|<span data-ttu-id="002a6-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="002a6-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="002a6-125">Ejemplo de ControlTemplate de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="002a6-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="002a6-126">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="002a6-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="002a6-127">El <xref:System.Windows.Controls.ControlTemplate> usa los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="002a6-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="002a6-128">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="002a6-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002a6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="002a6-129">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="002a6-130">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="002a6-130">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="002a6-131">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="002a6-131">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="002a6-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="002a6-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="002a6-133">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="002a6-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
