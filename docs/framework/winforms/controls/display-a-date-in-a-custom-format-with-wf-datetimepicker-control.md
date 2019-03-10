---
title: Filtrar Mostrar una fecha en un formato personalizado con el Control DateTimePicker de formularios de Windows
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
ms.openlocfilehash: c201455acaa9bde521afd623424d0cfc403b1bff
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705884"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>Filtrar Mostrar una fecha en un formato personalizado con el Control DateTimePicker de formularios de Windows
Los formularios de Windows <xref:System.Windows.Forms.DateTimePicker> control ofrece flexibilidad para dar formato a la presentación de fechas y horas en el control. El <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad le permite seleccionar de los formatos predefinidos enumerados en el <xref:System.Windows.Forms.DateTimePickerFormat>. Si ninguno de estos es adecuado para sus fines, puede crear su propio estilo de formato de caracteres de formato enumerados en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.  
  
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
  
1.  Utilice comillas simples para incluir cualquier carácter que no sea un carácter de formato como "M" o un delimitador como ":". Por ejemplo, la siguiente cadena de formato muestra la fecha actual con el formato "hoy en día es: 05:30:31 Friday March 02, 2012" en la referencia cultural inglés (Estados Unidos).  
  
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
  
     Según la configuración de la referencia cultural, se puede cambiar cualquier carácter que no se incluyen entre comillas simples. Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "hoy en día es: 05:30:31 Friday March 02, 2012" en la referencia cultural inglés (Estados Unidos). Tenga en cuenta que los primeros dos puntos se incluye entre comillas simples, porque no está diseñado para ser un carácter delimitador cuando sea "hh". En otra referencia cultural, el formato puede aparecer como "hoy en día es: 05.30.31 el viernes marzo 02, 2012".  
  
## <a name="see-also"></a>Vea también
- [Control DateTimePicker](datetimepicker-control-windows-forms.md)
- [Cómo: Establecer y devolver fechas con el Control DateTimePicker de formularios de Windows](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
