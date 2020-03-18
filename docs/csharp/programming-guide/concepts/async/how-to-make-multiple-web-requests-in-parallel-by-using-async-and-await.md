---
title: Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: 9f7420113d4af83d7d057b772af307bd8d4bcc00
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169954"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a><span data-ttu-id="a12b8-102">Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="a12b8-102">How to make multiple web requests in parallel by using async and await (C#)</span></span>
<span data-ttu-id="a12b8-103">En un método asincrónico, las tareas se inician en el momento de crearse.</span><span class="sxs-lookup"><span data-stu-id="a12b8-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="a12b8-104">El operador [await](../../../language-reference/operators/await.md) se aplica a la tarea en el momento del método en que no se puede continuar el procesamiento hasta que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="a12b8-104">The [await](../../../language-reference/operators/await.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="a12b8-105">A menudo se espera una tarea en cuanto se crea, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a12b8-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 <span data-ttu-id="a12b8-106">Pero puede separar la creación de la tarea de la espera si el programa tiene otro trabajo por efectuar que no dependa de la finalización de la tarea.</span><span class="sxs-lookup"><span data-stu-id="a12b8-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 <span data-ttu-id="a12b8-107">Entre el inicio de una tarea y la espera puede iniciar otras tareas.</span><span class="sxs-lookup"><span data-stu-id="a12b8-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="a12b8-108">Las tareas adicionales se ejecutan implícitamente en paralelo, pero no se crean subprocesos adicionales.</span><span class="sxs-lookup"><span data-stu-id="a12b8-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="a12b8-109">El programa siguiente inicia tres descargas web asincrónicas y las espera en el orden en el que se han llamado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="a12b8-110">Observe que, al ejecutar el programa, las tareas no siempre finalizan en el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="a12b8-111">Empiezan a ejecutarse en el momento de crearse y una o más tareas podrían finalizar antes de que el método llegue a las expresiones await.</span><span class="sxs-lookup"><span data-stu-id="a12b8-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a12b8-112">Para llevar a cabo este proyecto, debe tener instalados en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a12b8-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="a12b8-113">Para ver otro ejemplo que inicia varias tareas al mismo tiempo, vea [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="a12b8-113">For another example that starts multiple tasks at the same time, see [How to extend the async walkthrough by using Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>
  
 <span data-ttu-id="a12b8-114">Puede descargar el código de este ejemplo en [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span><span class="sxs-lookup"><span data-stu-id="a12b8-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="a12b8-115">Para configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a12b8-115">To set up the project</span></span>  
  
1. <span data-ttu-id="a12b8-116">Para configurar una aplicación WPF, lleve a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="a12b8-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="a12b8-117">Encontrará instrucciones detalladas de estos pasos en [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web usando async y await [C#]).</span><span class="sxs-lookup"><span data-stu-id="a12b8-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    - <span data-ttu-id="a12b8-118">Cree una aplicación WPF que contenga un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="a12b8-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="a12b8-119">Asigne al botón el nombre `startButton` y, al cuadro de texto, `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="a12b8-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    - <span data-ttu-id="a12b8-120">Agregue una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="a12b8-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    - <span data-ttu-id="a12b8-121">En el archivo MainWindow.xaml.cs, agregue una directiva `using` para `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="a12b8-121">In the MainWindow.xaml.cs file, add a `using` directive for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="a12b8-122">Para agregar el código</span><span class="sxs-lookup"><span data-stu-id="a12b8-122">To add the code</span></span>  
  
1. <span data-ttu-id="a12b8-123">En la ventana de diseño, MainWindow.xaml, haga doble clic en el botón para crear el controlador de eventos `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a12b8-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
2. <span data-ttu-id="a12b8-124">Copie el código siguiente y péguelo en el cuerpo de `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a12b8-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.cs.</span></span>  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     <span data-ttu-id="a12b8-125">El código llama a un método asincrónico, `CreateMultipleTasksAsync`, que dirige la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a12b8-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3. <span data-ttu-id="a12b8-126">Agregue los siguientes métodos de soporte técnico al proyecto:</span><span class="sxs-lookup"><span data-stu-id="a12b8-126">Add the following support methods to the project:</span></span>  
  
    - <span data-ttu-id="a12b8-127">`ProcessURLAsync` usa un método <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="a12b8-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="a12b8-128">Luego, el método de soporte, `ProcessURLAsync`, muestra y devuelve la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="a12b8-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    - <span data-ttu-id="a12b8-129">`DisplayResults` muestra el número de bytes de la matriz de bytes de cada dirección URL.</span><span class="sxs-lookup"><span data-stu-id="a12b8-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="a12b8-130">En esta pantalla se muestra cuándo se ha terminado la descarga de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="a12b8-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="a12b8-131">Copie los métodos siguientes y péguelos después del controlador de eventos `startButton_Click` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="a12b8-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.cs.</span></span>  
  
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
  
4. <span data-ttu-id="a12b8-132">Por último, defina el método `CreateMultipleTasksAsync`, que lleva a cabo los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="a12b8-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    - <span data-ttu-id="a12b8-133">El método declara un objeto `HttpClient`, que necesita para tener acceso al método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> en `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="a12b8-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    - <span data-ttu-id="a12b8-134">El método crea e inicia tres tareas de tipo <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="a12b8-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="a12b8-135">A medida que finaliza cada tarea, `DisplayResults` muestra la dirección URL de la tarea y la longitud del contenido descargado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="a12b8-136">Dado que las tareas se ejecutan de manera asincrónica, el orden en que aparecen los resultados puede ser diferente del orden en que se han declarado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    - <span data-ttu-id="a12b8-137">El método espera la finalización de cada tarea.</span><span class="sxs-lookup"><span data-stu-id="a12b8-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="a12b8-138">Cada operador `await` suspende la ejecución de `CreateMultipleTasksAsync` hasta que finalice la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="a12b8-138">Each `await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="a12b8-139">El operador también recupera el valor devuelto de la llamada a `ProcessURLAsync` desde cada tarea finalizada.</span><span class="sxs-lookup"><span data-stu-id="a12b8-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    - <span data-ttu-id="a12b8-140">Una vez concluidas las tareas y recuperados los valores enteros, el método suma las longitudes de los sitios web y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="a12b8-141">Copie el método siguiente y péguelo en la solución.</span><span class="sxs-lookup"><span data-stu-id="a12b8-141">Copy the following method, and paste it into your solution.</span></span>  
  
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
  
5. <span data-ttu-id="a12b8-142">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="a12b8-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="a12b8-143">Ejecute el programa varias veces para comprobar que las tres tareas no finalizan siempre en el mismo orden y que el orden en el que finalizan no es necesariamente el orden en que se han creado y esperado.</span><span class="sxs-lookup"><span data-stu-id="a12b8-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a12b8-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a12b8-144">Example</span></span>  
 <span data-ttu-id="a12b8-145">El código siguiente contiene el ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="a12b8-145">The following code contains the full example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a12b8-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="a12b8-146">See also</span></span>

- <span data-ttu-id="a12b8-147">[Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a web usando Async y Await [C#])</span><span class="sxs-lookup"><span data-stu-id="a12b8-147">[Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
- <span data-ttu-id="a12b8-148">[Asynchronous Programming with async and await (C#)](./index.md) (Programación asincrónica con async y await (C#))</span><span class="sxs-lookup"><span data-stu-id="a12b8-148">[Asynchronous Programming with async and await (C#)](./index.md)</span></span>
- [<span data-ttu-id="a12b8-149">Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="a12b8-149">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
