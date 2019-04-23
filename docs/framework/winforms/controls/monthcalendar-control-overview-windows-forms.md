---
title: Introducción al control MonthCalendar (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: 8928a78735392920d893661c70554bd35eba2886
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106241"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Introducción al control MonthCalendar (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control presenta una interfaz gráfica intuitiva para los usuarios ver y establecer información de fecha. El control muestra un calendario: una cuadrícula que contiene los días numerados del mes, organizados en columnas bajo los días de la semana, con el intervalo de fechas resaltado seleccionado. Puede seleccionar un mes distinto, haga clic en los botones de flecha a cada lado del título del mes. A diferencia de similar <xref:System.Windows.Forms.DateTimePicker> control, puede seleccionar más de una fecha con este control. Para obtener más información sobre la <xref:System.Windows.Forms.DateTimePicker> control, vea [DateTimePicker Control](datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Configurar el Control MonthCalendar  
 El <xref:System.Windows.Forms.MonthCalendar> la apariencia del control es altamente configurable. De forma predeterminada, la fecha de hoy se muestra con un círculo y también se indica en la parte inferior de la cuadrícula. Puede cambiar esta característica estableciendo la <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> y <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> propiedades a `false`. También puede agregar números de semana al calendario estableciendo el <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> propiedad `true`. Estableciendo el <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> propiedad, puede tener varios meses que se muestran horizontal y verticalmente. De forma predeterminada, se muestra el domingo como primer día de la semana, pero se puede designar cualquier día mediante la <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> propiedad.  
  
 También puede establecer determinadas fechas para mostrarse en negrita según una sola vez, anuales o mensuales, agregando <xref:System.DateTime> objetos a la <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, y <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> propiedades. Para obtener más información, vea [Cómo: Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 La propiedad de clave de la <xref:System.Windows.Forms.MonthCalendar> control es <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, el intervalo de fechas seleccionadas en el control. El <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> valor no puede superar el número máximo de días que se pueden seleccionar, establecido el <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> propiedad. El usuario puede seleccionar las primeras y últimas fechas están determinadas por la <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> y <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> propiedades.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
