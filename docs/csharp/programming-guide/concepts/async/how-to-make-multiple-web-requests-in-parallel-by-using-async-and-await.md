---
title: Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)
description: Obtenga información sobre cómo separar la creación de una tarea mediante el operador await en C#, en lugar de aplicarlo cuando se crea una tarea.
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: 899dfd9165d199a67a5178bb351081ee544b231f
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925168"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a><span data-ttu-id="4ae90-103">Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="4ae90-103">How to make multiple web requests in parallel by using async and await (C#)</span></span>
<span data-ttu-id="4ae90-104">En un método asincrónico, las tareas se inician en el momento de crearse.</span><span class="sxs-lookup"><span data-stu-id="4ae90-104">In an async method, tasks are started when they're created.</span></span> <span data-ttu-id="4ae90-105">El operador [await](../../../language-reference/operators/await.md) se aplica a la tarea en el momento del método en que no se puede continuar el procesamiento hasta que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="4ae90-105">The [await](../../../language-reference/operators/await.md) operator is applied to the task at the point in the method where processing can't continue until the task finishes.</span></span> <span data-ttu-id="4ae90-106">A menudo se espera una tarea en cuanto se crea, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4ae90-106">Often a task is awaited as soon as it's created, as the following example shows.</span></span>  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 <span data-ttu-id="4ae90-107">Pero puede separar la creación de la tarea de la espera si el programa tiene otro trabajo por efectuar que no dependa de la finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="4ae90-107">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn't depend on the completion of the task.</span></span>  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 <span data-ttu-id="4ae90-108">Entre el inicio de una tarea y la espera puede iniciar otras tareas.</span><span class="sxs-lookup"><span data-stu-id="4ae90-108">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="4ae90-109">Las tareas adicionales se ejecutan implícitamente en paralelo, pero no se crean subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="4ae90-109">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="4ae90-110">El programa siguiente inicia tres descargas web asincrónicas y las espera en el orden en el que se han llamado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-110">The following program starts three asynchronous web downloads and then awaits them in the order in which they're called.</span></span> <span data-ttu-id="4ae90-111">Observe que, al ejecutar el programa, las tareas no siempre finalizan en el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-111">Notice, when you run the program, that the tasks don't always finish in the order in which they're created and awaited.</span></span> <span data-ttu-id="4ae90-112">Empiezan a ejecutarse en el momento de crearse y una o más tareas podrían finalizar antes de que el método llegue a las expresiones await.</span><span class="sxs-lookup"><span data-stu-id="4ae90-112">They start to run when they're created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ae90-113">Para llevar a cabo este proyecto, debe tener instalados en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="4ae90-113">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="4ae90-114">Para ver otro ejemplo que inicia varias tareas al mismo tiempo, vea [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="4ae90-114">For another example that starts multiple tasks at the same time, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="4ae90-115">Puede descargar el código de este ejemplo en [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span><span class="sxs-lookup"><span data-stu-id="4ae90-115">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="4ae90-116">Para configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="4ae90-116">To set up the project</span></span>  
  
1. <span data-ttu-id="4ae90-117">Para configurar una aplicación WPF, lleve a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="4ae90-117">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="4ae90-118">Puede encontrar instrucciones detalladas para realizar estos pasos en [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="4ae90-118">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    - <span data-ttu-id="4ae90-119">Cree una aplicación WPF que contenga un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="4ae90-119">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="4ae90-120">Asigne al botón el nombre `startButton` y, al cuadro de texto, `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="4ae90-120">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    - <span data-ttu-id="4ae90-121">Agregue una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="4ae90-121">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    - <span data-ttu-id="4ae90-122">En el archivo MainWindow.xaml.cs, agregue una directiva `using` para `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="4ae90-122">In the MainWindow.xaml.cs file, add a `using` directive for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="4ae90-123">Para agregar el código</span><span class="sxs-lookup"><span data-stu-id="4ae90-123">To add the code</span></span>  
  
1. <span data-ttu-id="4ae90-124">En la ventana de diseño, MainWindow.xaml, haga doble clic en el botón para crear el controlador de eventos `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="4ae90-124">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2. <span data-ttu-id="4ae90-125">Copie el código siguiente y péguelo en el cuerpo de `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="4ae90-125">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     <span data-ttu-id="4ae90-126">El código llama a un método asincrónico, `CreateMultipleTasksAsync`, que dirige la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ae90-126">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3. <span data-ttu-id="4ae90-127">Agregue los siguientes métodos de soporte técnico al proyecto:</span><span class="sxs-lookup"><span data-stu-id="4ae90-127">Add the following support methods to the project:</span></span>  
  
    - <span data-ttu-id="4ae90-128">`ProcessURLAsync` usa un método <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="4ae90-128">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="4ae90-129">Luego, el método de soporte, `ProcessURLAsync`, muestra y devuelve la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4ae90-129">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    - <span data-ttu-id="4ae90-130">`DisplayResults` muestra el número de bytes de la matriz de bytes de cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4ae90-130">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="4ae90-131">En esta pantalla se muestra cuándo se ha terminado la descarga de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="4ae90-131">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="4ae90-132">Copie los métodos siguientes y péguelos después del controlador de eventos `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="4ae90-132">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    async Task<int> ProcessURLAsync(string url, HttpClient client)  
    {  
        var byteArray = await client.GetByteArrayAsync(url);  
        DisplayResults(url, byteArray);  
        return byteArray.Length;  
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
    ```  
  
4. <span data-ttu-id="4ae90-133">Por último, defina el método `CreateMultipleTasksAsync`, que lleva a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="4ae90-133">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    - <span data-ttu-id="4ae90-134">El método declara un objeto `HttpClient`, que necesita para tener acceso al método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> en `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="4ae90-134">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    - <span data-ttu-id="4ae90-135">El método crea e inicia tres tareas de tipo <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="4ae90-135">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="4ae90-136">A medida que finaliza cada tarea, `DisplayResults` muestra la dirección URL de la tarea y la longitud del contenido descargado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-136">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="4ae90-137">Dado que las tareas se ejecutan de manera asincrónica, el orden en que aparecen los resultados puede ser diferente del orden en que se han declarado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-137">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    - <span data-ttu-id="4ae90-138">El método espera la finalización de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="4ae90-138">The method awaits the completion of each task.</span></span> <span data-ttu-id="4ae90-139">Cada operador `await` suspende la ejecución de `CreateMultipleTasksAsync` hasta que finalice la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="4ae90-139">Each `await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="4ae90-140">El operador también recupera el valor devuelto de la llamada a `ProcessURLAsync` desde cada tarea finalizada.</span><span class="sxs-lookup"><span data-stu-id="4ae90-140">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    - <span data-ttu-id="4ae90-141">Una vez concluidas las tareas y recuperados los valores enteros, el método suma las longitudes de los sitios web y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-141">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="4ae90-142">Copie el método siguiente y péguelo en la solución.</span><span class="sxs-lookup"><span data-stu-id="4ae90-142">Copy the following method, and paste it into your solution.</span></span>  
  
    ```csharp  
    private async Task CreateMultipleTasksAsync()  
    {  
        // Declare an HttpClient object, and increase the buffer size. The  
        // default buffer size is 65,536.  
        HttpClient client =  
            new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
        // Create and start the tasks. As each task finishes, DisplayResults
        // displays its length.  
        Task<int> download1 =
            ProcessURLAsync("https://msdn.microsoft.com", client);  
        Task<int> download2 =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
        Task<int> download3 =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
        // Await each task.  
        int length1 = await download1;  
        int length2 = await download2;  
        int length3 = await download3;  
  
        int total = length1 + length2 + length3;  
  
        // Display the total count for the downloaded websites.  
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }  
    ```  
  
5. <span data-ttu-id="4ae90-143">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="4ae90-143">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="4ae90-144">Ejecute el programa varias veces para comprobar que las tres tareas no finalizan siempre en el mismo orden y que el orden en el que finalizan no es necesariamente el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="4ae90-144">Run the program several times to verify that the three tasks don't always finish in the same order and that the order in which they finish isn't necessarily the order in which they're created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae90-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ae90-145">Example</span></span>  
 <span data-ttu-id="4ae90-146">El código siguiente contiene el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="4ae90-146">The following code contains the full example.</span></span>  
  
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
  
// Add the following using directive, and add a reference for System.Net.Http.  
using System.Net.Http;  
  
namespace AsyncExample_MultipleTasks  
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
            await CreateMultipleTasksAsync();  
            resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
        }  
  
        private async Task CreateMultipleTasksAsync()  
        {  
            // Declare an HttpClient object, and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Create and start the tasks. As each task finishes, DisplayResults
            // displays its length.  
            Task<int> download1 =
                ProcessURLAsync("https://msdn.microsoft.com", client);  
            Task<int> download2 =
                ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
            Task<int> download3 =
                ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
            // Await each task.  
            int length1 = await download1;  
            int length2 = await download2;  
            int length3 = await download3;  
  
            int total = length1 + length2 + length3;  
  
            // Display the total count for the downloaded websites.  
            resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }  
  
        async Task<int> ProcessURLAsync(string url, HttpClient client)  
        {  
            var byteArray = await client.GetByteArrayAsync(url);  
            DisplayResults(url, byteArray);  
            return byteArray.Length;  
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
  
## <a name="see-also"></a><span data-ttu-id="4ae90-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae90-147">See also</span></span>

- [<span data-ttu-id="4ae90-148">Tutorial: Acceso a web usando Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="4ae90-148">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="4ae90-149">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="4ae90-149">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="4ae90-150">Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="4ae90-150">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
