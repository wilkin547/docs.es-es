---
title: Estilos y plantillas de ScrollViewer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74f8a693a143e1c6788dd79a1c1bbd1954f8cfd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="7d1c3-102">Estilos y plantillas de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d1c3-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="7d1c3-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="7d1c3-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7d1c3-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="7d1c3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="7d1c3-106">Partes de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d1c3-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="7d1c3-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="7d1c3-108">Parte</span><span class="sxs-lookup"><span data-stu-id="7d1c3-108">Part</span></span>|<span data-ttu-id="7d1c3-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="7d1c3-109">Type</span></span>|<span data-ttu-id="7d1c3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d1c3-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7d1c3-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="7d1c3-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="7d1c3-112">El marcador de posición para el contenido en el <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="7d1c3-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="7d1c3-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="7d1c3-114">El <xref:System.Windows.Controls.Primitives.ScrollBar> utilizado para desplazar el contenido horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="7d1c3-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="7d1c3-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="7d1c3-116">El <xref:System.Windows.Controls.Primitives.ScrollBar> utilizado para desplazar el contenido verticalmente.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="7d1c3-117">Estados de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d1c3-117">ScrollViewer States</span></span>  
 <span data-ttu-id="7d1c3-118">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="7d1c3-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="7d1c3-119">VisualState Name</span></span>|<span data-ttu-id="7d1c3-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="7d1c3-120">VisualStateGroup Name</span></span>|<span data-ttu-id="7d1c3-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d1c3-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7d1c3-122">Válido</span><span class="sxs-lookup"><span data-stu-id="7d1c3-122">Valid</span></span>|<span data-ttu-id="7d1c3-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d1c3-123">ValidationStates</span></span>|<span data-ttu-id="7d1c3-124">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7d1c3-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7d1c3-125">InvalidFocused</span></span>|<span data-ttu-id="7d1c3-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d1c3-126">ValidationStates</span></span>|<span data-ttu-id="7d1c3-127">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7d1c3-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7d1c3-128">InvalidUnfocused</span></span>|<span data-ttu-id="7d1c3-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d1c3-129">ValidationStates</span></span>|<span data-ttu-id="7d1c3-130">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="7d1c3-131">Ejemplo de ControlTemplate de ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="7d1c3-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="7d1c3-132">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ScrollViewer> control.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="7d1c3-133">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7d1c3-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7d1c3-134">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="7d1c3-134">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1c3-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d1c3-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="7d1c3-136">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="7d1c3-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="7d1c3-137">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="7d1c3-137">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="7d1c3-138">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="7d1c3-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7d1c3-139">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7d1c3-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
