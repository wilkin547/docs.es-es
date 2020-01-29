---
title: Introducción al control MonthCalendar
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734943"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Introducción al control MonthCalendar (formularios Windows Forms)
El control Windows Forms <xref:System.Windows.Forms.MonthCalendar> presenta una interfaz gráfica intuitiva para que los usuarios puedan ver y establecer la información de fecha. El control muestra un calendario: una cuadrícula que contiene los días numerados del mes, organizados en columnas debajo de los días de la semana, con el intervalo de fechas seleccionado resaltado. Puede seleccionar un mes diferente haciendo clic en los botones de flecha situados a cada lado del título del mes. A diferencia del control de <xref:System.Windows.Forms.DateTimePicker> similar, puede seleccionar más de una fecha con este control. Para obtener más información sobre el control de <xref:System.Windows.Forms.DateTimePicker>, vea [DateTimePicker (control](datetimepicker-control-windows-forms.md)).  
  
## <a name="configuring-the-monthcalendar-control"></a>Configurar el control MonthCalendar  
 La apariencia del control <xref:System.Windows.Forms.MonthCalendar> es muy configurable. De forma predeterminada, la fecha de hoy se muestra como con un círculo y también se anota en la parte inferior de la cuadrícula. Puede cambiar esta característica estableciendo las propiedades <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> y <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> en `false`. También puede agregar números de semana al calendario estableciendo la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`. Al establecer la propiedad <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>, puede tener varios meses visibles horizontal y verticalmente. De forma predeterminada, el domingo se muestra como el primer día de la semana, pero se puede designar cualquier día mediante la propiedad <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>.  
  
 También puede establecer que determinadas fechas se muestren en negrita de una vez, anualmente o mensualmente, agregando <xref:System.DateTime> objetos a las propiedades <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>y <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>. Para obtener más información, vea [Cómo: Mostrar días específicos en negrita con el control MonthCalendar Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 La propiedad clave del control <xref:System.Windows.Forms.MonthCalendar> es <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, el intervalo de fechas seleccionado en el control. El valor <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> no puede superar el número máximo de días que se pueden seleccionar, establecido en la propiedad <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>. Las fechas más tempranas y más recientes que puede seleccionar el usuario se determinan mediante las propiedades <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> y <xref:System.Windows.Forms.MonthCalendar.MinDate%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MonthCalendar>
- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
