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
ms.openlocfilehash: 4112306dab648d022e171401f5b9b362f2c91fdc
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460761"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="f4712-102">Estilos y plantillas de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f4712-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="f4712-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="f4712-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="f4712-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="f4712-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f4712-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="f4712-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="f4712-106">Elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f4712-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="f4712-107">El control <xref:System.Windows.Controls.ContextMenu> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="f4712-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="f4712-108">Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ContextMenu>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="f4712-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="f4712-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ContextMenu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="f4712-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="f4712-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="f4712-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="f4712-111">Estados de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f4712-111">ContextMenu States</span></span>  
 <span data-ttu-id="f4712-112">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="f4712-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="f4712-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="f4712-113">VisualState Name</span></span>|<span data-ttu-id="f4712-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f4712-114">VisualStateGroup Name</span></span>|<span data-ttu-id="f4712-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4712-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f4712-116">Válido</span><span class="sxs-lookup"><span data-stu-id="f4712-116">Valid</span></span>|<span data-ttu-id="f4712-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4712-117">ValidationStates</span></span>|<span data-ttu-id="f4712-118">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="f4712-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f4712-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f4712-119">InvalidFocused</span></span>|<span data-ttu-id="f4712-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4712-120">ValidationStates</span></span>|<span data-ttu-id="f4712-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f4712-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f4712-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f4712-122">InvalidUnfocused</span></span>|<span data-ttu-id="f4712-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4712-123">ValidationStates</span></span>|<span data-ttu-id="f4712-124">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f4712-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="f4712-125">Ejemplo de ControlTemplate de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f4712-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="f4712-126">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="f4712-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="f4712-127">En el <xref:System.Windows.Controls.ControlTemplate> se usan los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="f4712-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f4712-128">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f4712-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4712-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4712-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f4712-130">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="f4712-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="f4712-131">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="f4712-131">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="f4712-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f4712-132">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="f4712-133">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f4712-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
