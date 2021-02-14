---
description: Más información acerca de cómo cancelar tareas asincrónicas después de un período de tiempo (Visual Basic)
title: Cancelar tareas asincrónicas tras un período de tiempo
ms.date: 07/20/2015
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
ms.openlocfilehash: fa1711017128dd32f29adfd87a540676371d02cf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100431638"
---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a><span data-ttu-id="9691c-103">Cancelación de tareas asincrónicas tras un período de tiempo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9691c-103">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>

<span data-ttu-id="9691c-104">Puede cancelar una operación asincrónica después de un período de tiempo con el método <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> si no quiere esperar a que finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="9691c-104">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="9691c-105">Este método programa la cancelación de las tareas asociadas que no se completen en el período de tiempo designado por la expresión `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="9691c-105">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="9691c-106">Este ejemplo se agrega al código que se desarrolla en [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios web y mostrar la longitud del contenido de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9691c-106">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="9691c-107">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9691c-107">To run the examples, you must have Visual Studio 2012 or later and the .NET Framework 4.5 or later installed on your computer.</span></span>

## <a name="downloading-the-example"></a><span data-ttu-id="9691c-108">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9691c-108">Downloading the Example</span></span>

<span data-ttu-id="9691c-109">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9691c-109">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="9691c-110">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9691c-110">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="9691c-111">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="9691c-111">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="9691c-112">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="9691c-112">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>

4. <span data-ttu-id="9691c-113">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterTime** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="9691c-113">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="9691c-114">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9691c-114">Choose the F5 key to run the project.</span></span>

     <span data-ttu-id="9691c-115">Presione las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.</span><span class="sxs-lookup"><span data-stu-id="9691c-115">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>

6. <span data-ttu-id="9691c-116">Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web.</span><span class="sxs-lookup"><span data-stu-id="9691c-116">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

 <span data-ttu-id="9691c-117">Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9691c-117">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>

## <a name="building-the-example"></a><span data-ttu-id="9691c-118">Compilación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="9691c-118">Building the Example</span></span>

<span data-ttu-id="9691c-119">El ejemplo de este tema se agrega al proyecto que se desarrolla en [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) para cancelar una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="9691c-119">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="9691c-120">En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9691c-120">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="9691c-121">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="9691c-121">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="9691c-122">Agregue los cambios de este tema a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="9691c-122">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="9691c-123">Para especificar un tiempo máximo antes de que las tareas se marquen como canceladas, agregue una llamada a `CancelAfter` en `startButton_Click`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9691c-123">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="9691c-124">La adición se marca con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="9691c-124">The addition is marked with asterisks.</span></span>

```vb
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

    ' Instantiate the CancellationTokenSource.
    cts = New CancellationTokenSource()

    resultsTextBox.Clear()

    Try
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        ' can adjust the time.)
        cts.CancelAfter(2500)

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
```

<span data-ttu-id="9691c-125">Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web.</span><span class="sxs-lookup"><span data-stu-id="9691c-125">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="9691c-126">La siguiente salida es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9691c-126">The following output is a sample:</span></span>

```console
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="9691c-127">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="9691c-127">Complete Example</span></span>

<span data-ttu-id="9691c-128">El código siguiente es el texto completo del archivo MainWindow.xaml.vb para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9691c-128">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="9691c-129">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9691c-129">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="9691c-130">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="9691c-130">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="9691c-131">Puede descargar el proyecto desde [Async Sample: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="9691c-131">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
            ' can adjust the time.)
            cts.CancelAfter(2500)

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

        ' Process each element in the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
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

' Length of the downloaded string: 35990.

' Length of the downloaded string: 407399.

' Length of the downloaded string: 226091.

' Downloads canceled.
```

## <a name="see-also"></a><span data-ttu-id="9691c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9691c-132">See also</span></span>

- [<span data-ttu-id="9691c-133">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9691c-133">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="9691c-134">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9691c-134">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- <span data-ttu-id="9691c-135">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) (Cancelación de una tarea asincrónica o de una lista de tareas [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="9691c-135">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md)</span></span>
- <span data-ttu-id="9691c-136">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="9691c-136">[Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md)</span></span>
- [<span data-ttu-id="9691c-137">Ejemplo de async: Ajuste de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9691c-137">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
