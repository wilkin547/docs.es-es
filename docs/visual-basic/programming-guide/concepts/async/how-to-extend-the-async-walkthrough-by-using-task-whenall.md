---
title: Procedimiento para ampliar el tutorial de async mediante Task.WhenAll
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: fb323852c83b1edf51396a0b800c2d54a833d0c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396628"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a><span data-ttu-id="822c1-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="822c1-102">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>

<span data-ttu-id="822c1-103">Puede mejorar el rendimiento de la solución asincrónica en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) mediante el <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="822c1-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="822c1-104">Este método espera de forma asincrónica varias operaciones asincrónicas, que se representan como una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="822c1-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>

<span data-ttu-id="822c1-105">Es posible que en el tutorial observara que los sitios web se descargan a distintas velocidades.</span><span class="sxs-lookup"><span data-stu-id="822c1-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="822c1-106">A veces uno de los sitios web es muy lento, lo que retrasa las descargas restantes.</span><span class="sxs-lookup"><span data-stu-id="822c1-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="822c1-107">Cuando ejecute las soluciones asincrónicas que se compilan en el tutorial, puede finalizar el programa fácilmente si no quiere esperar, pero una mejor opción sería iniciar todas las descargas al mismo tiempo y dejar que las más rápidas continúen sin tener que esperar a la que se retrasa.</span><span class="sxs-lookup"><span data-stu-id="822c1-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>

<span data-ttu-id="822c1-108">El método `Task.WhenAll` se aplica a una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="822c1-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="822c1-109">La aplicación de `WhenAll` devuelve una única tarea que no está completa hasta que se completen todas las tareas de la colección.</span><span class="sxs-lookup"><span data-stu-id="822c1-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="822c1-110">La tarea parece ejecutarse en paralelo, pero no se crean subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="822c1-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="822c1-111">Las tareas se pueden completar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="822c1-111">The tasks can complete in any order.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="822c1-112">En los procedimientos siguientes se describen las extensiones para las aplicaciones asincrónicas desarrolladas en el [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="822c1-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="822c1-113">Puede desarrollar las aplicaciones completando el tutorial o descargando el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="822c1-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>
>
> <span data-ttu-id="822c1-114">Para ejecutar el ejemplo, debe tener instalado Visual Studio 2012 o una versión posterior en el equipo.</span><span class="sxs-lookup"><span data-stu-id="822c1-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="822c1-115">Para agregar Task.WhenAll a la solución GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="822c1-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>

1. <span data-ttu-id="822c1-116">Agregue el `ProcessURLAsync` método a la primera aplicación que se desarrolla en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="822c1-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="822c1-117">Si descargó el código de [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="822c1-117">If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>

    - <span data-ttu-id="822c1-118">Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que incluye el método `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="822c1-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="822c1-119">El archivo MainWindow. Xaml. VB para esta aplicación es el primer ejemplo de la sección "ejemplos de código completo desde el tutorial".</span><span class="sxs-lookup"><span data-stu-id="822c1-119">The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>

     <span data-ttu-id="822c1-120">El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `For Each` de `SumPageSizesAsync` en el tutorial original.</span><span class="sxs-lookup"><span data-stu-id="822c1-120">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="822c1-121">El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="822c1-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. <span data-ttu-id="822c1-122">Convierta en comentario o elimine el bucle `For Each` de `SumPageSizesAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="822c1-122">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```vb
    'Dim total = 0
    'For Each url In urlList

    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

    '    ' The previous line abbreviates the following two assignment statements.

    '    ' GetURLContentsAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. <span data-ttu-id="822c1-123">Cree una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="822c1-123">Create a collection of tasks.</span></span> <span data-ttu-id="822c1-124">El código siguiente define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web.</span><span class="sxs-lookup"><span data-stu-id="822c1-124">The following code defines a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="822c1-125">Las tareas se inician cuando se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="822c1-125">The tasks are started when the query is evaluated.</span></span>

     <span data-ttu-id="822c1-126">Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `urlList`.</span><span class="sxs-lookup"><span data-stu-id="822c1-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="822c1-127">Aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="822c1-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="822c1-128">`Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="822c1-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

     <span data-ttu-id="822c1-129">En el ejemplo siguiente, la expresión `Await` espera la finalización de la única tarea que devuelve `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="822c1-129">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="822c1-130">La expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado.</span><span class="sxs-lookup"><span data-stu-id="822c1-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="822c1-131">Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="822c1-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. <span data-ttu-id="822c1-132">Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de las longitudes de todos los sitios web.</span><span class="sxs-lookup"><span data-stu-id="822c1-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="822c1-133">Agregue la línea siguiente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="822c1-133">Add the following line to `SumPageSizesAsync`.</span></span>

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="822c1-134">Para agregar Task.WhenAll a la solución HttpClient.GetByteArrayAsync</span><span class="sxs-lookup"><span data-stu-id="822c1-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>

1. <span data-ttu-id="822c1-135">Agregue la siguiente versión de `ProcessURLAsync` a la segunda aplicación que se desarrolla en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="822c1-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="822c1-136">Si descargó el código de [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto de AsyncWalkthrough_HttpClient y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="822c1-136">If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.</span></span>

    - <span data-ttu-id="822c1-137">Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que usa el método `HttpClient.GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="822c1-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="822c1-138">El archivo MainWindow. Xaml. VB para esta aplicación es el segundo ejemplo de la sección "ejemplos de código completo desde el tutorial".</span><span class="sxs-lookup"><span data-stu-id="822c1-138">The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>

     <span data-ttu-id="822c1-139">El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `For Each` de `SumPageSizesAsync` en el tutorial original.</span><span class="sxs-lookup"><span data-stu-id="822c1-139">The `ProcessURLAsync` method consolidates the actions in the body of the `For Each` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="822c1-140">El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="822c1-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

     <span data-ttu-id="822c1-141">La única diferencia respecto al método `ProcessURLAsync` del procedimiento anterior es el uso de la instancia <xref:System.Net.Http.HttpClient>, `client`.</span><span class="sxs-lookup"><span data-stu-id="822c1-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. <span data-ttu-id="822c1-142">Convierta en comentario o elimine el bucle `For Each` de `SumPageSizesAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="822c1-142">Comment out or delete the `For Each` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```vb
    'Dim total = 0
    'For Each url In urlList
    '    ' GetByteArrayAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

    '    ' The following two lines can replace the previous assignment statement.
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. <span data-ttu-id="822c1-143">Define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web.</span><span class="sxs-lookup"><span data-stu-id="822c1-143">Define a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="822c1-144">Las tareas se inician cuando se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="822c1-144">The tasks are started when the query is evaluated.</span></span>

     <span data-ttu-id="822c1-145">Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `client` y `urlList`.</span><span class="sxs-lookup"><span data-stu-id="822c1-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. <span data-ttu-id="822c1-146">Después, aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="822c1-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="822c1-147">`Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="822c1-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

     <span data-ttu-id="822c1-148">En el ejemplo siguiente, la expresión `Await` espera la finalización de la única tarea que devuelve `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="822c1-148">In the following example, the `Await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="822c1-149">Cuando se completa, la expresión `Await` se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado.</span><span class="sxs-lookup"><span data-stu-id="822c1-149">When complete, the `Await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="822c1-150">Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="822c1-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. <span data-ttu-id="822c1-151">Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para obtener la suma de las longitudes de todos los sitios web.</span><span class="sxs-lookup"><span data-stu-id="822c1-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="822c1-152">Agregue la línea siguiente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="822c1-152">Add the following line to `SumPageSizesAsync`.</span></span>

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="822c1-153">Para probar las soluciones Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="822c1-153">To test the Task.WhenAll solutions</span></span>

<span data-ttu-id="822c1-154">Para cualquiera de las soluciones, presione la tecla F5 para ejecutar el programa y después haga clic en el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="822c1-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="822c1-155">La salida debe parecerse a la salida de las soluciones asincrónicas en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="822c1-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="822c1-156">Pero tenga en cuenta que los sitios web cada vez aparecen en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="822c1-156">However, notice that the websites appear in a different order each time.</span></span>

## <a name="example"></a><span data-ttu-id="822c1-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="822c1-157">Example</span></span>

<span data-ttu-id="822c1-158">El código siguiente muestra las extensiones para el proyecto que usa el método `GetURLContentsAsync` para descargar el contenido de la web.</span><span class="sxs-lookup"><span data-stu-id="822c1-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        'Dim total = 0
        'For Each url In urlList

        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

        '    ' The previous line abbreviates the following two assignment statements.

        '    ' GetURLContentsAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

    ' The actions from the foreach loop are moved to this async method.
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                ' CopyToAsync returns a Task, not a Task<T>.
                Await responseStream.CopyToAsync(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
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

## <a name="example"></a><span data-ttu-id="822c1-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="822c1-159">Example</span></span>

<span data-ttu-id="822c1-160">El código siguiente muestra las extensiones para el proyecto que usa el método `HttpClient.GetByteArrayAsync` para descargar el contenido de la web.</span><span class="sxs-lookup"><span data-stu-id="822c1-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        ''<snippet7>
        'Dim total = 0
        'For Each url In urlList
        '    ' GetByteArrayAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    '<snippet31>
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
        '    '</snippet31>

        '    ' The following two lines can replace the previous assignment statement.
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://www.msdn.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
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

## <a name="see-also"></a><span data-ttu-id="822c1-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="822c1-161">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [<span data-ttu-id="822c1-162">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="822c1-162">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
