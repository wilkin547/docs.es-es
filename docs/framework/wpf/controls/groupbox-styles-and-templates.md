---
title: Estilos y plantillas de GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 0835c106ffbda86bca8e01bc61adebfc1ab0c2cb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459646"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="32151-102">Estilos y plantillas de GroupBox</span><span class="sxs-lookup"><span data-stu-id="32151-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="32151-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="32151-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="32151-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="32151-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="32151-105">Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).</span><span class="sxs-lookup"><span data-stu-id="32151-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="32151-106">Elementos GroupBox</span><span class="sxs-lookup"><span data-stu-id="32151-106">GroupBox Parts</span></span>  
 <span data-ttu-id="32151-107">El control <xref:System.Windows.Controls.GroupBox> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="32151-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="32151-108">Estados de GroupBox</span><span class="sxs-lookup"><span data-stu-id="32151-108">GroupBox States</span></span>  
 <span data-ttu-id="32151-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="32151-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="32151-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="32151-110">VisualState Name</span></span>|<span data-ttu-id="32151-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="32151-111">VisualStateGroup Name</span></span>|<span data-ttu-id="32151-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="32151-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="32151-113">Válido</span><span class="sxs-lookup"><span data-stu-id="32151-113">Valid</span></span>|<span data-ttu-id="32151-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="32151-114">ValidationStates</span></span>|<span data-ttu-id="32151-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="32151-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="32151-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="32151-116">InvalidFocused</span></span>|<span data-ttu-id="32151-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="32151-117">ValidationStates</span></span>|<span data-ttu-id="32151-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="32151-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="32151-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="32151-119">InvalidUnfocused</span></span>|<span data-ttu-id="32151-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="32151-120">ValidationStates</span></span>|<span data-ttu-id="32151-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="32151-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="32151-122">Ejemplo de ControlTemplate de GroupBox</span><span class="sxs-lookup"><span data-stu-id="32151-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="32151-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="32151-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="32151-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="32151-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="32151-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="32151-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32151-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="32151-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="32151-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="32151-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="32151-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="32151-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="32151-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="32151-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="32151-130">Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="32151-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
