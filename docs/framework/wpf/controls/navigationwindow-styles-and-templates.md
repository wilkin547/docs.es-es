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
ms.openlocfilehash: 5cc504956ce036505ac9261ea1438c7881fa2790
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283490"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="a29af-102">Estilos y plantillas de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="a29af-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="a29af-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a29af-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="a29af-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="a29af-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a29af-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="a29af-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="a29af-106">Elementos NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="a29af-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="a29af-107">En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a29af-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="a29af-108">Parte</span><span class="sxs-lookup"><span data-stu-id="a29af-108">Part</span></span>|<span data-ttu-id="a29af-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="a29af-109">Type</span></span>|<span data-ttu-id="a29af-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a29af-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a29af-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="a29af-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="a29af-112">Área para el contenido.</span><span class="sxs-lookup"><span data-stu-id="a29af-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="a29af-113">Estados de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="a29af-113">NavigationWindow States</span></span>  
 <span data-ttu-id="a29af-114">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="a29af-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="a29af-115">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="a29af-115">VisualState Name</span></span>|<span data-ttu-id="a29af-116">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a29af-116">VisualStateGroup Name</span></span>|<span data-ttu-id="a29af-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a29af-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a29af-118">Válido</span><span class="sxs-lookup"><span data-stu-id="a29af-118">Valid</span></span>|<span data-ttu-id="a29af-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a29af-119">ValidationStates</span></span>|<span data-ttu-id="a29af-120">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="a29af-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a29af-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a29af-121">InvalidFocused</span></span>|<span data-ttu-id="a29af-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a29af-122">ValidationStates</span></span>|<span data-ttu-id="a29af-123">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a29af-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a29af-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a29af-124">InvalidUnfocused</span></span>|<span data-ttu-id="a29af-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a29af-125">ValidationStates</span></span>|<span data-ttu-id="a29af-126">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="a29af-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="a29af-127">Ejemplo de ControlTemplate de NavigationWindow</span><span class="sxs-lookup"><span data-stu-id="a29af-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="a29af-128">Aunque este ejemplo contiene todos los elementos que se definen en el <xref:System.Windows.Controls.ControlTemplate> de una <xref:System.Windows.Navigation.NavigationWindow> de forma predeterminada, los valores específicos deben considerarse como ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a29af-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="a29af-129">En el ejemplo anterior se usa uno o varios de los recursos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a29af-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a29af-130">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a29af-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29af-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a29af-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a29af-132">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="a29af-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="a29af-133">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="a29af-133">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="a29af-134">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a29af-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a29af-135">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="a29af-135">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
