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
ms.openlocfilehash: 48fe5887ebad86efad1b1aae39ba03a26fda3bd8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460019"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="e8e6a-102">Estilos y plantillas de ventanas</span><span class="sxs-lookup"><span data-stu-id="e8e6a-102">Window Styles and Templates</span></span>
<span data-ttu-id="e8e6a-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="e8e6a-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e8e6a-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="e8e6a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="e8e6a-106">Elementos de ventana</span><span class="sxs-lookup"><span data-stu-id="e8e6a-106">Window Parts</span></span>  
 <span data-ttu-id="e8e6a-107">El control <xref:System.Windows.Window> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="e8e6a-108">Estados de ventana</span><span class="sxs-lookup"><span data-stu-id="e8e6a-108">Window States</span></span>  
 <span data-ttu-id="e8e6a-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="e8e6a-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="e8e6a-110">VisualState Name</span></span>|<span data-ttu-id="e8e6a-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e8e6a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e8e6a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8e6a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e8e6a-113">Válido</span><span class="sxs-lookup"><span data-stu-id="e8e6a-113">Valid</span></span>|<span data-ttu-id="e8e6a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8e6a-114">ValidationStates</span></span>|<span data-ttu-id="e8e6a-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e8e6a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e8e6a-116">InvalidFocused</span></span>|<span data-ttu-id="e8e6a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8e6a-117">ValidationStates</span></span>|<span data-ttu-id="e8e6a-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e8e6a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e8e6a-119">InvalidUnfocused</span></span>|<span data-ttu-id="e8e6a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e8e6a-120">ValidationStates</span></span>|<span data-ttu-id="e8e6a-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="e8e6a-122">Ejemplo de ControlTemplate de ventana</span><span class="sxs-lookup"><span data-stu-id="e8e6a-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="e8e6a-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="e8e6a-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="e8e6a-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e8e6a-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e8e6a-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e6a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8e6a-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e8e6a-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="e8e6a-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="e8e6a-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="e8e6a-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="e8e6a-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="e8e6a-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e8e6a-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e8e6a-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
