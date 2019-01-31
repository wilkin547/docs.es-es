---
title: Filtrar Cambiar la apariencia de Windows Forms MonthCalendar del Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: b7f321c1557bc7ea19213f2fc67767fe56328cf4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258933"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="40bf9-102">Filtrar Cambiar la apariencia de Windows Forms MonthCalendar del Control</span><span class="sxs-lookup"><span data-stu-id="40bf9-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="40bf9-103">Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control le permite personalizar la apariencia del calendario de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="40bf9-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="40bf9-104">Por ejemplo, puede establecer la combinación de colores y elegir mostrar u ocultar los números de semana y la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="40bf9-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="40bf9-105">Para cambiar la combinación de colores del calendario mensual</span><span class="sxs-lookup"><span data-stu-id="40bf9-105">To change the month calendar's color scheme</span></span>  
  
-   <span data-ttu-id="40bf9-106">Establecer propiedades tales como <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> y <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="40bf9-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="40bf9-107">El <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> propiedad también determina el color de fuente para los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="40bf9-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="40bf9-108">El <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> propiedad determina el color de las fechas que preceden y siguen el mes que se muestra o meses.</span><span class="sxs-lookup"><span data-stu-id="40bf9-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    >  <span data-ttu-id="40bf9-109">A partir de Windows Vista y según el tema, establecer algunas propiedades podría no cambiar la apariencia del calendario.</span><span class="sxs-lookup"><span data-stu-id="40bf9-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="40bf9-110">Por ejemplo, si Windows está configurado para usar el tema de Aero, al establecer el <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> propiedades no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="40bf9-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="40bf9-111">Esto es debido a una versión actualizada del calendario se representa con un aspecto que se deriva en tiempo de ejecución del tema actual del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="40bf9-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="40bf9-112">Si desea usar estas propiedades y habilitar la versión anterior del calendario, puede deshabilitar estilos visuales para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="40bf9-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="40bf9-113">Deshabilitar estilos visuales podría afectar a la apariencia y comportamiento de otros controles en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="40bf9-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="40bf9-114">Para deshabilitar estilos visuales en Visual Basic, abra el Diseñador de proyectos y desactive el **estilos visuales de XP habilitar** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="40bf9-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="40bf9-115">Para deshabilitar estilos visuales en C#, abra Program.cs y marque como comentario `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="40bf9-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="40bf9-116">Para obtener más información sobre los estilos visuales, vea [Cómo: Habilitar estilos visuales de Windows XP](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span><span class="sxs-lookup"><span data-stu-id="40bf9-116">For more information about visual styles, see [How to: Enable Windows XP Visual Styles](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="40bf9-117">Para mostrar la fecha actual en la parte inferior del control</span><span class="sxs-lookup"><span data-stu-id="40bf9-117">To display the current date at the bottom of the control</span></span>  
  
-   <span data-ttu-id="40bf9-118">Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="40bf9-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="40bf9-119">En el ejemplo siguiente se alterna entre mostrar y omitir la fecha de hoy cuando se hace doble clic en el formulario.</span><span class="sxs-lookup"><span data-stu-id="40bf9-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="40bf9-120">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="40bf9-120">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="40bf9-121">Para mostrar los números de semana</span><span class="sxs-lookup"><span data-stu-id="40bf9-121">To display week numbers</span></span>  
  
-   <span data-ttu-id="40bf9-122">Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="40bf9-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="40bf9-123">Puede establecer esta propiedad en el código o en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="40bf9-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="40bf9-124">Números de semana aparecen en una columna independiente a la izquierda del primer día de la semana.</span><span class="sxs-lookup"><span data-stu-id="40bf9-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="40bf9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="40bf9-125">See also</span></span>
- [<span data-ttu-id="40bf9-126">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="40bf9-126">MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="40bf9-127">Cómo: Seleccione un intervalo de fechas en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="40bf9-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="40bf9-128">Cómo: Mostrar días específicos en negrita con el Windows Forms Control MonthCalendar de formularios</span><span class="sxs-lookup"><span data-stu-id="40bf9-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="40bf9-129">Cómo: Mostrar más de un mes en el Control MonthCalendar de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="40bf9-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
