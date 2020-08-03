---
title: Procesamiento de tareas asincrónicas a medida que se completan
description: En este ejemplo se muestra cómo usar Task.WhenAny en C# para iniciar varias tareas y procesar los resultados a medida que finalizan, en lugar de procesarlos en el orden en que se inician.
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: a7cfa0bdf783fe9bb735241ca398fde7895f1493
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925155"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)

Si usa <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, puede iniciar varias tareas a la vez y procesarlas una por una a medida que se completen, en lugar de procesarlas en el orden en el que se han iniciado.

En el siguiente ejemplo se usa una consulta para crear una colección de tareas. Cada tarea descarga el contenido de un sitio web especificado. En cada iteración de un bucle while, una llamada awaited a `WhenAny` devuelve la tarea en la colección de tareas que termine primero su descarga. Esa tarea se quita de la colección y se procesa. El bucle se repite hasta que la colección no contiene más tareas.

> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.

## <a name="download-an-example-solution"></a>Descargue una solución de ejemplo

Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) desde [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) y después seguir estos pasos.

> [!TIP]
> Si no quiere descargar el proyecto, en su lugar, puede revisar el archivo *MainWindow.xaml.cs* al final de este tema.

1. Extraiga los archivos que ha descargado del archivo *.zip* y, después, inicie Visual Studio.

2. En la barra de menús, elija **Archivo** > **Abrir** > **Proyecto/Solución**.

3. En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descargó y, después, abra el archivo de solución ( *.sln)* para *AsyncFineTuningCS*/*AsyncFineTuningVB*.

4. En el **Explorador de soluciones**, abra el menú contextual del proyecto **ProcessTasksAsTheyFinish** y, después, pulse **Establecer como proyecto de inicio**.

5. Presione la tecla <kbd>F5</kbd> para ejecutar el programa con depuración, o bien presione las teclas <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depurarlo.

6. Ejecute el proyecto varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.

## <a name="create-the-program-yourself"></a>Crear el programa usted mismo

Este ejemplo se agrega al código desarrollado en [Cancelar las tareas asincrónicas restantes cuando se completa una (C#)](cancel-remaining-async-tasks-after-one-is-complete.md) y usa la misma interfaz de usuario.

Para generar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección [Descargar el ejemplo](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), pero elija **CancelAfterOneTask** como el proyecto de inicio. Agregue los cambios de este tema al método `AccessTheWebAsync` de ese proyecto. Los cambios se marcan con asteriscos.

El proyecto **CancelAfterOneTask** ya incluye una consulta que, cuando se ejecuta, crea una colección de tareas. Cada llamada a `ProcessURLAsync` en el siguiente código devuelve un objeto <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero:

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

En el archivo *MainWindow.xaml.cs* del proyecto, realice los siguientes cambios en el método `AccessTheWebAsync`:

- Ejecute la consulta aplicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> en lugar de <xref:System.Linq.Enumerable.ToArray%2A>.

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- Agregue un bucle `while` que realice los pasos siguientes para cada tarea de la colección:

    1. Espera una llamada a `WhenAny` para identificar la primera tarea en la colección para finalizar su descarga.

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. Quita la tarea de la colección.

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. Espera `firstFinishedTask`, que se devuelve mediante una llamada a `ProcessURLAsync`. La variable `firstFinishedTask` es un <xref:System.Threading.Tasks.Task%601> donde `TReturn` es un entero. La tarea ya está completa, pero la espera para recuperar la longitud del sitio web descargado, como se muestra en el ejemplo siguiente. Si se produce un error en la tarea, `await` iniciará la primera excepción secundaria almacenada en `AggregateException`, a diferencia de leer la propiedad `Result` que iniciaría `AggregateException`.

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

Ejecute el programa varias veces para comprobar que las longitudes que se han descargado no aparecen siempre en el mismo orden.

> [!CAUTION]
> Puede usar `WhenAny` en un bucle, como se describe en el ejemplo, para solucionar problemas que implican un número reducido de tareas. Sin embargo, otros enfoques son más eficaces si hay que procesar un gran número de tareas. Para más información y ejemplos, vea [Processing Tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/) (Procesar tareas a medida que se completan).

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el texto completo del archivo *MainWindow.xaml.cs* para el ejemplo. Los asteriscos marcan los elementos que se agregaron para este ejemplo. Además, observe que debe agregar una referencia para <xref:System.Net.Http>.

Puede descargar el proyecto desde [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

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
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
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

## <a name="see-also"></a>Consulte también

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Ajustar una aplicación asincrónica (C#)](fine-tuning-your-async-application.md)
- [Programación asincrónica con Async y Await (C#)](index.md)
- [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
