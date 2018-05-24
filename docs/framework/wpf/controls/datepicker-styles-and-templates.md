---
title: Plantillas y estilos de DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: b50716cc83114fea5120b12659668437ac9bd6da
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="datepicker-styles-and-templates"></a>Plantillas y estilos de DatePicker
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.DatePicker> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datepicker-parts"></a>Partes de DatePicker  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.DatePicker> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|La raíz del control.|  
|PART_Button|<xref:System.Windows.Controls.Button>|El botón que abre y cierra el <xref:System.Windows.Controls.Calendar>.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|El cuadro de texto que permite especificar una fecha.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|La ventana emergente para la <xref:System.Windows.Controls.DatePicker> control.|  
  
## <a name="datepicker-states"></a>Estados de DatePicker  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.DatePicker> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El <xref:System.Windows.Controls.DatePicker> está deshabilitado.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox partes  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|El elemento que contiene el texto inicial en el <xref:System.Windows.Controls.DatePicker>.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|Elemento visual que puede contener una <xref:System.Windows.FrameworkElement>. El texto de la <xref:System.Windows.Controls.TextBox> se muestra en este elemento.|  
  
## <a name="datepickertextbox-states"></a>Estados de DatePickerTextBox  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DatePickerTextBox> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa encima el <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|El usuario no puede cambiar el texto en el <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Marca de agua|WatermarkStates|El control muestra el texto inicial.  El <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está en el estado cuando el usuario no ha escrito texto o selecciona una fecha.|  
|Unwatermarked|WatermarkStates|El usuario ha escrito texto en el <xref:System.Windows.Controls.Primitives.DatePickerTextBox> o seleccionar una fecha en el <xref:System.Windows.Controls.DatePicker>.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="datepicker-controltemplate-example"></a>Ejemplo de ControlTemplate de DatePicker  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.DatePicker> control.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
