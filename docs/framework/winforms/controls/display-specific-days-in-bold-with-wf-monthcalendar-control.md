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
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> de Windows Forms puede mostrar los días en negrita, ya sea como fechas singulares o de forma repetitiva. Podría hacer esto para atraer la atención a fechas especiales, como festividades y fines de semana.  
  
 Tres propiedades controlan esta característica. La propiedad <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> contiene fechas únicas. La propiedad <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> contiene fechas que aparecen en negrita todos los años. La propiedad <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> contiene fechas que aparecen en negrita cada mes. Cada una de estas propiedades contiene una matriz de objetos <xref:System.DateTime>. Para agregar o quitar una fecha de una de estas listas, debe agregar o quitar un objeto <xref:System.DateTime>.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Para que una fecha aparezca en negrita  
  
1. Cree los objetos <xref:System.DateTime>.  
  
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
  
2. Realice una sola fecha en negrita llamando al método <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> del control <xref:System.Windows.Forms.MonthCalendar>.  
  
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
  
     -O bien-  
  
     Cree un conjunto de fechas en negrita de una vez creando una matriz de <xref:System.DateTime> objetos y asignándoles una de las propiedades.  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>Para que una fecha aparezca en la fuente normal  
  
1. Haga que una sola fecha en negrita aparezca en la fuente normal llamando al método <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.  
  
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
  
     -O bien-  
  
     Quite todas las fechas en negrita de una de las tres listas llamando al método <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2. Actualice la apariencia de la fuente llamando al método <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## <a name="see-also"></a>Vea también

- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
- [Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](how-to-change-monthcalendar-control-appearance.md)
- [Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
