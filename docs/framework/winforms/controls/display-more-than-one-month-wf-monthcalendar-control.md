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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="1c8de-102">Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c8de-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="1c8de-103">Los formularios Windows Forms <xref:System.Windows.Forms.MonthCalendar> control puede mostrar un máximo de 12 meses a la vez.</span><span class="sxs-lookup"><span data-stu-id="1c8de-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="1c8de-104">De forma predeterminada, el control muestra un solo mes, pero puede especificar el número de meses se muestra y cómo se disponen dentro del control.</span><span class="sxs-lookup"><span data-stu-id="1c8de-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="1c8de-105">Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que no hay espacio suficiente en el formulario para las nuevas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="1c8de-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="1c8de-106">Para mostrar varios meses</span><span class="sxs-lookup"><span data-stu-id="1c8de-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="1c8de-107">Establecer el <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> propiedad al número de meses durante los que mostrar horizontalmente y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="1c8de-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c8de-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c8de-108">See Also</span></span>  
 [<span data-ttu-id="1c8de-109">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="1c8de-109">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [<span data-ttu-id="1c8de-110">Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c8de-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [<span data-ttu-id="1c8de-111">Cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c8de-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
