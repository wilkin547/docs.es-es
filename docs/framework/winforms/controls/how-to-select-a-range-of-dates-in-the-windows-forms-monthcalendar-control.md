---
title: Procedimiento Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows
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
ms.openlocfilehash: 4c7100f77c313d219cfd4cceff5ae3015eae4c18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558454"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a>Procedimiento Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows
Una característica importante de los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control es que el usuario puede seleccionar un intervalo de fechas. Esta característica es una mejora de la característica de selección de fecha de la <xref:System.Windows.Forms.DateTimePicker> control, que solo permite al usuario seleccionar un valor único de fecha y hora. Puede establecer un intervalo de fechas u obtener un intervalo de selección establecido por el usuario mediante las propiedades de la <xref:System.Windows.Forms.MonthCalendar> control. En el ejemplo de código siguiente se muestra cómo establecer un intervalo de selección.  
  
### <a name="to-select-a-range-of-dates"></a>Para seleccionar un intervalo de fechas  
  
1.  Crear <xref:System.DateTime> objetos que representan la primera y última fecha en un intervalo.  
  
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
  
2.  Establecer la propiedad <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.  
  
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
  
     -O bien-  
  
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
  
## <a name="see-also"></a>Vea también
- [MonthCalendar (control)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [Cómo: Cambiar la apariencia de Windows Forms MonthCalendar del Control](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
- [Cómo: Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar de formularios](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Cómo: Mostrar más de un mes en el Control MonthCalendar de formularios de Windows](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
