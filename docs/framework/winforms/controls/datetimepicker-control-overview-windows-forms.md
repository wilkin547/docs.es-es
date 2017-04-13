---
title: "Informaci&#243;n general sobre el control DateTimePicker (formularios Windows Forms) | Microsoft Docs"
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
  - "DateTimePicker"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles selectores de fecha y hora"
  - "DateTimePicker (control) [Windows Forms], acerca de"
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Informaci&#243;n general sobre el control DateTimePicker (formularios Windows Forms)
El control <xref:System.Windows.Forms.DateTimePicker> de Windows Forms permite al usuario seleccionar un solo elemento de una lista de fechas y horas.  Cuando se utiliza para representar una fecha, aparece en dos partes: una lista desplegable con una fecha representada como texto y una cuadrícula, que aparece al hacer clic en la flecha hacia abajo que se encuentra junto a la lista.  La cuadrícula es similar al control <xref:System.Windows.Forms.MonthCalendar>, que puede utilizarse para seleccionar múltiples fechas.  Para obtener más información sobre el control <xref:System.Windows.Forms.MonthCalendar>, vea [Introducción al control MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## Propiedades principales  
 Si desea que <xref:System.Windows.Forms.DateTimePicker> aparezca como un control para seleccionar y editar las horas en lugar de las fechas, establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> en `true` la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en <xref:System.Windows.Forms.DateTimePickerFormat>.  Para obtener más información, vea [Cómo: Mostrar la hora con el control DateTimePicker](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Cuando la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> se establece en `true`, se muestra una casilla junto a la fecha seleccionada en el control.  Cuando se comprueba la casilla, se puede actualizar el valor de fecha y hora seleccionado.  Cuando la casilla está vacía, el valor se muestra no disponible.  
  
 El control <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> y las propiedades <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> determinan el intervalo de fechas y horas.  La propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> contiene la fecha y la hora actuales en las que se establece el control.  Para obtener información detallada, vea [Cómo: Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md).  Los valores se pueden mostrar en cuatro formatos establecidos por la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A>: <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat> o <xref:System.Windows.Forms.DateTimePickerFormat>.  Si está seleccionado un formato personalizado, debe establecer la propiedad <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> en una cadena adecuada.  Para obtener información detallada, vea [Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## Vea también  
 [Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)   
 [Cómo: Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)