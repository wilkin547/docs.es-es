---
title: "Cancelar las tareas asincrónicas restantes cuando se completa una (C#)"
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
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 23e68327cfc52845b203acdf5f69253de746d566
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a><span data-ttu-id="a7dfb-102">Cancelar las tareas asincrónicas restantes cuando se completa una (C#)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-102">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>
<span data-ttu-id="a7dfb-103">Mediante el método <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> junto con <xref:System.Threading.CancellationToken>, puede cancelar todas las tareas restantes cuando se completa una tarea.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="a7dfb-104">El método `WhenAny` toma un argumento que es una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="a7dfb-105">El método inicia todas las tareas y devuelve una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="a7dfb-106">La tarea se completa cuando se complete cualquier tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="a7dfb-107">En este ejemplo se muestra cómo usar un token de cancelación junto con `WhenAny` para retener la primera tarea para finalizar de la colección de tareas y cancelar las tareas restantes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="a7dfb-108">Cada tarea descarga el contenido de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="a7dfb-109">En el ejemplo se muestra la longitud del contenido de la primera descarga completa y se cancelan las otras descargas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7dfb-110">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="a7dfb-111">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7dfb-111">Downloading the Example</span></span>  
 <span data-ttu-id="a7dfb-112">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="a7dfb-113">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a7dfb-114">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="a7dfb-115">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="a7dfb-116">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterOneTask** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="a7dfb-117">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="a7dfb-118">Presione las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="a7dfb-119">Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="a7dfb-120">Si no quiere descargar el proyecto, puede revisar el archivo MainWindow.xaml.cs al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-120">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="a7dfb-121">Compilación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7dfb-121">Building the Example</span></span>  
 <span data-ttu-id="a7dfb-122">El ejemplo de este tema se incorpora al proyecto desarrollado en [Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) (Cancelar una tarea asincrónica o una lista de tareas [C#]) para cancelar una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="a7dfb-123">En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="a7dfb-124">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="a7dfb-125">Agregue los cambios de este tema a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="a7dfb-126">En el archivo MainWindow.xaml.cs del proyecto **CancelAListOfTasks**, inicie la transición moviendo los pasos de procesamiento para cada sitio web desde el bucle en `AccessTheWebAsync` al siguiente método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-126">In the MainWindow.xaml.cs file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```csharp  
/ ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.   
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 <span data-ttu-id="a7dfb-127">En `AccessTheWebAsync`, este ejemplo usa una consulta, el método <xref:System.Linq.Enumerable.ToArray%2A> y el método `WhenAny` para crear e iniciar una matriz de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="a7dfb-128">La aplicación de `WhenAny` a la matriz devuelve una única tarea que, cuando se espera, se evalúa como la primera tarea que llega a la finalización de la matriz de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="a7dfb-129">Realice los siguientes cambios en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="a7dfb-130">Los asteriscos marcan los cambios en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="a7dfb-131">Convierta en comentario o elimine el bucle.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="a7dfb-132">Cree una consulta que, cuando se ejecute, genere una colección de tareas genéricas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="a7dfb-133">Cada llamada a `ProcessURLAsync` devuelve un <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3.  <span data-ttu-id="a7dfb-134">Llame a `ToArray` para ejecutar la consulta e iniciar las tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-134">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="a7dfb-135">La aplicación del método `WhenAny` en el paso siguiente ejecutaría la consulta e iniciaría las tareas sin usar `ToArray`, pero es posible que otros métodos no lo hagan.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-135">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="a7dfb-136">La práctica más segura es forzar explícitamente la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-136">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.   
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4.  <span data-ttu-id="a7dfb-137">Llame a `WhenAny` en la colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-137">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="a7dfb-138">`WhenAny` devuelve una `Task(Of Task(Of Integer))` o `Task<Task<int>>`.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-138">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="a7dfb-139">Es decir, `WhenAny` devuelve una tarea que se evalúa como una única `Task(Of Integer)` o `Task<int>` cuando se espera.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-139">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="a7dfb-140">Esa única tarea es la primera tarea de la colección en finalizar.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-140">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="a7dfb-141">La tarea que finalizó primero se asigna a `firstFinishedTask`.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-141">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="a7dfb-142">El tipo de `firstFinishedTask` es <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero, ya que es el tipo de valor devuelto de `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-142">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes   
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5.  <span data-ttu-id="a7dfb-143">En este ejemplo, solo le interesa la tarea que finaliza primero.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-143">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="a7dfb-144">Por lo tanto, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> para cancelar las tareas restantes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-144">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> to cancel the remaining tasks.</span></span>  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6.  <span data-ttu-id="a7dfb-145">Por último, espere a `firstFinishedTask` para recuperar la longitud del contenido descargado.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-145">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
    ```  
  
 <span data-ttu-id="a7dfb-146">Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-146">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="a7dfb-147">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="a7dfb-147">Complete Example</span></span>  
 <span data-ttu-id="a7dfb-148">El código siguiente es el archivo MainWindow.xaml.cs completo para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-148">The following code is the complete MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="a7dfb-149">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-149">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="a7dfb-150">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="a7dfb-150">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="a7dfb-151">Puede descargar el proyecto de [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="a7dfb-151">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive.  
using System.Threading;  
  
namespace CancelAfterOneTask  
{  
    public partial class MainWindow : Window  
    {  
        // Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.   
            //    // Argument ct carries the message if the Cancel button is chosen.   
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        String.Format("\r\nLength of the downloaded string: {0}.\r\n", urlContents.Length);  
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.   
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes   
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.   
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.   
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7dfb-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7dfb-152">See Also</span></span>  
 <span data-ttu-id="a7dfb-153"><xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="a7dfb-153"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
 <span data-ttu-id="a7dfb-154">[Ajustar una aplicación asincrónica (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="a7dfb-154">[Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
 <span data-ttu-id="a7dfb-155">[Programación asincrónica con async y await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7dfb-155">[Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
 <span data-ttu-id="a7dfb-156">[Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Ejemplo asincrónico: Ajustar la aplicación)</span><span class="sxs-lookup"><span data-stu-id="a7dfb-156">[Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>

