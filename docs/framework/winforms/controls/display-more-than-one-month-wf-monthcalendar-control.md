---
title: Filtrar Mostrar más de un mes en el Control MonthCalendar de formularios de Windows
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
ms.openlocfilehash: febed820bae460f51bb19f08caa6027011abd55d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715352"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="3b796-102">Procedimiento Mostrar más de un mes en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="3b796-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="3b796-103">Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control puede mostrar un máximo de 12 meses a la vez.</span><span class="sxs-lookup"><span data-stu-id="3b796-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="3b796-104">De forma predeterminada, el control muestra un solo mes, pero puede especificar el número de meses se muestra y cómo se organizan dentro del control.</span><span class="sxs-lookup"><span data-stu-id="3b796-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="3b796-105">Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que hay espacio suficiente en el formulario para las nuevas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3b796-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="3b796-106">Para mostrar varios meses</span><span class="sxs-lookup"><span data-stu-id="3b796-106">To display multiple months</span></span>  
  
-   <span data-ttu-id="3b796-107">Establecer el <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> propiedad para el número de meses para mostrar horizontalmente y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="3b796-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3b796-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b796-108">See also</span></span>
- [<span data-ttu-id="3b796-109">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="3b796-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="3b796-110">Cómo: Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="3b796-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="3b796-111">Cómo: Cambiar la apariencia de Windows Forms MonthCalendar del Control</span><span class="sxs-lookup"><span data-stu-id="3b796-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
