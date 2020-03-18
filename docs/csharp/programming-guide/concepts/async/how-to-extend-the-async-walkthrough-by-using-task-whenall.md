---
title: Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)
ms.date: 07/20/2015
ms.assetid: f6927ef2-dc6c-43f8-bc82-bbeac42de423
ms.openlocfilehash: afd7dda4e876b7faa54ae4a8e62d640d2b9aaf07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73970033"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-c"></a><span data-ttu-id="2591b-102">Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="2591b-102">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>

<span data-ttu-id="2591b-103">El rendimiento de la solución asincrónica de [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: acceso a la web con async y await [C#]) se puede mejorar con el método <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2591b-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2591b-104">Este método espera de forma asincrónica varias operaciones asincrónicas, que se representan como una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="2591b-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>

<span data-ttu-id="2591b-105">Es posible que en el tutorial observara que los sitios web se descargan a distintas velocidades.</span><span class="sxs-lookup"><span data-stu-id="2591b-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="2591b-106">A veces uno de los sitios web es muy lento, lo que retrasa las descargas restantes.</span><span class="sxs-lookup"><span data-stu-id="2591b-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="2591b-107">Cuando ejecute las soluciones asincrónicas que se compilan en el tutorial, puede finalizar el programa fácilmente si no quiere esperar, pero una mejor opción sería iniciar todas las descargas al mismo tiempo y dejar que las más rápidas continúen sin tener que esperar a la que se retrasa.</span><span class="sxs-lookup"><span data-stu-id="2591b-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>

<span data-ttu-id="2591b-108">El método `Task.WhenAll` se aplica a una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="2591b-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="2591b-109">La aplicación de `WhenAll` devuelve una única tarea que no está completa hasta que se completen todas las tareas de la colección.</span><span class="sxs-lookup"><span data-stu-id="2591b-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="2591b-110">La tarea parece ejecutarse en paralelo, pero no se crean subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="2591b-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="2591b-111">Las tareas se pueden completar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="2591b-111">The tasks can complete in any order.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2591b-112">Los procedimientos siguientes describen las extensiones para las aplicaciones asincrónicas que se desarrollan en [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web con async y await [C#]).</span><span class="sxs-lookup"><span data-stu-id="2591b-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="2591b-113">Puede desarrollar las aplicaciones completando el tutorial o descargando el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="2591b-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>
>
> <span data-ttu-id="2591b-114">Para ejecutar el ejemplo, debe tener instalado Visual Studio 2012 o una versión posterior en el equipo.</span><span class="sxs-lookup"><span data-stu-id="2591b-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="2591b-115">Para agregar Task.WhenAll a la solución GetURLContentsAsync</span><span class="sxs-lookup"><span data-stu-id="2591b-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>

1. <span data-ttu-id="2591b-116">Agregue el método `ProcessURLAsync` a la primera aplicación que se desarrolla en [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web con async y await [C#]).</span><span class="sxs-lookup"><span data-stu-id="2591b-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="2591b-117">Si descargó el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough y, después, agregue `ProcessURLAsync` al archivo MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="2591b-117">If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="2591b-118">Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que incluye el método `GetURLContentsAsync`.</span><span class="sxs-lookup"><span data-stu-id="2591b-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="2591b-119">El archivo MainWindow.xaml.cs para esta aplicación es el primer ejemplo en la sección "Ejemplos de código completados desde el tutorial".</span><span class="sxs-lookup"><span data-stu-id="2591b-119">The MainWindow.xaml.cs file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="2591b-120">El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `foreach` de `SumPageSizesAsync` en el tutorial original.</span><span class="sxs-lookup"><span data-stu-id="2591b-120">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="2591b-121">El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="2591b-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    ```csharp
    private async Task<int> ProcessURLAsync(string url)
    {
        var byteArray = await GetURLContentsAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="2591b-122">Convierta en comentario o elimine el bucle `foreach` de `SumPageSizesAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2591b-122">Comment out or delete the `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    byte[] urlContents = await GetURLContentsAsync(url);

    //    // The previous line abbreviates the following two assignment statements.
    //    // GetURLContentsAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //    //byte[] urlContents = await getContentsTask;

    //    DisplayResults(url, urlContents);

    //    // Update the total.
    //    total += urlContents.Length;
    //}
    ```

3. <span data-ttu-id="2591b-123">Cree una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="2591b-123">Create a collection of tasks.</span></span> <span data-ttu-id="2591b-124">El código siguiente define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web.</span><span class="sxs-lookup"><span data-stu-id="2591b-124">The following code defines a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="2591b-125">Las tareas se inician cuando se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="2591b-125">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="2591b-126">Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `urlList`.</span><span class="sxs-lookup"><span data-stu-id="2591b-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="2591b-127">Aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="2591b-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="2591b-128">`Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="2591b-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="2591b-129">En el ejemplo siguiente, la expresión `await` espera la finalización de la única tarea que devuelve `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="2591b-129">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="2591b-130">La expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado.</span><span class="sxs-lookup"><span data-stu-id="2591b-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="2591b-131">Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2591b-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="2591b-132">Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de las longitudes de todos los sitios web.</span><span class="sxs-lookup"><span data-stu-id="2591b-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="2591b-133">Agregue la línea siguiente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2591b-133">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="2591b-134">Para agregar Task.WhenAll a la solución HttpClient.GetByteArrayAsync</span><span class="sxs-lookup"><span data-stu-id="2591b-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>

1. <span data-ttu-id="2591b-135">Agregue la siguiente versión de `ProcessURLAsync` a la segunda aplicación que se desarrolla en [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web con async y await [C#]).</span><span class="sxs-lookup"><span data-stu-id="2591b-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="2591b-136">Si descargó el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough_HttpClient y, después, agregue `ProcessURLAsync` al archivo MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="2591b-136">If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="2591b-137">Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que usa el método `HttpClient.GetByteArrayAsync`.</span><span class="sxs-lookup"><span data-stu-id="2591b-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="2591b-138">El archivo MainWindow.xaml.cs para esta aplicación es el segundo ejemplo en la sección "Ejemplos de código completados desde el tutorial".</span><span class="sxs-lookup"><span data-stu-id="2591b-138">The MainWindow.xaml.cs file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="2591b-139">El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `foreach` de `SumPageSizesAsync` en el tutorial original.</span><span class="sxs-lookup"><span data-stu-id="2591b-139">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="2591b-140">El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="2591b-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    <span data-ttu-id="2591b-141">La única diferencia respecto al método `ProcessURLAsync` del procedimiento anterior es el uso de la instancia <xref:System.Net.Http.HttpClient>, `client`.</span><span class="sxs-lookup"><span data-stu-id="2591b-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>

    ```csharp
    async Task<int> ProcessURLAsync(string url, HttpClient client)
    {
        byte[] byteArray = await client.GetByteArrayAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="2591b-142">Convierta en comentario o elimine el bucle `For Each` o `foreach` de `SumPageSizesAsync`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2591b-142">Comment out or delete the `For Each` or `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    // GetByteArrayAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    byte[] urlContent = await client.GetByteArrayAsync(url);

    //    // The previous line abbreviates the following two assignment
    //    // statements.
    //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
    //    byte[] urlContent = await getContentTask;

    //    DisplayResults(url, urlContent);

    //    // Update the total.
    //    total += urlContent.Length;
    //}
    ```

3. <span data-ttu-id="2591b-143">Define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web.</span><span class="sxs-lookup"><span data-stu-id="2591b-143">Define a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="2591b-144">Las tareas se inician cuando se evalúa la consulta.</span><span class="sxs-lookup"><span data-stu-id="2591b-144">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="2591b-145">Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `client` y `urlList`.</span><span class="sxs-lookup"><span data-stu-id="2591b-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url, client);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="2591b-146">Después, aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="2591b-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="2591b-147">`Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="2591b-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="2591b-148">En el ejemplo siguiente, la expresión `await` espera la finalización de la única tarea que devuelve `WhenAll`.</span><span class="sxs-lookup"><span data-stu-id="2591b-148">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="2591b-149">Cuando se completa, la expresión `await` se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado.</span><span class="sxs-lookup"><span data-stu-id="2591b-149">When complete, the `await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="2591b-150">Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2591b-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="2591b-151">Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para obtener la suma de las longitudes de todos los sitios web.</span><span class="sxs-lookup"><span data-stu-id="2591b-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="2591b-152">Agregue la línea siguiente a `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2591b-152">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="2591b-153">Para probar las soluciones Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="2591b-153">To test the Task.WhenAll solutions</span></span>

- <span data-ttu-id="2591b-154">Para cualquiera de las soluciones, presione la tecla F5 para ejecutar el programa y después haga clic en el botón **Start**.</span><span class="sxs-lookup"><span data-stu-id="2591b-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="2591b-155">El resultado debe ser similar al de las soluciones asincrónicas en [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: acceso a la web con async y await [C#]).</span><span class="sxs-lookup"><span data-stu-id="2591b-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="2591b-156">Pero tenga en cuenta que los sitios web cada vez aparecen en un orden diferente.</span><span class="sxs-lookup"><span data-stu-id="2591b-156">However, notice that the websites appear in a different order each time.</span></span>

## <a name="example"></a><span data-ttu-id="2591b-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2591b-157">Example</span></span>

<span data-ttu-id="2591b-158">El código siguiente muestra las extensiones para el proyecto que usa el método `GetURLContentsAsync` para descargar el contenido de la web.</span><span class="sxs-lookup"><span data-stu-id="2591b-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Two-step async call.
            Task sumTask = SumPageSizesAsync();
            await sumTask;

            // One-step async call.
            //await SumPageSizesAsync();

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    byte[] urlContents = await GetURLContentsAsync(url);

            //    // The previous line abbreviates the following two assignment statements.
            //    // GetURLContentsAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
            //    //byte[] urlContents = await getContentsTask;

            //    DisplayResults(url, urlContents);

            //    // Update the total.
            //    total += urlContents.Length;
            //}

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        private async Task<int> ProcessURLAsync(string url)
        {
            var byteArray = await GetURLContentsAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    await responseStream.CopyToAsync(content);
                }
            }

            // Return the result as a byte array.
            return content.ToArray();

        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="2591b-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2591b-159">Example</span></span>

<span data-ttu-id="2591b-160">El código siguiente muestra las extensiones para el proyecto que usa el método `HttpClient.GetByteArrayAsync` para descargar el contenido de la web.</span><span class="sxs-lookup"><span data-stu-id="2591b-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_HttpClient_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client = new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url, client);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    // GetByteArrayAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    byte[] urlContent = await client.GetByteArrayAsync(url);

            //    // The previous line abbreviates the following two assignment
            //    // statements.
            //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
            //    byte[] urlContent = await getContentTask;

            //    DisplayResults(url, urlContent);

            //    // Update the total.
            //    total += urlContent.Length;
            //}

            // Display the total count for all of the web addresses.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
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
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        async Task<int> ProcessURLAsync(string url, HttpClient client)
        {
            byte[] byteArray = await client.GetByteArrayAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each web site. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2591b-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="2591b-161">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- <span data-ttu-id="2591b-162">[Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a web usando Async y Await [C#])</span><span class="sxs-lookup"><span data-stu-id="2591b-162">[Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
