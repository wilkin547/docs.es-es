---
title: Estilos y plantillas de NavigationWindow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b638d43fb59506572e2ccddd9da7188639bff279
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="52555-102">Estilos y plantillas de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="52555-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="52555-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="52555-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="52555-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="52555-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="52555-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="52555-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="52555-106">Partes de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="52555-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="52555-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="52555-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="52555-108">Parte</span><span class="sxs-lookup"><span data-stu-id="52555-108">Part</span></span>|<span data-ttu-id="52555-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="52555-109">Type</span></span>|<span data-ttu-id="52555-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="52555-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="52555-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="52555-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="52555-112">El área para el contenido.</span><span class="sxs-lookup"><span data-stu-id="52555-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="52555-113">Estados de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="52555-113">NavigationWindow States</span></span>  
 <span data-ttu-id="52555-114">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="52555-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="52555-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="52555-115">VisualState Name</span></span>|<span data-ttu-id="52555-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="52555-116">VisualStateGroup Name</span></span>|<span data-ttu-id="52555-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="52555-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="52555-118">Válido</span><span class="sxs-lookup"><span data-stu-id="52555-118">Valid</span></span>|<span data-ttu-id="52555-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52555-119">ValidationStates</span></span>|<span data-ttu-id="52555-120">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="52555-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="52555-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="52555-121">InvalidFocused</span></span>|<span data-ttu-id="52555-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52555-122">ValidationStates</span></span>|<span data-ttu-id="52555-123">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="52555-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="52555-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="52555-124">InvalidUnfocused</span></span>|<span data-ttu-id="52555-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52555-125">ValidationStates</span></span>|<span data-ttu-id="52555-126">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="52555-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="52555-127">Ejemplo de ControlTemplate de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="52555-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="52555-128">Aunque este ejemplo contiene todos los elementos que se definen en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Navigation.NavigationWindow> de forma predeterminada, los valores específicos deben considerarse ejemplos.</span><span class="sxs-lookup"><span data-stu-id="52555-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="52555-129">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="52555-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="52555-130">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="52555-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52555-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="52555-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="52555-132">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="52555-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="52555-133">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="52555-133">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="52555-134">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="52555-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="52555-135">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="52555-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
