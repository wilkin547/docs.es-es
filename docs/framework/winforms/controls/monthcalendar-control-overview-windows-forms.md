---
title: "Introducci&#243;n al control MonthCalendar (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MonthCalendar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles de calendario, Windows Forms"
  - "calendarios, controles de Windows Forms"
  - "MonthCalendar (control) [Windows Forms], establecer el primer día de la semana"
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Introducci&#243;n al control MonthCalendar (formularios Windows Forms)
El control <xref:System.Windows.Forms.MonthCalendar> de Windows Forms muestra una intuitiva interfaz gráfica de usuario para que los usuarios vean y establezcan información relativa a fechas.  El control muestra un calendario: una cuadrícula que contiene el número de días del mes, ordenado en columnas debajo de los días de la semana con el intervalo de fechas seleccionado resaltado  Para seleccionar un mes diferente, puede hacer clic en los botones de fecha a los lados de la leyenda del mes.  A diferencia del control <xref:System.Windows.Forms.DateTimePicker> similar, puede seleccionar más de una fecha con este control.  Para obtener más información sobre el control <xref:System.Windows.Forms.DateTimePicker>, vea [DateTimePicker \(Control\)](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md).  
  
## Configurar el control MonthCalendar  
 El aspecto del control <xref:System.Windows.Forms.MonthCalendar> es muy configurable.  De manera predeterminada, la fecha de hoy se muestra con un círculo y se muestra en la parte inferior de la cuadrícula.  Puede cambiar esta característica estableciendo las propiedades <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> y <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> en `false`.  También puede agregar los números de la semana al calendario estableciendo la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`.  Estableciendo la propiedad <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A>, puede tener varios meses mostrados horizontal y verticalmente.  De manera predeterminada, el domingo se muestra como el primer día de la semana, pero se puede designar cualquier día utilizando la propiedad <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A>.  
  
 También puede establecer que se muestren determinadas fechas en negrita una sola vez, anual o mensualmente, agregando objetos <xref:System.DateTime> a las propiedades <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> y <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A>.  Para obtener más información, vea [Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 La propiedad clave del control <xref:System.Windows.Forms.MonthCalendar> es <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, el intervalo de fechas seleccionado en el control.  El valor <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> no puede superar el número máximo de días que se pueden seleccionar, establecido en la propiedad <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A>.  Las propiedades <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> y <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> determinan las primeras y últimas fechas que puede seleccionar el usuario.  
  
## Vea también  
 <xref:System.Windows.Forms.MonthCalendar>   
 [MonthCalendar \(Control\)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)