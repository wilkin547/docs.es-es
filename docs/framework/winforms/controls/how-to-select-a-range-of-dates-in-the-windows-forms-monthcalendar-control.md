---
title: Seleccionar un intervalo de fechas en el control MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], selecting range in calendar controls
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], selecting date range
- MonthCalendar control [Windows Forms], selecting date range
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
ms.openlocfilehash: bda96af21a8f86a54d5c0fe0204546b980076d26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732899"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Cómo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms
Una característica importante del control de <xref:System.Windows.Forms.MonthCalendar> Windows Forms es que el usuario puede seleccionar un intervalo de fechas. Esta característica es una mejora respecto a la característica de selección de fecha del control <xref:System.Windows.Forms.DateTimePicker>, que solo permite al usuario seleccionar un valor de fecha y hora único. Puede establecer un intervalo de fechas u obtener un intervalo de selección establecido por el usuario mediante las propiedades del control <xref:System.Windows.Forms.MonthCalendar>. En el ejemplo de código siguiente se muestra cómo establecer un intervalo de selección.  
  
### <a name="to-select-a-range-of-dates"></a>Para seleccionar un intervalo de fechas  
  
1. Cree <xref:System.DateTime> objetos que representen la primera y la última fecha de un intervalo.  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2. Establecer la propiedad <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     O bien  
  
     Establezca las propiedades <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> y <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## <a name="see-also"></a>Consulte también

- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
- [Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](how-to-change-monthcalendar-control-appearance.md)
- [Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
