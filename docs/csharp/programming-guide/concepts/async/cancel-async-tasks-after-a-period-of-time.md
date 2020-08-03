---
title: Cancelar tareas asincrónicas tras un período de tiempo (C#)
description: Use el método CancellationTokenSource.CancelAfter de C# para programar la cancelación de las tareas asociadas que no se hayan completado en un período establecido en este ejemplo.
ms.date: 07/20/2015
ms.assetid: 194282c2-399f-46da-a7a6-96674e00b0b3
ms.openlocfilehash: f32af1d893c60ac17648f60fa3aa90adaa0383e8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925297"
---
# <a name="cancel-async-tasks-after-a-period-of-time-c"></a><span data-ttu-id="c9cfe-103">Cancelar tareas asincrónicas tras un período de tiempo (C#)</span><span class="sxs-lookup"><span data-stu-id="c9cfe-103">Cancel async tasks after a period of time (C#)</span></span>

<span data-ttu-id="c9cfe-104">Puede cancelar una operación asincrónica después de un período de tiempo con el método <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> si no quiere esperar a que finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-104">You can cancel an asynchronous operation after a period of time by using the  <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> method if you don't want to wait for the operation to finish.</span></span> <span data-ttu-id="c9cfe-105">Este método programa la cancelación de las tareas asociadas que no se completen en el período de tiempo designado por la expresión `CancelAfter`.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-105">This method schedules the cancellation of any associated tasks that aren’t complete within the period of time that’s designated by the `CancelAfter` expression.</span></span>

<span data-ttu-id="c9cfe-106">Este ejemplo se agrega al código que se desarrolla en [Cancelar una tarea asincrónica o una lista de tareas (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios web y mostrar la longitud del contenido de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-106">This example adds to the code that’s developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to download a list of websites and to display the length of the contents of each one.</span></span>

> [!NOTE]
> <span data-ttu-id="c9cfe-107">Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-107">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-the-example"></a><span data-ttu-id="c9cfe-108">Descargar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9cfe-108">Download the example</span></span>

<span data-ttu-id="c9cfe-109">Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Ejemplo de async: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo de Async: Ajuste de la aplicación) y después seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-109">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

1. <span data-ttu-id="c9cfe-110">Descomprima el archivo descargado y, a continuación, inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-110">Decompress the file that you downloaded, and then start Visual Studio.</span></span>

2. <span data-ttu-id="c9cfe-111">En la barra de menús, elija **Archivo** > **Abrir** > **Proyecto/Solución**.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-111">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="c9cfe-112">En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y, a después, abra el archivo de solución (.sln) para AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-112">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>

4. <span data-ttu-id="c9cfe-113">En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterTime** y, después, elija **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-113">In **Solution Explorer**, open the shortcut menu for the **CancelAfterTime** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="c9cfe-114">Presione la tecla **F5** para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-114">Choose the **F5** key to run the project.</span></span> <span data-ttu-id="c9cfe-115">(O presione **Ctrl**+**F5** para ejecutar el proyecto sin depurarlo).</span><span class="sxs-lookup"><span data-stu-id="c9cfe-115">(Or, press **Ctrl**+**F5** to run the project without debugging it).</span></span>

6. <span data-ttu-id="c9cfe-116">Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-116">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span>

<span data-ttu-id="c9cfe-117">Si no quiere descargar el proyecto, puede revisar el archivo MainWindow.xaml.cs al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-117">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>

## <a name="build-the-example"></a><span data-ttu-id="c9cfe-118">Compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9cfe-118">Build the example</span></span>

<span data-ttu-id="c9cfe-119">El ejemplo de este tema se incorpora al proyecto desarrollado en [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) (Cancelar una tarea asincrónica o una lista de tareas [C#]) para cancelar una lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-119">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="c9cfe-120">En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-120">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>

<span data-ttu-id="c9cfe-121">Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-121">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="c9cfe-122">Agregue los cambios de este tema a ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-122">Add the changes in this topic to that project.</span></span>

<span data-ttu-id="c9cfe-123">Para especificar un tiempo máximo antes de que las tareas se marquen como canceladas, agregue una llamada a `CancelAfter` en `startButton_Click`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-123">To specify a maximum time before the tasks are marked as canceled, add a call to `CancelAfter` to `startButton_Click`, as the following example shows.</span></span> <span data-ttu-id="c9cfe-124">La adición se marca con asteriscos.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-124">The addition is marked with asterisks.</span></span>

```csharp
private async void startButton_Click(object sender, RoutedEventArgs e)
{
    // Instantiate the CancellationTokenSource.
    cts = new CancellationTokenSource();

    resultsTextBox.Clear();

    try
    {
        // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        // can adjust the time.)
        cts.CancelAfter(2500);

        await AccessTheWebAsync(cts.Token);
        resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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
```

 <span data-ttu-id="c9cfe-125">Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-125">Run the program several times to verify that the output might show output for all websites, no websites, or some web sites.</span></span> <span data-ttu-id="c9cfe-126">El siguiente resultado es un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-126">The following output is a sample.</span></span>

```output
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a><span data-ttu-id="c9cfe-127">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="c9cfe-127">Complete example</span></span>

<span data-ttu-id="c9cfe-128">El código siguiente es el texto completo del archivo MainWindow.xaml.cs para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-128">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="c9cfe-129">Los asteriscos marcan los elementos que se agregaron para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-129">Asterisks mark the elements that were added for this example.</span></span>

<span data-ttu-id="c9cfe-130">Observe que debe agregar una referencia para <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="c9cfe-130">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="c9cfe-131">Puede descargar el proyecto desde [Async Sample: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="c9cfe-131">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

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

namespace CancelAfterTime
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
                // ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
                // can adjust the time.)
                cts.CancelAfter(2500);

                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads succeeded.\r\n";
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

        // You can still include a Cancel button if you want to.
        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            // Declare an HttpClient object.
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            foreach (var url in urlList)
            {
                // GetAsync returns a Task<HttpResponseMessage>.
                // Argument ct carries the message if the Cancel button is chosen.
                // Note that the Cancel button cancels all remaining downloads.
                HttpResponseMessage response = await client.GetAsync(url, ct);

                // Retrieve the website contents from the HttpResponseMessage.
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

                resultsTextBox.Text +=
                    $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }
    }

    // Sample Output:

    // Length of the downloaded string: 35990.

    // Length of the downloaded string: 407399.

    // Length of the downloaded string: 226091.

    // Downloads canceled.
}
```

## <a name="see-also"></a><span data-ttu-id="c9cfe-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9cfe-132">See also</span></span>

- [<span data-ttu-id="c9cfe-133">Programación asincrónica con Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="c9cfe-133">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- [<span data-ttu-id="c9cfe-134">Tutorial: Acceso a web usando Async y Await (C#)</span><span class="sxs-lookup"><span data-stu-id="c9cfe-134">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="c9cfe-135">Cancelar una tarea asincrónica o una lista de tareas (C#)</span><span class="sxs-lookup"><span data-stu-id="c9cfe-135">Cancel an Async Task or a List of Tasks (C#)</span></span>](./cancel-an-async-task-or-a-list-of-tasks.md)
- [<span data-ttu-id="c9cfe-136">Ajustar una aplicación asincrónica (C#)</span><span class="sxs-lookup"><span data-stu-id="c9cfe-136">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- [<span data-ttu-id="c9cfe-137">Ejemplo de async: Ajuste de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c9cfe-137">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
