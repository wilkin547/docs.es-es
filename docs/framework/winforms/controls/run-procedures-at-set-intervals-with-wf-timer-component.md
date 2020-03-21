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
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a>Cómo: Ejecutar procedimientos a intervalos establecidos con el componente Timer de formularios Windows Forms
A veces, conviene crear un procedimiento que se ejecuta a intervalos de tiempo específicos hasta que finaliza un bucle o que se ejecuta cuando ha transcurrido un intervalo de tiempo establecido. El componente <xref:System.Windows.Forms.Timer> hace posible este procedimiento.  
  
 Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
> [!NOTE]
> Existen algunas limitaciones cuando se usa el componente <xref:System.Windows.Forms.Timer>. Para obtener más información, vea [Limitaciones de la propiedad Intervalo del componente de](limitations-of-the-timer-component-interval-property.md)temporizador de Windows Forms .  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a>Para ejecutar un procedimiento a intervalos establecidos con el componente Timer  
  
1. Agregue un <xref:System.Windows.Forms.Timer> al formulario. Consulte la siguiente sección Ejemplo para ver cómo hacerlo mediante programación. Visual Studio también tiene compatibilidad para agregar componentes a un formulario. Consulte también [Cómo: Agregar controles sin una interfaz](how-to-add-controls-without-a-user-interface-to-windows-forms.md)de usuario a formularios Windows Forms .  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> (en milisegundos) para el temporizador. Esta propiedad determina cuánto tiempo transcurrirá antes de que el procedimiento se ejecute de nuevo.  
  
    > [!NOTE]
    > Cuanta mayor sea frecuencia con la que se produce un evento del temporizador, más tiempo del procesador se usará para responder al evento. Esto puede reducir el rendimiento general. No establezca un intervalo menor del necesario.  
  
3. Escriba el código adecuado el controlador de eventos <xref:System.Windows.Forms.Timer.Tick>. El código que escriba en este evento se ejecutará en el intervalo especificado en la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
4. Establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `true` para iniciar el temporizador. El evento <xref:System.Windows.Forms.Timer.Tick> empezará a tener lugar y el procedimiento se ejecutará según el intervalo establecido.  
  
5. En el momento adecuado, establezca la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> en `false` para detener el procedimiento y que no vuelva a ejecutarse. Establecer el `0` intervalo en no hace que el temporizador se detenga.  
  
## <a name="example"></a>Ejemplo  
 Este primer ejemplo de código realiza el seguimiento de la hora del día en incrementos de un segundo. Usa un componente <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Label> y <xref:System.Windows.Forms.Timer> en un formulario. La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> se establece en 1000 (igual a un segundo). En el evento <xref:System.Windows.Forms.Timer.Tick>, el título de la etiqueta se establece en la hora actual. Al hacer clic en el botón, la propiedad <xref:System.Windows.Forms.Timer.Enabled%2A> se establece en `false`, lo que detiene el temporizador y deja de actualizar el título de la etiqueta. En el ejemplo de código siguiente se <xref:System.Windows.Forms.Button> requiere `Button1`que <xref:System.Windows.Forms.Timer> tenga `Timer1`un <xref:System.Windows.Forms.Label> formulario `Label1`con un control denominado , un control denominado y un control denominado .  
  
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
  
## <a name="example"></a>Ejemplo  
 En este segundo ejemplo de código se ejecuta un procedimiento cada 600 milisegundos hasta que termina un bucle. En el ejemplo de código siguiente se <xref:System.Windows.Forms.Button> requiere `Button1`que <xref:System.Windows.Forms.Timer> tenga `Timer1`un <xref:System.Windows.Forms.Label> formulario `Label1`con un control denominado , un control denominado y un control denominado .  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Timer>
- [Componente Timer](timer-component-windows-forms.md)
- [Información general sobre el componente Timer](timer-component-overview-windows-forms.md)
