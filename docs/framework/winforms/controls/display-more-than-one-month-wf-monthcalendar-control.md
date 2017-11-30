---
title: "Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63cf236f93fa3352e536c71000f6bb110abf02fa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.MonthCalendar> control puede mostrar un máximo de 12 meses a la vez. De forma predeterminada, el control muestra un solo mes, pero puede especificar el número de meses se muestra y cómo se disponen dentro del control. Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que no hay espacio suficiente en el formulario para las nuevas dimensiones.  
  
### <a name="to-display-multiple-months"></a>Para mostrar varios meses  
  
-   Establecer el <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> propiedad al número de meses durante los que mostrar horizontalmente y verticalmente.  
  
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
 [MonthCalendar (control)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
