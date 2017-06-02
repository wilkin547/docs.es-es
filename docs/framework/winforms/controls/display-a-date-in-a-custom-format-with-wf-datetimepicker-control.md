---
title: "C&#243;mo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms | Microsoft Docs"
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
  - "fechas, mostrar en el control DateTimePicker"
  - "DateTimePicker (control) [Windows Forms], estilos de presentación"
  - "ejemplos [Windows Forms], DateTimePicker (control)"
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms
El control <xref:System.Windows.Forms.DateTimePicker> de formularios Windows Forms proporciona flexibilidad para dar formato a la presentación de fechas y horas en el control.  La propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> le permite seleccionar entre formatos predefinidos, que se enumeran en <xref:System.Windows.Forms.DateTimePickerFormat>.  Si ninguno de ellos es adecuado para lograr el objetivo deseado, puede crear estilos de formato propios utilizando los caracteres de formato que se enumeran en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### Para mostrar un formato personalizado  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> como una cadena de formato.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### Para agregar texto al valor con formato  
  
1.  Utilice las comillas sencillas para agregar cualquier carácter que no sea un carácter de formato, como "M" o un delimitador como ":".  Por ejemplo, la siguiente cadena de formato muestra la fecha actual con el formato "Today is: 05:30:31 Friday March 02, 2012" en la referencia cultural Inglés \(Estados Unidos\).  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     Dependiendo del valor de la referencia cultural, se pueden cambiar los caracteres que no estén rodeados de comillas simples.  Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "Today is: 05:30:31 Friday March 02, 2012" en la referencia cultural Inglés \(Estados Unidos\).  Observe que los primeros dos puntos están encerrados entre comillas simples, dado que no pretenden ser un carácter delimitador como en "hh:mm:ss".  En otra referencia cultural, el formato puede aparecer como "Today is: 05.30.31 Friday March 02, 2012".  
  
## Vea también  
 [DateTimePicker \(Control\)](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)   
 [Cómo: Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)