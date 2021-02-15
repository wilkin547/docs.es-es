---
description: 'Más información acerca de: flujo de control en programas Async (Visual Basic)'
title: Flujo de control en programas Async
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: bf0ca6a083971cb02cfb6dff2dfcaaabd5405b36
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428251"
---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="3dba2-103">Control Flow in Async Programs (Visual Basic) (Flujo de control en programas asincrónicos [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3dba2-103">Control Flow in Async Programs (Visual Basic)</span></span>

<span data-ttu-id="3dba2-104">Puede escribir y mantener los programas asincrónicos más fácilmente usando las palabras clave `Async` y `Await`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-104">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="3dba2-105">Aun así, los resultados pueden sorprenderle si no sabe cómo funciona el programa.</span><span class="sxs-lookup"><span data-stu-id="3dba2-105">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="3dba2-106">En este tema se hace un seguimiento del flujo de control a través de un programa asincrónico simple en el que se muestra cuándo se mueve el control de un método a otro y qué información se transfiere cada vez.</span><span class="sxs-lookup"><span data-stu-id="3dba2-106">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>

> [!NOTE]
> <span data-ttu-id="3dba2-107">Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="3dba2-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>

<span data-ttu-id="3dba2-108">En general, los métodos que contienen código asincrónico se marcan con el modificador [Async](../../../language-reference/modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="3dba2-108">In general, you mark methods that contain asynchronous code with the [Async](../../../language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="3dba2-109">En un método que está marcado con un modificador Async, puede usar un operador [Await (Visual Basic)](../../../language-reference/operators/await-operator.md) para especificar dónde se detiene el método para esperar a que se complete el proceso asincrónico al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="3dba2-109">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="3dba2-110">Para obtener más información, vea [programación asincrónica con Async y Await (Visual Basic)](index.md).</span><span class="sxs-lookup"><span data-stu-id="3dba2-110">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](index.md).</span></span>

<span data-ttu-id="3dba2-111">En el ejemplo siguiente se usan métodos asincrónicos para descargar el contenido de un sitio web especificado como una cadena y mostrar la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3dba2-111">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="3dba2-112">El ejemplo contiene los dos métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dba2-112">The example contains the following two methods.</span></span>

- <span data-ttu-id="3dba2-113">`startButton_Click`, que llama a `AccessTheWebAsync` y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="3dba2-113">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>

- <span data-ttu-id="3dba2-114">`AccessTheWebAsync`, que descarga el contenido de un sitio web como una cadena y devuelve la longitud de esta.</span><span class="sxs-lookup"><span data-stu-id="3dba2-114">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="3dba2-115">`AccessTheWebAsync` usa un método <xref:System.Net.Http.HttpClient> asincrónico, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, para descargar el contenido.</span><span class="sxs-lookup"><span data-stu-id="3dba2-115">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>

<span data-ttu-id="3dba2-116">Las líneas de visualización numeradas aparecen en puntos estratégicos de todo el programa para ayudarle a entender cómo se ejecuta el programa y explicar lo que ocurre en cada punto marcado.</span><span class="sxs-lookup"><span data-stu-id="3dba2-116">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="3dba2-117">Las líneas de visualización tienen las etiquetas comprendidas entre "UNO" y "SEIS".</span><span class="sxs-lookup"><span data-stu-id="3dba2-117">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="3dba2-118">Las etiquetas representan el orden en el que el programa alcanza estas líneas de código.</span><span class="sxs-lookup"><span data-stu-id="3dba2-118">The labels represent the order in which the program reaches these lines of code.</span></span>

<span data-ttu-id="3dba2-119">En el código siguiente se muestra un esquema del programa.</span><span class="sxs-lookup"><span data-stu-id="3dba2-119">The following code shows an outline of the program.</span></span>

```vb
Class MainWindow

    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

        ' ONE
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

        ' FOUR
        Dim contentLength As Integer = Await getLengthTask

        ' SIX
        ResultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

    End Sub

    Async Function AccessTheWebAsync() As Task(Of Integer)

        ' TWO
        Dim client As HttpClient = New HttpClient()
        Dim getStringTask As Task(Of String) =
            client.GetStringAsync("https://msdn.microsoft.com")

        ' THREE
        Dim urlContents As String = Await getStringTask

        ' FIVE
        Return urlContents.Length
    End Function

End Class
```

<span data-ttu-id="3dba2-120">Cada una de las ubicaciones etiquetadas (del "UNO" al "SEIS") muestra información sobre el estado actual del programa.</span><span class="sxs-lookup"><span data-stu-id="3dba2-120">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="3dba2-121">Se produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3dba2-121">The following output is produced:</span></span>

```console
ONE:   Entering startButton_Click.
           Calling AccessTheWebAsync.

TWO:   Entering AccessTheWebAsync.
           Calling HttpClient.GetStringAsync.

THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.

FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.

FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.

SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.

Length of the downloaded string: 33946.
```

## <a name="set-up-the-program"></a><span data-ttu-id="3dba2-122">Configurar el programa</span><span class="sxs-lookup"><span data-stu-id="3dba2-122">Set Up the Program</span></span>

<span data-ttu-id="3dba2-123">Puede descargar el código que se usa en este tema desde MSDN o crearlo usted mismo.</span><span class="sxs-lookup"><span data-stu-id="3dba2-123">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>

> [!NOTE]
> <span data-ttu-id="3dba2-124">Para ejecutar el ejemplo, debe tener Visual Studio 2012 o posterior y el .NET Framework 4,5 o posterior instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3dba2-124">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>

### <a name="download-the-program"></a><span data-ttu-id="3dba2-125">Descargar el programa</span><span class="sxs-lookup"><span data-stu-id="3dba2-125">Download the Program</span></span>

<span data-ttu-id="3dba2-126">Puede descargar la aplicación para este tema en [Ejemplo de Async: Flujo de control en programas asincrónicos](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span><span class="sxs-lookup"><span data-stu-id="3dba2-126">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="3dba2-127">Con los siguientes pasos se abre y se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="3dba2-127">The following steps open and run the program.</span></span>

1. <span data-ttu-id="3dba2-128">Descomprima el archivo descargado e inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3dba2-128">Unzip the downloaded file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="3dba2-129">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-129">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>

3. <span data-ttu-id="3dba2-130">Navegue hasta la carpeta que contiene el código de ejemplo descomprimido, abra el archivo de la solución (.sln) y elija la tecla F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3dba2-130">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>

### <a name="build-the-program-yourself"></a><span data-ttu-id="3dba2-131">Compilar el programa usted mismo</span><span class="sxs-lookup"><span data-stu-id="3dba2-131">Build the Program Yourself</span></span>

<span data-ttu-id="3dba2-132">El siguiente proyecto de Windows Presentation Foundation (WPF) contiene el ejemplo de código de este tema.</span><span class="sxs-lookup"><span data-stu-id="3dba2-132">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>

<span data-ttu-id="3dba2-133">Para ejecutar el proyecto, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dba2-133">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="3dba2-134">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3dba2-134">Start Visual Studio.</span></span>

2. <span data-ttu-id="3dba2-135">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-135">On the menu bar, choose **File**, **New**, **Project**.</span></span>

    <span data-ttu-id="3dba2-136">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="3dba2-136">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="3dba2-137">En el panel **plantillas instaladas** , elija **Visual Basic** y, a continuación, elija **aplicación WPF** en la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3dba2-137">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="3dba2-138">Escriba `AsyncTracer` como el nombre del proyecto y elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-138">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>

    <span data-ttu-id="3dba2-139">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-139">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="3dba2-140">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="3dba2-140">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

    <span data-ttu-id="3dba2-141">Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-141">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="3dba2-142">En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3dba2-142">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>

    ```vb
    <Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"
        Title="Control Flow Trace" Height="350" Width="525">
        <Grid>
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>

        </Grid>
    </Window>
    ```

    <span data-ttu-id="3dba2-143">En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="3dba2-143">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>

7. <span data-ttu-id="3dba2-144">Agregue una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="3dba2-144">Add a reference for <xref:System.Net.Http>.</span></span>

8. <span data-ttu-id="3dba2-145">En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="3dba2-145">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

9. <span data-ttu-id="3dba2-146">En MainWindow. Xaml. VB, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3dba2-146">In MainWindow.xaml.vb , replace the code with the following code.</span></span>

    ```vb
    ' Add an Imports statement and a reference for System.Net.Http.
    Imports System.Net.Http

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

            ' The display lines in the example lead you through the control shifts.
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &
                "           Calling AccessTheWebAsync." & vbCrLf

            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is started." & vbCrLf &
                "           About to await getLengthTask -- no caller to return to." & vbCrLf

            Dim contentLength As Integer = Await getLengthTask

            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is finished." & vbCrLf &
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &
                "           About to display contentLength and exit." & vbCrLf

            ResultsTextBox.Text &=
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)
        End Sub

        Async Function AccessTheWebAsync() As Task(Of Integer)

            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."

            ' Declare an HttpClient object.
            Dim client As HttpClient = New HttpClient()

            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf

            ' GetStringAsync returns a Task(Of String).
            Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")

            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &
                "           Task getStringTask is started."

            ' AccessTheWebAsync can continue to work until getStringTask is awaited.

            ResultsTextBox.Text &=
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf

            ' Retrieve the website contents when task is complete.
            Dim urlContents As String = Await getStringTask

            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &
                vbCrLf & "           Task getStringTask is complete." &
                vbCrLf & "           Processing the return statement." &
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf

            Return urlContents.Length
        End Function

    End Class
    ```

10. <span data-ttu-id="3dba2-147">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="3dba2-147">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

    <span data-ttu-id="3dba2-148">Debería aparecer el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3dba2-148">The following output should appear:</span></span>

    ```console
    ONE:   Entering startButton_Click.
               Calling AccessTheWebAsync.

    TWO:   Entering AccessTheWebAsync.
               Calling HttpClient.GetStringAsync.

    THREE: Back in AccessTheWebAsync.
               Task getStringTask is started.
               About to await getStringTask & return a Task<int> to startButton_Click.

    FOUR:  Back in startButton_Click.
               Task getLengthTask is started.
               About to await getLengthTask -- no caller to return to.

    FIVE:  Back in AccessTheWebAsync.
               Task getStringTask is complete.
               Processing the return statement.
               Exiting from AccessTheWebAsync.

    SIX:   Back in startButton_Click.
               Task getLengthTask is finished.
               Result from AccessTheWebAsync is stored in contentLength.
               About to display contentLength and exit.

    Length of the downloaded string: 33946.
    ```

## <a name="trace-the-program"></a><span data-ttu-id="3dba2-149">Hacer un seguimiento del programa</span><span class="sxs-lookup"><span data-stu-id="3dba2-149">Trace the Program</span></span>

### <a name="steps-one-and-two"></a><span data-ttu-id="3dba2-150">Pasos UNO y DOS</span><span class="sxs-lookup"><span data-stu-id="3dba2-150">Steps ONE and TWO</span></span>

<span data-ttu-id="3dba2-151">Las dos primeras líneas siguen la ruta de acceso a medida que `startButton_Click` llama a `AccessTheWebAsync` y `AccessTheWebAsync` llama al método <xref:System.Net.Http.HttpClient> asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="3dba2-151">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="3dba2-152">En la siguiente imagen se describen las llamadas de método a método.</span><span class="sxs-lookup"><span data-stu-id="3dba2-152">The following image outlines the calls from method to method.</span></span>

<span data-ttu-id="3dba2-153">![Pasos UNO y DOS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace (pasos UNO y DOS)")</span><span class="sxs-lookup"><span data-stu-id="3dba2-153">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>

<span data-ttu-id="3dba2-154">El tipo de valor devuelto de `AccessTheWebAsync` y `client.GetStringAsync` es <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="3dba2-154">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="3dba2-155">Para `AccessTheWebAsync`, TResult es un entero.</span><span class="sxs-lookup"><span data-stu-id="3dba2-155">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="3dba2-156">Para `GetStringAsync`, TResult es una cadena.</span><span class="sxs-lookup"><span data-stu-id="3dba2-156">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="3dba2-157">Para obtener más información sobre los tipos de valor devueltos de métodos asincrónicos, vea [tipos de valor devuelto asincrónico (Visual Basic)](async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="3dba2-157">For more information about async method return types, see [Async Return Types (Visual Basic)](async-return-types.md).</span></span>

<span data-ttu-id="3dba2-158">Un método asincrónico de devolución de tarea devuelve una instancia de la tarea cuando el control se desplaza al llamador.</span><span class="sxs-lookup"><span data-stu-id="3dba2-158">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="3dba2-159">El control vuelve a su llamador procedente de un método asincrónico cuando se encuentra un operador `Await` en el método llamado o cuando este finaliza.</span><span class="sxs-lookup"><span data-stu-id="3dba2-159">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="3dba2-160">Las líneas de visualización que tienen las etiquetas comprendidas entre "TRES" y "SEIS" rastrean esta parte del proceso.</span><span class="sxs-lookup"><span data-stu-id="3dba2-160">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>

### <a name="step-three"></a><span data-ttu-id="3dba2-161">Paso TRES</span><span class="sxs-lookup"><span data-stu-id="3dba2-161">Step THREE</span></span>

<span data-ttu-id="3dba2-162">En `AccessTheWebAsync`, el método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> se llama para descargar el contenido de la página web de destino.</span><span class="sxs-lookup"><span data-stu-id="3dba2-162">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="3dba2-163">El control vuelve a `AccessTheWebAsync` procedente de `client.GetStringAsync` cuando se devuelve `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-163">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>

<span data-ttu-id="3dba2-164">El método `client.GetStringAsync` devuelve una tarea de la cadena que se asigna a la variable `getStringTask` en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-164">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="3dba2-165">En la siguiente línea del programa de ejemplo se muestra la llamada a `client.GetStringAsync` y la asignación.</span><span class="sxs-lookup"><span data-stu-id="3dba2-165">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>

```vb
Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")
```

<span data-ttu-id="3dba2-166">Puede considerar la tarea como una promesa de `client.GetStringAsync` de generar una cadena real.</span><span class="sxs-lookup"><span data-stu-id="3dba2-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="3dba2-167">Mientras tanto, si `AccessTheWebAsync` tiene trabajo que no depende de la cadena prometida de `client.GetStringAsync`, dicho trabajo puede continuar mientras `client.GetStringAsync` espera.</span><span class="sxs-lookup"><span data-stu-id="3dba2-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="3dba2-168">En el ejemplo, las siguientes líneas de salida, que tienen la etiqueta "TRES", representan la oportunidad de realizar un trabajo independiente</span><span class="sxs-lookup"><span data-stu-id="3dba2-168">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>

```console
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 <span data-ttu-id="3dba2-169">La siguiente instrucción suspende el progreso en `AccessTheWebAsync` cuando se espera a `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-169">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>

```vb
Dim urlContents As String = Await getStringTask
```

<span data-ttu-id="3dba2-170">En la imagen siguiente se muestra el flujo de control desde `client.GetStringAsync` hasta la asignación hasta la `getStringTask` creación de `getStringTask` a la aplicación de un operador Await.</span><span class="sxs-lookup"><span data-stu-id="3dba2-170">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>

<span data-ttu-id="3dba2-171">![Paso TRES](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace (paso TRES)")</span><span class="sxs-lookup"><span data-stu-id="3dba2-171">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>

<span data-ttu-id="3dba2-172">La expresión await suspende `AccessTheWebAsync` hasta que se devuelva `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-172">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="3dba2-173">Mientras tanto, el control vuelve al llamador de `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-173">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>

> [!NOTE]
> <span data-ttu-id="3dba2-174">Normalmente se espera la llamada a un método asincrónico de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="3dba2-174">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="3dba2-175">Por ejemplo, la siguiente asignación podría reemplazar el código anterior que crea y espera `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="3dba2-175">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`</span></span>
>
> <span data-ttu-id="3dba2-176">En este tema, el operador await se aplica más adelante para dar cabida a las líneas de salida que marcan el flujo de control a través del programa.</span><span class="sxs-lookup"><span data-stu-id="3dba2-176">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>

### <a name="step-four"></a><span data-ttu-id="3dba2-177">Paso CUATRO</span><span class="sxs-lookup"><span data-stu-id="3dba2-177">Step FOUR</span></span>

<span data-ttu-id="3dba2-178">El tipo de valor devuelto declarado de `AccessTheWebAsync` es `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-178">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="3dba2-179">Por lo tanto, cuando se suspende `AccessTheWebAsync`, devuelve una tarea de entero en `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-179">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="3dba2-180">Debe entender que la tarea devuelta no es `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-180">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="3dba2-181">La tarea devuelta es una nueva tarea de entero que representa lo que falta por hacer en el método suspendido, `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-181">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="3dba2-182">La tarea es una promesa de `AccessTheWebAsync` de generar un entero cuando finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="3dba2-182">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>

<span data-ttu-id="3dba2-183">La siguiente instrucción asigna esta tarea a la variable `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-183">The following statement assigns this task to the `getLengthTask` variable.</span></span>

```vb
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()
```

<span data-ttu-id="3dba2-184">Como en `AccessTheWebAsync`, `startButton_Click` puede continuar con el trabajo que no depende de los resultados de la tarea asincrónica (`getLengthTask`) hasta que se espere la tarea.</span><span class="sxs-lookup"><span data-stu-id="3dba2-184">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="3dba2-185">Las siguientes líneas de salida representan ese trabajo:</span><span class="sxs-lookup"><span data-stu-id="3dba2-185">The following output lines represent that work:</span></span>

```console
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

<span data-ttu-id="3dba2-186">El progreso de `startButton_Click` se suspende cuando se espera `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-186">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="3dba2-187">La siguiente instrucción de asignación suspende `startButton_Click` hasta que concluya `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-187">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>

```vb
Dim contentLength As Integer = Await getLengthTask
```

<span data-ttu-id="3dba2-188">En la siguiente ilustración, las flechas muestran el flujo de control desde la expresión await en `AccessTheWebAsync` hasta la asignación de un valor a `getLengthTask`, seguido del procesamiento normal en `startButton_Click` hasta que se espera a `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-188">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>

<span data-ttu-id="3dba2-189">![Paso CUATRO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace (paso CUATRO)")</span><span class="sxs-lookup"><span data-stu-id="3dba2-189">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>

### <a name="step-five"></a><span data-ttu-id="3dba2-190">Paso CINCO</span><span class="sxs-lookup"><span data-stu-id="3dba2-190">Step FIVE</span></span>

<span data-ttu-id="3dba2-191">Cuando `client.GetStringAsync` indica que ha finalizado, el procesamiento de `AccessTheWebAsync` sale de la suspensión y puede continuar una vez superada la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="3dba2-191">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="3dba2-192">Las siguientes líneas de salida representan la reanudación del procesamiento:</span><span class="sxs-lookup"><span data-stu-id="3dba2-192">The following lines of output represent the resumption of processing:</span></span>

```console
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

<span data-ttu-id="3dba2-193">El operando de la instrucción de devolución, `urlContents.Length`, se almacena en la tarea que devuelve `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-193">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="3dba2-194">La expresión await recupera ese valor de `getLengthTask` en `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-194">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>

<span data-ttu-id="3dba2-195">En la siguiente imagen se muestra la transferencia de control una vez concluido `client.GetStringAsync` (y `getStringTask`).</span><span class="sxs-lookup"><span data-stu-id="3dba2-195">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>

<span data-ttu-id="3dba2-196">![Paso CINCO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace (paso CINCO)")</span><span class="sxs-lookup"><span data-stu-id="3dba2-196">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>

<span data-ttu-id="3dba2-197">`AccessTheWebAsync` se ejecuta hasta el final y el control vuelve a `startButton_Click`, que espera la finalización.</span><span class="sxs-lookup"><span data-stu-id="3dba2-197">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>

### <a name="step-six"></a><span data-ttu-id="3dba2-198">Paso SEIS</span><span class="sxs-lookup"><span data-stu-id="3dba2-198">Step SIX</span></span>

<span data-ttu-id="3dba2-199">Cuando `AccessTheWebAsync` indica que ha finalizado, el procesamiento puede continuar una vez superada la instrucción await en `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-199">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="3dba2-200">De hecho, el programa no tiene nada más que hacer.</span><span class="sxs-lookup"><span data-stu-id="3dba2-200">In fact, the program has nothing more to do.</span></span>

<span data-ttu-id="3dba2-201">En las siguientes líneas de salida se representa la reanudación del procesamiento en `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="3dba2-201">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>

```console
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

<span data-ttu-id="3dba2-202">La expresión await recupera de `getLengthTask` el valor entero que es el operando de la instrucción de devolución de `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-202">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="3dba2-203">La siguiente instrucción asigna ese valor a la variable `contentLength`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-203">The following statement assigns that value to the `contentLength` variable.</span></span>

```vb
Dim contentLength As Integer = Await getLengthTask
```

<span data-ttu-id="3dba2-204">En la siguiente imagen se muestra la devolución del control de `AccessTheWebAsync` a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3dba2-204">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>

<span data-ttu-id="3dba2-205">![Paso SEIS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace (paso SEIS)")</span><span class="sxs-lookup"><span data-stu-id="3dba2-205">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>

## <a name="see-also"></a><span data-ttu-id="3dba2-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dba2-206">See also</span></span>

- [<span data-ttu-id="3dba2-207">Programación asincrónica con Async y Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dba2-207">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="3dba2-208">[Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="3dba2-208">[Async Return Types (Visual Basic)](async-return-types.md)</span></span>
- [<span data-ttu-id="3dba2-209">Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dba2-209">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="3dba2-210">Ejemplo de async: Flujo de control en programas asincrónicos (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dba2-210">Async Sample: Control Flow in Async Programs (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
