---
title: "Estilos y plantillas de Calendar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Calendario [WPF], estilos y plantillas"
  - "ControlTemplate [WPF], Calendar"
  - "partes [WPF], Calendar"
  - "estados [WPF], Calendar"
  - "estilos [WPF], Calendar"
  - "plantillas [WPF], Calendar"
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Estilos y plantillas de Calendar
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.Calendar>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de Calendar  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.Calendar>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|El mes o año mostrado actualmente en <xref:System.Windows.Controls.Calendar>.|  
|PART\_Root|<xref:System.Windows.Controls.Panel>|Panel que contiene el <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## Estados de Calendar  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Calendar>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de CalendarItem  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_Root|<xref:System.Windows.FrameworkElement>|Raíz del control.|  
|PART\_PreviousButton|<xref:System.Windows.Controls.Button>|Botón que muestra la página anterior del calendario cuando se hace clic en él.|  
|PART\_NextButton|<xref:System.Windows.Controls.Button>|Botón que muestra la página siguiente del calendario cuando se hace clic en él.|  
|PART\_HeaderButton|<xref:System.Windows.Controls.Button>|Botón que permite cambiar entre el modo de mes, el modo de año y el modo de década.|  
|PART\_MonthView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido cuando está en el modo de mes.|  
|PART\_YearView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido cuando está en el modo de año o de década.|  
|PART\_DisabledVisual|<xref:System.Windows.FrameworkElement>|Superposición del estado deshabilitado.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|<xref:System.Windows.DataTemplate> que describe la estructura visual.|  
  
## Estados de CalendarItem  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarItem>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Estado Normal|CommonStates|Estado predeterminado.|  
|Estado Disabled|CommonStates|Estado del calendario cuando la propiedad <xref:System.Windows.UIElement.IsEnabled%2A> es `false`.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de CalendarDayButton  
 El control <xref:System.Windows.Controls.Primitives.CalendarDayButton> no tiene ningún elemento con nombre.  
  
## Estados de CalendarDayButton  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarDayButton>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.CalendarDayButton> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre el control <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Pressed|CommonStates|El control <xref:System.Windows.Controls.Primitives.CalendarDayButton> está presionado.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Focused|FocusStates|El botón tiene el foco.|  
|Unfocused|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|RegularDay|DayStates|El botón no representa <xref:System.DateTime.Today%2A?displayProperty=fullName>.|  
|Today|DayStates|El botón representa <xref:System.DateTime.Today%2A?displayProperty=fullName>.|  
|NormalDay|BlackoutDayStates|El botón representa un día que se puede seleccionar.|  
|BlackoutDay|BlackoutDayStates|El botón representa un día que no se puede seleccionar.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de CalendarButton  
 El control <xref:System.Windows.Controls.Primitives.CalendarButton> no tiene ningún elemento con nombre.  
  
## Estados de CalendarButton  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Primitives.CalendarButton>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control <xref:System.Windows.Controls.Primitives.CalendarButton> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre el control <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Pressed|CommonStates|El control <xref:System.Windows.Controls.Primitives.CalendarButton> está presionado.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Focused|FocusStates|El botón tiene el foco.|  
|Unfocused|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate para Calendar  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Calendar> y los tipos asociados.  
  
 [!code-xml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 El ejemplo anterior utiliza uno o más de los siguientes recursos.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para obtener el ejemplo completo, vea          [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)