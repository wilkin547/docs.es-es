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
# <a name="groupbox-styles-and-templates"></a>Estilos y plantillas de GroupBox
<a name="introduction"></a>En este tema se describen <xref:System.Windows.Controls.GroupBox> los estilos y plantillas para el control. Puede modificar el <xref:System.Windows.Controls.ControlTemplate> valor predeterminado para dar al control una apariencia única. Para obtener más información, vea [Crear una plantilla para un control.](../../../desktop-wpf/themes/how-to-create-apply-template.md)  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a>Piezas GroupBox  
 El <xref:System.Windows.Controls.GroupBox> control no tiene ninguna parte con nombre.  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a>Estados de GroupBox  
 En la tabla siguiente se <xref:System.Windows.Controls.GroupBox> enumeran los estados visuales del control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control <xref:System.Windows.Controls.Validation> utiliza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> clase `false`y la propiedad adjunta es .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta tiene el control no tiene el foco.|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a>Ejemplo de GroupBox ControlTemplate  
 En el ejemplo siguiente <xref:System.Windows.Controls.ControlTemplate> se <xref:System.Windows.Controls.GroupBox> muestra cómo definir a para el control.  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 Utiliza <xref:System.Windows.Controls.ControlTemplate> uno o varios de los siguientes recursos.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
