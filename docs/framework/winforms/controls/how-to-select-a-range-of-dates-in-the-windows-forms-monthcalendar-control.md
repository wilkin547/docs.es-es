---
title: Filtrar para seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms
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
ms.openlocfilehash: 0e032a6285c43d7e96c7d59444da6d6598bd8100
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129953"
---
# <a name="how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="f775c-102">Filtrar para seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f775c-102">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="f775c-103">Una característica importante de los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control es que el usuario puede seleccionar un intervalo de fechas.</span><span class="sxs-lookup"><span data-stu-id="f775c-103">An important feature of the Windows Forms <xref:System.Windows.Forms.MonthCalendar> control is that the user can select a range of dates.</span></span> <span data-ttu-id="f775c-104">Esta característica es una mejora de la característica de selección de fecha de la <xref:System.Windows.Forms.DateTimePicker> control, que solo permite al usuario seleccionar un valor único de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="f775c-104">This feature is an improvement over the date-selection feature of the <xref:System.Windows.Forms.DateTimePicker> control, which only enables the user to select a single date/time value.</span></span> <span data-ttu-id="f775c-105">Puede establecer un intervalo de fechas u obtener un intervalo de selección establecido por el usuario mediante las propiedades de la <xref:System.Windows.Forms.MonthCalendar> control.</span><span class="sxs-lookup"><span data-stu-id="f775c-105">You can set a range of dates or get a selection range set by the user by using properties of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span> <span data-ttu-id="f775c-106">En el ejemplo de código siguiente se muestra cómo establecer un intervalo de selección.</span><span class="sxs-lookup"><span data-stu-id="f775c-106">The following code example demonstrates how to set a selection range.</span></span>  
  
### <a name="to-select-a-range-of-dates"></a><span data-ttu-id="f775c-107">Para seleccionar un intervalo de fechas</span><span class="sxs-lookup"><span data-stu-id="f775c-107">To select a range of dates</span></span>  
  
1.  <span data-ttu-id="f775c-108">Crear <xref:System.DateTime> objetos que representan la primera y última fecha en un intervalo.</span><span class="sxs-lookup"><span data-stu-id="f775c-108">Create <xref:System.DateTime> objects that represent the first and last dates in a range.</span></span>  
  
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
  
2.  <span data-ttu-id="f775c-109">Establecer la propiedad <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.</span><span class="sxs-lookup"><span data-stu-id="f775c-109">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> property.</span></span>  
  
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
  
     <span data-ttu-id="f775c-110">-O bien-</span><span class="sxs-lookup"><span data-stu-id="f775c-110">–or–</span></span>  
  
     <span data-ttu-id="f775c-111">Establezca las propiedades <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> y <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="f775c-111">Set the <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> and <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> properties.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f775c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f775c-112">See also</span></span>

- [<span data-ttu-id="f775c-113">Control MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="f775c-113">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="f775c-114">Filtrar para cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f775c-114">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="f775c-115">Filtrar para mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f775c-115">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="f775c-116">Filtrar para mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f775c-116">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
