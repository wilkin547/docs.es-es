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
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187478"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="336ef-102">Estilos y plantillas de GroupBox</span><span class="sxs-lookup"><span data-stu-id="336ef-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="336ef-103">En este tema se describen <xref:System.Windows.Controls.GroupBox> los estilos y plantillas para el control.</span><span class="sxs-lookup"><span data-stu-id="336ef-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="336ef-104">Puede modificar el <xref:System.Windows.Controls.ControlTemplate> valor predeterminado para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="336ef-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="336ef-105">Para obtener más información, vea [Crear una plantilla para un control.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="336ef-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="336ef-106">Piezas GroupBox</span><span class="sxs-lookup"><span data-stu-id="336ef-106">GroupBox Parts</span></span>  
 <span data-ttu-id="336ef-107">El <xref:System.Windows.Controls.GroupBox> control no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="336ef-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="336ef-108">Estados de GroupBox</span><span class="sxs-lookup"><span data-stu-id="336ef-108">GroupBox States</span></span>  
 <span data-ttu-id="336ef-109">En la tabla siguiente se <xref:System.Windows.Controls.GroupBox> enumeran los estados visuales del control.</span><span class="sxs-lookup"><span data-stu-id="336ef-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="336ef-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="336ef-110">VisualState Name</span></span>|<span data-ttu-id="336ef-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="336ef-111">VisualStateGroup Name</span></span>|<span data-ttu-id="336ef-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="336ef-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="336ef-113">Válido</span><span class="sxs-lookup"><span data-stu-id="336ef-113">Valid</span></span>|<span data-ttu-id="336ef-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="336ef-114">ValidationStates</span></span>|<span data-ttu-id="336ef-115">El control <xref:System.Windows.Controls.Validation> utiliza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> clase `false`y la propiedad adjunta es .</span><span class="sxs-lookup"><span data-stu-id="336ef-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="336ef-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="336ef-116">InvalidFocused</span></span>|<span data-ttu-id="336ef-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="336ef-117">ValidationStates</span></span>|<span data-ttu-id="336ef-118">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es tiene el control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="336ef-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="336ef-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="336ef-119">InvalidUnfocused</span></span>|<span data-ttu-id="336ef-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="336ef-120">ValidationStates</span></span>|<span data-ttu-id="336ef-121">La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="336ef-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="336ef-122">Ejemplo de GroupBox ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="336ef-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="336ef-123">En el ejemplo siguiente <xref:System.Windows.Controls.ControlTemplate> se <xref:System.Windows.Controls.GroupBox> muestra cómo definir a para el control.</span><span class="sxs-lookup"><span data-stu-id="336ef-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="336ef-124">Utiliza <xref:System.Windows.Controls.ControlTemplate> uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="336ef-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="336ef-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="336ef-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="336ef-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="336ef-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="336ef-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="336ef-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="336ef-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="336ef-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="336ef-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="336ef-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="336ef-130">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="336ef-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
