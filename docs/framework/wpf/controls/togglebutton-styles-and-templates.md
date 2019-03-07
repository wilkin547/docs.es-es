---
title: ToggleButton estilos y plantillas
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 46fd7d07c3904ee752ae3f467f65af4b0c031c84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509514"
---
# <a name="togglebutton-styles-and-templates"></a>ToggleButton estilos y plantillas

En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Primitives.ToggleButton> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

## <a name="togglebutton-parts"></a>Partes de ToggleButton

El <xref:System.Windows.Controls.Primitives.ToggleButton> control no tiene elementos con nombre.

## <a name="togglebutton-states"></a>Estados de ToggleButton

En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.ToggleButton> control.

|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|
|-|-|-|
|Normal|CommonStates|El estado predeterminado.|
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|
|Presionado|CommonStates|El control está presionado.|
|Deshabilitado|CommonStates|El control está deshabilitado.|
|Con foco|FocusStates|El control tiene el foco.|
|Sin foco|FocusStates|El control no tiene el foco.|
|Activado|CheckStates|El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `true`.|
|desactivada|CheckStates|El valor de <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `false`.|
|Indeterminado|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> es `true`, y <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> es `null`.|
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|

> [!NOTE]
> Si el estado indeterminado visual no existe en la plantilla de control, se usará como el estado visual de forma predeterminada el estado visual desactivado.

## <a name="togglebutton-controltemplate-example"></a>Ejemplo de ControlTemplate de ToggleButton

El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Primitives.ToggleButton> control.

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

En el ejemplo anterior se usa uno o varios de los recursos siguientes.

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
