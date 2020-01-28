---
title: Información general sobre el control DateTimePicker
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 63271dd91116c1f68d426f3ed5aa710644ded928
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746934"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Información general sobre el control DateTimePicker (formularios Windows Forms)
El control Windows Forms <xref:System.Windows.Forms.DateTimePicker> permite al usuario seleccionar un único elemento de una lista de fechas u horas. Cuando se usa para representar una fecha, aparece en dos partes: una lista desplegable con una fecha representada en el texto y una cuadrícula que aparece al hacer clic en la flecha hacia abajo situada junto a la lista. La cuadrícula se parece al control <xref:System.Windows.Forms.MonthCalendar>, que se puede usar para seleccionar varias fechas. Para obtener más información sobre el control de <xref:System.Windows.Forms.MonthCalendar>, vea [información general sobre el control MonthCalendar](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Propiedades clave  
 Si desea que la <xref:System.Windows.Forms.DateTimePicker> aparezca como un control para la selección o edición de horas en lugar de fechas, establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> en `true` y la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Para obtener más información, vea [Cómo: Mostrar la hora con el control DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Cuando la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> está establecida en `true`, se muestra una casilla junto a la fecha seleccionada en el control. Cuando la casilla está activada, el valor de fecha y hora seleccionado se puede actualizar. Cuando la casilla está vacía, el valor aparece como no disponible.  
  
 Las propiedades <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> y <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> del control determinan el intervalo de fechas y horas. La propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> contiene la fecha y la hora actuales en que se establece el control. Para obtener más información, vea [Cómo: establecer y devolver fechas con el Control Windows Forms DateTimePicker](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Los valores se pueden mostrar en cuatro formatos, que se establecen mediante la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A>: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Si se selecciona un formato personalizado, debe establecer la propiedad <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> en una cadena adecuada. Para obtener más información, vea [Cómo: mostrar una fecha en un formato personalizado con el Control Windows Forms DateTimePicker](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vea también

- [Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
