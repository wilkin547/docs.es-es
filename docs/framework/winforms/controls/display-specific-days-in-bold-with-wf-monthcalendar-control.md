---
title: Mostrar días específicos en negrita con el control MonthCalendar
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
ms.openlocfilehash: 377eb76f562fff20aae2136ddb7130516d2d76f7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745884"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a><span data-ttu-id="f3983-102">Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3983-102">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>
<span data-ttu-id="f3983-103">El control <xref:System.Windows.Forms.MonthCalendar> de Windows Forms puede mostrar los días en negrita, ya sea como fechas singulares o de forma repetitiva.</span><span class="sxs-lookup"><span data-stu-id="f3983-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control can display days in bold type, either as singular dates or on a repeating basis.</span></span> <span data-ttu-id="f3983-104">Podría hacer esto para atraer la atención a fechas especiales, como festividades y fines de semana.</span><span class="sxs-lookup"><span data-stu-id="f3983-104">You might do this to draw attention to special dates, such as holidays and weekends.</span></span>  
  
 <span data-ttu-id="f3983-105">Tres propiedades controlan esta característica.</span><span class="sxs-lookup"><span data-stu-id="f3983-105">Three properties control this feature.</span></span> <span data-ttu-id="f3983-106">La propiedad <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> contiene fechas únicas.</span><span class="sxs-lookup"><span data-stu-id="f3983-106">The <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> property contains single dates.</span></span> <span data-ttu-id="f3983-107">La propiedad <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> contiene fechas que aparecen en negrita todos los años.</span><span class="sxs-lookup"><span data-stu-id="f3983-107">The <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> property contains dates that appear in bold every year.</span></span> <span data-ttu-id="f3983-108">La propiedad <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> contiene fechas que aparecen en negrita cada mes.</span><span class="sxs-lookup"><span data-stu-id="f3983-108">The <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> property contains dates that appear in bold every month.</span></span> <span data-ttu-id="f3983-109">Cada una de estas propiedades contiene una matriz de objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="f3983-109">Each of these properties contains an array of <xref:System.DateTime> objects.</span></span> <span data-ttu-id="f3983-110">Para agregar o quitar una fecha de una de estas listas, debe agregar o quitar un objeto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="f3983-110">To add or remove a date from one of these lists, you must add or remove a <xref:System.DateTime> object.</span></span>  
  
### <a name="to-make-a-date-appear-in-bold-type"></a><span data-ttu-id="f3983-111">Para que una fecha aparezca en negrita</span><span class="sxs-lookup"><span data-stu-id="f3983-111">To make a date appear in bold type</span></span>  
  
1. <span data-ttu-id="f3983-112">Cree los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="f3983-112">Create the <xref:System.DateTime> objects.</span></span>  
  
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
  
2. <span data-ttu-id="f3983-113">Realice una sola fecha en negrita llamando al método <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> del control <xref:System.Windows.Forms.MonthCalendar>.</span><span class="sxs-lookup"><span data-stu-id="f3983-113">Make a single date bold by calling the <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> method of the <xref:System.Windows.Forms.MonthCalendar> control.</span></span>  
  
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
  
     <span data-ttu-id="f3983-114">-O bien-</span><span class="sxs-lookup"><span data-stu-id="f3983-114">–or–</span></span>  
  
     <span data-ttu-id="f3983-115">Cree un conjunto de fechas en negrita de una vez creando una matriz de <xref:System.DateTime> objetos y asignándoles una de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="f3983-115">Make a set of dates bold all at once by creating an array of <xref:System.DateTime> objects and assigning it to one of the properties.</span></span>  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a><span data-ttu-id="f3983-116">Para que una fecha aparezca en la fuente normal</span><span class="sxs-lookup"><span data-stu-id="f3983-116">To make a date appear in the regular font</span></span>  
  
1. <span data-ttu-id="f3983-117">Haga que una sola fecha en negrita aparezca en la fuente normal llamando al método <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3983-117">Make a single bolded date appear in the regular font by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> method.</span></span>  
  
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
  
     <span data-ttu-id="f3983-118">-O bien-</span><span class="sxs-lookup"><span data-stu-id="f3983-118">–or–</span></span>  
  
     <span data-ttu-id="f3983-119">Quite todas las fechas en negrita de una de las tres listas llamando al método <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3983-119">Remove all the bolded dates from one of the three lists by calling the <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, or <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. <span data-ttu-id="f3983-120">Actualice la apariencia de la fuente llamando al método <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3983-120">Update the appearance of the font by calling the <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> method.</span></span>  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f3983-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3983-121">See also</span></span>

- [<span data-ttu-id="f3983-122">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="f3983-122">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="f3983-123">Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3983-123">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="f3983-124">Cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3983-124">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>](how-to-change-monthcalendar-control-appearance.md)
- [<span data-ttu-id="f3983-125">Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3983-125">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
