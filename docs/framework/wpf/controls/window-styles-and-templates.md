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
ms.openlocfilehash: ebd21829591b8fefe87aeba0b86280f18eff4f06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203735"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="e85ea-102">Estilos y plantillas de ventanas</span><span class="sxs-lookup"><span data-stu-id="e85ea-102">Window Styles and Templates</span></span>
<span data-ttu-id="e85ea-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="e85ea-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="e85ea-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="e85ea-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e85ea-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e85ea-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="e85ea-106">Partes de la ventana</span><span class="sxs-lookup"><span data-stu-id="e85ea-106">Window Parts</span></span>  
 <span data-ttu-id="e85ea-107">El <xref:System.Windows.Window> control no tiene elementos con nombre.</span><span class="sxs-lookup"><span data-stu-id="e85ea-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="e85ea-108">Estados de la ventana</span><span class="sxs-lookup"><span data-stu-id="e85ea-108">Window States</span></span>  
 <span data-ttu-id="e85ea-109">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="e85ea-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="e85ea-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="e85ea-110">VisualState Name</span></span>|<span data-ttu-id="e85ea-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e85ea-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e85ea-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e85ea-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e85ea-113">Válido</span><span class="sxs-lookup"><span data-stu-id="e85ea-113">Valid</span></span>|<span data-ttu-id="e85ea-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e85ea-114">ValidationStates</span></span>|<span data-ttu-id="e85ea-115">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="e85ea-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e85ea-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e85ea-116">InvalidFocused</span></span>|<span data-ttu-id="e85ea-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e85ea-117">ValidationStates</span></span>|<span data-ttu-id="e85ea-118">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e85ea-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e85ea-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e85ea-119">InvalidUnfocused</span></span>|<span data-ttu-id="e85ea-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e85ea-120">ValidationStates</span></span>|<span data-ttu-id="e85ea-121">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e85ea-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="e85ea-122">Ejemplo de ControlTemplate de ventana</span><span class="sxs-lookup"><span data-stu-id="e85ea-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="e85ea-123">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Window> control.</span><span class="sxs-lookup"><span data-stu-id="e85ea-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="e85ea-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="e85ea-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e85ea-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e85ea-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85ea-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e85ea-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e85ea-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="e85ea-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="e85ea-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="e85ea-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="e85ea-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="e85ea-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="e85ea-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e85ea-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
