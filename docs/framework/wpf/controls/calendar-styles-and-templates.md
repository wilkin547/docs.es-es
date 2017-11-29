---
title: Estilos y plantillas de Calendar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Calendar
- templates [WPF], Calendar
- states [WPF], Calendar
- parts [WPF], Calendar
- Calendar [WPF], styles and templates
- ControlTemplate [WPF], Calendar
ms.assetid: f4fcf046-7a8f-41b8-b5a8-534b64e0345c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b27049c63faa9bf84dc5febd210a29a530f175a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="calendar-styles-and-templates"></a>Estilos y plantillas de Calendar
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.Calendar> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
## <a name="calendar-parts"></a>Elementos de calendario  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Calendar> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_CalendarItem|<xref:System.Windows.Controls.Primitives.CalendarItem>|El mes que se muestra actualmente o el año en el <xref:System.Windows.Controls.Calendar>.|  
|PART_Root|<xref:System.Windows.Controls.Panel>|El panel que contiene el <xref:System.Windows.Controls.Primitives.CalendarItem>.|  
  
## <a name="calendar-states"></a>Estados de calendario  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Calendar> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="calendaritem-parts"></a>Partes de CalendarItem  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.CalendarItem> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Root|<xref:System.Windows.FrameworkElement>|La raíz del control.|  
|PART_PreviousButton|<xref:System.Windows.Controls.Button>|El botón que muestra la página anterior del calendario cuando se hace clic en.|  
|PART_NextButton|<xref:System.Windows.Controls.Button>|El botón que muestra la página siguiente del calendario cuando se hace clic en.|  
|PART_HeaderButton|<xref:System.Windows.Controls.Button>|El botón que permite cambiar entre el modo de mes, el modo de año y el modo de década.|  
|PART_MonthView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido cuando está en modo de mes.|  
|PART_YearView|<xref:System.Windows.Controls.Grid>|Hospeda el contenido cuando está en modo de año o década.|  
|PART_DisabledVisual|<xref:System.Windows.FrameworkElement>|La superposición del estado deshabilitado.|  
|DayTitleTemplate|<xref:System.Windows.DataTemplate>|El <xref:System.Windows.DataTemplate> que describe la estructura visual.|  
  
## <a name="calendaritem-states"></a>Estados de CalendarItem  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.CalendarItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Estado normal|CommonStates|El estado predeterminado.|  
|Estado deshabilitado|CommonStates|El estado del calendario cuando la <xref:System.Windows.UIElement.IsEnabled%2A> propiedad es `false`.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="calendardaybutton-parts"></a>Partes de CalendarDayButton  
 El <xref:System.Windows.Controls.Primitives.CalendarDayButton> control no tiene los elementos con nombre.  
  
## <a name="calendardaybutton-states"></a>Estados de CalendarDayButton  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.CalendarDayButton> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El <xref:System.Windows.Controls.Primitives.CalendarDayButton> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa encima el <xref:System.Windows.Controls.Primitives.CalendarDayButton>.|  
|Presionado|CommonStates|El <xref:System.Windows.Controls.Primitives.CalendarDayButton> está presionado.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Con foco|FocusStates|El botón tiene el foco.|  
|Sin foco|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|RegularDay|DayStates|El botón no representa <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|Hoy|DayStates|Representa el botón <xref:System.DateTime.Today%2A?displayProperty=nameWithType>.|  
|NormalDay|BlackoutDayStates|El botón representa un día que se pueden seleccionar.|  
|BlackoutDay|BlackoutDayStates|El botón representa un día que no se pueden seleccionar.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="calendarbutton-parts"></a>Partes de CalendarButton  
 El <xref:System.Windows.Controls.Primitives.CalendarButton> control no tiene los elementos con nombre.  
  
## <a name="calendarbutton-states"></a>Estados de CalendarButton  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.CalendarButton> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El <xref:System.Windows.Controls.Primitives.CalendarButton> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se sitúa encima el <xref:System.Windows.Controls.Primitives.CalendarButton>.|  
|Presionado|CommonStates|El <xref:System.Windows.Controls.Primitives.CalendarButton> está presionado.|  
|Seleccionado|SelectionStates|El botón está seleccionado.|  
|No seleccionado|SelectionStates|El botón no está seleccionado.|  
|CalendarButtonFocused|CalendarButtonFocusStates|El botón tiene el foco.|  
|CalendarButtonUnfocused|CalendarButtonFocusStates|El botón no tiene el foco.|  
|Con foco|FocusStates|El botón tiene el foco.|  
|Sin foco|FocusStates|El botón no tiene el foco.|  
|Activo|ActiveStates|El botón está activo.|  
|Inactivo|ActiveStates|El botón está inactivo.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="calendar-controltemplate-example"></a>Ejemplo de ControlTemplate de calendario  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Calendar> control y tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#Calendar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/calendar.xaml#calendar)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
