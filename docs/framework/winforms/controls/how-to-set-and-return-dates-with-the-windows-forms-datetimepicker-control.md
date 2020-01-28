---
title: Establecer y devolver fechas con el control DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- dates [Windows Forms], setting in DateTimePicker
- DateTimePicker control [Windows Forms], setting and returning dates
- examples [Windows Forms], DateTimePicker control
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
ms.openlocfilehash: 1e0aa58e98748ccde9411f0f4871adbae3a5f14d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747102"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a>Cómo: Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms
La fecha u hora seleccionadas actualmente en el control <xref:System.Windows.Forms.DateTimePicker> de Windows Forms viene determinada por la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A>. Puede establecer la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> antes de que el control se muestre (por ejemplo, en tiempo de diseño o en el evento <xref:System.Windows.Forms.Form.Load> del formulario) para determinar qué fecha se seleccionará inicialmente en el control. De forma de predeterminada, el <xref:System.Windows.Forms.DateTimePicker.Value%2A> del control se establece en la fecha actual. Si cambia el <xref:System.Windows.Forms.DateTimePicker.Value%2A> del control en el código, el control se actualiza automáticamente en el formulario para reflejar la nueva configuración.  
  
 La propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> devuelve una estructura <xref:System.DateTime> como su valor. Hay varias propiedades de la estructura <xref:System.DateTime> que devuelven información específica acerca de la fecha mostrada. Estas propiedades solo pueden usarse para devolver un valor; no las use para establecer un valor.  
  
- Para los valores de fecha, las propiedades <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> y <xref:System.DateTime.Year%2A> devuelven valores enteros para las unidades de tiempo de la fecha seleccionada. La propiedad <xref:System.DateTime.DayOfWeek%2A> devuelve un valor que indica el día de la semana seleccionado (los valores posibles se incluyen en la enumeración <xref:System.DayOfWeek>).  
  
- Para los valores de tiempo, las propiedades <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> y <xref:System.DateTime.Millisecond%2A> devuelven valores enteros para las unidades de tiempo. Para configurar el control para mostrar horas, vea [Cómo: Mostrar la hora con el control DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a>Para establecer el valor de fecha y hora del control  
  
- Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> en un valor de fecha u hora.  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a>Para devolver el valor de fecha y hora  
  
- Llame a la propiedad <xref:System.Windows.Forms.DateTimePicker.Text%2A> para devolver el valor completo con el formato que tiene en el control, o llame al método correspondiente de la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> para devolver una parte del valor. Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> para convertir la información en una cadena que puede mostrarse al usuario.  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## <a name="see-also"></a>Vea también

- [Control DateTimePicker](datetimepicker-control-windows-forms.md)
- [Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
