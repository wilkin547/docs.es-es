---
title: Filtrar para mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], displaying dates in bold
- examples [Windows Forms], calendar controls
- GetDayBold event
- MonthCalendar control [Windows Forms], dates displayed in bold
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
ms.openlocfilehash: cf3ec21aa0272f60599f5659d78214120bcfcaf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073707"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="a585a-102">Filtrar para mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a585a-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="a585a-103">Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control puede mostrar días en negrita, como fechas singulares o de forma repetida.</span><span class="sxs-lookup"><span data-stu-id="a585a-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="a585a-104">Puede hacerlo para llamar la atención sobre las fechas especiales, tales como vacaciones y fines de semana.</span><span class="sxs-lookup"><span data-stu-id="a585a-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="a585a-105">Tres propiedades que controlan esta característica.</span><span class="sxs-lookup"><span data-stu-id="a585a-105">Three properties control this feature.</span></span> <span data-ttu-id="a585a-106">El <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> propiedad contiene fechas únicas.</span><span class="sxs-lookup"><span data-stu-id="a585a-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="a585a-107">El <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> propiedad contiene las fechas que aparecen en negrita cada año.</span><span class="sxs-lookup"><span data-stu-id="a585a-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="a585a-108">El <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> propiedad contiene las fechas que aparecen en negrita cada mes.</span><span class="sxs-lookup"><span data-stu-id="a585a-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="a585a-109">Cada una de estas propiedades contiene una matriz de <xref:System.DateTime> objetos.</span><span class="sxs-lookup"><span data-stu-id="a585a-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="a585a-110">Para agregar o quitar una fecha de una de estas listas, debe agregar o quitar un <xref:System.DateTime> objeto.</span><span class="sxs-lookup"><span data-stu-id="a585a-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="a585a-111">Para que una fecha aparecen en negrita</span><span class="sxs-lookup"><span data-stu-id="a585a-111">To make a date appear in bold type</span></span>  
  
1.  <span data-ttu-id="a585a-112">Crear el <xref:System.DateTime> objetos.</span><span class="sxs-lookup"><span data-stu-id="a585a-112">Create the <xref:System.DateTime> objects.</span></span>  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2.  <span data-ttu-id="a585a-113">Realizar una sola fecha en negrita mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> método de la <xref:System.Windows.Forms.MonthCalendar> control.</span><span class="sxs-lookup"><span data-stu-id="a585a-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a585a-114">-O bien-</span><span class="sxs-lookup"><span data-stu-id="a585a-114">–or–</span></span>  
  
     <span data-ttu-id="a585a-115">Poner un conjunto de fechas en negrita a la vez mediante la creación de una matriz de <xref:System.DateTime> objetos y asígnela a una de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a585a-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="a585a-116">Para que una fecha aparezca en la fuente normal</span><span class="sxs-lookup"><span data-stu-id="a585a-116">To make a date appear in the regular font</span></span>  
  
1.  <span data-ttu-id="a585a-117">Para que una fecha en negrita solo aparecen en la fuente normal mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a585a-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     <span data-ttu-id="a585a-118">-O bien-</span><span class="sxs-lookup"><span data-stu-id="a585a-118">–or–</span></span>  
  
     <span data-ttu-id="a585a-119">Quitar todas las fechas en negrita de una de las tres listas mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a585a-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <span data-ttu-id="a585a-120">Actualizar la apariencia de la fuente mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a585a-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a585a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a585a-121">See also</span></span>

- [<span data-ttu-id="a585a-122">Control MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="a585a-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="a585a-123">Filtrar para seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a585a-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="a585a-124">Filtrar para cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a585a-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="a585a-125">Filtrar para mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a585a-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
