---
title: Estilos y plantillas de Calendar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
ms.openlocfilehash: 64cb62a3459a3eeea6aa5e91b433a58a88ab08ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283554"
---
# <a name="calendar-styles-and-templates"></a>Estilos y plantillas de Calendar
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.Calendar>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="calendar-parts"></a>Elementos de calendario  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Calendar>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|Mes o año mostrado actualmente en el <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|El panel que contiene el <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Estados del calendario  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Calendar>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="calendaritem-parts"></a>Elementos CalendarItem  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|Raíz del control.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|Botón que muestra la página anterior del calendario cuando se hace clic en él.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|Botón que muestra la página siguiente del calendario cuando se hace clic en él.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|El botón que permite cambiar entre el modo de mes, el modo de año y el modo de década.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido en modo de mes.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido en modo de año o década.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|La superposición del Estado deshabilitado.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate> que describe la estructura visual.|  
  
## <a name="calendaritem-states"></a>Estados de CalendarItem  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Estado normal|CommonStates|El estado predeterminado.|  
|Estado deshabilitado|CommonStates|Estado del calendario cuando se `false`la propiedad <xref:System.Windows.UIElement.IsEnabled%2A>.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="calendardaybutton-parts"></a>Elementos CalendarDayButton  
 El control <xref:System.Windows.Controls.Primitives.CalendarDayButton> no tiene ninguna parte con nombre.  
  
## <a name="calendardaybutton-states"></a>Estados de CalendarDayButton  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarDayButton>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|La <xref:System.Windows.Controls.Primitives.CalendarDayButton> está deshabilitada.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Presionado|CommonStates|Se presiona el <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Con foco|FocusStates|El botón tiene el foco.|  
|Sin foco|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|RegularDay|DayStates|El botón no representa <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Hoy|DayStates|El botón representa <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|El botón representa un día que se puede seleccionar.|  
|BlackoutDay|BlackoutDayStates|El botón representa un día que no se puede seleccionar.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="calendarbutton-parts"></a>Elementos CalendarButton  
 El control <xref:System.Windows.Controls.Primitives.CalendarButton> no tiene ninguna parte con nombre.  
  
## <a name="calendarbutton-states"></a>Estados de CalendarButton  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarButton>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|La <xref:System.Windows.Controls.Primitives.CalendarButton> está deshabilitada.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Presionado|CommonStates|Se presiona el <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Con foco|FocusStates|El botón tiene el foco.|  
|Sin foco|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="calendar-controltemplate-example"></a>Ejemplo de ControlTemplate de Calendar  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Calendar> y los tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
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
