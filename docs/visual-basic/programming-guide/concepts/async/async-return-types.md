---
title: Tipos de valor devueltos de Async
ms.date: 07/20/2015
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
ms.openlocfilehash: 5d19fc9831580412da24333be0885fce55384658
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396719"
---
# <a name="async-return-types-visual-basic"></a>Async Return Types (Visual Basic) (Tipos de valor devuelto de Async [Visual Basic])

Los métodos asincrónicos tienen tres posibles tipos devueltos: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> y void. En Visual Basic, el tipo de valor devuelto void se escribe como un procedimiento [Sub](../../language-features/procedures/sub-procedures.md). Para obtener más información sobre los métodos asincrónicos, vea [programación asincrónica con Async y Await (Visual Basic)](index.md).

Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.

> [!NOTE]
> Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.

## <a name="taskt-return-type"></a><a name="BKMK_TaskTReturnType"></a> Tipo de valor devuelto Task(T)

El <xref:System.Threading.Tasks.Task%601> tipo de valor devuelto se usa para un método asincrónico que contiene una instrucción [Return](../../../language-reference/statements/return-statement.md) en la que el operando tiene el tipo `TResult` .

En el ejemplo siguiente, el método asincrónico `TaskOfT_MethodAsync` contiene una instrucción return que devuelve un entero. Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task(Of Integer)`.

```vb
' TASK(OF T) EXAMPLE
Async Function TaskOfT_MethodAsync() As Task(Of Integer)

    ' The body of an async method is expected to contain an awaited
    ' asynchronous call.
    ' Task.FromResult is a placeholder for actual work that returns a string.
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())

    ' The method then can process the result in some way.
    Dim leisureHours As Integer
    If today.First() = "S" Then
        leisureHours = 16
    Else
        leisureHours = 5
    End If

    ' Because the return statement specifies an operand of type Integer, the
    ' method must have a return type of Task(Of Integer).
    Return leisureHours
End Function
```

Cuando se llama a `TaskOfT_MethodAsync` desde una expresión await, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que `TaskOfT_MethodAsync` devuelve. Para obtener más información sobre las expresiones Await, vea [Await (operador](../../../language-reference/operators/await-operator.md)).

El código siguiente llama y espera al método `TaskOfT_MethodAsync`. El resultado se asigna a la variable `result1`.

```vb
' Call and await the Task(Of T)-returning async method in the same statement.
Dim result1 As Integer = Await TaskOfT_MethodAsync()
```

Comprenderá mejor cómo sucede esto separando la llamada a `TaskOfT_MethodAsync` de la aplicación de `Await`, como se muestra en el código siguiente. Una llamada al método `TaskOfT_MethodAsync` que no se espera inmediatamente devuelve `Task(Of Integer)`, como se podría esperar de la declaración del método. La tarea se asigna a la variable `integerTask` en el ejemplo. Dado que `integerTask` es <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`. En este caso, TResult representa un tipo entero. Cuando `Await` se aplica a `integerTask`, la expresión await se evalúa en el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `integerTask`. El valor se asigna a la variable `result2`.

> [!WARNING]
> La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo. Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor usando `Await` en lugar de tener acceso directamente a la propiedad.

```vb
' Call and await in separate statements.
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()

' You can do other work that does not rely on resultTask before awaiting.
textBox1.Text &= "Application can continue working while the Task(Of T) runs. . . . " & vbCrLf

Dim result2 As Integer = Await integerTask
```

Las instrucciones mostradas en el siguiente código comprueban que los valores de la variable `result1`, la variable `result2` y la propiedad `Result` son los mismos. Recuerde que la propiedad `Result` es una propiedad bloqueo y no se debe tener acceso a ella antes de haber esperado a su tarea.

```vb
' Display the values of the result1 variable, the result2 variable, and
' the resultTask.Result property.
textBox1.Text &= vbCrLf & $"Value of result1 variable:   {result1}" & vbCrLf
textBox1.Text &= $"Value of result2 variable:   {result2}" & vbCrLf
textBox1.Text &= $"Value of resultTask.Result:  {integerTask.Result}" & vbCrLf
```

## <a name="task-return-type"></a><a name="BKMK_TaskReturnType"></a>Tipo de valor devuelto de tarea

Los métodos asincrónicos que no contienen una instrucción return o que contienen una instrucción return que no devuelve un operando tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>. Estos métodos serían procedimientos [Sub](../../language-features/procedures/sub-procedures.md) si se escribieron para ejecutarse de forma sincrónica. Si se usa un tipo de valor devuelto `Task` para un método asincrónico, un método de llamada puede usar un operador `Await` para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.

En el ejemplo siguiente, el método asincrónico `Task_MethodAsync` no contiene una instrucción return. Por tanto, se especifica un tipo de valor devuelto de `Task` para el método, lo que permite aplicar await a `Task_MethodAsync`. La definición del tipo `Task` no incluye una propiedad `Result` para almacenar un valor devuelto.

```vb
' TASK EXAMPLE
Async Function Task_MethodAsync() As Task

    ' The body of an async method is expected to contain an awaited
    ' asynchronous call.
    ' Task.Delay is a placeholder for actual work.
    Await Task.Delay(2000)
    textBox1.Text &= vbCrLf & "Sorry for the delay. . . ." & vbCrLf

    ' This method has no return statement, so its return type is Task.
End Function
```

Se llama y se espera a `Task_MethodAsync` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un `Sub` sincrónica o método que devuelve void. En este caso, la aplicación de un `Await` operador no genera un valor.

El código siguiente llama y espera al método `Task_MethodAsync`.

```vb
' Call and await the Task-returning async method in the same statement.
Await Task_MethodAsync()
```

Como en el <xref:System.Threading.Tasks.Task%601> ejemplo anterior, puede separar la llamada a `Task_MethodAsync` de la aplicación de un `Await` operador, como se muestra en el código siguiente. Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.

El código siguiente separa la llamada de `Task_MethodAsync` de la espera de la tarea que `Task_MethodAsync` devuelve.

```vb
' Call and await in separate statements.
Dim simpleTask As Task = Task_MethodAsync()

' You can do other work that does not rely on simpleTask before awaiting.
textBox1.Text &= vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf

Await simpleTask
```

## <a name="void-return-type"></a><a name="BKMK_VoidReturnType"></a>Tipo de valor devuelto void

El uso principal de `Sub` los procedimientos está en los controladores de eventos, donde no hay ningún tipo de valor devuelto (denominado tipo de valor devuelto void en otros lenguajes). Un valor devuelto void también se puede usar para invalidar métodos que devuelven void o para los métodos que realizan actividades que se pueden clasificar como "desencadenar y omitir" (dispare y olvídese). Pero se debe devolver `Task` siempre que sea posible, ya que no se puede esperar a un método asincrónico que devuelve void. Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.

El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación. Si se produce una excepción en un método asincrónico que devuelve <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y se vuelve a emitir cuando se espera la tarea. Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y que se esperan llamadas al método.

Para más información sobre cómo capturar excepciones en métodos asincrónicos, vea [Instrucción Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).

El código siguiente define un controlador de eventos asincrónico.

```vb
' SUB EXAMPLE
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click

    textBox1.Clear()

    ' Start the process and await its completion. DriverAsync is a
    ' Task-returning async method.
    Await DriverAsync()

    ' Say goodbye.
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."
End Sub
```

## <a name="complete-example"></a><a name="BKMK_Example"></a>Ejemplo completo

El siguiente proyecto de Windows Presentation Foundation (WPF) contiene los ejemplos de código de este tema.

 Para ejecutar el proyecto, realice los pasos siguientes:

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En la categoría **instalado**, **plantillas** , elija **Visual Basic**y, a continuación, elija **Windows**. Seleccione **Aplicación WPF** en la lista de tipos de proyecto.

4. Escriba `AsyncReturnTypes` como el nombre del proyecto y elija el botón **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

5. En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .

     Si la pestaña no es visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y después haga clic en **Abrir**.

6. En la ventana **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.

    ```vb
    <Window x:Class="MainWindow"
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

7. En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.

8. Reemplace el código en el archivo MainWindow.xaml.vb por el código siguiente.

    ```vb
    Class MainWindow

        ' SUB EXAMPLE
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click

            textBox1.Clear()

            ' Start the process and await its completion. DriverAsync is a
            ' Task-returning async method.
            Await DriverAsync()

            ' Say goodbye.
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."
        End Sub

        Async Function DriverAsync() As Task

            ' Task(Of T)
            ' Call and await the Task(Of T)-returning async method in the same statement.
            Dim result1 As Integer = Await TaskOfT_MethodAsync()

            ' Call and await in separate statements.
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()

            ' You can do other work that does not rely on resultTask before awaiting.
            textBox1.Text &= "Application can continue working while the Task(Of T) runs. . . . " & vbCrLf

            Dim result2 As Integer = Await integerTask

            ' Display the values of the result1 variable, the result2 variable, and
            ' the resultTask.Result property.
            textBox1.Text &= vbCrLf & $"Value of result1 variable:   {result1}" & vbCrLf
            textBox1.Text &= $"Value of result2 variable:   {result2}" & vbCrLf
            textBox1.Text &= $"Value of resultTask.Result:  {integerTask.Result}" & vbCrLf

            ' Task
            ' Call and await the Task-returning async method in the same statement.
            Await Task_MethodAsync()

            ' Call and await in separate statements.
            Dim simpleTask As Task = Task_MethodAsync()

            ' You can do other work that does not rely on simpleTask before awaiting.
            textBox1.Text &= vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf

            Await simpleTask
        End Function

        ' TASK(OF T) EXAMPLE
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)

            ' The body of an async method is expected to contain an awaited
            ' asynchronous call.
            ' Task.FromResult is a placeholder for actual work that returns a string.
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())

            ' The method then can process the result in some way.
            Dim leisureHours As Integer
            If today.First() = "S" Then
                leisureHours = 16
            Else
                leisureHours = 5
            End If

            ' Because the return statement specifies an operand of type Integer, the
            ' method must have a return type of Task(Of Integer).
            Return leisureHours
        End Function

        ' TASK EXAMPLE
        Async Function Task_MethodAsync() As Task

            ' The body of an async method is expected to contain an awaited
            ' asynchronous call.
            ' Task.Delay is a placeholder for actual work.
            Await Task.Delay(2000)
            textBox1.Text &= vbCrLf & "Sorry for the delay. . . ." & vbCrLf

            ' This method has no return statement, so its return type is Task.
        End Function

    End Class
    ```

9. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio**.

     Debería aparecer el siguiente resultado:

    ```console
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

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [Visual Basic])
- [Asincrónica](../../../language-reference/modifiers/async.md)
- [Await (operador)](../../../language-reference/operators/await-operator.md)
