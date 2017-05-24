---
title: "Tipos de valor devueltos asincrónicos (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: d974e93c3c50a61889a9ed37ad5f68f7a131a538
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="async-return-types-c"></a>Tipos de valor devueltos asincrónicos (C#)
Los métodos asincrónicos tienen tres tipos de valor devueltos posibles: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> y void. En Visual Basic, el tipo de valor devuelto void se escribe como un procedimiento [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md). Para más información sobre los métodos async, vea [Programación asincrónica con async y await 8C#)](../../../../csharp/programming-guide/concepts/async/index.md).  
  
 Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.  
  
> [!NOTE]
>  Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior.  
  
##  <a name="BKMK_TaskTReturnType"></a> Tipo de valor devuelto Task(T)  
 El tipo de valor devuelto <xref:System.Threading.Tasks.Task%601> se usa para un método asincrónico que contiene una instrucción [return](../../../../csharp/language-reference/keywords/return.md) (C#) en la que el operando tiene el tipo `TResult`.  
  
 En el ejemplo siguiente, el método asincrónico `TaskOfT_MethodAsync` contiene una instrucción return que devuelve un entero. Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task<int>`.  
  
```csharp  
// TASK<T> EXAMPLE  
async Task<int> TaskOfT_MethodAsync()  
{  
    // The body of the method is expected to contain an awaited asynchronous  
    // call.  
    // Task.FromResult is a placeholder for actual work that returns a string.  
    var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
    // The method then can process the result in some way.  
    int leisureHours;  
    if (today.First() == 'S')  
        leisureHours = 16;  
    else  
        leisureHours = 5;  
  
    // Because the return statement specifies an operand of type int, the  
    // method must have a return type of Task<int>.  
    return leisureHours;  
}  
```  
  
 Cuando se llama a `TaskOfT_MethodAsync` desde una expresión await, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que `TaskOfT_MethodAsync` devuelve. Para más información sobre las expresiones await, vea [await](../../../../csharp/language-reference/keywords/await.md).  
  
 El código siguiente llama y espera al método `TaskOfT_MethodAsync`. El resultado se asigna a la variable `result1`.  
  
```csharp  
// Call and await the Task<T>-returning async method in the same statement.  
int result1 = await TaskOfT_MethodAsync();  
```  
  
 Comprenderá mejor cómo sucede esto separando la llamada a `TaskOfT_MethodAsync` de la aplicación de `await`, como se muestra en el código siguiente. Una llamada al método `TaskOfT_MethodAsync` que no se espera inmediatamente devuelve `Task<int>`, como se podría esperar de la declaración del método. La tarea se asigna a la variable `integerTask` en el ejemplo. Como `integerTask` es una <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`. En este caso, TResult representa un tipo entero. Cuando `await` se aplica a `integerTask`, la expresión await se evalúa como el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `integerTask`. El valor se asigna a la variable `result2`.  
  
> [!WARNING]
>  La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo. Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor usando `await` en lugar de tener acceso directamente a la propiedad.  
  
```csharp  
// Call and await in separate statements.  
Task<int> integerTask = TaskOfT_MethodAsync();  
  
// You can do other work that does not rely on integerTask before awaiting.  
textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
int result2 = await integerTask;  
```  
  
 Las instrucciones mostradas en el siguiente código comprueban que los valores de la variable `result1`, la variable `result2` y la propiedad `Result` son los mismos. Recuerde que la propiedad `Result` es una propiedad bloqueo y no se debe tener acceso a ella antes de haber esperado a su tarea.  
  
```csharp  
// Display the values of the result1 variable, the result2 variable, and  
// the integerTask.Result property.  
textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
```  
  
##  <a name="BKMK_TaskReturnType"></a> Tipo de valor devuelto Task  
 Los métodos asincrónicos que no contienen una instrucción return o que contienen una instrucción return que no devuelve un operando, tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>. Estos métodos deben ser métodos que devuelven void, si se escribieron para ejecutarse de forma sincrónica. Si se usa un tipo de valor devuelto `Task` para un método asincrónico, un método de llamada puede usar un operador await para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.  
  
 En el ejemplo siguiente, el método asincrónico `Task_MethodAsync` no contiene una instrucción return. Por tanto, se especifica un tipo de valor devuelto de `Task` para el método, lo que permite aplicar await a `Task_MethodAsync`. La definición del tipo `Task` no incluye una propiedad `Result` para almacenar un valor devuelto.  
  
```csharp  
// TASK EXAMPLE  
async Task Task_MethodAsync()  
{  
    // The body of an async method is expected to contain an awaited   
    // asynchronous call.  
    // Task.Delay is a placeholder for actual work.  
    await Task.Delay(2000);  
    // Task.Delay delays the following line by two seconds.  
    textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
    // This method has no return statement, so its return type is Task.    
}  
```  
  
 Se llama y se espera a `Task_MethodAsync` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un método sincrónico que devuelve void. En este caso, la aplicación de un operador await no genera un valor.  
  
 El código siguiente llama y espera al método `Task_MethodAsync`.  
  
```csharp  
// Call and await the Task-returning async method in the same statement.  
await Task_MethodAsync();  
```  
  
 Como en el ejemplo <xref:System.Threading.Tasks.Task%601> anterior, se puede separar la llamada a `Task_MethodAsync` de la aplicación de un operador await, como muestra el código siguiente. Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.  
  
 El código siguiente separa la llamada de `Task_MethodAsync` de la espera de la tarea que `Task_MethodAsync` devuelve.  
  
```csharp  
// Call and await in separate statements.  
Task simpleTask = Task_MethodAsync();  
  
// You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
await simpleTask;  
```  
  
##  <a name="BKMK_VoidReturnType"></a> Tipo de valor devuelto Void  
 El uso principal de tipo de valor devuelto void es en los controladores de eventos, donde se requiere un tipo de valor devuelto void. Un valor devuelto void también se puede usar para invalidar métodos que devuelven void o para los métodos que realizan actividades que se pueden clasificar como "desencadenar y omitir" (dispare y olvídese). Pero se debe devolver `Task` siempre que sea posible, ya que no se puede esperar a un método asincrónico que devuelve void. Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.  
  
 El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación. Si se produce una excepción en un método asincrónico que devuelve una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y se vuelve a producir cuando se espera la tarea. Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, y que se esperan las llamadas al método.  
  
 Para más información sobre cómo capturar excepciones en métodos asincrónicos, vea [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).  
  
 El código siguiente define un controlador de eventos asincrónico.  
  
```csharp  
// VOID EXAMPLE  
private async void button1_Click(object sender, RoutedEventArgs e)  
{  
    textBox1.Clear();  
  
    // Start the process and await its completion. DriverAsync is a   
    // Task-returning async method.  
    await DriverAsync();  
  
    // Say goodbye.  
    textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
}  
```  
  
##  <a name="BKMK_Example"></a> Ejemplo completo  
 El siguiente proyecto de Windows Presentation Foundation (WPF) contiene los ejemplos de código de este tema.  
  
 Para ejecutar el proyecto, realice los pasos siguientes:  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
3.  En la categoría **Instalado**, **Plantillas**, seleccione Visual C# y luego **Windows**. Seleccione **Aplicación WPF** en la lista de tipos de proyecto.  
  
4.  Escriba `AsyncReturnTypes` como el nombre del proyecto y, después, haga clic en el botón **Aceptar**.  
  
     El proyecto nuevo aparece en el **Explorador de soluciones**.  
  
5.  En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .  
  
     Si la pestaña no es visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y después haga clic en **Abrir**.  
  
6.  En la ventana **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.  
  
    ```csharp  
    <Window x:Class="AsyncReturnTypes.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     En la ventana **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.  
  
7.  En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después seleccione **Ver código**.  
  
8.  Reemplace el código del archivo MainWindow.xaml.cs por el código siguiente.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.Threading.Tasks;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Data;  
    using System.Windows.Documents;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    using System.Windows.Media.Imaging;  
    using System.Windows.Navigation;  
    using System.Windows.Shapes;  
  
    namespace AsyncReturnTypes  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            // VOID EXAMPLE  
            private async void button1_Click(object sender, RoutedEventArgs e)  
            {  
                textBox1.Clear();  
  
                // Start the process and await its completion. DriverAsync is a   
                // Task-returning async method.  
                await DriverAsync();  
  
                // Say goodbye.  
                textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
            }  
  
            async Task DriverAsync()  
            {  
                // Task<T>   
                // Call and await the Task<T>-returning async method in the same statement.  
                int result1 = await TaskOfT_MethodAsync();  
  
                // Call and await in separate statements.  
                Task<int> integerTask = TaskOfT_MethodAsync();  
  
                // You can do other work that does not rely on integerTask before awaiting.  
                textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
                int result2 = await integerTask;  
  
                // Display the values of the result1 variable, the result2 variable, and  
                // the integerTask.Result property.  
                textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
                textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
                textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
  
                // Task  
                // Call and await the Task-returning async method in the same statement.  
                await Task_MethodAsync();  
  
                // Call and await in separate statements.  
                Task simpleTask = Task_MethodAsync();  
  
                // You can do other work that does not rely on simpleTask before awaiting.  
                textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
                await simpleTask;  
            }  
  
            // TASK<T> EXAMPLE  
            async Task<int> TaskOfT_MethodAsync()  
            {  
                // The body of the method is expected to contain an awaited asynchronous  
                // call.  
                // Task.FromResult is a placeholder for actual work that returns a string.  
                var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
                // The method then can process the result in some way.  
                int leisureHours;  
                if (today.First() == 'S')  
                    leisureHours = 16;  
                else  
                    leisureHours = 5;  
  
                // Because the return statement specifies an operand of type int, the  
                // method must have a return type of Task<int>.  
                return leisureHours;  
            }  
  
            // TASK EXAMPLE  
            async Task Task_MethodAsync()  
            {  
                // The body of an async method is expected to contain an awaited   
                // asynchronous call.  
                // Task.Delay is a placeholder for actual work.  
                await Task.Delay(2000);  
                // Task.Delay delays the following line by two seconds.  
                textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
                // This method has no return statement, so its return type is Task.    
            }  
        }  
    }  
    ```  
  
9. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
     Debe aparecer los siguientes resultados.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  (Tutorial: Acceso la web con async y await [C#])  
 [Controlar el flujo en los programas asincrónicos (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [async](../../../../csharp/language-reference/keywords/async.md)   
 [await](../../../../csharp/language-reference/keywords/await.md)
