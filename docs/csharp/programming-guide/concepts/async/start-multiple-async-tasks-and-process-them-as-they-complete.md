---
title: "Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a5339e1d2d592f3ae2a2b5c0e4e96e2bff2df64c
ms.sourcegitcommit: cec0525b2121c36198379525e69aa5388266db5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2018
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="f0df6-102">Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)</span><span class="sxs-lookup"><span data-stu-id="f0df6-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>
<span data-ttu-id="f0df6-103">Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="f0df6-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="f0df6-104">En el siguiente ejemplo se usa una consulta para crear una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="f0df6-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="f0df6-105">Cada tarea descarga el contenido de un sitio web especificado.</span><span class="sxs-lookup"><span data-stu-id="f0df6-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="f0df6-106">En cada iteración de un bucle while, una llamada awaited a `WhenAny` devuelve la tarea en la colección de tareas que termine primero su descarga.</span><span class="sxs-lookup"><span data-stu-id="f0df6-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="f0df6-107">Esa tarea se quita de la colección y se procesa.</span><span class="sxs-lookup"><span data-stu-id="f0df6-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="f0df6-108">El bucle se repite hasta que la colección no contiene más tareas.</span><span class="sxs-lookup"><span data-stu-id="f0df6-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0df6-109">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f0df6-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="f0df6-110">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0df6-110">Downloading the Example</span></span>  
 <span data-ttu-id="f0df6-111">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f0df6-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="f0df6-112">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0df6-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f0df6-113">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f0df6-114">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="f0df6-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="f0df6-115">En el **Explorador de soluciones**, abra el menú contextual del proyecto **ProcessTasksAsTheyFinish** y, después, pulse **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="f0df6-116">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0df6-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="f0df6-117">Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="f0df6-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="f0df6-118">Ejecute el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="f0df6-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="f0df6-119">Si no quiere descargar el proyecto, puede revisar el archivo MainWindow.xaml.cs al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f0df6-119">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="f0df6-120">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0df6-120">Building the Example</span></span>  
 <span data-ttu-id="f0df6-121">Este ejemplo se agrega al código que se ha desarrollado en [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Cancelar las tareas asincrónicas restantes cuando se completa una](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) y usa la misma interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f0df6-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Cancel Remaining Async Tasks after One Is Complete](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) and uses the same UI.</span></span>  
  
 <span data-ttu-id="f0df6-122">Para generar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAfterOneTask** como el **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="f0df6-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="f0df6-123">Agregue los cambios de este tema al método `AccessTheWebAsync` de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="f0df6-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="f0df6-124">Los cambios se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="f0df6-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="f0df6-125">El proyecto **CancelAfterOneTask** ya incluye una consulta que, cuando se ejecuta, crea una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="f0df6-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="f0df6-126">Cada llamada a `ProcessURLAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="f0df6-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
```csharp  
IEnumerable<Task<int>> downloadTasksQuery =  
    from url in urlList select ProcessURL(url, client, ct);  
```  
  
 <span data-ttu-id="f0df6-127">En el archivo MainWindow.xaml.cs del proyecto, realice los siguientes cambios en el método `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0df6-127">In the MainWindow.xaml.cs file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="f0df6-128">Ejecute la consulta aplicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> en lugar de <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0df6-128">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
    ```csharp  
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
    ```  
  
-   <span data-ttu-id="f0df6-129">Agregue un bucle while que realice los pasos siguientes para cada tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="f0df6-129">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="f0df6-130">Espera una llamada a `WhenAny` para identificar la primera tarea en la colección para finalizar su descarga.</span><span class="sxs-lookup"><span data-stu-id="f0df6-130">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
        ```csharp  
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
        ```  
  
    2.  <span data-ttu-id="f0df6-131">Quita la tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="f0df6-131">Removes that task from the collection.</span></span>  
  
        ```csharp  
        downloadTasks.Remove(firstFinishedTask);  
        ```  
  
    3.  <span data-ttu-id="f0df6-132">Espera `firstFinishedTask`, que se devuelve mediante una llamada a `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="f0df6-132">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="f0df6-133">La variable `firstFinishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TReturn` es un entero.</span><span class="sxs-lookup"><span data-stu-id="f0df6-133">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="f0df6-134">La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f0df6-134">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```csharp  
        int length = await firstFinishedTask;  
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
        ```  
  
 <span data-ttu-id="f0df6-135">Debe ejecutar el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="f0df6-135">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f0df6-136">Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas.</span><span class="sxs-lookup"><span data-stu-id="f0df6-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="f0df6-137">Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas.</span><span class="sxs-lookup"><span data-stu-id="f0df6-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="f0df6-138">Para más información y ejemplos, vea [Processing Tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/) (Procesar tareas a medida que se completan).</span><span class="sxs-lookup"><span data-stu-id="f0df6-138">For more information and examples, see [Processing tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="f0df6-139">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="f0df6-139">Complete Example</span></span>  
 <span data-ttu-id="f0df6-140">El código siguiente es el texto completo del archivo MainWindow.xaml.cs para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f0df6-140">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="f0df6-141">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f0df6-141">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="f0df6-142">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="f0df6-142">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="f0df6-143">Puede descargar el proyecto de [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]).</span><span class="sxs-lookup"><span data-stu-id="f0df6-143">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
  
namespace ProcessTasksAsTheyFinish  
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
            resultsTextBox.Clear();  
  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownloads complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";  
            }  
  
            cts = null;  
        }  
  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURL(url, client, ct);  
  
            // ***Use ToList to execute the query and start the tasks.   
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
  
            // ***Add a loop to process the tasks one at a time until none remain.  
            while (downloadTasks.Count > 0)  
            {  
                    // Identify the first task that completes.  
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
                    // ***Remove the selected task from the list so that you don't  
                    // process it more than once.  
                    downloadTasks.Remove(firstFinishedTask);  
  
                    // Await the completed task.  
                    int length = await firstFinishedTask;  
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
            }  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
  
        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.   
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
    }  
}  
  
// Sample Output:  
  
// Length of the download:  226093  
// Length of the download:  412588  
// Length of the download:  175490  
// Length of the download:  204890  
// Length of the download:  158855  
// Length of the download:  145790  
// Length of the download:  44908  
// Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0df6-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0df6-144">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 <span data-ttu-id="f0df6-145">[Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Ajuste de la aplicación asincrónica [C#])</span><span class="sxs-lookup"><span data-stu-id="f0df6-145">[Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)</span></span>  
 [<span data-ttu-id="f0df6-146">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="f0df6-146">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 <span data-ttu-id="f0df6-147">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: ajuste de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="f0df6-147">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
