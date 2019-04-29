---
title: Estilos y plantillas de PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: 7783330dd56ec5b2759e783a6935761eb3587978
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770648"
---
# <a name="passwordbox-styles-and-templates"></a>Estilos y plantillas de PasswordBox

En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.PasswordBox> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).

## <a name="passwordbox-parts"></a>Partes de PasswordBox

En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.PasswordBox> control.

|Parte|Tipo|Descripción|
|-|-|-|
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Un elemento visual que puede contener un <xref:System.Windows.FrameworkElement>. El texto de la <xref:System.Windows.Controls.PasswordBox> se muestra en este elemento.|

## <a name="passwordbox-states"></a>Estados de PasswordBox

En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.PasswordBox> control.

|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|
|-|-|-|
|Normal|CommonStates|El estado predeterminado.|
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|
|Deshabilitado|CommonStates|El control está deshabilitado.|
|Con foco|FocusStates|El control tiene el foco.|
|Sin foco|FocusStates|El control no tiene el foco.|
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|

## <a name="passwordbox-controltemplate-example"></a>Ejemplo de ControlTemplate de PasswordBox

El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.PasswordBox> control.

[!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]

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
