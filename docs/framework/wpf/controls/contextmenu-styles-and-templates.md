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
ms.openlocfilehash: fa192e20ea84e96c9f85ff84e16c63b7f56c8a98
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283536"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="21d57-102">Estilos y plantillas de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="21d57-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="21d57-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="21d57-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="21d57-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="21d57-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="21d57-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="21d57-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="21d57-106">Elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="21d57-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="21d57-107">El control <xref:System.Windows.Controls.ContextMenu> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="21d57-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="21d57-108">Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ContextMenu>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="21d57-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="21d57-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ContextMenu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="21d57-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="21d57-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="21d57-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="21d57-111">Estados de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="21d57-111">ContextMenu States</span></span>  
 <span data-ttu-id="21d57-112">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="21d57-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="21d57-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="21d57-113">VisualState Name</span></span>|<span data-ttu-id="21d57-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="21d57-114">VisualStateGroup Name</span></span>|<span data-ttu-id="21d57-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="21d57-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="21d57-116">Válido</span><span class="sxs-lookup"><span data-stu-id="21d57-116">Valid</span></span>|<span data-ttu-id="21d57-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21d57-117">ValidationStates</span></span>|<span data-ttu-id="21d57-118">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="21d57-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="21d57-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="21d57-119">InvalidFocused</span></span>|<span data-ttu-id="21d57-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21d57-120">ValidationStates</span></span>|<span data-ttu-id="21d57-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="21d57-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="21d57-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="21d57-122">InvalidUnfocused</span></span>|<span data-ttu-id="21d57-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="21d57-123">ValidationStates</span></span>|<span data-ttu-id="21d57-124">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="21d57-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="21d57-125">Ejemplo de ControlTemplate de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="21d57-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="21d57-126">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="21d57-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="21d57-127">En el <xref:System.Windows.Controls.ControlTemplate> se usan los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="21d57-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="21d57-128">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="21d57-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d57-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="21d57-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="21d57-130">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="21d57-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="21d57-131">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="21d57-131">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="21d57-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="21d57-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="21d57-133">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="21d57-133">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
