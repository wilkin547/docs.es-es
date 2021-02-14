---
description: Más información acerca de cómo cancelar las tareas asincrónicas restantes una vez completada (Visual Basic)
title: Cancelar las tareas asincrónicas restantes cuando se completa una
ms.date: 07/20/2015
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
ms.openlocfilehash: 6f7fc8af707c6c0d69fcf88e511b84b31ba75a82
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438897"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="b8796-103">Cancel Remaining Async Tasks after One Is Complete (Visual Basic) (Cancelación de tareas asincrónicas restantes [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="b8796-103">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>

<span data-ttu-id="b8796-104">Mediante el método <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> junto con <xref:System.Threading.CancellationToken>, puede cancelar todas las tareas restantes cuando se completa una tarea.</span><span class="sxs-lookup"><span data-stu-id="b8796-104">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="b8796-105">El método `WhenAny` toma un argumento que es una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-105">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="b8796-106">El método inicia todas las tareas y devuelve una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="b8796-106">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="b8796-107">La tarea se completa cuando se complete cualquier tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="b8796-107">The single task is complete when any task in the collection is complete.</span></span>

<span data-ttu-id="b8796-108">En este ejemplo se muestra cómo usar un token de cancelación junto con `WhenAny` para retener la primera tarea para finalizar de la colección de tareas y cancelar las tareas restantes.</span><span class="sxs-lookup"><span data-stu-id="b8796-108">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="b8796-109">Cada tarea descarga el contenido de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="b8796-109">Each task downloads the contents of a website.</span></span> <span data-ttu-id="b8796-110">En el ejemplo se muestra la longitud del contenido de la primera descarga completa y se cancelan las otras descargas.</span><span class="sxs-lookup"><span data-stu-id="b8796-110">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>

> [!NOTE]
> <span data-ttu-id="b8796-111">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="b8796-111">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="downloading-the-example"></a><span data-ttu-id="b8796-112">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8796-112">Downloading the Example</span></span>

<span data-ttu-id="b8796-113">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b8796-113">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="b8796-114">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8796-114">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="b8796-115">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="b8796-115">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="b8796-116">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="b8796-116">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="b8796-117">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterOneTask** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="b8796-117">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="b8796-118">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8796-118">Choose the F5 key to run the project.</span></span>

    <span data-ttu-id="b8796-119">Presione las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="b8796-119">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

6. <span data-ttu-id="b8796-120">Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8796-120">Run the program several times to verify that different downloads finish first.</span></span>

<span data-ttu-id="b8796-121">Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b8796-121">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>

## <a name="building-the-example"></a><span data-ttu-id="b8796-122">Compilación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8796-122">Building the Example</span></span>

<span data-ttu-id="b8796-123">En el ejemplo de este tema se agrega al proyecto desarrollado en [cancelar una tarea asincrónica o una lista de tareas](cancel-an-async-task-or-a-list-of-tasks.md) para cancelar una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-123">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="b8796-124">En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b8796-124">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="b8796-125">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="b8796-125">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="b8796-126">Agregue los cambios de este tema a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="b8796-126">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="b8796-127">En el archivo MainWindow. Xaml. VB del proyecto **CancelAListOfTasks** , inicie la transición moviendo los pasos de procesamiento de cada sitio web del bucle `AccessTheWebAsync` al siguiente método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b8796-127">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>

```vb
' ***Bundle the processing steps for a website into one async method.
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

    ' GetAsync returns a Task(Of HttpResponseMessage).
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

    ' Retrieve the website contents from the HttpResponseMessage.
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

    Return urlContents.Length
End Function
```

<span data-ttu-id="b8796-128">En `AccessTheWebAsync`, este ejemplo usa una consulta, el método <xref:System.Linq.Enumerable.ToArray%2A> y el método `WhenAny` para crear e iniciar una matriz de tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-128">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="b8796-129">La aplicación de `WhenAny` a la matriz devuelve una única tarea que, cuando se espera, se evalúa como la primera tarea que llega a la finalización de la matriz de tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-129">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>

<span data-ttu-id="b8796-130">Realice los siguientes cambios en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="b8796-130">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="b8796-131">Los asteriscos marcan los cambios en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="b8796-131">Asterisks mark the changes in the code file.</span></span>

1. <span data-ttu-id="b8796-132">Convierta en comentario o elimine el bucle.</span><span class="sxs-lookup"><span data-stu-id="b8796-132">Comment out or delete the loop.</span></span>

2. <span data-ttu-id="b8796-133">Cree una consulta que, cuando se ejecute, genere una colección de tareas genéricas.</span><span class="sxs-lookup"><span data-stu-id="b8796-133">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="b8796-134">Cada llamada a `ProcessURLAsync` devuelve un <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="b8796-134">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>

    ```vb
    ' ***Create a query that, when executed, returns a collection of tasks.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client, ct)
    ```

3. <span data-ttu-id="b8796-135">Llame a `ToArray` para ejecutar la consulta e iniciar las tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="b8796-136">La aplicación del método `WhenAny` en el paso siguiente ejecutaría la consulta e iniciaría las tareas sin usar `ToArray`, pero es posible que otros métodos no lo hagan.</span><span class="sxs-lookup"><span data-stu-id="b8796-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="b8796-137">La práctica más segura es forzar explícitamente la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b8796-137">The safest practice is to force execution of the query explicitly.</span></span>

    ```vb
    ' ***Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="b8796-138">Llame a `WhenAny` en la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="b8796-138">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="b8796-139">`WhenAny` devuelve una `Task(Of Task(Of Integer))` o `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="b8796-139">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="b8796-140">Es decir, `WhenAny` devuelve una tarea que se evalúa como una única `Task(Of Integer)` o `Task<int>` cuando se espera.</span><span class="sxs-lookup"><span data-stu-id="b8796-140">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="b8796-141">Esa única tarea es la primera tarea de la colección en finalizar.</span><span class="sxs-lookup"><span data-stu-id="b8796-141">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="b8796-142">La tarea que finalizó primero se asigna a `finishedTask`.</span><span class="sxs-lookup"><span data-stu-id="b8796-142">The task that finished first is assigned to `finishedTask`.</span></span> <span data-ttu-id="b8796-143">El tipo de `finishedTask` es <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero, ya que es el tipo de valor devuelto de `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="b8796-143">The type of `finishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>

    ```vb
    ' ***Call WhenAny and then await the result. The task that finishes
    ' first is assigned to finishedTask.
    Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)
    ```

5. <span data-ttu-id="b8796-144">En este ejemplo, solo le interesa la tarea que finaliza primero.</span><span class="sxs-lookup"><span data-stu-id="b8796-144">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="b8796-145">Por lo tanto, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> para cancelar las tareas restantes.</span><span class="sxs-lookup"><span data-stu-id="b8796-145">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>

    ```vb
    ' ***Cancel the rest of the downloads. You just want the first one.
    cts.Cancel()
    ```

6. <span data-ttu-id="b8796-146">Por último, espere a `finishedTask` para recuperar la longitud del contenido descargado.</span><span class="sxs-lookup"><span data-stu-id="b8796-146">Finally, await `finishedTask` to retrieve the length of the downloaded content.</span></span>

    ```vb
    Dim length = Await finishedTask
    resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    ```

<span data-ttu-id="b8796-147">Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8796-147">Run the program several times to verify that different downloads finish first.</span></span>

## <a name="complete-example"></a><span data-ttu-id="b8796-148">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="b8796-148">Complete Example</span></span>

<span data-ttu-id="b8796-149">El código siguiente es el archivo completo MainWindow. Xaml. vb o MainWindow.xaml.cs para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8796-149">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="b8796-150">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8796-150">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="b8796-151">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="b8796-151">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="b8796-152">Puede descargar el proyecto desde [Async Sample: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="b8796-152">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

        ' Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            Await AccessTheWebAsync(cts.Token)
            resultsTextBox.Text &= vbCrLf & "Download complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' You can still include a Cancel button if you want to.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        '' Comment out or delete the loop.
        ''For Each url In urlList
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).
        ''    ' Argument ct carries the message if the Cancel button is chosen.
        ''    ' Note that the Cancel button can cancel all remaining downloads.
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ''    ' Retrieve the website contents from the HttpResponseMessage.
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ''    resultsTextBox.Text &=
        ''        vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        ''Next

        ' ***Create a query that, when executed, returns a collection of tasks.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client, ct)

        ' ***Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' ***Call WhenAny and then await the result. The task that finishes
        ' first is assigned to finishedTask.
        Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)

        ' ***Cancel the rest of the downloads. You just want the first one.
        cts.Cancel()

        ' ***Await the first completed task and display the results
        ' Run the program several times to demonstrate that different
        ' websites can finish first.
        Dim length = Await finishedTask
        resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    End Function

    ' ***Bundle the processing steps for a website into one async method.
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        Return urlContents.Length
    End Function

    ' Add a method that creates a list of web addresses.
    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

End Class

' Sample output:

' Length of the downloaded website:  158856

' Download complete.
```

## <a name="see-also"></a><span data-ttu-id="b8796-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8796-153">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- <span data-ttu-id="b8796-154">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="b8796-154">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="b8796-155">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8796-155">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="b8796-156">Ejemplo de async: Ajuste de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b8796-156">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
