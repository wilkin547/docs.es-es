---
title: Estilos y plantillas de NavigationWindow
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 32d8aac99d40693e66c7b52a6c7d2c116d2f3baf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225812"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="04179-102">Estilos y plantillas de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="04179-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="04179-103">En este tema se describe los estilos y plantillas para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="04179-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="04179-104">Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="04179-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="04179-105">Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="04179-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="04179-106">Partes de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="04179-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="04179-107">En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="04179-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="04179-108">Parte</span><span class="sxs-lookup"><span data-stu-id="04179-108">Part</span></span>|<span data-ttu-id="04179-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="04179-109">Type</span></span>|<span data-ttu-id="04179-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="04179-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="04179-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="04179-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="04179-112">El área para el contenido.</span><span class="sxs-lookup"><span data-stu-id="04179-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="04179-113">Estados de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="04179-113">NavigationWindow States</span></span>  
 <span data-ttu-id="04179-114">En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Navigation.NavigationWindow> control.</span><span class="sxs-lookup"><span data-stu-id="04179-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="04179-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="04179-115">VisualState Name</span></span>|<span data-ttu-id="04179-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="04179-116">VisualStateGroup Name</span></span>|<span data-ttu-id="04179-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="04179-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="04179-118">Válido</span><span class="sxs-lookup"><span data-stu-id="04179-118">Valid</span></span>|<span data-ttu-id="04179-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04179-119">ValidationStates</span></span>|<span data-ttu-id="04179-120">El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.</span><span class="sxs-lookup"><span data-stu-id="04179-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="04179-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="04179-121">InvalidFocused</span></span>|<span data-ttu-id="04179-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04179-122">ValidationStates</span></span>|<span data-ttu-id="04179-123">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04179-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="04179-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="04179-124">InvalidUnfocused</span></span>|<span data-ttu-id="04179-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="04179-125">ValidationStates</span></span>|<span data-ttu-id="04179-126">El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="04179-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="04179-127">Ejemplo de ControlTemplate de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="04179-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="04179-128">Aunque este ejemplo contiene todos los elementos que se definen en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Navigation.NavigationWindow> de forma predeterminada, los valores específicos que deben considerarse ejemplos.</span><span class="sxs-lookup"><span data-stu-id="04179-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="04179-129">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="04179-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="04179-130">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="04179-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04179-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="04179-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="04179-132">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="04179-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="04179-133">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="04179-133">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="04179-134">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="04179-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="04179-135">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="04179-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
