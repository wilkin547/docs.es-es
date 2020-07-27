---
title: Estilos y plantillas de ComboBox
description: Obtenga información sobre los estilos y las plantillas para el control ComboBox Windows Presentation Foundation. Modifique el ControlTemplate para dar al control una apariencia única.
ms.date: 03/30/2017
helpviewer_keywords:
- ComboBox [WPF], styles and templates
- states [WPF], ComboBox
- ControlTemplate [WPF], ComboBox
- styles [WPF], ComboBox
- templates [WPF], ComboBox
- parts [WPF], ComboBox
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
ms.openlocfilehash: 5e929bafeaf849b4b5682a17ca51cb0aab963613
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165919"
---
# <a name="combobox-styles-and-templates"></a>Estilos y plantillas de ComboBox
En este tema se describen los estilos y las plantillas del <xref:System.Windows.Controls.ComboBox> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="combobox-parts"></a>Elementos ComboBox  
 En la tabla siguiente se enumeran las partes con nombre para el <xref:System.Windows.Controls.ComboBox> control.  
  
|Parte|Tipo|Description|  
|-|-|-|  
|PART_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene el texto de <xref:System.Windows.Controls.ComboBox> .|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|La lista desplegable que contiene los elementos del cuadro combinado.|  
  
 Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ComboBox> , la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Muestra cada elemento en <xref:System.Windows.Controls.ComboBox> ; <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de <xref:System.Windows.Controls.ScrollViewer> , debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> nombre, `ItemsPresenter` .  
  
## <a name="combobox-states"></a>Estados de ComboBox  
 En la tabla siguiente se enumeran los Estados del <xref:System.Windows.Controls.ComboBox> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa sobre el <xref:System.Windows.Controls.ComboBox> control.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|FocusedDropDown|FocusStates|La lista desplegable de <xref:System.Windows.Controls.ComboBox> tiene el foco.|  
|Válido|ValidationStates|El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.|  
|Modificable|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `true`.|  
|No editables|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `false`.|  
  
## <a name="comboboxitem-parts"></a>Elementos de ComboBoxItem  
 El <xref:System.Windows.Controls.ComboBoxItem> control no tiene ninguna parte con nombre.  
  
## <a name="comboboxitem-states"></a>Estados de ComboBoxItem  
 En la tabla siguiente se enumeran los Estados del <xref:System.Windows.Controls.ComboBoxItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa sobre el <xref:System.Windows.Controls.ComboBoxItem> control.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Seleccionado|SelectionStates|El elemento está seleccionado actualmente.|  
|No seleccionado|SelectionStates|El elemento no está seleccionado.|  
|SelectedUnfocused|SelectionStates|El elemento está seleccionado, pero no tiene el foco.|  
|Válido|ValidationStates|El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` y el control no tiene el foco.|  
  
## <a name="combobox-controltemplate-example"></a>Ejemplo de ControlTemplate de ComboBox  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ComboBox> control y los tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#ComboBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creación de una plantilla de un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
