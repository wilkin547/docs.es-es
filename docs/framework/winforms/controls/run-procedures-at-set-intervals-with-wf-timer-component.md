---
title: Ejecutar procedimientos en Intervalos establecidos con componente de temporizador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: 52d68a8136551384f67ff6232799600af09f8b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182062"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="2d4ed-102">Cómo: Ejecutar procedimientos a intervalos establecidos con el componente Timer de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d4ed-102">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>
<span data-ttu-id="2d4ed-103">A veces, conviene crear un procedimiento que se ejecuta a intervalos de tiempo específicos hasta que finaliza un bucle o que se ejecuta cuando ha transcurrido un intervalo de tiempo establecido.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-103">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="2d4ed-104">El componente <xref:System.Windows.Forms.Timer> hace posible este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-104">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="2d4ed-105">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="2d4ed-106">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2d4ed-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d4ed-107">Existen algunas limitaciones cuando se usa el componente <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-107">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="2d4ed-108">Para obtener más información, vea [Limitaciones de la propiedad Intervalo del componente de](limitations-of-the-timer-component-interval-property.md)temporizador de Windows Forms .</span><span class="sxs-lookup"><span data-stu-id="2d4ed-108">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="2d4ed-109">Para ejecutar un procedimiento a intervalos establecidos con el componente Timer</span><span class="sxs-lookup"><span data-stu-id="2d4ed-109">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="2d4ed-110">Agregue un <xref:System.Windows.Forms.Timer> al formulario.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-110">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="2d4ed-111">Consulte la siguiente sección Ejemplo para ver cómo hacerlo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-111">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="2d4ed-112">Visual Studio también tiene compatibilidad para agregar componentes a un formulario.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-112">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="2d4ed-113">Consulte también [Cómo: Agregar controles sin una interfaz](how-to-add-controls-without-a-user-interface-to-windows-forms.md)de usuario a formularios Windows Forms .</span><span class="sxs-lookup"><span data-stu-id="2d4ed-113">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="2d4ed-114">Establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> (en milisegundos) para el temporizador.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-114">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="2d4ed-115">Esta propiedad determina cuánto tiempo transcurrirá antes de que el procedimiento se ejecute de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-115">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2d4ed-116">Cuanta mayor sea frecuencia con la que se produce un evento del temporizador, más tiempo del procesador se usará para responder al evento.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-116">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="2d4ed-117">Esto puede reducir el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-117">This can slow down overall performance.</span></span> <span data-ttu-id="2d4ed-118">No establezca un intervalo menor del necesario.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-118">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="2d4ed-119">Escriba el código adecuado el controlador de eventos <xref:System.Windows.Forms.Timer.Tick>.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-119">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="2d4ed-120">El código que escriba en este evento se ejecutará en el intervalo especificado en la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-120">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="2d4ed-121">Establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true` para iniciar el temporizador.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-121">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="2d4ed-122">El evento <xref:System.Windows.Forms.Timer.Tick> empezará a tener lugar y el procedimiento se ejecutará según el intervalo establecido.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-122">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="2d4ed-123">En el momento adecuado, establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `false` para detener el procedimiento y que no vuelva a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-123">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="2d4ed-124">Establecer el `0` intervalo en no hace que el temporizador se detenga.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-124">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d4ed-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d4ed-125">Example</span></span>  
 <span data-ttu-id="2d4ed-126">Este primer ejemplo de código realiza el seguimiento de la hora del día en incrementos de un segundo.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-126">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="2d4ed-127">Usa un componente <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> y <xref:System.Windows.Forms.Timer> en un formulario.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-127">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="2d4ed-128">La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> se establece en 1000 (igual a un segundo).</span><span class="sxs-lookup"><span data-stu-id="2d4ed-128">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="2d4ed-129">En el evento <xref:System.Windows.Forms.Timer.Tick>, el título de la etiqueta se establece en la hora actual.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-129">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="2d4ed-130">Al hacer clic en el botón, la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> se establece en `false`, lo que detiene el temporizador y deja de actualizar el título de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-130">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="2d4ed-131">En el ejemplo de código siguiente se <xref:System.Windows.Forms.Button> requiere `Button1`que <xref:System.Windows.Forms.Timer> tenga `Timer1`un <xref:System.Windows.Forms.Label> formulario `Label1`con un control denominado , un control denominado y un control denominado .</span><span class="sxs-lookup"><span data-stu-id="2d4ed-131">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="2d4ed-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d4ed-132">Example</span></span>  
 <span data-ttu-id="2d4ed-133">En este segundo ejemplo de código se ejecuta un procedimiento cada 600 milisegundos hasta que termina un bucle.</span><span class="sxs-lookup"><span data-stu-id="2d4ed-133">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="2d4ed-134">En el ejemplo de código siguiente se <xref:System.Windows.Forms.Button> requiere `Button1`que <xref:System.Windows.Forms.Timer> tenga `Timer1`un <xref:System.Windows.Forms.Label> formulario `Label1`con un control denominado , un control denominado y un control denominado .</span><span class="sxs-lookup"><span data-stu-id="2d4ed-134">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)
{  
   if (counter >= 10)
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d4ed-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d4ed-135">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="2d4ed-136">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="2d4ed-136">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="2d4ed-137">Información general sobre el componente Timer</span><span class="sxs-lookup"><span data-stu-id="2d4ed-137">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
