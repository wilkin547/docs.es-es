---
title: Cambiar la apariencia del control MonthCalendar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: ded9059ede4ad03f637c0e697b880c41a9a8ba32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746656"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a><span data-ttu-id="03442-102">Cómo: Cambiar la apariencia del control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03442-102">How to: Change the Windows Forms MonthCalendar Control's Appearance</span></span>
<span data-ttu-id="03442-103">El control Windows Forms <xref:System.Windows.Forms.MonthCalendar> permite personalizar la apariencia del calendario de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="03442-103">The Windows Forms <xref:System.Windows.Forms.MonthCalendar> control allows you to customize the calendar's appearance in many ways.</span></span> <span data-ttu-id="03442-104">Por ejemplo, puede establecer la combinación de colores y elegir mostrar u ocultar los números de semana y la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="03442-104">For example, you can set the color scheme and choose to display or hide week numbers and the current date.</span></span>  
  
### <a name="to-change-the-month-calendars-color-scheme"></a><span data-ttu-id="03442-105">Para cambiar la combinación de colores del calendario mensual</span><span class="sxs-lookup"><span data-stu-id="03442-105">To change the month calendar's color scheme</span></span>  
  
- <span data-ttu-id="03442-106">Establezca propiedades como <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> y <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span><span class="sxs-lookup"><span data-stu-id="03442-106">Set properties such as <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> and <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>.</span></span> <span data-ttu-id="03442-107">La propiedad <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> también determina el color de fuente de los días de la semana.</span><span class="sxs-lookup"><span data-stu-id="03442-107">The <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> property also determines the font color for the days of the week.</span></span> <span data-ttu-id="03442-108">La propiedad <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> determina el color de las fechas que preceden y siguen al mes o meses que se muestran.</span><span class="sxs-lookup"><span data-stu-id="03442-108">The <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> property determines the color of the dates that precede and follow the displayed month or months.</span></span>  
  
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
    > <span data-ttu-id="03442-109">A partir de Windows Vista y según el tema, la configuración de algunas propiedades podría no cambiar la apariencia del calendario.</span><span class="sxs-lookup"><span data-stu-id="03442-109">Starting with Windows Vista and depending on the theme, setting some properties might not change the appearance of the calendar.</span></span> <span data-ttu-id="03442-110">Por ejemplo, si Windows está establecido para usar el tema de Aero, el establecimiento de las propiedades <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="03442-110">For example, if Windows is set to use the Aero theme, setting the <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, or <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> properties has no effect.</span></span> <span data-ttu-id="03442-111">Esto se debe a que una versión actualizada del calendario se representa con una apariencia que se deriva en tiempo de ejecución del tema del sistema operativo actual.</span><span class="sxs-lookup"><span data-stu-id="03442-111">This is because an updated version of the calendar is rendered with an appearance that is derived at run time from the current operating system theme.</span></span> <span data-ttu-id="03442-112">Si desea usar estas propiedades y habilitar la versión anterior del calendario, puede deshabilitar los estilos visuales para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03442-112">If you want to use these properties and enable the earlier version of the calendar, you can disable visual styles for your application.</span></span> <span data-ttu-id="03442-113">Deshabilitar los estilos visuales puede afectar a la apariencia y el comportamiento de otros controles de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03442-113">Disabling visual styles might affect the appearance and behavior of other controls in your application.</span></span> <span data-ttu-id="03442-114">Para deshabilitar los estilos visuales en Visual Basic, abra el diseñador de proyectos y desactive la casilla **habilitar estilos visuales de XP** .</span><span class="sxs-lookup"><span data-stu-id="03442-114">To disable visual styles in Visual Basic, open the Project Designer and uncheck the **Enable XP visual styles** check box.</span></span> <span data-ttu-id="03442-115">Para deshabilitar los estilos C#visuales en, abra Program.CS y comente `Application.EnableVisualStyles();`.</span><span class="sxs-lookup"><span data-stu-id="03442-115">To disable visual styles in C#, open Program.cs and comment out `Application.EnableVisualStyles();`.</span></span> <span data-ttu-id="03442-116">Para obtener más información sobre los estilos visuales, vea [habilitar estilos visuales](/windows/desktop/controls/cookbook-overview).</span><span class="sxs-lookup"><span data-stu-id="03442-116">For more information about visual styles, see [Enabling Visual Styles](/windows/desktop/controls/cookbook-overview).</span></span>  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a><span data-ttu-id="03442-117">Para mostrar la fecha actual en la parte inferior del control</span><span class="sxs-lookup"><span data-stu-id="03442-117">To display the current date at the bottom of the control</span></span>  
  
- <span data-ttu-id="03442-118">Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="03442-118">Set the <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> property to `true`.</span></span> <span data-ttu-id="03442-119">En el ejemplo siguiente se alterna entre mostrar y omitir la fecha de hoy cuando se hace doble clic en el formulario.</span><span class="sxs-lookup"><span data-stu-id="03442-119">The example below toggles between displaying and omitting today's date when the form is double-clicked.</span></span>  
  
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
  
     <span data-ttu-id="03442-120">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="03442-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a><span data-ttu-id="03442-121">Para mostrar los números de semana</span><span class="sxs-lookup"><span data-stu-id="03442-121">To display week numbers</span></span>  
  
- <span data-ttu-id="03442-122">Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="03442-122">Set the <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> property to `true`.</span></span> <span data-ttu-id="03442-123">Puede establecer esta propiedad en el código o en el ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="03442-123">You can set this property either in code or in the Properties window.</span></span>  
  
     <span data-ttu-id="03442-124">Los números de semana aparecen en una columna independiente a la izquierda del primer día de la semana.</span><span class="sxs-lookup"><span data-stu-id="03442-124">Week numbers appear in a separate column to the left of the first day of the week.</span></span>  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="03442-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="03442-125">See also</span></span>

- [<span data-ttu-id="03442-126">MonthCalendar (control)</span><span class="sxs-lookup"><span data-stu-id="03442-126">MonthCalendar Control</span></span>](monthcalendar-control-windows-forms.md)
- [<span data-ttu-id="03442-127">Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03442-127">How to: Select a Range of Dates in the Windows Forms MonthCalendar Control</span></span>](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [<span data-ttu-id="03442-128">Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03442-128">How to: Display Specific Days in Bold with the Windows Forms MonthCalendar Control</span></span>](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [<span data-ttu-id="03442-129">Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03442-129">How to: Display More than One Month in the Windows Forms MonthCalendar Control</span></span>](display-more-than-one-month-wf-monthcalendar-control.md)
