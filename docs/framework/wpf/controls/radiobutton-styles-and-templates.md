---
title: Estilos y plantillas de RadioButton
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 2d732dc6620cd06c99bdbaedfa5be474477d4917
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283432"
---
# <a name="radiobutton-styles-and-templates"></a>Estilos y plantillas de RadioButton
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.RadioButton>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="radiobutton-parts"></a>Elementos RadioButton  
 El control <xref:System.Windows.Controls.RadioButton> no tiene ninguna parte con nombre.  
  
## <a name="radiobutton-states"></a>Estados de RadioButton  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.RadioButton>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Presionado|CommonStates|El control está presionado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Activadas|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.|  
|Desactivada|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.|  
|Determina|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true`y se `null`<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="radiobutton-controltemplate-example"></a>Ejemplo de ControlTemplate de RadioButton  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.RadioButton>.  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
