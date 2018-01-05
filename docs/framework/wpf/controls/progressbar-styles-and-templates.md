---
title: Estilos y plantillas de ProgressBar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6809ce2f51af8a1baf535afa8fe80f4e5b5f53e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="d2d33-102">Estilos y plantillas de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d2d33-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="d2d33-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="d2d33-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="d2d33-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="d2d33-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d2d33-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="d2d33-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="d2d33-106">Partes de la barra de progreso</span><span class="sxs-lookup"><span data-stu-id="d2d33-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="d2d33-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="d2d33-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="d2d33-108">Parte</span><span class="sxs-lookup"><span data-stu-id="d2d33-108">Part</span></span>|<span data-ttu-id="d2d33-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2d33-109">Type</span></span>|<span data-ttu-id="d2d33-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2d33-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d2d33-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="d2d33-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="d2d33-112">El objeto que indica el progreso.</span><span class="sxs-lookup"><span data-stu-id="d2d33-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="d2d33-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="d2d33-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="d2d33-114">El objeto que define la ruta de acceso del indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="d2d33-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="d2d33-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="d2d33-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="d2d33-116">Objeto que embellishes la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="d2d33-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="d2d33-117">Estados de la barra de progreso</span><span class="sxs-lookup"><span data-stu-id="d2d33-117">ProgressBar States</span></span>  
 <span data-ttu-id="d2d33-118">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="d2d33-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="d2d33-119">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="d2d33-119">VisualState Name</span></span>|<span data-ttu-id="d2d33-120">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d2d33-120">VisualStateGroup Name</span></span>|<span data-ttu-id="d2d33-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2d33-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="d2d33-122">Determinada</span><span class="sxs-lookup"><span data-stu-id="d2d33-122">Determinate</span></span>|<span data-ttu-id="d2d33-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d2d33-123">CommonStates</span></span>|<span data-ttu-id="d2d33-124"><xref:System.Windows.Controls.ProgressBar>informa del progreso tomando como base el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d2d33-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="d2d33-125">Indeterminado</span><span class="sxs-lookup"><span data-stu-id="d2d33-125">Indeterminate</span></span>|<span data-ttu-id="d2d33-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d2d33-126">CommonStates</span></span>|<span data-ttu-id="d2d33-127"><xref:System.Windows.Controls.ProgressBar>indica el progreso general con un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="d2d33-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="d2d33-128">Válido</span><span class="sxs-lookup"><span data-stu-id="d2d33-128">Valid</span></span>|<span data-ttu-id="d2d33-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2d33-129">ValidationStates</span></span>|<span data-ttu-id="d2d33-130">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="d2d33-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d2d33-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d2d33-131">InvalidFocused</span></span>|<span data-ttu-id="d2d33-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2d33-132">ValidationStates</span></span>|<span data-ttu-id="d2d33-133">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d2d33-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d2d33-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d2d33-134">InvalidUnfocused</span></span>|<span data-ttu-id="d2d33-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d2d33-135">ValidationStates</span></span>|<span data-ttu-id="d2d33-136">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d2d33-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="d2d33-137">Ejemplo de ControlTemplate de ProgressBar</span><span class="sxs-lookup"><span data-stu-id="d2d33-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="d2d33-138">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ProgressBar> control.</span><span class="sxs-lookup"><span data-stu-id="d2d33-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="d2d33-139">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d2d33-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d2d33-140">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="d2d33-140">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d33-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2d33-141">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d2d33-142">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="d2d33-142">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="d2d33-143">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="d2d33-143">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="d2d33-144">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="d2d33-144">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d2d33-145">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d2d33-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
