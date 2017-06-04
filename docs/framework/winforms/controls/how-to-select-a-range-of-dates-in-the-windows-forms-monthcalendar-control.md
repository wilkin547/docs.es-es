---
title: "C&#243;mo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms | Microsoft Docs"
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
  - "calendarios, seleccionar intervalo de fechas"
  - "fechas, seleccionar intervalo de fechas en los controles de calendario"
  - "ejemplos [Windows Forms], controles de calendario"
  - "MonthCalendar (control) [Windows Forms], seleccionar intervalo de fechas"
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms
Una característica importante del control <xref:System.Windows.Forms.MonthCalendar> de formularios Windows Forms es que el usuario puede seleccionar un intervalo de fechas.  Esta característica es una mejora de la selección de fechas del control <xref:System.Windows.Forms.DateTimePicker>, que sólo permite al usuario seleccionar un único valor de fecha u hora.  Puede establecer un intervalo de fechas u obtener un intervalo de selección establecido por el usuario mediante las propiedades del control <xref:System.Windows.Forms.MonthCalendar>.  El ejemplo de código siguiente muestra cómo establecer un intervalo de selección.  
  
### Para seleccionar un intervalo de fechas  
  
1.  Cree objetos <xref:System.DateTime> que representan la primera y la última fecha del intervalo.  
  
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
  
2.  Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>.  
  
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
  
     O bien  
  
     Establezca las propiedades <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> y <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A>.  
  
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
  
## Vea también  
 [MonthCalendar \(Control\)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Cómo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)