---
title: Estilos y plantillas de GroupBox
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99150de10fcbd45d3617621a916793ad5cfe72db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="9f786-102">Estilos y plantillas de GroupBox</span><span class="sxs-lookup"><span data-stu-id="9f786-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="9f786-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="9f786-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="9f786-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="9f786-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9f786-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="9f786-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="9f786-106">GroupBox partes</span><span class="sxs-lookup"><span data-stu-id="9f786-106">GroupBox Parts</span></span>  
 <span data-ttu-id="9f786-107">El <xref:System.Windows.Controls.GroupBox> control no tiene los elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="9f786-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="9f786-108">Estados de GroupBox</span><span class="sxs-lookup"><span data-stu-id="9f786-108">GroupBox States</span></span>  
 <span data-ttu-id="9f786-109">La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="9f786-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="9f786-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="9f786-110">VisualState Name</span></span>|<span data-ttu-id="9f786-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="9f786-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9f786-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f786-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f786-113">Válido</span><span class="sxs-lookup"><span data-stu-id="9f786-113">Valid</span></span>|<span data-ttu-id="9f786-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f786-114">ValidationStates</span></span>|<span data-ttu-id="9f786-115">El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="9f786-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9f786-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9f786-116">InvalidFocused</span></span>|<span data-ttu-id="9f786-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f786-117">ValidationStates</span></span>|<span data-ttu-id="9f786-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f786-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9f786-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9f786-119">InvalidUnfocused</span></span>|<span data-ttu-id="9f786-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f786-120">ValidationStates</span></span>|<span data-ttu-id="9f786-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="9f786-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="9f786-122">Ejemplo de ControlTemplate de GroupBox</span><span class="sxs-lookup"><span data-stu-id="9f786-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="9f786-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="9f786-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="9f786-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="9f786-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9f786-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="9f786-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f786-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f786-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="9f786-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="9f786-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 <span data-ttu-id="9f786-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="9f786-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>  
 [<span data-ttu-id="9f786-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="9f786-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="9f786-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="9f786-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
