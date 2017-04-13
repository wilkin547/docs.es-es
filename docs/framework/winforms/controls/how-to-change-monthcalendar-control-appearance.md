---
title: "C&#243;mo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], controles de calendario"
  - "MonthBackColor (propiedad)"
  - "MonthCalendar (control) [Windows Forms], aplicar formato a la presentación"
  - "TitleBackColor (propiedad)"
  - "TitleForeColor (propiedad)"
  - "TrailingForeColor (propiedad)"
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms
El control <xref:System.Windows.Forms.MonthCalendar> de formularios Windows Forms permite personalizar la apariencia del calendario de muchas maneras.  Entre estas posibilidades se incluye la combinación de colores, y la elección entre mostrar u ocultar los números de semana y la fecha actual.  
  
### Para cambiar la combinación de colores del calendario del mes  
  
-   Establezca propiedades como <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> y <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.  La propiedad <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> determina también el color de fuente para los días de la semana.  La propiedad <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> determina el color de las fechas que preceden y siguen al mes o los meses que se muestran.  
  
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
    >  A partir de Windows vista y dependiendo del tema, la configuración de algunas propiedades podría no cambiar la apariencia del calendario.  Por ejemplo, si Windows está configurado para usar el tema Aero, establecer las propiedades <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> no tiene ningún efecto.  Esto se debe a que se representa una versión actualizada del calendario con una apariencia derivada en tiempo de ejecución del tema actual del sistema operativo.  Si desea usar estas propiedades y habilitar la versión anterior del calendario, puede deshabilitar los estilos visuales para la aplicación.  Deshabilitar los estilos visuales puede afectar a la apariencia y el comportamiento de otros controles de la aplicación.  Para deshabilitar los estilos visuales en Visual Basic, abra el Diseñador de proyectos y desactive la casilla **Habilitar estilos visuales de XP**.  Para deshabilitar los estilos visuales en C\#, abra Program.cs y marque como comentario `Application.EnableVisualStyles();`.  Para obtener más información sobre los estilos visuales, vea [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/es-es/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### Para mostrar la fecha actual en la parte inferior del control  
  
-   Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> en `true`.  El ejemplo siguiente alterna entre mostrar y omitir la fecha actual cuando se hace doble clic en el formulario.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### Para mostrar los números de semana  
  
-   Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`.  Esta propiedad puede establecerse en el código o en la ventana Propiedades.  
  
     Los números de semana aparecen en una columna independiente situada a la izquierda del primer día de la semana.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## Vea también  
 [MonthCalendar \(Control\)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [Cómo: Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [Cómo: Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [Cómo: Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)