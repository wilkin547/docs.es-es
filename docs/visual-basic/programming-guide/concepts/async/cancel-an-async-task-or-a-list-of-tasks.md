---
title: Cancelar una tarea asincrónica o una lista de tareas
ms.date: 07/20/2015
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
ms.openlocfilehash: 2956582cd0c8e044fcd37ffab13686489a7c854c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347969"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a><span data-ttu-id="31bbd-102">Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31bbd-102">Cancel an Async Task or a List of Tasks (Visual Basic)</span></span>

<span data-ttu-id="31bbd-103">Puede configurar un botón para cancelar una aplicación asincrónica si no quiere esperar a que termine.</span><span class="sxs-lookup"><span data-stu-id="31bbd-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="31bbd-104">Mediante los ejemplos de este tema, puede agregar un botón de cancelación a una aplicación que descargue el contenido de un sitio web o una lista de sitios web.</span><span class="sxs-lookup"><span data-stu-id="31bbd-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>

<span data-ttu-id="31bbd-105">En los ejemplos se usa la interfaz de usuario que describe la [optimización de la aplicación asincrónica (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) .</span><span class="sxs-lookup"><span data-stu-id="31bbd-105">The examples use the UI that [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>

> [!NOTE]
> <span data-ttu-id="31bbd-106">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="31bbd-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="BKMK_CancelaTask"></a> <span data-ttu-id="31bbd-107">Cancelar una tarea</span><span class="sxs-lookup"><span data-stu-id="31bbd-107">Cancel a Task</span></span>

<span data-ttu-id="31bbd-108">En el primer ejemplo se asocia el botón **Cancelar** a una sola tarea de descarga.</span><span class="sxs-lookup"><span data-stu-id="31bbd-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="31bbd-109">Si elige el botón mientras la aplicación descarga contenido, se cancela la descarga.</span><span class="sxs-lookup"><span data-stu-id="31bbd-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="31bbd-110">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bbd-110">Downloading the Example</span></span>

<span data-ttu-id="31bbd-111">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="31bbd-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="31bbd-112">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31bbd-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="31bbd-113">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="31bbd-114">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="31bbd-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="31bbd-115">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelATask** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="31bbd-116">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="31bbd-116">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="31bbd-117">Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="31bbd-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="31bbd-118">Si no desea descargar el proyecto, puede revisar los archivos MainWindow. Xaml. VB que se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="31bbd-118">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="31bbd-119">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bbd-119">Building the Example</span></span>

<span data-ttu-id="31bbd-120">Los cambios siguientes agregan un botón **Cancelar** a una aplicación que descarga un sitio web.</span><span class="sxs-lookup"><span data-stu-id="31bbd-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="31bbd-121">Si no quiere descargar ni generar el ejemplo, puede revisar el producto final en la sección "Ejemplos completos" al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="31bbd-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="31bbd-122">Los cambios en el código se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="31bbd-122">Asterisks mark the changes in the code.</span></span>

<span data-ttu-id="31bbd-123">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **StarterCode** como **Proyecto de inicio** en lugar de **CancelATask**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>

<span data-ttu-id="31bbd-124">Después, agregue los siguientes cambios al archivo MainWindow. Xaml. VB de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="31bbd-124">Then add the following changes to the MainWindow.xaml.vb file of that project.</span></span>

1. <span data-ttu-id="31bbd-125">Declare una variable de `CancellationTokenSource`, `cts`, que esté en el ámbito de todos los métodos que acceden a ella.</span><span class="sxs-lookup"><span data-stu-id="31bbd-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>

    ```vb
    Class MainWindow

        ' ***Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. <span data-ttu-id="31bbd-126">Agregue el controlador de eventos siguiente para el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="31bbd-127">El controlador de eventos usa el método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> para notificar `cts` cuando el usuario solicita la cancelación.</span><span class="sxs-lookup"><span data-stu-id="31bbd-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> method to notify `cts` when the user requests cancellation.</span></span>

    ```vb
    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub
    ```

3. <span data-ttu-id="31bbd-128">Realice los siguientes cambios en el controlador de eventos para el botón **Iniciar**, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>

    - <span data-ttu-id="31bbd-129">Cree una instancia de `CancellationTokenSource`, `cts`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>

      ```vb
      ' ***Instantiate the CancellationTokenSource.
      cts = New CancellationTokenSource()
      ```

    - <span data-ttu-id="31bbd-130">En la llamada a `AccessTheWebAsync`, que descarga el contenido de un sitio web especificado, envíe la propiedad <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> de `cts` como un argumento.</span><span class="sxs-lookup"><span data-stu-id="31bbd-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> property of `cts` as an argument.</span></span> <span data-ttu-id="31bbd-131">La propiedad `Token` propaga el mensaje si se solicita la cancelación.</span><span class="sxs-lookup"><span data-stu-id="31bbd-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="31bbd-132">Agregue un bloque catch que muestre un mensaje si el usuario decide cancelar la operación de descarga.</span><span class="sxs-lookup"><span data-stu-id="31bbd-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="31bbd-133">En el código siguiente se muestran los cambios.</span><span class="sxs-lookup"><span data-stu-id="31bbd-133">The following code shows the changes.</span></span>

      ```vb
      Try
          ' ***Send a token to carry the message if cancellation is requested.
          Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

          resultsTextBox.Text &=
              vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

          ' *** If cancellation is requested, an OperationCanceledException results.
      Catch ex As OperationCanceledException
          resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

      Catch ex As Exception
          resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
      End Try
      ```

4. <span data-ttu-id="31bbd-134">En `AccessTheWebAsync`, use la sobrecarga <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del método `GetAsync` en el tipo <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="31bbd-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="31bbd-135">Pase `ct`, el parámetro <xref:System.Threading.CancellationToken> de `AccessTheWebAsync`, como el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="31bbd-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="31bbd-136">El token lleva el mensaje si el usuario elige el botón **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-136">The token carries the message if the user chooses the **Cancel** button.</span></span>

    <span data-ttu-id="31bbd-137">En el código siguiente se muestran los cambios en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &= vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
    ```

5. <span data-ttu-id="31bbd-138">Si no cancela el programa, se genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31bbd-138">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Ready to download.
    Length of the downloaded string: 158125.
    ```

    <span data-ttu-id="31bbd-139">Si elige el botón **Cancelar** antes de que el programa termine de descargar el contenido, el programa genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31bbd-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output:</span></span>

    ```console
    Ready to download.
    Download canceled.
    ```

## <a name="BKMK_CancelaListofTasks"></a> <span data-ttu-id="31bbd-140">Cancelar una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="31bbd-140">Cancel a List of Tasks</span></span>

<span data-ttu-id="31bbd-141">Puede ampliar el ejemplo anterior para cancelar muchas tareas asociando la misma instancia de `CancellationTokenSource` a cada tarea.</span><span class="sxs-lookup"><span data-stu-id="31bbd-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="31bbd-142">Si elige el botón **Cancelar**, cancela todas las tareas que aún no se han completado.</span><span class="sxs-lookup"><span data-stu-id="31bbd-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>

### <a name="downloading-the-example"></a><span data-ttu-id="31bbd-143">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bbd-143">Downloading the Example</span></span>

<span data-ttu-id="31bbd-144">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="31bbd-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="31bbd-145">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31bbd-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="31bbd-146">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="31bbd-147">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="31bbd-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="31bbd-148">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAListOfTasks** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="31bbd-149">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="31bbd-149">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="31bbd-150">Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="31bbd-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

 <span data-ttu-id="31bbd-151">Si no desea descargar el proyecto, puede revisar los archivos MainWindow. Xaml. VB que se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="31bbd-151">If you don't want to download the project, you can review the MainWindow.xaml.vb files at the end of this topic.</span></span>

### <a name="building-the-example"></a><span data-ttu-id="31bbd-152">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bbd-152">Building the Example</span></span>

<span data-ttu-id="31bbd-153">Para ampliar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelATask** como el **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="31bbd-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="31bbd-154">Agregue los siguientes cambios a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="31bbd-154">Add the following changes to that project.</span></span> <span data-ttu-id="31bbd-155">Los cambios en el programa se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="31bbd-155">Asterisks mark the changes in the program.</span></span>

1. <span data-ttu-id="31bbd-156">Agregue un método para crear una lista de direcciones web.</span><span class="sxs-lookup"><span data-stu-id="31bbd-156">Add a method to create a list of web addresses.</span></span>

    ```vb
    ' ***Add a method that creates a list of web addresses.
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
    ```

2. <span data-ttu-id="31bbd-157">Llame al método en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="31bbd-157">Call the method in `AccessTheWebAsync`.</span></span>

    ```vb
    ' ***Call SetUpURLList to make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()
    ```

3. <span data-ttu-id="31bbd-158">Agregue el siguiente bucle en `AccessTheWebAsync` para procesar cada dirección web de la lista.</span><span class="sxs-lookup"><span data-stu-id="31bbd-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>

    ```vb
    ' ***Add a loop to process the list of web addresses.
    For Each url In urlList
        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' Argument ct carries the message if the Cancel button is chosen.
        ' ***Note that the Cancel button can cancel all remaining downloads.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        resultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
    Next
    ```

4. <span data-ttu-id="31bbd-159">Como `AccessTheWebAsync` muestra las duraciones, el método no tiene que devolver nada.</span><span class="sxs-lookup"><span data-stu-id="31bbd-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="31bbd-160">Quite la instrucción Return y cambie el tipo de valor devuelto del método a <xref:System.Threading.Tasks.Task> en lugar de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="31bbd-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>

    ```vb
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task
    ```

    <span data-ttu-id="31bbd-161">Llame al método desde `startButton_Click` mediante una instrucción en lugar de una expresión.</span><span class="sxs-lookup"><span data-stu-id="31bbd-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>

    ```vb
    Await AccessTheWebAsync(cts.Token)
    ```

5. <span data-ttu-id="31bbd-162">Si no cancela el programa, se genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="31bbd-162">If you don’t cancel the program, it produces the following output:</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

    <span data-ttu-id="31bbd-163">Si elige el botón **Cancelar** antes de que se completen las descargas, la salida contiene las duraciones de las descargas completadas antes de la cancelación.</span><span class="sxs-lookup"><span data-stu-id="31bbd-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="BKMK_CompleteExamples"></a> <span data-ttu-id="31bbd-164">Ejemplos completos</span><span class="sxs-lookup"><span data-stu-id="31bbd-164">Complete Examples</span></span>

<span data-ttu-id="31bbd-165">Las secciones siguientes contienen el código para cada uno de los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="31bbd-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="31bbd-166">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="31bbd-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="31bbd-167">Puede descargar los proyectos en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="31bbd-167">You can download the projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

### <a name="cancel-a-task-example"></a><span data-ttu-id="31bbd-168">Ejemplo de cancelación de una tarea</span><span class="sxs-lookup"><span data-stu-id="31bbd-168">Cancel a Task Example</span></span>

<span data-ttu-id="31bbd-169">El código siguiente es el archivo MainWindow. Xaml. VB completo para el ejemplo que cancela una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="31bbd-169">The following code is the complete MainWindow.xaml.vb file for the example that cancels a single task.</span></span>

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' ***Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)
        ' ***Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            ' ***Send a token to carry the message if cancellation is requested.
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

            ' *** If cancellation is requested, an OperationCanceledException results.
        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' ***Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &=
            vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
End Class

' Output for a successful download:

' Ready to download.

' Length of the downloaded string: 158125.

' Or, if you cancel:

' Ready to download.

' Download canceled.
```

### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="31bbd-170">Ejemplo de cancelación de una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="31bbd-170">Cancel a List of Tasks Example</span></span>

<span data-ttu-id="31bbd-171">El código siguiente es el archivo MainWindow. Xaml. VB completo para el ejemplo que cancela una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="31bbd-171">The following code is the complete MainWindow.xaml.vb file for the example that cancels a list of tasks.</span></span>

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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).
            Await AccessTheWebAsync(cts.Token)
            '  ***Small change in the display lines.
            resultsTextBox.Text &= vbCrLf & "Downloads complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' ***Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' ***Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' ***Add a loop to process the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' ***Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
    End Function

    ' ***Add a method that creates a list of web addresses.
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

' Output if you do not choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Length of the downloaded string: 158124.

' Length of the downloaded string: 204890.

' Length of the downloaded string: 175488.

' Length of the downloaded string: 145790.

' Downloads complete.

'  Sample output if you choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Downloads canceled.
```

## <a name="see-also"></a><span data-ttu-id="31bbd-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="31bbd-172">See also</span></span>

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [<span data-ttu-id="31bbd-173">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31bbd-173">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
- <span data-ttu-id="31bbd-174">[Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="31bbd-174">[Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="31bbd-175">Ejemplo de async: Ajuste de la aplicación</span><span class="sxs-lookup"><span data-stu-id="31bbd-175">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
