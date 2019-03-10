---
title: Filtrar Establecer y devolver fechas con el Control DateTimePicker de formularios de Windows
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
ms.openlocfilehash: 73c40a48a75955d1ba44decae6b50ca641a63f7b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703223"
---
# <a name="how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="888a1-102">Filtrar Establecer y devolver fechas con el Control DateTimePicker de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="888a1-102">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="888a1-103">La fecha u hora seleccionadas actualmente en el control <xref:System.Windows.Forms.DateTimePicker> de Windows Forms viene determinada por la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="888a1-103">The currently selected date or time in the Windows Forms <xref:System.Windows.Forms.DateTimePicker> control is determined by the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property.</span></span> <span data-ttu-id="888a1-104">Puede establecer la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> antes de que el control se muestre (por ejemplo, en tiempo de diseño o en el evento <xref:System.Windows.Forms.Form.Load> del formulario) para determinar qué fecha se seleccionará inicialmente en el control.</span><span class="sxs-lookup"><span data-stu-id="888a1-104">You can set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property before the control is displayed (for example, at design time or in the form's <xref:System.Windows.Forms.Form.Load> event) to determine which date will be initially selected in the control.</span></span> <span data-ttu-id="888a1-105">De forma de predeterminada, el <xref:System.Windows.Forms.DateTimePicker.Value%2A> del control se establece en la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="888a1-105">By default, the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> is set to the current date.</span></span> <span data-ttu-id="888a1-106">Si cambia el <xref:System.Windows.Forms.DateTimePicker.Value%2A> del control en el código, el control se actualiza automáticamente en el formulario para reflejar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="888a1-106">If you change the control's <xref:System.Windows.Forms.DateTimePicker.Value%2A> in code, the control is automatically updated on the form to reflect the new setting.</span></span>  
  
 <span data-ttu-id="888a1-107">La propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> devuelve una estructura <xref:System.DateTime> como su valor.</span><span class="sxs-lookup"><span data-stu-id="888a1-107">The <xref:System.Windows.Forms.DateTimePicker.Value%2A> property returns a <xref:System.DateTime> structure as its value.</span></span> <span data-ttu-id="888a1-108">Hay varias propiedades de la estructura <xref:System.DateTime> que devuelven información específica acerca de la fecha mostrada.</span><span class="sxs-lookup"><span data-stu-id="888a1-108">There are several properties of the <xref:System.DateTime> structure that return specific information about the displayed date.</span></span> <span data-ttu-id="888a1-109">Estas propiedades solo pueden usarse para devolver un valor; no las use para establecer un valor.</span><span class="sxs-lookup"><span data-stu-id="888a1-109">These properties can only be used to return a value; do not use them to set a value.</span></span>  
  
-   <span data-ttu-id="888a1-110">Para los valores de fecha, las propiedades <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> y <xref:System.DateTime.Year%2A> devuelven valores enteros para las unidades de tiempo de la fecha seleccionada.</span><span class="sxs-lookup"><span data-stu-id="888a1-110">For date values, the <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A>, and <xref:System.DateTime.Year%2A> properties return integer values for those time units of the selected date.</span></span> <span data-ttu-id="888a1-111">La propiedad <xref:System.DateTime.DayOfWeek%2A> devuelve un valor que indica el día de la semana seleccionado (los valores posibles se incluyen en la enumeración <xref:System.DayOfWeek>).</span><span class="sxs-lookup"><span data-stu-id="888a1-111">The <xref:System.DateTime.DayOfWeek%2A> property returns a value indicating the selected day of the week (possible values are listed in the <xref:System.DayOfWeek> enumeration).</span></span>  
  
-   <span data-ttu-id="888a1-112">Para los valores de tiempo, las propiedades <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> y <xref:System.DateTime.Millisecond%2A> devuelven valores enteros para las unidades de tiempo.</span><span class="sxs-lookup"><span data-stu-id="888a1-112">For time values, the <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A>, and <xref:System.DateTime.Millisecond%2A> properties return integer values for those time units.</span></span> <span data-ttu-id="888a1-113">Para configurar el control para mostrar las veces, consulte [Cómo: Mostrar la hora con el Control DateTimePicker](how-to-display-time-with-the-datetimepicker-control.md).</span><span class="sxs-lookup"><span data-stu-id="888a1-113">To configure the control to display times, see [How to: Display Time with the DateTimePicker Control](how-to-display-time-with-the-datetimepicker-control.md).</span></span>  
  
### <a name="to-set-the-date-and-time-value-of-the-control"></a><span data-ttu-id="888a1-114">Para establecer el valor de fecha y hora del control</span><span class="sxs-lookup"><span data-stu-id="888a1-114">To set the date and time value of the control</span></span>  
  
-   <span data-ttu-id="888a1-115">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> en un valor de fecha u hora.</span><span class="sxs-lookup"><span data-stu-id="888a1-115">Set the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to a date or time value.</span></span>  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### <a name="to-return-the-date-and-time-value"></a><span data-ttu-id="888a1-116">Para devolver el valor de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="888a1-116">To return the date and time value</span></span>  
  
-   <span data-ttu-id="888a1-117">Llame a la propiedad <xref:System.Windows.Forms.DateTimePicker.Text%2A> para devolver el valor completo con el formato que tiene en el control, o llame al método correspondiente de la propiedad <xref:System.Windows.Forms.DateTimePicker.Value%2A> para devolver una parte del valor.</span><span class="sxs-lookup"><span data-stu-id="888a1-117">Call the <xref:System.Windows.Forms.DateTimePicker.Text%2A> property to return the entire value as formatted in the control, or call the appropriate method of the <xref:System.Windows.Forms.DateTimePicker.Value%2A> property to return a part of the value.</span></span> <span data-ttu-id="888a1-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> para convertir la información en una cadena que puede mostrarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="888a1-118">Use <xref:System.Windows.Forms.DateTimePicker.ToString%2A> to convert the information into a string that can be displayed to the user.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="888a1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="888a1-119">See also</span></span>
- [<span data-ttu-id="888a1-120">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="888a1-120">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="888a1-121">Cómo: Mostrar una fecha en un formato personalizado con el Control DateTimePicker de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="888a1-121">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>](display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)
