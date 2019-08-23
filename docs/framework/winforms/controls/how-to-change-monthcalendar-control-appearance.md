---
title: Procedimiento para cambiar la apariencia del control MonthCalendar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 5582624d881b2d8039bcd5e8ac45e548c7b38f57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929046"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Procedimiento para cambiar la apariencia del control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> Windows Forms permite personalizar la apariencia del calendario de muchas maneras. Por ejemplo, puede establecer la combinación de colores y elegir mostrar u ocultar los números de semana y la fecha actual.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Para cambiar la combinación de colores del calendario mensual  
  
- Establezca propiedades como <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> y <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. La <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> propiedad también determina el color de fuente de los días de la semana. La <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> propiedad determina el color de las fechas que preceden y siguen al mes o meses que se muestran.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    > A partir de Windows Vista y según el tema, la configuración de algunas propiedades podría no cambiar la apariencia del calendario. Por ejemplo, si Windows está establecido para usar el tema de Aero, el <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>establecimiento <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>de las propiedades <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> ,, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>o no tiene ningún efecto. Esto se debe a que una versión actualizada del calendario se representa con una apariencia que se deriva en tiempo de ejecución del tema del sistema operativo actual. Si desea usar estas propiedades y habilitar la versión anterior del calendario, puede deshabilitar los estilos visuales para la aplicación. Deshabilitar los estilos visuales puede afectar a la apariencia y el comportamiento de otros controles de la aplicación. Para deshabilitar los estilos visuales en Visual Basic, abra el diseñador de proyectos y desactive la casilla **habilitar estilos visuales de XP** . Para deshabilitar los estilos C#visuales en, abra Program.CS y `Application.EnableVisualStyles();`comente. Para obtener más información sobre los estilos visuales, vea [habilitar estilos visuales](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Para mostrar la fecha actual en la parte inferior del control  
  
- Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> en `true`. En el ejemplo siguiente se alterna entre mostrar y omitir la fecha de hoy cuando se hace doble clic en el formulario.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     (Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Para mostrar los números de semana  
  
- Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`. Puede establecer esta propiedad en el código o en el ventana Propiedades.  
  
     Los números de semana aparecen en una columna independiente a la izquierda del primer día de la semana.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>Vea también

- [MonthCalendar (control)](monthcalendar-control-windows-forms.md)
- [Cómo: Seleccionar un intervalo de fechas en el control MonthCalendar Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Procedimientos: Mostrar días específicos en negrita con el control MonthCalendar Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Procedimientos: Mostrar más de un mes en el control MonthCalendar Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
