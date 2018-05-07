---
title: 'Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 2f563b5de9b80dab2af00290e8a6b3b309410a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.DateTimePicker> control ofrece flexibilidad para dar formato a la presentación de fechas y horas en el control. El <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad le permite seleccionar entre los formatos predefinidos, aparecen en la <xref:System.Windows.Forms.DateTimePickerFormat>. Si ninguno de estos es adecuado para sus necesidades, puede crear su propio estilo de formato de caracteres de formato que se indican en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
### <a name="to-display-a-custom-format"></a>Para mostrar un formato personalizado  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.  
  
2.  Establecer el <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad a una cadena de formato.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>Para agregar texto al valor con formato  
  
1.  Utilice comillas simples para delimitar cualquier carácter que no es un carácter de formato como "M" o un delimitador como ":". Por ejemplo, la siguiente cadena de formato muestra la fecha actual con el formato "en la actualidad es: 05:30:31 el viernes 02 de marzo de 2012" en el inglés (Estados Unidos) de la referencia cultural.  
  
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
  
     Según la configuración de la referencia cultural, se puede cambiar cualquier carácter no encerrado entre comillas simples. Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "en la actualidad es: 05:30:31 el viernes 02 de marzo de 2012" en el inglés (Estados Unidos) de la referencia cultural. Tenga en cuenta que los primeros dos puntos están encerrados entre comillas simples, porque no está pensado para ser un carácter delimitador como en "hh". En otra referencia cultural, el formato puede aparecer como "en la actualidad es: 05.30.31 el viernes 02 de marzo de 2012".  
  
## <a name="see-also"></a>Vea también  
 [Control DateTimePicker](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
