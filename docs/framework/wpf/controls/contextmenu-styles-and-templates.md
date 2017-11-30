---
title: Estilos y plantillas de ContextMenu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a51860b21c21f8ce21510b04e817ec75d0e3b4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="e5d6e-102">Estilos y plantillas de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e5d6e-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="e5d6e-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="e5d6e-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e5d6e-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="e5d6e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="e5d6e-106">Partes de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e5d6e-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="e5d6e-107">El <xref:System.Windows.Controls.ContextMenu> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="e5d6e-108">Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ContextMenu>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="e5d6e-109">(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.ContextMenu>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).</span><span class="sxs-lookup"><span data-stu-id="e5d6e-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="e5d6e-110">Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="e5d6e-111">Estados de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e5d6e-111">ContextMenu States</span></span>  
 <span data-ttu-id="e5d6e-112">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="e5d6e-113">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="e5d6e-113">VisualState Name</span></span>|<span data-ttu-id="e5d6e-114">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e5d6e-114">VisualStateGroup Name</span></span>|<span data-ttu-id="e5d6e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5d6e-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e5d6e-116">Válido</span><span class="sxs-lookup"><span data-stu-id="e5d6e-116">Valid</span></span>|<span data-ttu-id="e5d6e-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5d6e-117">ValidationStates</span></span>|<span data-ttu-id="e5d6e-118">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e5d6e-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e5d6e-119">InvalidFocused</span></span>|<span data-ttu-id="e5d6e-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5d6e-120">ValidationStates</span></span>|<span data-ttu-id="e5d6e-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e5d6e-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e5d6e-122">InvalidUnfocused</span></span>|<span data-ttu-id="e5d6e-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e5d6e-123">ValidationStates</span></span>|<span data-ttu-id="e5d6e-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="e5d6e-125">Ejemplo de ControlTemplate de ContextMenu</span><span class="sxs-lookup"><span data-stu-id="e5d6e-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="e5d6e-126">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ContextMenu> control.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="e5d6e-127">El <xref:System.Windows.Controls.ControlTemplate> usa los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="e5d6e-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e5d6e-128">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="e5d6e-128">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d6e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5d6e-129">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="e5d6e-130">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="e5d6e-130">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="e5d6e-131">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="e5d6e-131">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="e5d6e-132">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="e5d6e-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="e5d6e-133">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e5d6e-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
