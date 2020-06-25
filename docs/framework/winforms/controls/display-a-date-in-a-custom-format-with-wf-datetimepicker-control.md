---
title: Mostrar una fecha en un formato personalizado con el control DateTimePicker
description: Aprenda a usar el control Windows Forms DateTimePicker para dar formato a la presentación de fechas y horas en el control.
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
ms.openlocfilehash: 773070136e4fd43ab1bf510ebcaf6b0aa6a7ba8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325833"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Procedimiento para mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms
El <xref:System.Windows.Forms.DateTimePicker> control Windows Forms proporciona flexibilidad para dar formato a la presentación de fechas y horas en el control. La <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad permite seleccionar entre formatos predefinidos, que se enumeran en <xref:System.Windows.Forms.DateTimePickerFormat> . Si ninguno de ellos es adecuado para sus propósitos, puede crear su propio estilo de formato con los caracteres de formato enumerados en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> .  
  
### <a name="to-display-a-custom-format"></a>Para mostrar un formato personalizado  
  
1. Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.  
  
2. Establezca la <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad en una cadena de formato.  
  
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
  
1. Use comillas simples para encerrar cualquier carácter que no sea un carácter de formato como "M" o un delimitador como ":". Por ejemplo, la cadena de formato siguiente muestra la fecha actual con el formato "hoy es: 05:30:31 Friday marzo 02, 2012" en la referencia cultural inglés (Estados Unidos).  
  
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
  
     En función de la configuración de la referencia cultural, se pueden cambiar los caracteres no incluidos entre comillas simples. Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "hoy es: 05:30:31 Friday marzo 02, 2012" en la referencia cultural inglés (Estados Unidos). Tenga en cuenta que los primeros dos puntos están entre comillas simples, ya que no pretende ser un carácter delimitador, como en "HH: mm: SS". En otra referencia cultural, el formato puede aparecer como "hoy es: 05.30.31 Friday marzo 02, 2012".  
  
## <a name="see-also"></a>Vea también

- [Control DateTimePicker](datetimepicker-control-windows-forms.md)
- [Procedimiento para establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
