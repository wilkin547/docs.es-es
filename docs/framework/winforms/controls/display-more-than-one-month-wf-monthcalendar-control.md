---
title: Procedimiento para mostrar más de un mes en el control MonthCalendar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: c2252ccf1c8fec0dcaba634e6da093ab976ce1f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614764"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Procedimiento para mostrar más de un mes en el control MonthCalendar de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control puede mostrar un máximo de 12 meses a la vez. De forma predeterminada, el control muestra un solo mes, pero puede especificar el número de meses se muestra y cómo se organizan dentro del control. Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que hay espacio suficiente en el formulario para las nuevas dimensiones.  
  
### <a name="to-display-multiple-months"></a>Para mostrar varios meses  
  
- Establecer el <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> propiedad para el número de meses para mostrar horizontalmente y verticalmente.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>Vea también

- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
- [Cómo: Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Cómo: Cambiar la apariencia de Windows Forms MonthCalendar del Control](how-to-change-monthcalendar-control-appearance.md)
