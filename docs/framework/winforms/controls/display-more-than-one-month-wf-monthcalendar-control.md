---
title: "C&#243;mo: Mostrar m&#225;s de un mes en el control MonthCalendar de formularios Windows Forms | Microsoft Docs"
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
  - "calendarios, aplicar formato a la presentación"
  - "calendarios, varios meses"
  - "ejemplos [Windows Forms], controles de calendario"
  - "MonthCalendar (control) [Windows Forms], aplicar formato a la presentación"
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Mostrar m&#225;s de un mes en el control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> de formularios Windows Forms puede mostrar 12 meses al mismo tiempo como máximo.  De forma predeterminada, el control muestra un solo mes; sin embargo, se puede especificar el número de meses que se han de mostrar y cómo se disponen dentro del control.  Cuando cambian las dimensiones del calendario, el tamaño del control también cambia, por lo que hay que asegurarse de que existe espacio suficiente en el formulario para las nuevas dimensiones.  
  
### Para mostrar varios meses  
  
-   Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> en el número de meses que se deben mostrar horizontal y verticalmente.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## Vea también  
 [MonthCalendar \(Control\)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Cómo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Cómo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)