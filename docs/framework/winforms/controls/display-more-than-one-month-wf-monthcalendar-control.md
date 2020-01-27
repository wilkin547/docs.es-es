---
title: Mostrar más de un mes en el control MonthCalendar
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
ms.openlocfilehash: 5d3925bc19ddcd67742f0ab8b5b2e45530820f38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745902"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> de Windows Forms puede mostrar hasta 12 meses a la vez. De forma predeterminada, el control solo muestra un mes, pero puede especificar el número de meses que se muestran y cómo se organizan dentro del control. Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que debe asegurarse de que hay suficiente espacio en el formulario para las nuevas dimensiones.  
  
### <a name="to-display-multiple-months"></a>Para mostrar varios meses  
  
- Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> en el número de meses que se mostrarán horizontal y verticalmente.  
  
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
- [Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](how-to-change-monthcalendar-control-appearance.md)
