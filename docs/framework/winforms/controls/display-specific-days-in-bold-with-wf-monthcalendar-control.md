---
title: "C&#243;mo: Mostrar d&#237;as espec&#237;ficos en negrita con el control MonthCalendar de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "calendarios, mostrar las fechas en negrita"
  - "ejemplos [Windows Forms], controles de calendario"
  - "GetDayBold (evento)"
  - "MonthCalendar (control) [Windows Forms], fechas en negrita"
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Mostrar d&#237;as espec&#237;ficos en negrita con el control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> de formularios Windows Forms puede mostrar días en negrita, ya sea porque correspondan a fechas señaladas o con una periodicidad.  Puede hacer esto para destacar fechas especiales, tales como vacaciones y fines de semana.  
  
 Hay tres propiedades que controlan esta característica.  La propiedad <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> contiene fechas únicas.  La propiedad <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> contiene fechas que aparecen en negrita todos los años.  La propiedad <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> contiene fechas que aparecen en negrita todos los meses.  Cada una de estas propiedades contiene una matriz de objetos <xref:System.DateTime>.  Para agregar o quitar una fecha de una de estas listas, deberá agregar o quitar un objeto <xref:System.DateTime>.  
  
### Para que una fecha aparezca en negrita  
  
1.  Cree los objetos <xref:System.DateTime>.  
  
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
  
2.  Para poner en negrita una única fecha, llame a los métodos <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> o <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> del control <xref:System.Windows.Forms.MonthCalendar>.  
  
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
  
     O bien  
  
     Para poner en negrita un conjunto de fechas a la vez, cree una matriz de objetos <xref:System.DateTime> y asígnela a una de las propiedades.  
  
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
  
### Para que una fecha aparezca con la fuente normal  
  
1.  Para que una única fecha en negrita aparezca con la fuente normal, llame a los métodos <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> o <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A>.  
  
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
  
     O bien  
  
     Para quitar todas las fechas en negrita de una de las tres listas, llame a los métodos <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> o <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  Para actualizar la apariencia de la fuente, llame al método <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A>.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## Vea también  
 [MonthCalendar \(Control\)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Cómo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Cómo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)