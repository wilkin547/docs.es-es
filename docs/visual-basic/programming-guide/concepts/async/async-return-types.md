---
title: Tipos de valor devueltos de Async (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a>Tipos de valor devueltos de Async (Visual Basic)
Los métodos Async tienen tres posibles tipos de valor devueltos: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>y void.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> En Visual Basic, el tipo de valor devuelto void se escribe como un [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedimiento. Para obtener más información acerca de los métodos asincrónicos, vea [la programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.  
  
> [!NOTE]
>  Para ejecutar el ejemplo, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
##  <a name="BKMK_TaskTReturnType"></a>Tipo de valor devuelto de Task(T)  
 El <xref:System.Threading.Tasks.Task%601>devolver el tipo se utiliza para un método asincrónico que contiene un [devolver](../../../../visual-basic/language-reference/statements/return-statement.md) en el que el operando tiene el tipo de instrucción `TResult`.</xref:System.Threading.Tasks.Task%601>  
  
 En el ejemplo siguiente, la `TaskOfT_MethodAsync` método asincrónico contiene una instrucción return que devuelve un entero. Por lo tanto, la declaración de método debe especificar un tipo de valor devuelto de `Task(Of Integer)`.  
  
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
  
 Cuando `TaskOfT_MethodAsync` se llama desde dentro de una expresión await, la expresión await recupera el valor entero (el valor de `leisureHours`) que se almacena en la tarea devuelta por `TaskOfT_MethodAsync`. Para obtener más información acerca de expresiones await, consulte [operador Await](../../../../visual-basic/language-reference/operators/await-operator.md).  
  
 El código siguiente llama a y espera el método `TaskOfT_MethodAsync`. El resultado se asigna a la `result1` variable.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 Comprender mejor cómo sucede separando la llamada a `TaskOfT_MethodAsync` de la aplicación de `Await`, como se muestra en el código siguiente. Una llamada al método `TaskOfT_MethodAsync` que no se devuelve inmediatamente espera un `Task(Of Integer)`, como se podría esperar de la declaración del método. La tarea se asigna a la `integerTask` variable en el ejemplo. Porque `integerTask` es un <xref:System.Threading.Tasks.Task%601>, contiene un <xref:System.Threading.Tasks.Task%601.Result>propiedad de tipo `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601> En este caso, TResult representa un tipo entero. Cuando `Await` se aplica a `integerTask`, evalúa la expresión await en el contenido de la <xref:System.Threading.Tasks.Task%601.Result%2A>propiedad de `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A> El valor se asigna a la `result2` variable.  
  
> [!WARNING]
>  El <xref:System.Threading.Tasks.Task%601.Result%2A>es una propiedad bloqueo.</xref:System.Threading.Tasks.Task%601.Result%2A> Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible. En la mayoría de los casos, se debe tener acceso al valor mediante el uso de `Await` en lugar de tener acceso directamente a la propiedad.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 Las instrucciones de la pantalla en el siguiente código que comprueban los valores de la `result1` variable, el `result2` variable y el `Result` propiedad son los mismos. Recuerde que el `Result` propiedad es una propiedad bloqueo y no debe tener acceso antes de la tarea se ha esperado.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a>Tipo de valor devuelto de la tarea  
 Los métodos asincrónicos que no contienen una instrucción return o que contengan una instrucción return que no devuelve un operando normalmente tienen un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> Estos métodos sería [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedimientos si se escribieron para ejecutarse de forma sincrónica. Si utiliza un `Task` tipo de valor devuelto para un método asincrónico, se puede utilizar un método de llamada un `Await` operador para suspender la finalización del llamador hasta que finaliza el método de llamada asincrónica.  
  
 En el ejemplo siguiente, el método asincrónico `Task_MethodAsync` no contiene una instrucción return. Por lo tanto, especifica un tipo de valor devuelto de `Task` para el método, lo que permite `Task_MethodAsync` a esperar. La definición de la `Task` no incluye el tipo de un `Result` propiedad para almacenar un valor devuelto.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync`se le llama y espera mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para sincrónica `Sub` o método que devuelve void. La aplicación de un `Await` (operador) en este caso no genera un valor.  
  
 El código siguiente llama a y espera el método `Task_MethodAsync`.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 Al igual que en el anterior <xref:System.Threading.Tasks.Task%601>ejemplo, puede separar la llamada a `Task_MethodAsync` de la aplicación de un `Await` operador, como se muestra en el siguiente código.</xref:System.Threading.Tasks.Task%601> Sin embargo, recuerde que un `Task` no tiene un `Result` propiedad y que ningún valor se genera cuando se aplica un operador await a una `Task`.  
  
 El siguiente código separa llamada `Task_MethodAsync` de espera de la tarea que `Task_MethodAsync` devuelve.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a>Tipo de valor devuelto void  
 El uso principal de `Sub` procedimientos está en controladores de eventos, donde no hay ningún tipo de valor devuelto (denominada un tipo de valor devuelto void en otros lenguajes). Un valor devuelto void también se puede usar para invalidar métodos que devuelven void o para los métodos que realizan actividades que se pueden clasificar como "desencadenar y omitir" (dispare y olvídese). Sin embargo, se debe devolver un `Task` siempre que sea posible, ya que no se puede esperar un método asincrónico devuelve void. Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.  
  
 El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación. Si se produce una excepción en un método asincrónico que devuelve un <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y vuelve a producir cuando se espera el task.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>y que las llamadas al método se esperado.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 Para obtener más información acerca de cómo detectar excepciones en métodos asincrónicos, vea [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 El código siguiente define un controlador de eventos asincrónico.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a>Ejemplo completo  
 El siguiente proyecto de Windows Presentation Foundation (WPF) contiene los ejemplos de código de este tema.  
  
 Para ejecutar el proyecto, realice los pasos siguientes:  
  
1.  Inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.  
  
     Aparece el cuadro de diálogo **Nuevo proyecto** .  
  
3.  En el **instalado**, **plantillas** categoría, elija **Visual Basic**y, a continuación, elija **Windows**. Elija **aplicación WPF** de la lista de tipos de proyecto.  
  
4.  Escriba `AsyncReturnTypes` como el nombre del proyecto y, a continuación, elija la **Aceptar** botón.  
  
     El proyecto nuevo aparece en **el Explorador de soluciones**.  
  
5.  En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .  
  
     Si la ficha no está visible, abra el menú contextual de MainWindow.xaml en **el Explorador de soluciones**y, a continuación, elija **abrir**.  
  
6.  En el **XAML** ventana de MainWindow.xaml, reemplace el código por el código siguiente.  
  
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
  
     Aparece una ventana simple que contiene un cuadro de texto y un botón en la **diseño** ventana de MainWindow.xaml.  
  
7.  En **el Explorador de soluciones**, abra el menú contextual para MainWindow.xaml.vb y, a continuación, elija **ver código**.  
  
8.  Reemplace el código en el archivo MainWindow.xaml.vb por el código siguiente.  
  
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
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
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
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
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
 <xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Tutorial: Acceso a la Web usando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Flujo de control en programas Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Await (operador)](../../../../visual-basic/language-reference/operators/await-operator.md)
