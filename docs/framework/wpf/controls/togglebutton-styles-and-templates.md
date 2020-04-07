---
title: Estilos y plantillas de ToggleButton
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: e055dcbd557f9b90eb2fe99ad15a05b6f229fd28
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805912"
---
# <a name="togglebutton-styles-and-templates"></a>Estilos y plantillas de ToggleButton

En este tema se describen <xref:System.Windows.Controls.Primitives.ToggleButton> los estilos y plantillas para el control. Puede modificar el <xref:System.Windows.Controls.ControlTemplate> valor predeterminado para dar al control una apariencia única. Para obtener más información, vea [Crear una plantilla para un control.](../../../desktop-wpf/themes/how-to-create-apply-template.md)

## <a name="togglebutton-parts"></a>Piezas ToggleButton

El <xref:System.Windows.Controls.Primitives.ToggleButton> control no tiene ninguna parte con nombre.

## <a name="togglebutton-states"></a>Estados ToggleButton

En la tabla siguiente se <xref:System.Windows.Controls.Primitives.ToggleButton> enumeran los estados visuales del control.

|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|
|-|-|-|
|Normal|CommonStates|El estado predeterminado.|
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|
|Presionado|CommonStates|El control está presionado.|
|Disabled|CommonStates|El control está deshabilitado.|
|Con foco|FocusStates|El control tiene el foco.|
|Sin foco|FocusStates|El control no tiene el foco.|
|Activado|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.|
|No activado|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.|
|Indeterminado|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true` y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `null`.|
|Válido|ValidationStates|El control <xref:System.Windows.Controls.Validation> utiliza la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> clase `false`y la propiedad adjunta es .|
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es y el control tiene el foco.|
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad `true` adjunta es y el control no tiene el foco.|

> [!NOTE]
> Si el estado visual Indeterminado no existe en la plantilla de control, el estado visual Desmarcado se usará como estado visual predeterminado.

## <a name="togglebutton-controltemplate-example"></a>Ejemplo de ToggleButton ControlTemplate

En el ejemplo siguiente <xref:System.Windows.Controls.ControlTemplate> se <xref:System.Windows.Controls.Primitives.ToggleButton> muestra cómo definir a para el control.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

En el ejemplo anterior se usa uno o varios de los recursos siguientes.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
