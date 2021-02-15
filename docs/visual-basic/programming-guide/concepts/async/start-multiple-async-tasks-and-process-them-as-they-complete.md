---
description: 'Más información acerca de: iniciar varias tareas asincrónicas y procesarlas a medida que se completan (Visual Basic)'
title: Iniciar varias tareas asincrónicas y procesarlas a medida que se completan
ms.date: 07/20/2015
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
ms.openlocfilehash: 5053bb55acaa058c551ad5f4169ef93c773fc1ab
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474270"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="1f05a-103">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic) (Inicio de varias tareas asincrónicas y cómo procesarlas a medida que se completan [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="1f05a-103">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>

<span data-ttu-id="1f05a-104">Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="1f05a-104">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="1f05a-105">En el siguiente ejemplo se usa una consulta para crear una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="1f05a-105">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="1f05a-106">Cada tarea descarga el contenido de un sitio web especificado.</span><span class="sxs-lookup"><span data-stu-id="1f05a-106">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="1f05a-107">En cada iteración de un bucle while, una llamada awaited a `WhenAny` devuelve la tarea en la colección de tareas que termine primero su descarga.</span><span class="sxs-lookup"><span data-stu-id="1f05a-107">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="1f05a-108">Esa tarea se quita de la colección y se procesa.</span><span class="sxs-lookup"><span data-stu-id="1f05a-108">That task is removed from the collection and processed.</span></span> <span data-ttu-id="1f05a-109">El bucle se repite hasta que la colección no contiene más tareas.</span><span class="sxs-lookup"><span data-stu-id="1f05a-109">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f05a-110">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1f05a-110">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="1f05a-111">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f05a-111">Downloading the Example</span></span>  

 <span data-ttu-id="1f05a-112">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1f05a-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1. <span data-ttu-id="1f05a-113">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f05a-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2. <span data-ttu-id="1f05a-114">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="1f05a-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3. <span data-ttu-id="1f05a-115">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="1f05a-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4. <span data-ttu-id="1f05a-116">En el **Explorador de soluciones**, abra el menú contextual del proyecto **ProcessTasksAsTheyFinish** y, después, pulse **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="1f05a-116">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="1f05a-117">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f05a-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="1f05a-118">Presione las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="1f05a-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6. <span data-ttu-id="1f05a-119">Ejecute el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="1f05a-119">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="1f05a-120">Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="1f05a-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="1f05a-121">Compilación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f05a-121">Building the Example</span></span>  

 <span data-ttu-id="1f05a-122">En este ejemplo se agrega al código que [se ha desarrollado en cancelar las tareas asincrónicas restantes una vez que se ha completado una (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) y se usa la misma interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="1f05a-122">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="1f05a-123">Para generar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAfterOneTask** como el **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="1f05a-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="1f05a-124">Agregue los cambios de este tema al método `AccessTheWebAsync` de ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="1f05a-124">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="1f05a-125">Los cambios se marcan con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="1f05a-125">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="1f05a-126">El proyecto **CancelAfterOneTask** ya incluye una consulta que, cuando se ejecuta, crea una colección de tareas.</span><span class="sxs-lookup"><span data-stu-id="1f05a-126">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="1f05a-127">Cada llamada a `ProcessURLAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.</span><span class="sxs-lookup"><span data-stu-id="1f05a-127">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
```vb  
Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
    From url In urlList Select ProcessURLAsync(url, client, ct)  
```  
  
 <span data-ttu-id="1f05a-128">En el archivo MainWindow. Xaml. VB del proyecto, realice los cambios siguientes en el `AccessTheWebAsync` método.</span><span class="sxs-lookup"><span data-stu-id="1f05a-128">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
- <span data-ttu-id="1f05a-129">Ejecute la consulta aplicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> en lugar de <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f05a-129">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
    ```vb  
    Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
    ```  
  
- <span data-ttu-id="1f05a-130">Agregue un bucle while que realice los pasos siguientes para cada tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="1f05a-130">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1. <span data-ttu-id="1f05a-131">Espera una llamada a `WhenAny` para identificar la primera tarea en la colección para finalizar su descarga.</span><span class="sxs-lookup"><span data-stu-id="1f05a-131">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
        ```vb  
        Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
        ```  
  
    2. <span data-ttu-id="1f05a-132">Quita la tarea de la colección.</span><span class="sxs-lookup"><span data-stu-id="1f05a-132">Removes that task from the collection.</span></span>  
  
        ```vb  
        downloadTasks.Remove(finishedTask)  
        ```  
  
    3. <span data-ttu-id="1f05a-133">Espera `finishedTask`, que se devuelve mediante una llamada a `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="1f05a-133">Awaits `finishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="1f05a-134">La variable `finishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TReturn` es un entero.</span><span class="sxs-lookup"><span data-stu-id="1f05a-134">The `finishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="1f05a-135">La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1f05a-135">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await finishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="1f05a-136">Debe ejecutar el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="1f05a-136">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="1f05a-137">Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas.</span><span class="sxs-lookup"><span data-stu-id="1f05a-137">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="1f05a-138">Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas.</span><span class="sxs-lookup"><span data-stu-id="1f05a-138">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="1f05a-139">Para obtener más información y ejemplos, consulte [procesamiento de tareas a medida que se completan](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span><span class="sxs-lookup"><span data-stu-id="1f05a-139">For more information and examples, see [Processing Tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="1f05a-140">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="1f05a-140">Complete Example</span></span>  

 <span data-ttu-id="1f05a-141">El código siguiente es el texto completo del archivo MainWindow.xaml.vb para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f05a-141">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="1f05a-142">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1f05a-142">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="1f05a-143">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="1f05a-143">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="1f05a-144">Puede descargar el proyecto desde [Async Sample: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="1f05a-144">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
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
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(finishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await finishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
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
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f05a-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f05a-145">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- <span data-ttu-id="1f05a-146">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="1f05a-146">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="1f05a-147">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f05a-147">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="1f05a-148">Ejemplo de async: Ajuste de la aplicación</span><span class="sxs-lookup"><span data-stu-id="1f05a-148">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
