---
description: 'Más información sobre: tipos de valor devueltos Async (Visual Basic)'
title: Tipos de valor devueltos de Async
ms.date: 07/20/2015
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
ms.openlocfilehash: 12a7f577a89ff8f8037de879f9e37d6fdb917aa8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438923"
---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="a1751-103">Async Return Types (Visual Basic) (Tipos de valor devuelto de Async [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="a1751-103">Async Return Types (Visual Basic)</span></span>

<span data-ttu-id="a1751-104">Los métodos asincrónicos tienen tres posibles tipos devueltos: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> y void.</span><span class="sxs-lookup"><span data-stu-id="a1751-104">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="a1751-105">En Visual Basic, el tipo de valor devuelto void se escribe como un procedimiento [Sub](../../language-features/procedures/sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a1751-105">In Visual Basic, the void return type is written as a [Sub](../../language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="a1751-106">Para obtener más información sobre los métodos asincrónicos, vea [programación asincrónica con Async y Await (Visual Basic)](index.md).</span><span class="sxs-lookup"><span data-stu-id="a1751-106">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](index.md).</span></span>

<span data-ttu-id="a1751-107">Cada tipo de valor devuelto se examina en una de las siguientes secciones, y puede encontrar un ejemplo completo que usa los tres tipos al final del tema.</span><span class="sxs-lookup"><span data-stu-id="a1751-107">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>

> [!NOTE]
> <span data-ttu-id="a1751-108">Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a1751-108">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="taskt-return-type"></a><a name="BKMK_TaskTReturnType"></a> <span data-ttu-id="a1751-109">Tipo de valor devuelto Task(T)</span><span class="sxs-lookup"><span data-stu-id="a1751-109">Task(T) Return Type</span></span>

<span data-ttu-id="a1751-110">El <xref:System.Threading.Tasks.Task%601> tipo de valor devuelto se usa para un método asincrónico que contiene una instrucción [Return](../../../language-reference/statements/return-statement.md) en la que el operando tiene el tipo `TResult` .</span><span class="sxs-lookup"><span data-stu-id="a1751-110">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>

<span data-ttu-id="a1751-111">En el ejemplo siguiente, el método asincrónico `TaskOfT_MethodAsync` contiene una instrucción return que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="a1751-111">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="a1751-112">Por tanto, la declaración del método debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="a1751-112">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>

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

<span data-ttu-id="a1751-113">Cuando se llama a `TaskOfT_MethodAsync` desde una expresión await, esta recupera el valor entero (el valor de `leisureHours`) que está almacenado en la tarea que `TaskOfT_MethodAsync` devuelve.</span><span class="sxs-lookup"><span data-stu-id="a1751-113">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="a1751-114">Para obtener más información sobre las expresiones Await, vea [Await (operador](../../../language-reference/operators/await-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="a1751-114">For more information about await expressions, see [Await Operator](../../../language-reference/operators/await-operator.md).</span></span>

<span data-ttu-id="a1751-115">El código siguiente llama y espera al método `TaskOfT_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="a1751-115">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="a1751-116">El resultado se asigna a la variable `result1`.</span><span class="sxs-lookup"><span data-stu-id="a1751-116">The result is assigned to the `result1` variable.</span></span>

```vb
' Call and await the Task(Of T)-returning async method in the same statement.
Dim result1 As Integer = Await TaskOfT_MethodAsync()
```

<span data-ttu-id="a1751-117">Comprenderá mejor cómo sucede esto separando la llamada a `TaskOfT_MethodAsync` de la aplicación de `Await`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1751-117">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="a1751-118">Una llamada al método `TaskOfT_MethodAsync` que no se espera inmediatamente devuelve `Task(Of Integer)`, como se podría esperar de la declaración del método.</span><span class="sxs-lookup"><span data-stu-id="a1751-118">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="a1751-119">La tarea se asigna a la variable `integerTask` en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1751-119">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="a1751-120">Dado que `integerTask` es <xref:System.Threading.Tasks.Task%601>, contiene una propiedad <xref:System.Threading.Tasks.Task%601.Result> de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="a1751-120">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="a1751-121">En este caso, TResult representa un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="a1751-121">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="a1751-122">Cuando `Await` se aplica a `integerTask`, la expresión await se evalúa en el contenido de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> de `integerTask`.</span><span class="sxs-lookup"><span data-stu-id="a1751-122">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="a1751-123">El valor se asigna a la variable `result2`.</span><span class="sxs-lookup"><span data-stu-id="a1751-123">The value is assigned to the `result2` variable.</span></span>

> [!WARNING]
> <span data-ttu-id="a1751-124">La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> es una propiedad de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a1751-124">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="a1751-125">Si se intenta acceder a ella antes de que termine su tarea, se bloquea el subproceso que está activo actualmente hasta que finaliza la tarea y el valor está disponible.</span><span class="sxs-lookup"><span data-stu-id="a1751-125">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="a1751-126">En la mayoría de los casos, se debe tener acceso al valor usando `Await` en lugar de tener acceso directamente a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1751-126">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>

```vb
' Call and await in separate statements.
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()

' You can do other work that does not rely on resultTask before awaiting.
textBox1.Text &= "Application can continue working while the Task(Of T) runs. . . . " & vbCrLf

Dim result2 As Integer = Await integerTask
```

<span data-ttu-id="a1751-127">Las instrucciones mostradas en el siguiente código comprueban que los valores de la variable `result1`, la variable `result2` y la propiedad `Result` son los mismos.</span><span class="sxs-lookup"><span data-stu-id="a1751-127">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="a1751-128">Recuerde que la propiedad `Result` es una propiedad bloqueo y no se debe tener acceso a ella antes de haber esperado a su tarea.</span><span class="sxs-lookup"><span data-stu-id="a1751-128">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>

```vb
' Display the values of the result1 variable, the result2 variable, and
' the resultTask.Result property.
textBox1.Text &= vbCrLf & $"Value of result1 variable:   {result1}" & vbCrLf
textBox1.Text &= $"Value of result2 variable:   {result2}" & vbCrLf
textBox1.Text &= $"Value of resultTask.Result:  {integerTask.Result}" & vbCrLf
```

## <a name="task-return-type"></a><a name="BKMK_TaskReturnType"></a> <span data-ttu-id="a1751-129">Tipo de valor devuelto de tarea</span><span class="sxs-lookup"><span data-stu-id="a1751-129">Task Return Type</span></span>

<span data-ttu-id="a1751-130">Los métodos asincrónicos que no contienen una instrucción return o que contienen una instrucción return que no devuelve un operando tienen normalmente un tipo de valor devuelto de <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="a1751-130">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="a1751-131">Estos métodos serían procedimientos [Sub](../../language-features/procedures/sub-procedures.md) si se escribieron para ejecutarse de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a1751-131">Such methods would be [Sub](../../language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="a1751-132">Si se usa un tipo de valor devuelto `Task` para un método asincrónico, un método de llamada puede usar un operador `Await` para suspender la finalización del llamador hasta que finalice el método asincrónico llamado.</span><span class="sxs-lookup"><span data-stu-id="a1751-132">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>

<span data-ttu-id="a1751-133">En el ejemplo siguiente, el método asincrónico `Task_MethodAsync` no contiene una instrucción return.</span><span class="sxs-lookup"><span data-stu-id="a1751-133">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="a1751-134">Por tanto, se especifica un tipo de valor devuelto de `Task` para el método, lo que permite aplicar await a `Task_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="a1751-134">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="a1751-135">La definición del tipo `Task` no incluye una propiedad `Result` para almacenar un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="a1751-135">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>

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

<span data-ttu-id="a1751-136">Se llama y se espera a `Task_MethodAsync` mediante una instrucción await en lugar de una expresión await, similar a la instrucción de llamada para un `Sub` sincrónica o método que devuelve void.</span><span class="sxs-lookup"><span data-stu-id="a1751-136">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="a1751-137">En este caso, la aplicación de un `Await` operador no genera un valor.</span><span class="sxs-lookup"><span data-stu-id="a1751-137">The application of an `Await` operator in this case doesn't produce a value.</span></span>

<span data-ttu-id="a1751-138">El código siguiente llama y espera al método `Task_MethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="a1751-138">The following code calls and awaits method `Task_MethodAsync`.</span></span>

```vb
' Call and await the Task-returning async method in the same statement.
Await Task_MethodAsync()
```

<span data-ttu-id="a1751-139">Como en el <xref:System.Threading.Tasks.Task%601> ejemplo anterior, puede separar la llamada a `Task_MethodAsync` de la aplicación de un `Await` operador, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1751-139">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="a1751-140">Pero recuerde que una `Task` no tiene una propiedad `Result` y que no se genera ningún valor cuando se aplica un operador await a una `Task`.</span><span class="sxs-lookup"><span data-stu-id="a1751-140">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>

<span data-ttu-id="a1751-141">El código siguiente separa la llamada de `Task_MethodAsync` de la espera de la tarea que `Task_MethodAsync` devuelve.</span><span class="sxs-lookup"><span data-stu-id="a1751-141">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>

```vb
' Call and await in separate statements.
Dim simpleTask As Task = Task_MethodAsync()

' You can do other work that does not rely on simpleTask before awaiting.
textBox1.Text &= vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf

Await simpleTask
```

## <a name="void-return-type"></a><a name="BKMK_VoidReturnType"></a> <span data-ttu-id="a1751-142">Tipo de valor devuelto void</span><span class="sxs-lookup"><span data-stu-id="a1751-142">Void Return Type</span></span>

<span data-ttu-id="a1751-143">El uso principal de `Sub` los procedimientos está en los controladores de eventos, donde no hay ningún tipo de valor devuelto (denominado tipo de valor devuelto void en otros lenguajes).</span><span class="sxs-lookup"><span data-stu-id="a1751-143">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="a1751-144">Un valor devuelto void también se puede usar para invalidar métodos que devuelven void o para los métodos que realizan actividades que se pueden clasificar como "desencadenar y omitir" (dispare y olvídese).</span><span class="sxs-lookup"><span data-stu-id="a1751-144">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="a1751-145">Pero se debe devolver `Task` siempre que sea posible, ya que no se puede esperar a un método asincrónico que devuelve void.</span><span class="sxs-lookup"><span data-stu-id="a1751-145">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="a1751-146">Cualquier llamador de este método debe poder continuar hasta completarse sin esperar a que finalice el método asincrónico llamado y el llamador debe ser independiente de los valores o las excepciones que genera el método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a1751-146">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>

<span data-ttu-id="a1751-147">El llamador de un método asincrónico que devuelve void no puede capturar las excepciones emitidas desde el método y dichas excepciones no controladas pueden provocar un error de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1751-147">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="a1751-148">Si se produce una excepción en un método asincrónico que devuelve <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, la excepción se almacena en la tarea devuelta y se vuelve a emitir cuando se espera la tarea.</span><span class="sxs-lookup"><span data-stu-id="a1751-148">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="a1751-149">Por tanto, asegúrese de que cualquier método asincrónico que puede producir una excepción tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> y que se esperan llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="a1751-149">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>

<span data-ttu-id="a1751-150">Para más información sobre cómo capturar excepciones en métodos asincrónicos, vea [Instrucción Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a1751-150">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md).</span></span>

<span data-ttu-id="a1751-151">El código siguiente define un controlador de eventos asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a1751-151">The following code defines an async event handler.</span></span>

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

## <a name="complete-example"></a><a name="BKMK_Example"></a> <span data-ttu-id="a1751-152">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="a1751-152">Complete Example</span></span>

<span data-ttu-id="a1751-153">El siguiente proyecto de Windows Presentation Foundation (WPF) contiene los ejemplos de código de este tema.</span><span class="sxs-lookup"><span data-stu-id="a1751-153">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>

 <span data-ttu-id="a1751-154">Para ejecutar el proyecto, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1751-154">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="a1751-155">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a1751-155">Start Visual Studio.</span></span>

2. <span data-ttu-id="a1751-156">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a1751-156">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="a1751-157">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="a1751-157">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="a1751-158">En la categoría **instalado**, **plantillas** , elija **Visual Basic** y, a continuación, elija **Windows**.</span><span class="sxs-lookup"><span data-stu-id="a1751-158">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="a1751-159">Seleccione **Aplicación WPF** en la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a1751-159">Choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="a1751-160">Escriba `AsyncReturnTypes` como el nombre del proyecto y elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1751-160">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="a1751-161">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a1751-161">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="a1751-162">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="a1751-162">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="a1751-163">Si la pestaña no es visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y después haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a1751-163">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>

6. <span data-ttu-id="a1751-164">En la ventana **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1751-164">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>

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

     <span data-ttu-id="a1751-165">En la ventana **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="a1751-165">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>

7. <span data-ttu-id="a1751-166">En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="a1751-166">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

8. <span data-ttu-id="a1751-167">Reemplace el código en el archivo MainWindow.xaml.vb por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1751-167">Replace the code in MainWindow.xaml.vb with the following code.</span></span>

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

9. <span data-ttu-id="a1751-168">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="a1751-168">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="a1751-169">Debería aparecer el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a1751-169">The following output should appear:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a1751-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1751-170">See also</span></span>

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [<span data-ttu-id="a1751-171">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1751-171">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- <span data-ttu-id="a1751-172">[Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md) (Flujo de control en programas asincrónicos [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="a1751-172">[Control Flow in Async Programs (Visual Basic)](control-flow-in-async-programs.md)</span></span>
- [<span data-ttu-id="a1751-173">Asincrónico</span><span class="sxs-lookup"><span data-stu-id="a1751-173">Async</span></span>](../../../language-reference/modifiers/async.md)
- [<span data-ttu-id="a1751-174">Await (Operador)</span><span class="sxs-lookup"><span data-stu-id="a1751-174">Await Operator</span></span>](../../../language-reference/operators/await-operator.md)
