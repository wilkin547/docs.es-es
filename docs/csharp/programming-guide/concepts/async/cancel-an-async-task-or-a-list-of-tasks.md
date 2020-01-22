---
title: Cancelar una tarea asincrónica o una lista de tareas (C#)
ms.date: 07/20/2015
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 93526f772f79e993767fd8f29087b6caf4e29468
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595721"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a><span data-ttu-id="fdd9c-102">Cancelar una tarea asincrónica o una lista de tareas (C#)</span><span class="sxs-lookup"><span data-stu-id="fdd9c-102">Cancel an async task or a list of tasks (C#)</span></span>

<span data-ttu-id="fdd9c-103">Puede configurar un botón para cancelar una aplicación asincrónica si no quiere esperar a que termine.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="fdd9c-104">Mediante los ejemplos de este tema, puede agregar un botón de cancelación a una aplicación que descargue el contenido de un sitio web o una lista de sitios web.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="fdd9c-105">En los ejemplos se usa la interfaz de usuario que se describe en [Ajustar una aplicación asincrónica (C#)](./fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="fdd9c-105">The examples use the UI that [Fine-Tuning Your Async Application (C#)](./fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="fdd9c-106">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="cancel-a-task"></a><span data-ttu-id="fdd9c-107">Cancelar una tarea</span><span class="sxs-lookup"><span data-stu-id="fdd9c-107">Cancel a task</span></span>

<span data-ttu-id="fdd9c-108">En el primer ejemplo se asocia el botón **Cancelar** a una sola tarea de descarga.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="fdd9c-109">Si elige el botón mientras la aplicación descarga contenido, se cancela la descarga.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="fdd9c-110">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdd9c-110">Download the example</span></span>

<span data-ttu-id="fdd9c-111">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="fdd9c-112">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="fdd9c-113">En la barra de menús, elija **Archivo** > **Abrir** > **Proyecto/Solución**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-113">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="fdd9c-114">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="fdd9c-115">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelATask** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="fdd9c-116">Presione la tecla **F5** para ejecutar el proyecto, o bien presione las teclas **Ctrl**+**F5** para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-116">Choose the **F5** key to run the project (or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

> [!TIP]
> <span data-ttu-id="fdd9c-117">Si no quiere descargar el proyecto, puede revisar los archivos MainWindow.xaml.cs al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-117">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="fdd9c-118">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdd9c-118">Build the example</span></span>
 <span data-ttu-id="fdd9c-119">Los cambios siguientes agregan un botón **Cancelar** a una aplicación que descarga un sitio web.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-119">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="fdd9c-120">Si no quiere descargar ni generar el ejemplo, puede revisar el producto final en la sección "Ejemplos completos" al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-120">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="fdd9c-121">Los cambios en el código se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-121">Asterisks mark the changes in the code.</span></span>

 <span data-ttu-id="fdd9c-122">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **StarterCode** como **Proyecto de inicio** en lugar de **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

 <span data-ttu-id="fdd9c-123">Luego, realice los cambios siguientes en el archivo MainWindow.xaml.cs del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-123">Then add the following changes to the MainWindow.xaml.cs file of that project.</span></span>

1. <span data-ttu-id="fdd9c-124">Declare una variable de `CancellationTokenSource`, `cts`, que esté en el ámbito de todos los métodos que acceden a ella.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-124">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```csharp
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;
    ```

2. <span data-ttu-id="fdd9c-125">Agregue el controlador de eventos siguiente para el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-125">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="fdd9c-126">El controlador de eventos usa el método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> para notificar `cts` cuando el usuario solicita la cancelación.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-126">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```csharp
    // ***Add an event handler for the Cancel button.
    private void cancelButton_Click(object sender, RoutedEventArgs e)
    {
        if (cts != null)
        {
            cts.Cancel();
        }
    }
    ```

3. <span data-ttu-id="fdd9c-127">Realice los siguientes cambios en el controlador de eventos para el botón **Iniciar**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-127">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="fdd9c-128">Cree una instancia de `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-128">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

        ```csharp
        // ***Instantiate the CancellationTokenSource.
        cts = new CancellationTokenSource();
        ```

    - <span data-ttu-id="fdd9c-129">En la llamada a `AccessTheWebAsync`, que descarga el contenido de un sitio web especificado, envíe la propiedad <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> de `cts` como un argumento.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-129">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="fdd9c-130">La propiedad `Token` propaga el mensaje si se solicita la cancelación.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-130">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="fdd9c-131">Agregue un bloque catch que muestre un mensaje si el usuario decide cancelar la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-131">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="fdd9c-132">En el código siguiente se muestran los cambios.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-132">The following code shows the changes.</span></span>

        ```csharp
        try
        {
            // ***Send a token to carry the message if cancellation is requested.
            int contentLength = await AccessTheWebAsync(cts.Token);
            resultsTextBox.Text += $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }
        // *** If cancellation is requested, an OperationCanceledException results.
        catch (OperationCanceledException)
        {
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";
        }
        catch (Exception)
        {
            resultsTextBox.Text += "\r\nDownload failed.\r\n";
        }
        ```

4. <span data-ttu-id="fdd9c-133">En `AccessTheWebAsync`, use la sobrecarga <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del método `GetAsync` en el tipo <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-133">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="fdd9c-134">Pase `ct`, el parámetro <xref:System.Threading.CancellationToken> de `AccessTheWebAsync`, como el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-134">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="fdd9c-135">El token lleva el mensaje si el usuario elige el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-135">The token carries the message if the user chooses the **Cancel** button.</span></span>

     <span data-ttu-id="fdd9c-136">En el código siguiente se muestran los cambios en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-136">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Provide a parameter for the CancellationToken.
    async Task<int> AccessTheWebAsync(CancellationToken ct)
    {
        HttpClient client = new HttpClient();

        resultsTextBox.Text += "\r\nReady to download.\r\n";

        // You might need to slow things down to have a chance to cancel.
        await Task.Delay(250);

        // GetAsync returns a Task<HttpResponseMessage>.
        // ***The ct argument carries the message if the Cancel button is chosen.
        HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        // The result of the method is the length of the downloaded website.
        return urlContents.Length;
    }
    ```

5. <span data-ttu-id="fdd9c-137">Si no lo cancela, el programa produce el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-137">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Ready to download.
    Length of the downloaded string: 158125.
    ```

     <span data-ttu-id="fdd9c-138">Si elige el botón **Cancelar** antes de que el programa termine de descargar el contenido, el programa produce el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-138">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>

    ```text
    Ready to download.
    Download canceled.
    ```

## <a name="cancel-a-list-of-tasks"></a><span data-ttu-id="fdd9c-139">Cancelar una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="fdd9c-139">Cancel a list of tasks</span></span>

<span data-ttu-id="fdd9c-140">Puede ampliar el ejemplo anterior para cancelar muchas tareas asociando la misma instancia de `CancellationTokenSource` a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-140">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="fdd9c-141">Si elige el botón **Cancelar**, cancela todas las tareas que aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-141">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="download-the-example"></a><span data-ttu-id="fdd9c-142">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdd9c-142">Download the example</span></span>

<span data-ttu-id="fdd9c-143">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-143">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="fdd9c-144">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-144">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="fdd9c-145">En la barra de menús, elija **Archivo** > **Abrir** > **Proyecto/Solución**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-145">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="fdd9c-146">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-146">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="fdd9c-147">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAListOfTasks** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-147">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="fdd9c-148">Presione la tecla **F5** para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-148">Choose the **F5** key to run the project.</span></span>

     <span data-ttu-id="fdd9c-149">Presione las teclas **Ctrl**+**F5** para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-149">Choose the **Ctrl**+**F5** keys to run the project without debugging it.</span></span>

<span data-ttu-id="fdd9c-150">Si no quiere descargar el proyecto, puede revisar los archivos MainWindow.xaml.cs al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-150">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>

### <a name="build-the-example"></a><span data-ttu-id="fdd9c-151">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdd9c-151">Build the example</span></span>

<span data-ttu-id="fdd9c-152">Para ampliar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelATask** como el **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-152">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="fdd9c-153">Agregue los siguientes cambios a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-153">Add the following changes to that project.</span></span> <span data-ttu-id="fdd9c-154">Los cambios en el programa se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-154">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="fdd9c-155">Agregue un método para crear una lista de direcciones web.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-155">Add a method to create a list of web addresses.</span></span>

    ```csharp
    // ***Add a method that creates a list of web addresses.
    private List<string> SetUpURLList()
    {
        List<string> urls = new List<string>
        {
            "https://msdn.microsoft.com",
            "https://msdn.microsoft.com/library/hh290138.aspx",
            "https://msdn.microsoft.com/library/hh290140.aspx",
            "https://msdn.microsoft.com/library/dd470362.aspx",
            "https://msdn.microsoft.com/library/aa578028.aspx",
            "https://msdn.microsoft.com/library/ms404677.aspx",
            "https://msdn.microsoft.com/library/ff730837.aspx"
        };
        return urls;
    }
    ```

2. <span data-ttu-id="fdd9c-156">Llame al método en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-156">Call the method in `AccessTheWebAsync`.</span></span>

    ```csharp
    // ***Call SetUpURLList to make a list of web addresses.
    List<string> urlList = SetUpURLList();
    ```

3. <span data-ttu-id="fdd9c-157">Agregue el siguiente bucle en `AccessTheWebAsync` para procesar cada dirección web de la lista.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-157">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```csharp
    // ***Add a loop to process the list of web addresses.
    foreach (var url in urlList)
    {
        // GetAsync returns a Task<HttpResponseMessage>.
        // Argument ct carries the message if the Cancel button is chosen.
        // ***Note that the Cancel button can cancel all remaining downloads.
        HttpResponseMessage response = await client.GetAsync(url, ct);

        // Retrieve the website contents from the HttpResponseMessage.
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

        resultsTextBox.Text +=
            $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
    }
    ```

4. <span data-ttu-id="fdd9c-158">Como `AccessTheWebAsync` muestra las duraciones, el método no tiene que devolver nada.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-158">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="fdd9c-159">Quite la instrucción Return y cambie el tipo de valor devuelto del método a <xref:System.Threading.Tasks.Task> en lugar de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-159">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```csharp
    async Task AccessTheWebAsync(CancellationToken ct)
    ```

     <span data-ttu-id="fdd9c-160">Llame al método desde `startButton_Click` mediante una instrucción en lugar de una expresión.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-160">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```csharp
    await AccessTheWebAsync(cts.Token);
    ```

5. <span data-ttu-id="fdd9c-161">Si no lo cancela, el programa produce el resultado siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-161">If you don’t cancel the program, it produces the following output.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

     <span data-ttu-id="fdd9c-162">Si elige el botón **Cancelar** antes de que se completen las descargas, la salida contiene las duraciones de las descargas completadas antes de la cancelación.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-162">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```text
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="complete-examples"></a><span data-ttu-id="fdd9c-163">Ejemplos completos</span><span class="sxs-lookup"><span data-stu-id="fdd9c-163">Complete examples</span></span>

<span data-ttu-id="fdd9c-164">Las secciones siguientes contienen el código para cada uno de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-164">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="fdd9c-165">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-165">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="fdd9c-166">Puede descargar los proyectos desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de async: Ajuste de la aplicación).</span><span class="sxs-lookup"><span data-stu-id="fdd9c-166">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="example---cancel-a-task"></a><span data-ttu-id="fdd9c-167">Ejemplo: Cancelar una tarea</span><span class="sxs-lookup"><span data-stu-id="fdd9c-167">Example - Cancel a task</span></span>

<span data-ttu-id="fdd9c-168">El código siguiente es el archivo MainWindow.xaml.cs completo del ejemplo que cancela una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-168">The following code is the complete MainWindow.xaml.cs file for the example that cancels a single task.</span></span>

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

// Add the following using directive for System.Threading.

using System.Threading;
namespace CancelATask
{
    public partial class MainWindow : Window
    {
        // ***Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // ***Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            resultsTextBox.Clear();

            try
            {
                // ***Send a token to carry the message if cancellation is requested.
                int contentLength = await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {contentLength}.\r\n";
            }
            // *** If cancellation is requested, an OperationCanceledException results.
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownload failed.\r\n";
            }

            // ***Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // ***Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // ***Provide a parameter for the CancellationToken.
        async Task<int> AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            resultsTextBox.Text += "\r\nReady to download.\r\n";

            // You might need to slow things down to have a chance to cancel.
            await Task.Delay(250);

            // GetAsync returns a Task<HttpResponseMessage>.
            // ***The ct argument carries the message if the Cancel button is chosen.
            HttpResponseMessage response = await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            // The result of the method is the length of the downloaded website.
            return urlContents.Length;
        }
    }

    // Output for a successful download:

    // Ready to download.

    // Length of the downloaded string: 158125.

    // Or, if you cancel:

    // Ready to download.

    // Download canceled.
}
```

### <a name="example---cancel-a-list-of-tasks"></a><span data-ttu-id="fdd9c-169">Ejemplo: Cancelar una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="fdd9c-169">Example - Cancel a list of tasks</span></span>

<span data-ttu-id="fdd9c-170">El código siguiente es el archivo MainWindow.xaml.cs completo del ejemplo que cancela una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="fdd9c-170">The following code is the complete MainWindow.xaml.cs file for the example that cancels a list of tasks.</span></span>

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

// Add the following using directive for System.Threading.
using System.Threading;

namespace CancelAListOfTasks
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
                // ***Small change in the display lines.
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.";
            }

            // Set the CancellationTokenSource to null when the download is complete.
            cts = null;
        }

        // Add an event handler for the Cancel button.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        // Provide a parameter for the CancellationToken.
        // ***Change the return type to Task because the method has no return statement.
        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // ***Call SetUpURLList to make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Add a loop to process the list of web addresses.
            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // ***Note that the Cancel button can cancel all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        // ***Add a method that creates a list of web addresses.
        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Output if you do not choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Length of the downloaded string: 158124.

    //Length of the downloaded string: 204890.

    //Length of the downloaded string: 175488.

    //Length of the downloaded string: 145790.

    //Downloads complete.

    // Sample output if you choose to cancel:

    //Length of the downloaded string: 35939.

    //Length of the downloaded string: 237682.

    //Length of the downloaded string: 128607.

    //Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="fdd9c-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdd9c-171">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="fdd9c-172">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="fdd9c-172">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="fdd9c-173">Ajustar una aplicación asincrónica (C#)</span><span class="sxs-lookup"><span data-stu-id="fdd9c-173">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- <span data-ttu-id="fdd9c-174">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de async: Ajuste de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="fdd9c-174">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
