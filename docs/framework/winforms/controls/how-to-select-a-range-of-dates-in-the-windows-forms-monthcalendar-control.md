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
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="c1141-102">Procedimiento Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="c1141-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="c1141-103">Una característica importante de los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control es que el usuario puede seleccionar un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="c1141-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="c1141-104">Esta característica es una mejora de la característica de selección de fecha de la <xref:System.Windows.Forms.DateTimePicker> control, que solo permite al usuario seleccionar un valor único de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c1141-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="c1141-105">Puede establecer un intervalo de fechas u obtener un intervalo de selección establecido por el usuario mediante las propiedades de la <xref:System.Windows.Forms.MonthCalendar> control.</span><span class="sxs-lookup"><span data-stu-id="c1141-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="c1141-106">En el ejemplo de código siguiente se muestra cómo establecer un intervalo de selección.</span><span class="sxs-lookup"><span data-stu-id="c1141-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="c1141-107">Para seleccionar un intervalo de fechas</span><span class="sxs-lookup"><span data-stu-id="c1141-107">To select a range of dates</span></span>  
  
1.  <span data-ttu-id="c1141-108">Crear <xref:System.DateTime> objetos que representan la primera y última fecha en un intervalo.</span><span class="sxs-lookup"><span data-stu-id="c1141-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
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
  
2.  <span data-ttu-id="c1141-109">Establecer la propiedad <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1141-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
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
  
     <span data-ttu-id="c1141-110">-O bien-</span><span class="sxs-lookup"><span data-stu-id="c1141-110">–or–</span></span>  
  
     <span data-ttu-id="c1141-111">Establezca las propiedades <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> y <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1141-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1141-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1141-112">See also</span></span>
- [<span data-ttu-id="c1141-113">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="c1141-113">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="c1141-114">Cómo: Cambiar la apariencia de Windows Forms MonthCalendar del Control</span><span class="sxs-lookup"><span data-stu-id="c1141-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="c1141-115">Cómo: Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar de formularios</span><span class="sxs-lookup"><span data-stu-id="c1141-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="c1141-116">Cómo: Mostrar más de un mes en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="c1141-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
