---
title: Estilos y plantillas de ToolTip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e39372083ede5649addee4b493f2425116ec2aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="a9104-102">Estilos y plantillas de ToolTip</span><span class="sxs-lookup"><span data-stu-id="a9104-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="a9104-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="a9104-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="a9104-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="a9104-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a9104-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="a9104-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="a9104-106">Partes de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a9104-106">ToolTip Parts</span></span>  
 <span data-ttu-id="a9104-107">El <xref:System.Windows.Controls.ToolTip> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="a9104-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="a9104-108">Estados de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a9104-108">ToolTip States</span></span>  
 <span data-ttu-id="a9104-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="a9104-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="a9104-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="a9104-110">VisualState Name</span></span>|<span data-ttu-id="a9104-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a9104-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a9104-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9104-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a9104-113">Cerrado</span><span class="sxs-lookup"><span data-stu-id="a9104-113">Closed</span></span>|<span data-ttu-id="a9104-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="a9104-114">OpenStates</span></span>|<span data-ttu-id="a9104-115">El estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a9104-115">The default state.</span></span>|  
|<span data-ttu-id="a9104-116">Abrir</span><span class="sxs-lookup"><span data-stu-id="a9104-116">Open</span></span>|<span data-ttu-id="a9104-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="a9104-117">OpenStates</span></span>|<span data-ttu-id="a9104-118">El <xref:System.Windows.Controls.ToolTip> está visible.</span><span class="sxs-lookup"><span data-stu-id="a9104-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="a9104-119">Válido</span><span class="sxs-lookup"><span data-stu-id="a9104-119">Valid</span></span>|<span data-ttu-id="a9104-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9104-120">ValidationStates</span></span>|<span data-ttu-id="a9104-121">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="a9104-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a9104-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a9104-122">InvalidFocused</span></span>|<span data-ttu-id="a9104-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9104-123">ValidationStates</span></span>|<span data-ttu-id="a9104-124">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a9104-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a9104-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a9104-125">InvalidUnfocused</span></span>|<span data-ttu-id="a9104-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a9104-126">ValidationStates</span></span>|<span data-ttu-id="a9104-127">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a9104-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="a9104-128">Ejemplo de ControlTemplate de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="a9104-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="a9104-129">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ToolTip> control.</span><span class="sxs-lookup"><span data-stu-id="a9104-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="a9104-130">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a9104-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a9104-131">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="a9104-131">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9104-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9104-132">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a9104-133">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="a9104-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="a9104-134">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="a9104-134">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="a9104-135">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a9104-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a9104-136">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a9104-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
