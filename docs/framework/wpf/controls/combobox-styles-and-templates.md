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
ms.openlocfilehash: 99869b929e70ab7ae5b68d8c0eb6d70358f4a48d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369310"
---
# <a name="combobox-styles-and-templates"></a>Estilos y plantillas de ComboBox
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ComboBox> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="combobox-parts"></a>Elementos de cuadro combinado  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ComboBox> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene el texto de la <xref:System.Windows.Controls.ComboBox>.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|La lista desplegable que contiene los elementos en el cuadro combinado.|  
  
 Cuando creas un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ComboBox>, la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento en el <xref:System.Windows.Controls.ComboBox>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> el nombre, `ItemsPresenter`.  
  
## <a name="combobox-states"></a>Estados de control ComboBox  
 En la tabla siguiente se enumera los Estados de la <xref:System.Windows.Controls.ComboBox> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse está sobre el <xref:System.Windows.Controls.ComboBox> control.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|FocusedDropDown|FocusStates|La lista desplegable para el <xref:System.Windows.Controls.ComboBox> tiene el foco.|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
|Puede editar|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `true`.|  
|No modificables|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `false`.|  
  
## <a name="comboboxitem-parts"></a>Partes ComboBoxItem  
 El <xref:System.Windows.Controls.ComboBoxItem> control no tiene elementos con nombre.  
  
## <a name="comboboxitem-states"></a>Estados de ComboBoxItem  
 En la tabla siguiente se enumera los Estados de la <xref:System.Windows.Controls.ComboBoxItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse está sobre el <xref:System.Windows.Controls.ComboBox> control.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Seleccionado|SelectionStates|El elemento está seleccionado actualmente.|  
|No seleccionado|SelectionStates|El elemento no está seleccionado.|  
|SelectedUnfocused|SelectionStates|El elemento está seleccionado, pero no tiene el foco.|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="combobox-controltemplate-example"></a>Ejemplo de ControlTemplate de ComboBox  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ComboBox> control y tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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
