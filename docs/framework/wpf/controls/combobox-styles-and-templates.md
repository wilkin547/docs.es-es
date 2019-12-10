---
title: Estilos y plantillas de ComboBox
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 887698bdaebf7bc5ddac8997167589d9fbd3dd4d
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960375"
---
# <a name="combobox-styles-and-templates"></a>Estilos y plantillas de ComboBox
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ComboBox>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Elementos ComboBox  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ComboBox>.  
  
|Componente|Tipo de|Descripción|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene el texto del <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|La lista desplegable que contiene los elementos del cuadro combinado.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ComboBox>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ComboBox>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## <a name="combobox-states"></a>Estados de ComboBox  
 En la tabla siguiente se enumeran los Estados del control <xref:System.Windows.Controls.ComboBox>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa sobre el control de <xref:System.Windows.Controls.ComboBox>.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|FocusedDropDown|FocusStates|La lista desplegable del <xref:System.Windows.Controls.ComboBox> tiene el foco.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
|Editable|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `true`.|  
|No editables|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `false`.|  
  
## <a name="comboboxitem-parts"></a>Elementos de ComboBoxItem  
 El control <xref:System.Windows.Controls.ComboBoxItem> no tiene ninguna parte con nombre.  
  
## <a name="comboboxitem-states"></a>Estados de ComboBoxItem  
 En la tabla siguiente se enumeran los Estados del control <xref:System.Windows.Controls.ComboBoxItem>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa sobre el control de <xref:System.Windows.Controls.ComboBoxItem>.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Seleccionado|SelectionStates|El elemento está seleccionado actualmente.|  
|No seleccionado|SelectionStates|El elemento no está seleccionado.|  
|SelectedUnfocused|SelectionStates|El elemento está seleccionado, pero no tiene el foco.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="combobox-controltemplate-example"></a>Ejemplo de ControlTemplate de ComboBox  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ComboBox> y los tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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
