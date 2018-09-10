---
title: Controlar el flujo en los programas asincrónicos (C#)
ms.date: 07/20/2015
ms.assetid: fc92b08b-fe1d-4d07-84ab-5192fafe06bb
ms.openlocfilehash: b05bfbd231745caf9e8b6031ce8e063469d8898b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502507"
---
# <a name="control-flow-in-async-programs-c"></a><span data-ttu-id="3c1ab-102">Controlar el flujo en los programas asincrónicos (C#)</span><span class="sxs-lookup"><span data-stu-id="3c1ab-102">Control Flow in Async Programs (C#)</span></span>
<span data-ttu-id="3c1ab-103">Puede escribir y mantener los programas asincrónicos más fácilmente usando las palabras clave `async` y `await`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-103">You can write and maintain asynchronous programs more easily by using the `async` and `await` keywords.</span></span> <span data-ttu-id="3c1ab-104">Aun así, los resultados pueden sorprenderle si no sabe cómo funciona el programa.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="3c1ab-105">En este tema se hace un seguimiento del flujo de control a través de un programa asincrónico simple en el que se muestra cuándo se mueve el control de un método a otro y qué información se transfiere cada vez.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c1ab-106">Las palabras clave `async` y `await` se incluyeron en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-106">The `async` and `await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="3c1ab-107">En general, los métodos que contienen código asincrónico se marcan con el modificador [async (C#)](../../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="3c1ab-107">In general, you mark methods that contain asynchronous code with the [async (C#)](../../../../csharp/language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="3c1ab-108">En un método que está marcado con un modificador async, puede usar un operador [await (C#)](../../../../csharp/language-reference/keywords/await.md) para especificar dónde se para el método para esperar a que concluya un proceso asincrónico al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-108">In a method that's marked with an async modifier, you can use an [await (C#)](../../../../csharp/language-reference/keywords/await.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="3c1ab-109">Para obtener más información, vea [Programación asincrónica con async y await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c1ab-109">For more information, see [Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="3c1ab-110">En el ejemplo siguiente se usan métodos asincrónicos para descargar el contenido de un sitio web especificado como una cadena y mostrar la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="3c1ab-111">El ejemplo contiene los dos métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c1ab-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="3c1ab-112">`startButton_Click`, que llama a `AccessTheWebAsync` y muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="3c1ab-113">`AccessTheWebAsync`, que descarga el contenido de un sitio web como una cadena y devuelve la longitud de esta.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="3c1ab-114">`AccessTheWebAsync` usa un método <xref:System.Net.Http.HttpClient> asincrónico, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, para descargar el contenido.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="3c1ab-115">Las líneas de visualización numeradas aparecen en puntos estratégicos de todo el programa para ayudarle a entender cómo se ejecuta el programa y explicar lo que ocurre en cada punto marcado.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="3c1ab-116">Las líneas de visualización tienen las etiquetas comprendidas entre "UNO" y "SEIS".</span><span class="sxs-lookup"><span data-stu-id="3c1ab-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="3c1ab-117">Las etiquetas representan el orden en el que el programa alcanza estas líneas de código.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="3c1ab-118">En el código siguiente se muestra un esquema del programa.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-118">The following code shows an outline of the program.</span></span>  
  
```csharp  
public partial class MainWindow : Window  
{  
    // . . .  
    private async void startButton_Click(object sender, RoutedEventArgs e)  
    {  
        // ONE  
        Task<int> getLengthTask = AccessTheWebAsync();  
  
        // FOUR  
        int contentLength = await getLengthTask;  
  
        // SIX  
        resultsTextBox.Text +=  
            String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
    }  
  
    async Task<int> AccessTheWebAsync()  
    {  
        // TWO  
        HttpClient client = new HttpClient();  
        Task<string> getStringTask =  
            client.GetStringAsync("http://msdn.microsoft.com");  
  
        // THREE                   
        string urlContents = await getStringTask;  
  
        // FIVE  
        return urlContents.Length;  
    }  
}  
```  
  
 <span data-ttu-id="3c1ab-119">Cada una de las ubicaciones etiquetadas (del "UNO" al "SEIS") muestra información sobre el estado actual del programa.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="3c1ab-120">Se genera la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-120">The following output is produced.</span></span>  
  
```  
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
  
## <a name="set-up-the-program"></a><span data-ttu-id="3c1ab-121">Configurar el programa</span><span class="sxs-lookup"><span data-stu-id="3c1ab-121">Set Up the Program</span></span>  
 <span data-ttu-id="3c1ab-122">Puede descargar el código que se usa en este tema desde MSDN o crearlo usted mismo.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c1ab-123">Para ejecutar el ejemplo, debe tener instalado en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-123">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="3c1ab-124">Descargar el programa</span><span class="sxs-lookup"><span data-stu-id="3c1ab-124">Download the Program</span></span>  
 <span data-ttu-id="3c1ab-125">Puede descargar la aplicación de este tema en [Ejemplo de Async: Controlar el flujo en los programas asincrónicos](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span><span class="sxs-lookup"><span data-stu-id="3c1ab-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0).</span></span> <span data-ttu-id="3c1ab-126">Con los siguientes pasos se abre y se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="3c1ab-127">Descomprima el archivo descargado e inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="3c1ab-128">En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="3c1ab-129">Navegue hasta la carpeta que contiene el código de ejemplo descomprimido, abra el archivo de la solución (.sln) y elija la tecla F5 para compilar y ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="3c1ab-130">Compilar el programa usted mismo</span><span class="sxs-lookup"><span data-stu-id="3c1ab-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="3c1ab-131">El siguiente proyecto de Windows Presentation Foundation (WPF) contiene el ejemplo de código de este tema.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="3c1ab-132">Para ejecutar el proyecto, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c1ab-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="3c1ab-133">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="3c1ab-134">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="3c1ab-135">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="3c1ab-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="3c1ab-136">En el panel **Plantillas instaladas**, elija **Visual C#** y luego elija **Aplicación WPF** en la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-136">In the **Installed Templates** pane, choose **Visual C#**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="3c1ab-137">Escriba `AsyncTracer` como el nombre del proyecto y elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="3c1ab-138">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="3c1ab-139">En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .</span><span class="sxs-lookup"><span data-stu-id="3c1ab-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="3c1ab-140">Si la pestaña no está visible, abra el menú contextual de MainWindow.xaml en el **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="3c1ab-141">En la vista **XAML** de MainWindow.xaml, reemplace el código por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```csharp  
    <Window  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="AsyncTracer.MainWindow"  
            Title="Control Flow Trace" Height="350" Width="592">  
        <Grid>  
            <Button x:Name="startButton" Content="Start  
    " HorizontalAlignment="Left" Margin="250,10,0,0" VerticalAlignment="Top" Width="75" Height="24"  Click="startButton_Click" d:LayoutOverrides="GridBox"/>  
            <TextBox x:Name="resultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="576" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" Grid.ColumnSpan="3"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="3c1ab-142">En la vista **Diseño** de MainWindow.xaml aparece una ventana simple que contiene un cuadro de texto y un botón.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="3c1ab-143">Agregue una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="3c1ab-144">En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.cs, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="3c1ab-145">Reemplace el código del archivo MainWindow.xaml.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-145">In MainWindow.xaml.cs, replace the code with the following code.</span></span>  
  
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
  
    // Add a using directive and a reference for System.Net.Http;  
    using System.Net.Http;  
  
    namespace AsyncTracer  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            private async void startButton_Click(object sender, RoutedEventArgs e)  
            {  
                // The display lines in the example lead you through the control shifts.  
                resultsTextBox.Text += "ONE:   Entering startButton_Click.\r\n" +  
                    "           Calling AccessTheWebAsync.\r\n";  
  
                Task<int> getLengthTask = AccessTheWebAsync();  
  
                resultsTextBox.Text += "\r\nFOUR:  Back in startButton_Click.\r\n" +  
                    "           Task getLengthTask is started.\r\n" +  
                    "           About to await getLengthTask -- no caller to return to.\r\n";  
  
                int contentLength = await getLengthTask;  
  
                resultsTextBox.Text += "\r\nSIX:   Back in startButton_Click.\r\n" +  
                    "           Task getLengthTask is finished.\r\n" +  
                    "           Result from AccessTheWebAsync is stored in contentLength.\r\n" +  
                    "           About to display contentLength and exit.\r\n";  
  
                resultsTextBox.Text +=  
                    String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
            }  
  
            async Task<int> AccessTheWebAsync()  
            {  
                resultsTextBox.Text += "\r\nTWO:   Entering AccessTheWebAsync.";  
  
                // Declare an HttpClient object.  
                HttpClient client = new HttpClient();  
  
                resultsTextBox.Text += "\r\n           Calling HttpClient.GetStringAsync.\r\n";  
  
                // GetStringAsync returns a Task<string>.   
                Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
  
                resultsTextBox.Text += "\r\nTHREE: Back in AccessTheWebAsync.\r\n" +  
                    "           Task getStringTask is started.";  
  
                // AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
                resultsTextBox.Text +=  
                    "\r\n           About to await getStringTask and return a Task<int> to startButton_Click.\r\n";  
  
                // Retrieve the website contents when task is complete.  
                string urlContents = await getStringTask;  
  
                resultsTextBox.Text += "\r\nFIVE:  Back in AccessTheWebAsync." +  
                    "\r\n           Task getStringTask is complete." +  
                    "\r\n           Processing the return statement." +  
                    "\r\n           Exiting from AccessTheWebAsync.\r\n";  
  
                return urlContents.Length;  
            }  
        }  
    }  
    ```  
  
10. <span data-ttu-id="3c1ab-146">Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="3c1ab-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="3c1ab-147">Debe aparecer los siguientes resultados.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-147">The following output should appear.</span></span>  
  
    ```  
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
  
## <a name="trace-the-program"></a><span data-ttu-id="3c1ab-148">Hacer un seguimiento del programa</span><span class="sxs-lookup"><span data-stu-id="3c1ab-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="3c1ab-149">Pasos UNO y DOS</span><span class="sxs-lookup"><span data-stu-id="3c1ab-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="3c1ab-150">Las dos primeras líneas siguen la ruta de acceso a medida que `startButton_Click` llama a `AccessTheWebAsync` y `AccessTheWebAsync` llama al método <xref:System.Net.Http.HttpClient> asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="3c1ab-151">En la siguiente imagen se describen las llamadas de método a método.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="3c1ab-152">![Pasos UNO y DOS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span><span class="sxs-lookup"><span data-stu-id="3c1ab-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="3c1ab-153">El tipo de valor devuelto de `AccessTheWebAsync` y `client.GetStringAsync` es <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="3c1ab-154">Para `AccessTheWebAsync`, TResult es un entero.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="3c1ab-155">Para `GetStringAsync`, TResult es una cadena.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="3c1ab-156">Para obtener más información sobre los tipos de valor devuelto de los métodos asincrónicos, vea [Tipos de valor devueltos asincrónicos (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="3c1ab-156">For more information about async method return types, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="3c1ab-157">Un método asincrónico de devolución de tarea devuelve una instancia de la tarea cuando el control se desplaza al llamador.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="3c1ab-158">El control vuelve a su llamador procedente de un método asincrónico cuando se encuentra un operador `await` en el método llamado o cuando este finaliza.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-158">Control returns from an async method to its caller either when an `await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="3c1ab-159">Las líneas de visualización que tienen las etiquetas comprendidas entre "TRES" y "SEIS" rastrean esta parte del proceso.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="3c1ab-160">Paso TRES</span><span class="sxs-lookup"><span data-stu-id="3c1ab-160">Step THREE</span></span>  
 <span data-ttu-id="3c1ab-161">En `AccessTheWebAsync`, el método asincrónico <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> se llama para descargar el contenido de la página web de destino.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="3c1ab-162">El control vuelve a `AccessTheWebAsync` procedente de `client.GetStringAsync` cuando se devuelve `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="3c1ab-163">El método `client.GetStringAsync` devuelve una tarea de la cadena que se asigna a la variable `getStringTask` en `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="3c1ab-164">En la siguiente línea del programa de ejemplo se muestra la llamada a `client.GetStringAsync` y la asignación.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
```csharp  
Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
```  
  
 <span data-ttu-id="3c1ab-165">Puede considerar la tarea como una promesa de `client.GetStringAsync` de generar una cadena real.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-165">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="3c1ab-166">Mientras tanto, si `AccessTheWebAsync` tiene trabajo que no depende de la cadena prometida de `client.GetStringAsync`, dicho trabajo puede continuar mientras `client.GetStringAsync` espera.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-166">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="3c1ab-167">En el ejemplo, las siguientes líneas de salida, que tienen la etiqueta "TRES", representan la oportunidad de realizar un trabajo independiente</span><span class="sxs-lookup"><span data-stu-id="3c1ab-167">In the example, the following lines of output, which are labeled "THREE," represent the opportunity to do independent work</span></span>  
  
```  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
```  
  
 <span data-ttu-id="3c1ab-168">La siguiente instrucción suspende el progreso en `AccessTheWebAsync` cuando se espera a `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-168">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
```csharp  
string urlContents = await getStringTask;  
```  
  
 <span data-ttu-id="3c1ab-169">En la siguiente imagen se muestra el flujo de control procedente de `client.GetStringAsync` a la asignación de `getStringTask` y procedente de la creación de `getStringTask` a la aplicación de un operador await.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-169">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an await operator.</span></span>  
  
 <span data-ttu-id="3c1ab-170">![Paso TRES](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span><span class="sxs-lookup"><span data-stu-id="3c1ab-170">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="3c1ab-171">La expresión await suspende `AccessTheWebAsync` hasta que se devuelva `client.GetStringAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-171">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="3c1ab-172">Mientras tanto, el control vuelve al llamador de `AccessTheWebAsync`, `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-172">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c1ab-173">Normalmente se espera la llamada a un método asincrónico de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-173">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="3c1ab-174">Por ejemplo, la siguiente asignación podría reemplazar el código anterior que crea y espera `getStringTask`: `string urlContents = await client.GetStringAsync("http://msdn.microsoft.com");`</span><span class="sxs-lookup"><span data-stu-id="3c1ab-174">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `string urlContents = await client.GetStringAsync("http://msdn.microsoft.com");`</span></span>  
>   
>  <span data-ttu-id="3c1ab-175">En este tema, el operador await se aplica más adelante para dar cabida a las líneas de salida que marcan el flujo de control a través del programa.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-175">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="3c1ab-176">Paso CUATRO</span><span class="sxs-lookup"><span data-stu-id="3c1ab-176">Step FOUR</span></span>  
 <span data-ttu-id="3c1ab-177">El tipo de valor devuelto declarado de `AccessTheWebAsync` es `Task<int>`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-177">The declared return type of `AccessTheWebAsync` is `Task<int>`.</span></span> <span data-ttu-id="3c1ab-178">Por lo tanto, cuando se suspende `AccessTheWebAsync`, devuelve una tarea de entero en `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-178">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="3c1ab-179">Debe entender que la tarea devuelta no es `getStringTask`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-179">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="3c1ab-180">La tarea devuelta es una nueva tarea de entero que representa lo que falta por hacer en el método suspendido, `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-180">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="3c1ab-181">La tarea es una promesa de `AccessTheWebAsync` de generar un entero cuando finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-181">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="3c1ab-182">La siguiente instrucción asigna esta tarea a la variable `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-182">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
```csharp  
Task<int> getLengthTask = AccessTheWebAsync();  
```  
  
 <span data-ttu-id="3c1ab-183">Como en `AccessTheWebAsync`, `startButton_Click` puede continuar con el trabajo que no depende de los resultados de la tarea asincrónica (`getLengthTask`) hasta que se espere la tarea.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-183">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="3c1ab-184">Las siguientes líneas de salida representan ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-184">The following output lines represent that work.</span></span>  
  
```  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
```  
  
 <span data-ttu-id="3c1ab-185">El progreso de `startButton_Click` se suspende cuando se espera `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-185">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="3c1ab-186">La siguiente instrucción de asignación suspende `startButton_Click` hasta que concluya `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-186">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
```csharp  
int contentLength = await getLengthTask;  
```  
  
 <span data-ttu-id="3c1ab-187">En la siguiente ilustración, las flechas muestran el flujo de control desde la expresión await en `AccessTheWebAsync` hasta la asignación de un valor a `getLengthTask`, seguido del procesamiento normal en `startButton_Click` hasta que se espera a `getLengthTask`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-187">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="3c1ab-188">![Paso CUATRO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span><span class="sxs-lookup"><span data-stu-id="3c1ab-188">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="3c1ab-189">Paso CINCO</span><span class="sxs-lookup"><span data-stu-id="3c1ab-189">Step FIVE</span></span>  
 <span data-ttu-id="3c1ab-190">Cuando `client.GetStringAsync` indica que ha finalizado, el procesamiento de `AccessTheWebAsync` sale de la suspensión y puede continuar una vez superada la instrucción await.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-190">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="3c1ab-191">En las siguientes líneas de salida se representa la reanudación del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-191">The following lines of output represent the resumption of processing.</span></span>  
  
```  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
```  
  
 <span data-ttu-id="3c1ab-192">El operando de la instrucción de devolución, `urlContents.Length`, se almacena en la tarea que devuelve `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-192">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="3c1ab-193">La expresión await recupera ese valor de `getLengthTask` en `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-193">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="3c1ab-194">En la siguiente imagen se muestra la transferencia de control una vez concluido `client.GetStringAsync` (y `getStringTask`).</span><span class="sxs-lookup"><span data-stu-id="3c1ab-194">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="3c1ab-195">![Paso CINCO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span><span class="sxs-lookup"><span data-stu-id="3c1ab-195">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="3c1ab-196">`AccessTheWebAsync` se ejecuta hasta el final y el control vuelve a `startButton_Click`, que espera la finalización.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-196">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="3c1ab-197">Paso SEIS</span><span class="sxs-lookup"><span data-stu-id="3c1ab-197">Step SIX</span></span>  
 <span data-ttu-id="3c1ab-198">Cuando `AccessTheWebAsync` indica que ha finalizado, el procesamiento puede continuar una vez superada la instrucción await en `startButton_Async`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-198">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="3c1ab-199">De hecho, el programa no tiene nada más que hacer.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-199">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="3c1ab-200">En las siguientes líneas de salida se representa la reanudación del procesamiento en `startButton_Async`:</span><span class="sxs-lookup"><span data-stu-id="3c1ab-200">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
```  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
```  
  
 <span data-ttu-id="3c1ab-201">La expresión await recupera de `getLengthTask` el valor entero que es el operando de la instrucción de devolución de `AccessTheWebAsync`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-201">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="3c1ab-202">La siguiente instrucción asigna ese valor a la variable `contentLength`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-202">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
```csharp  
int contentLength = await getLengthTask;  
```  
  
 <span data-ttu-id="3c1ab-203">En la siguiente imagen se muestra la devolución del control de `AccessTheWebAsync` a `startButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="3c1ab-203">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="3c1ab-204">![Paso SEIS](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span><span class="sxs-lookup"><span data-stu-id="3c1ab-204">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1ab-205">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c1ab-205">See Also</span></span>

- [<span data-ttu-id="3c1ab-206">Programación asincrónica con async y await (C#)</span><span class="sxs-lookup"><span data-stu-id="3c1ab-206">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
- <span data-ttu-id="3c1ab-207">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md) (Tipos de valor devuelto de async [C#])</span><span class="sxs-lookup"><span data-stu-id="3c1ab-207">[Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)</span></span>  
- <span data-ttu-id="3c1ab-208">[Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a web usando Async y Await [C#])</span><span class="sxs-lookup"><span data-stu-id="3c1ab-208">[Walkthrough: Accessing the Web by Using async and await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>  
- [<span data-ttu-id="3c1ab-209">Ejemplo de Async: Controlar el flujo en los programas asincrónicos (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c1ab-209">Async Sample: Control Flow in Async Programs (C# and Visual Basic)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)
