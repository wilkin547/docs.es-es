---
title: Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)
description: Obtenga información sobre cómo mejorar el rendimiento de la solución async en C# mediante Task.WhenAll. Este método espera de forma asincrónica varias operaciones asincrónicas.
ms.date: 07/20/2015
ms.assetid: f6927ef2-dc6c-43f8-bc82-bbeac42de423
ms.openlocfilehash: 275f4aeca854f8938642dbea40bf7fd9dc5362d9
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925220"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-c"></a>Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)

El rendimiento de la solución asincrónica de [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: acceso a la web con async y await [C#]) se puede mejorar con el método <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Este método espera de forma asincrónica varias operaciones asincrónicas, que se representan como una colección de tareas.

Es posible que en el tutorial observara que los sitios web se descargan a distintas velocidades. A veces uno de los sitios web es muy lento, lo que retrasa las descargas restantes. Cuando ejecute las soluciones asincrónicas que se compilan en el tutorial, puede finalizar el programa fácilmente si no quiere esperar, pero una mejor opción sería iniciar todas las descargas al mismo tiempo y dejar que las más rápidas continúen sin tener que esperar a la que se retrasa.

El método `Task.WhenAll` se aplica a una colección de tareas. La aplicación de `WhenAll` devuelve una única tarea que no está completa hasta que se completen todas las tareas de la colección. La tarea parece ejecutarse en paralelo, pero no se crean subprocesos adicionales. Las tareas se pueden completar en cualquier orden.

> [!IMPORTANT]
> En los procedimientos siguientes se describen las extensiones para las aplicaciones asincrónicas que se desarrollan en [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md). Puede desarrollar las aplicaciones completando el tutorial o descargando el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).
>
> Para ejecutar el ejemplo, debe tener instalado Visual Studio 2012 o una versión posterior en el equipo.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>Para agregar Task.WhenAll a la solución GetURLContentsAsync

1. Agregue el método `ProcessURLAsync` a la primera aplicación que se desarrolla en [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Si descargó el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough y, después, agregue `ProcessURLAsync` al archivo MainWindow.xaml.cs.

    - Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que incluye el método `GetURLContentsAsync`. El archivo MainWindow.xaml.cs para esta aplicación es el primer ejemplo en la sección "Ejemplos de código completados desde el tutorial".

    El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `foreach` de `SumPageSizesAsync` en el tutorial original. El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.

    ```csharp
    private async Task<int> ProcessURLAsync(string url)
    {
        var byteArray = await GetURLContentsAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. Convierta en comentario o elimine el bucle `foreach` de `SumPageSizesAsync`, como se muestra en el código siguiente.

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    byte[] urlContents = await GetURLContentsAsync(url);

    //    // The previous line abbreviates the following two assignment statements.
    //    // GetURLContentsAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //    //byte[] urlContents = await getContentsTask;

    //    DisplayResults(url, urlContents);

    //    // Update the total.
    //    total += urlContents.Length;
    //}
    ```

3. Cree una colección de tareas. El código siguiente define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web. Las tareas se inician cuando se evalúa la consulta.

    Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `urlList`.

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. Aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.

    En el ejemplo siguiente, la expresión `await` espera la finalización de la única tarea que devuelve `WhenAll`. La expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado. Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de las longitudes de todos los sitios web. Agregue la línea siguiente a `SumPageSizesAsync`.

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>Para agregar Task.WhenAll a la solución HttpClient.GetByteArrayAsync

1. Agregue la versión siguiente de `ProcessURLAsync` a la primera aplicación que se desarrolla en [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Si descargó el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough_HttpClient y, después, agregue `ProcessURLAsync` al archivo MainWindow.xaml.cs.

    - Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que usa el método `HttpClient.GetByteArrayAsync`. El archivo MainWindow.xaml.cs para esta aplicación es el segundo ejemplo en la sección "Ejemplos de código completados desde el tutorial".

    El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `foreach` de `SumPageSizesAsync` en el tutorial original. El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.

    La única diferencia respecto al método `ProcessURLAsync` del procedimiento anterior es el uso de la instancia <xref:System.Net.Http.HttpClient>, `client`.

    ```csharp
    async Task<int> ProcessURLAsync(string url, HttpClient client)
    {
        byte[] byteArray = await client.GetByteArrayAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. Convierta en comentario o elimine el bucle `For Each` o `foreach` de `SumPageSizesAsync`, como se muestra en el código siguiente.

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    // GetByteArrayAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    byte[] urlContent = await client.GetByteArrayAsync(url);

    //    // The previous line abbreviates the following two assignment
    //    // statements.
    //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
    //    byte[] urlContent = await getContentTask;

    //    DisplayResults(url, urlContent);

    //    // Update the total.
    //    total += urlContent.Length;
    //}
    ```

3. Define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web. Las tareas se inician cuando se evalúa la consulta.

    Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `client` y `urlList`.

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url, client);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. Después, aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.

    En el ejemplo siguiente, la expresión `await` espera la finalización de la única tarea que devuelve `WhenAll`. Cuando se completa, la expresión `await` se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado. Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para obtener la suma de las longitudes de todos los sitios web. Agregue la línea siguiente a `SumPageSizesAsync`.

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>Para probar las soluciones Task.WhenAll

- Para cualquiera de las soluciones, presione la tecla F5 para ejecutar el programa y después haga clic en el botón **Start**. El resultado debe ser similar al de las soluciones asincrónicas de [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md). Pero tenga en cuenta que los sitios web cada vez aparecen en un orden diferente.

## <a name="example"></a>Ejemplo

El código siguiente muestra las extensiones para el proyecto que usa el método `GetURLContentsAsync` para descargar el contenido de la web.

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_WhenAll
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

            // Two-step async call.
            Task sumTask = SumPageSizesAsync();
            await sumTask;

            // One-step async call.
            //await SumPageSizesAsync();

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    byte[] urlContents = await GetURLContentsAsync(url);

            //    // The previous line abbreviates the following two assignment statements.
            //    // GetURLContentsAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
            //    //byte[] urlContents = await getContentsTask;

            //    DisplayResults(url, urlContents);

            //    // Update the total.
            //    total += urlContents.Length;
            //}

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        private async Task<int> ProcessURLAsync(string url)
        {
            var byteArray = await GetURLContentsAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    await responseStream.CopyToAsync(content);
                }
            }

            // Return the result as a byte array.
            return content.ToArray();

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

## <a name="example"></a>Ejemplo

El código siguiente muestra las extensiones para el proyecto que usa el método `HttpClient.GetByteArrayAsync` para descargar el contenido de la web.

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_HttpClient_WhenAll
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

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client = new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url, client);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    // GetByteArrayAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    byte[] urlContent = await client.GetByteArrayAsync(url);

            //    // The previous line abbreviates the following two assignment
            //    // statements.
            //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
            //    byte[] urlContent = await getContentTask;

            //    DisplayResults(url, urlContent);

            //    // Update the total.
            //    total += urlContent.Length;
            //}

            // Display the total count for all of the web addresses.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        async Task<int> ProcessURLAsync(string url, HttpClient client)
        {
            byte[] byteArray = await client.GetByteArrayAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each web site. The string format
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

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Tutorial: Acceso a web usando Async y Await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
