---
description: 'Más información sobre: Cómo: hacer varias solicitudes web en paralelo mediante Async y Await (Visual Basic)'
title: Procedimiento para realizar varias solicitudes web en paralelo con async y await
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: e1137424911b77ba94a760a4b4b034e45ef83462
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474348"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="7b61b-103">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic) (Realización de solicitudes web en paralelo mediante Async y Await [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="7b61b-103">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="7b61b-104">En un método asincrónico, las tareas se inician en el momento de crearse.</span><span class="sxs-lookup"><span data-stu-id="7b61b-104">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="7b61b-105">El operador [Await](../../../language-reference/operators/await-operator.md) se aplica a la tarea en el punto del método en el que el procesamiento no puede continuar hasta que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="7b61b-105">The [Await](../../../language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="7b61b-106">A menudo se espera una tarea en cuanto se crea, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7b61b-106">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

<span data-ttu-id="7b61b-107">Pero puede separar la creación de la tarea de la espera si el programa tiene otro trabajo por efectuar que no dependa de la finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="7b61b-107">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>

```vb
' The following line creates and starts the task.
Dim myTask = someWebAccessMethodAsync(url)

' While the task is running, you can do other work that does not depend
' on the results of the task.
' . . . . .

' The application of Await suspends the rest of this method until the task is
' complete.
Dim result = Await myTask
```

<span data-ttu-id="7b61b-108">Entre el inicio de una tarea y la espera puede iniciar otras tareas.</span><span class="sxs-lookup"><span data-stu-id="7b61b-108">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="7b61b-109">Las tareas adicionales se ejecutan implícitamente en paralelo, pero no se crean subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="7b61b-109">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>

<span data-ttu-id="7b61b-110">El programa siguiente inicia tres descargas web asincrónicas y las espera en el orden en el que se han llamado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-110">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="7b61b-111">Observe que, al ejecutar el programa, las tareas no siempre finalizan en el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-111">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="7b61b-112">Empiezan a ejecutarse en el momento de crearse y una o más tareas podrían finalizar antes de que el método llegue a las expresiones await.</span><span class="sxs-lookup"><span data-stu-id="7b61b-112">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="7b61b-113">Para llevar a cabo este proyecto, debe tener instalados en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="7b61b-113">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>

<span data-ttu-id="7b61b-114">Para ver otro ejemplo en el que se inician varias tareas al mismo tiempo, vea [Cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="7b61b-114">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

<span data-ttu-id="7b61b-115">Puede descargar el código de este ejemplo en [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span><span class="sxs-lookup"><span data-stu-id="7b61b-115">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>

### <a name="to-set-up-the-project"></a><span data-ttu-id="7b61b-116">Para configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="7b61b-116">To set up the project</span></span>

1. <span data-ttu-id="7b61b-117">Para configurar una aplicación WPF, lleve a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="7b61b-117">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="7b61b-118">Puede encontrar instrucciones detalladas para estos pasos en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="7b61b-118">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="7b61b-119">Cree una aplicación WPF que contenga un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="7b61b-119">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="7b61b-120">Asigne al botón el nombre `startButton` y, al cuadro de texto, `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="7b61b-120">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>

    - <span data-ttu-id="7b61b-121">Agregue una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="7b61b-121">Add a reference for <xref:System.Net.Http>.</span></span>

    - <span data-ttu-id="7b61b-122">En el archivo MainWindow. Xaml. VB, agregue una `Imports` instrucción para `System.Net.Http` .</span><span class="sxs-lookup"><span data-stu-id="7b61b-122">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>

### <a name="to-add-the-code"></a><span data-ttu-id="7b61b-123">Para agregar el código</span><span class="sxs-lookup"><span data-stu-id="7b61b-123">To add the code</span></span>

1. <span data-ttu-id="7b61b-124">En la ventana de diseño, MainWindow. XAML, haga doble clic en el botón para crear el `startButton_Click` controlador de eventos en MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="7b61b-124">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="7b61b-125">Copie el código siguiente y péguelo en el cuerpo de `startButton_Click` en MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="7b61b-125">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     <span data-ttu-id="7b61b-126">El código llama a un método asincrónico, `CreateMultipleTasksAsync`, que dirige la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b61b-126">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>

3. <span data-ttu-id="7b61b-127">Agregue los siguientes métodos de soporte técnico al proyecto:</span><span class="sxs-lookup"><span data-stu-id="7b61b-127">Add the following support methods to the project:</span></span>

    - <span data-ttu-id="7b61b-128">`ProcessURLAsync` usa un método <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="7b61b-128">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="7b61b-129">Luego, el método de soporte, `ProcessURLAsync`, muestra y devuelve la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="7b61b-129">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>

    - <span data-ttu-id="7b61b-130">`DisplayResults` muestra el número de bytes de la matriz de bytes de cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="7b61b-130">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="7b61b-131">En esta pantalla se muestra cuándo se ha terminado la descarga de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="7b61b-131">This display shows when each task has finished downloading.</span></span>

     <span data-ttu-id="7b61b-132">Copie los métodos siguientes y péguelos después del `startButton_Click` controlador de eventos en MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="7b61b-132">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

4. <span data-ttu-id="7b61b-133">Por último, defina el método `CreateMultipleTasksAsync`, que lleva a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="7b61b-133">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>

    - <span data-ttu-id="7b61b-134">El método declara un objeto `HttpClient`, que necesita para tener acceso al método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> en `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="7b61b-134">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>

    - <span data-ttu-id="7b61b-135">El método crea e inicia tres tareas de tipo <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="7b61b-135">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="7b61b-136">A medida que finaliza cada tarea, `DisplayResults` muestra la dirección URL de la tarea y la longitud del contenido descargado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-136">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="7b61b-137">Dado que las tareas se ejecutan de manera asincrónica, el orden en que aparecen los resultados puede ser diferente del orden en que se han declarado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-137">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>

    - <span data-ttu-id="7b61b-138">El método espera la finalización de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="7b61b-138">The method awaits the completion of each task.</span></span> <span data-ttu-id="7b61b-139">Cada operador `Await` suspende la ejecución de `CreateMultipleTasksAsync` hasta que finalice la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="7b61b-139">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="7b61b-140">El operador también recupera el valor devuelto de la llamada a `ProcessURLAsync` desde cada tarea finalizada.</span><span class="sxs-lookup"><span data-stu-id="7b61b-140">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>

    - <span data-ttu-id="7b61b-141">Una vez concluidas las tareas y recuperados los valores enteros, el método suma las longitudes de los sitios web y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-141">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>

     <span data-ttu-id="7b61b-142">Copie el método siguiente y péguelo en la solución.</span><span class="sxs-lookup"><span data-stu-id="7b61b-142">Copy the following method, and paste it into your solution.</span></span>

    ```vb
    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function
    ```

5. <span data-ttu-id="7b61b-143">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="7b61b-143">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="7b61b-144">Ejecute el programa varias veces para comprobar que las tres tareas no finalizan siempre en el mismo orden y que el orden en el que finalizan no es necesariamente el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="7b61b-144">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>

## <a name="example"></a><span data-ttu-id="7b61b-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b61b-145">Example</span></span>

<span data-ttu-id="7b61b-146">El código siguiente contiene el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="7b61b-146">The following code contains the full example.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
        resultsTextBox.Clear()
        Await CreateMultipleTasksAsync()
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="7b61b-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b61b-147">See also</span></span>

- [<span data-ttu-id="7b61b-148">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b61b-148">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="7b61b-149">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b61b-149">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="7b61b-150">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="7b61b-150">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
