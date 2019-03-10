---
title: Filtrar Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar de formularios
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
ms.openlocfilehash: c27037a166d147df51731c5d59fd42f73294c7ad
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718979"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Procedimiento Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar de formularios
Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control puede mostrar días en negrita, como fechas singulares o de forma repetida. Puede hacerlo para llamar la atención sobre las fechas especiales, tales como vacaciones y fines de semana.  
  
 Tres propiedades que controlan esta característica. El <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> propiedad contiene fechas únicas. El <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> propiedad contiene las fechas que aparecen en negrita cada año. El <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> propiedad contiene las fechas que aparecen en negrita cada mes. Cada una de estas propiedades contiene una matriz de <xref:System.DateTime> objetos. Para agregar o quitar una fecha de una de estas listas, debe agregar o quitar un <xref:System.DateTime> objeto.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Para que una fecha aparecen en negrita  
  
1.  Crear el <xref:System.DateTime> objetos.  
  
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
  
2.  Realizar una sola fecha en negrita mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> método de la <xref:System.Windows.Forms.MonthCalendar> control.  
  
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
  
     Poner un conjunto de fechas en negrita a la vez mediante la creación de una matriz de <xref:System.DateTime> objetos y asígnela a una de las propiedades.  
  
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
  
1.  Para que una fecha en negrita solo aparecen en la fuente normal mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> método.  
  
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
  
     Quitar todas las fechas en negrita de una de las tres listas mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> método.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  Actualizar la apariencia de la fuente mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> método.  
  
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
- [Cómo: Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Cómo: Cambiar la apariencia de Windows Forms MonthCalendar del Control](how-to-change-monthcalendar-control-appearance.md)
- [Cómo: Mostrar más de un mes en el Control MonthCalendar de formularios de Windows](display-more-than-one-month-wf-monthcalendar-control.md)
