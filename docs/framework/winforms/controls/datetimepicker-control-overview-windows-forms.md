---
title: Información general sobre el control DateTimePicker (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
ms.openlocfilehash: 1d2e286e3ce91c722be24f059a874b9db5f2ba82
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703186"
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Información general sobre el control DateTimePicker (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.DateTimePicker> control permite al usuario seleccionar un único elemento de una lista de fechas u horas. Cuando se utiliza para representar una fecha, aparece en dos partes: una lista desplegable con una fecha representada en texto y una cuadrícula que aparece al hacer clic en la flecha abajo junto a la lista. La cuadrícula es similar a la <xref:System.Windows.Forms.MonthCalendar> control, que puede utilizarse para seleccionar varias fechas. Para obtener más información sobre la <xref:System.Windows.Forms.MonthCalendar> control, vea [información general del Control MonthCalendar](monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Propiedades clave  
 Si lo desea la <xref:System.Windows.Forms.DateTimePicker> para que aparezca como un control para seleccionar o modificar los tiempos en lugar de fechas, establezca la <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> propiedad `true` y el <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Para obtener más información, vea [Cómo: Mostrar la hora con el Control DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
 Cuando el <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> propiedad está establecida en `true`, se muestra una casilla de verificación situada junto a la fecha seleccionada en el control. Cuando se activa la casilla de verificación, se puede actualizar el valor de fecha y hora seleccionado. Cuando la casilla de verificación está vacía, el valor aparece disponible.  
  
 El control <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> y <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> propiedades determinan el intervalo de fechas y horas. El <xref:System.Windows.Forms.DateTimePicker.Value%2A> propiedad contiene la fecha y hora actuales es establecer el control. Para obtener más detalles, vea [Cómo: Establecer y devolver fechas con el Windows Forms Control DateTimePicker](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Los valores se pueden mostrar en cuatro formatos, que se establecen mediante el <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Si se selecciona un formato personalizado, debe establecer el <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad en una cadena adecuada. Para obtener más detalles, vea [Cómo: Mostrar una fecha en un formato personalizado con el Control DateTimePicker de formularios de Windows](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vea también
- [Cómo: Mostrar una fecha en un formato personalizado con el Control DateTimePicker de formularios de Windows](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
- [Cómo: Establecer y devolver fechas con el Control DateTimePicker de formularios de Windows](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
