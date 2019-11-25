---
title: Estilos y plantillas de DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 002d1c3271827239dcd3a319621f66fb5bc68d4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283770"
---
# <a name="datepicker-styles-and-templates"></a>Estilos y plantillas de DatePicker
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.DatePicker>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datepicker-parts"></a>Elementos DatePicker  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.DatePicker>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|Raíz del control.|  
|PART_Button|<xref:System.Windows.Controls.Button>|El botón que abre y cierra el <xref:System.Windows.Controls.Calendar>.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Cuadro de texto que permite especificar una fecha.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Elemento emergente del control de <xref:System.Windows.Controls.DatePicker>.|  
  
## <a name="datepicker-states"></a>Estados de DatePicker  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.DatePicker>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|La <xref:System.Windows.Controls.DatePicker> está deshabilitada.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="datepickertextbox-parts"></a>Elementos DatePickerTextBox  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|Elemento que contiene el texto inicial en el <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Elemento visual que puede contener un <xref:System.Windows.FrameworkElement>. El texto del <xref:System.Windows.Controls.TextBox> se muestra en este elemento.|  
  
## <a name="datepickertextbox-states"></a>Estados de DatePickerTextBox  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|La <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está deshabilitada.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|El usuario no puede cambiar el texto en el <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Una marca|WatermarkStates|El control muestra su texto inicial.  El <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está en el estado cuando el usuario no ha escrito texto o ha seleccionado una fecha.|  
|No con marca de agua|WatermarkStates|El usuario ha escrito texto en el <xref:System.Windows.Controls.Primitives.DatePickerTextBox> o ha seleccionado una fecha en el <xref:System.Windows.Controls.DatePicker>.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` y el control no tiene el foco.|  
  
## <a name="datepicker-controltemplate-example"></a>Ejemplo de ControlTemplate de DatePicker  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DatePicker>.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
