---
title: Estilos y plantillas de ventanas
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 9095405c47d4e113a2f0e7d572ba1209718f4b37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640087"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="f7fed-102">Estilos y plantillas de ventanas</span><span class="sxs-lookup"><span data-stu-id="f7fed-102">Window Styles and Templates</span></span>
<span data-ttu-id="f7fed-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="f7fed-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="f7fed-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="f7fed-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f7fed-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="f7fed-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="f7fed-106">Partes de la ventana</span><span class="sxs-lookup"><span data-stu-id="f7fed-106">Window Parts</span></span>  
 <span data-ttu-id="f7fed-107">El <xref:System.Windows.Window> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="f7fed-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="f7fed-108">Estados de la ventana</span><span class="sxs-lookup"><span data-stu-id="f7fed-108">Window States</span></span>  
 <span data-ttu-id="f7fed-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="f7fed-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="f7fed-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="f7fed-110">VisualState Name</span></span>|<span data-ttu-id="f7fed-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="f7fed-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f7fed-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7fed-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f7fed-113">Válido</span><span class="sxs-lookup"><span data-stu-id="f7fed-113">Valid</span></span>|<span data-ttu-id="f7fed-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f7fed-114">ValidationStates</span></span>|<span data-ttu-id="f7fed-115">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="f7fed-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f7fed-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f7fed-116">InvalidFocused</span></span>|<span data-ttu-id="f7fed-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f7fed-117">ValidationStates</span></span>|<span data-ttu-id="f7fed-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f7fed-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f7fed-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f7fed-119">InvalidUnfocused</span></span>|<span data-ttu-id="f7fed-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f7fed-120">ValidationStates</span></span>|<span data-ttu-id="f7fed-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="f7fed-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="f7fed-122">Ejemplo de ControlTemplate de ventana</span><span class="sxs-lookup"><span data-stu-id="f7fed-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="f7fed-123">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="f7fed-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="f7fed-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="f7fed-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f7fed-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="f7fed-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fed-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7fed-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f7fed-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="f7fed-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- <span data-ttu-id="f7fed-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="f7fed-128">[Control Customization](../../../../docs/framework/wpf/controls/control-customization.md)</span></span>
- [<span data-ttu-id="f7fed-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f7fed-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="f7fed-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="f7fed-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
