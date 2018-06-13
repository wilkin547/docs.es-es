---
title: 'Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms'
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
ms.openlocfilehash: 0ee89fb4cfb6ddbf975eb0e85e7dd1bab30f08d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528536"
---
# <a name="how-to-display-specific-days-in-bold-with-the-windows-forms-monthcalendar-control"></a>Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.MonthCalendar> control puede mostrar días en negrita, como fechas singulares o de forma repetitiva. Puede hacer esto para destacar fechas especiales, tales como vacaciones y fines de semana.  
  
 Tres propiedades que controlan esta característica. El <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> propiedad contiene fechas únicas. El <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> propiedad contiene fechas que aparecen en negrita todos los años. El <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> propiedad contiene fechas que aparecen en negrita todos los meses. Cada una de estas propiedades contiene una matriz de <xref:System.DateTime> objetos. Para agregar o quitar una fecha de una de estas listas, debe agregar o quitar un <xref:System.DateTime> objeto.  
  
### <a name="to-make-a-date-appear-in-bold-type"></a>Para que una fecha aparezca en negrita  
  
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
  
2.  Poner una sola fecha en negrita mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> método de la <xref:System.Windows.Forms.MonthCalendar> control.  
  
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
  
     Realizar un conjunto de fechas de negrita a la vez mediante la creación de una matriz de <xref:System.DateTime> objetos y asígnela a una de las propiedades.  
  
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
  
### <a name="to-make-a-date-appear-in-the-regular-font"></a>Para que una fecha aparezca en el formato de fuente normal  
  
1.  Que una fecha única en negrita aparezca con la fuente normal mediante una llamada a la <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A>, o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> método.  
  
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
 [MonthCalendar (control)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)  
 [Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
