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
ms.openlocfilehash: be26156d74f3a3509bf150e5611512172f08a14e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369073"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="4a13b-102">Estilos y plantillas de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4a13b-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="4a13b-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="4a13b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="4a13b-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="4a13b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4a13b-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="4a13b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="4a13b-106">Elementos ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4a13b-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="4a13b-107">El <xref:System.Windows.Controls.ContextMenu> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="4a13b-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="4a13b-108">Cuando creas un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ContextMenu>, la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="4a13b-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="4a13b-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento en el <xref:System.Windows.Controls.ContextMenu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).</span><span class="sxs-lookup"><span data-stu-id="4a13b-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="4a13b-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> el nombre, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="4a13b-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="4a13b-111">Estados de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4a13b-111">ContextMenu States</span></span>  
 <span data-ttu-id="4a13b-112">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="4a13b-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="4a13b-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="4a13b-113">VisualState Name</span></span>|<span data-ttu-id="4a13b-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="4a13b-114">VisualStateGroup Name</span></span>|<span data-ttu-id="4a13b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a13b-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4a13b-116">Válido</span><span class="sxs-lookup"><span data-stu-id="4a13b-116">Valid</span></span>|<span data-ttu-id="4a13b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a13b-117">ValidationStates</span></span>|<span data-ttu-id="4a13b-118">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="4a13b-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4a13b-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4a13b-119">InvalidFocused</span></span>|<span data-ttu-id="4a13b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a13b-120">ValidationStates</span></span>|<span data-ttu-id="4a13b-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4a13b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4a13b-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4a13b-122">InvalidUnfocused</span></span>|<span data-ttu-id="4a13b-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4a13b-123">ValidationStates</span></span>|<span data-ttu-id="4a13b-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="4a13b-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="4a13b-125">Ejemplo de ControlTemplate de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4a13b-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="4a13b-126">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="4a13b-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="4a13b-127">El <xref:System.Windows.Controls.ControlTemplate> usa los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="4a13b-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4a13b-128">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="4a13b-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a13b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a13b-129">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4a13b-130">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="4a13b-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="4a13b-131">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="4a13b-131">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="4a13b-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="4a13b-132">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4a13b-133">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4a13b-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
