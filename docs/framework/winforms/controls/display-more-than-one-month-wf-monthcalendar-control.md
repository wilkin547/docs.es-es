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
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="40007-102">Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40007-102">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="40007-103">El control <xref:System.Windows.Forms.MonthCalendar> de Windows Forms puede mostrar hasta 12 meses a la vez.</span><span class="sxs-lookup"><span data-stu-id="40007-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display up to 12 months at a time.</span></span> <span data-ttu-id="40007-104">De forma predeterminada, el control solo muestra un mes, pero puede especificar el número de meses que se muestran y cómo se organizan dentro del control.</span><span class="sxs-lookup"><span data-stu-id="40007-104">By default, the control displays only one month, but you can specify how many months are displayed and how they are arranged within the control.</span></span> <span data-ttu-id="40007-105">Al cambiar las dimensiones del calendario, el control cambia de tamaño, por lo que debe asegurarse de que hay suficiente espacio en el formulario para las nuevas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="40007-105">When you change the calendar dimensions, the control is resized, so be sure there is enough room on the form for the new dimensions.</span></span>  
  
### <a name="to-display-multiple-months"></a><span data-ttu-id="40007-106">Para mostrar varios meses</span><span class="sxs-lookup"><span data-stu-id="40007-106">To display multiple months</span></span>  
  
- <span data-ttu-id="40007-107">Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> en el número de meses que se mostrarán horizontal y verticalmente.</span><span class="sxs-lookup"><span data-stu-id="40007-107">Set the <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> property to the number of months to display horizontally and vertically.</span></span>  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="40007-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40007-108">See also</span></span>

- [<span data-ttu-id="40007-109">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="40007-109">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="40007-110">Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40007-110">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="40007-111">Cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40007-111">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
