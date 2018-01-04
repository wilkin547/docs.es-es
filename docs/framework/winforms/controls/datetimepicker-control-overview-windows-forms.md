---
title: "Información general sobre el control DateTimePicker (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0db5e532a2688d7f213fd42772234b9600192390
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="datetimepicker-control-overview-windows-forms"></a>Información general sobre el control DateTimePicker (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.DateTimePicker> control permite al usuario seleccionar un único elemento de una lista de fechas u horas. Cuando se utiliza para representar una fecha, aparece en dos partes: una lista desplegable con una fecha representada como texto y una cuadrícula que aparece al hacer clic en la flecha abajo junto a la lista. La cuadrícula es similar a la <xref:System.Windows.Forms.MonthCalendar> control, que puede utilizarse para seleccionar múltiples fechas. Para obtener más información sobre la <xref:System.Windows.Forms.MonthCalendar> control, vea [información general del Control MonthCalendar](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md).  
  
## <a name="key-properties"></a>Propiedades clave  
 Si lo desea el <xref:System.Windows.Forms.DateTimePicker> para que aparezca como un control para seleccionar y editar las horas en lugar de fechas, establezca la <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> propiedad `true` y la <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad <xref:System.Windows.Forms.DateTimePickerFormat.Time>. Para obtener más información, consulte [Cómo: muestra la hora con el DateTimePicker Control](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md).  
  
 Cuando el <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> propiedad está establecida en `true`, se muestra una casilla de verificación situada junto a la fecha seleccionada en el control. Cuando se activa la casilla de verificación, se puede actualizar el valor de fecha y hora seleccionado. Cuando la casilla de verificación está vacía, el valor aparece disponible.  
  
 El control <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> y <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> propiedades determinan el intervalo de fechas y horas. El <xref:System.Windows.Forms.DateTimePicker.Value%2A> propiedad contiene la fecha y hora actual es establecer el control. Para obtener más información, consulte [Cómo: conjunto y devolver fechas con el DateTimePicker Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md). Los valores se pueden mostrar en cuatro formatos, que se establecen mediante el <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, o <xref:System.Windows.Forms.DateTimePickerFormat.Custom>. Si se selecciona un formato personalizado, debe establecer el <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad a una cadena adecuada. Para obtener más información, consulte [Cómo: mostrar una fecha en formato personalizado con el DateTimePicker Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md).  
  
## <a name="see-also"></a>Vea también  
 [Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
