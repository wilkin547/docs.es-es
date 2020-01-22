---
title: 'Tutorial: Acceso a web usando Async y Await (C#)'
ms.date: 07/20/2015
ms.assetid: c95d8d71-5a98-4bf0-aaf4-45fed2ebbacd
ms.openlocfilehash: 42b09dab26fd514e184163eaf41aff117d3a463f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281790"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-c"></a>Tutorial: Acceso a web usando Async y Await (C#)

Puede escribir programas asincrónicos de manera más fácil e intuitiva usando las características async/await. Puede escribir código asincrónico parecido al código sincrónico y dejar que el compilador gestione las difíciles funciones de devolución de llamada y continuaciones que normalmente implica el código asincrónico.

Para obtener más información sobre la característica Async, consulte [Programación asincrónica con async y await (C#)](./index.md).

Este tutorial comienza con una aplicación sincrónica de Windows Presentation Foundation (WPF) que suma el número de bytes de una lista de sitios web. A continuación, el tutorial convierte la aplicación en una solución asincrónica mediante el uso de las características nuevas.

Si no quiere compilar usted mismo las aplicaciones, puede descargar [Ejemplo de Async: obtener acceso al tutorial web (C# y Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.

## <a name="create-a-wpf-application"></a>Crear una aplicación WPF

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo** > **Nuevo** > **Proyecto**.

     Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En el panel **Plantillas instaladas**, elija Visual C# y después elija **Aplicación WPF** en la lista de tipos de proyecto.

4. En el cuadro de texto **Nombre**, escriba `AsyncExampleWPF` y elija el botón **Aceptar**.

     El proyecto nuevo aparece en el **Explorador de soluciones**.

## <a name="design-a-simple-wpf-mainwindow"></a>Diseñar una ventana MainWindow simple de WPF

1. En el Editor de código de Visual Studio, elija la pestaña **MainWindow.xaml** .

2. Si la ventana **Cuadro de herramientas** no está visible, abra el menú **Vista** y elija **Cuadro de herramientas**.

3. Agregue un control **Botón** y un control **TextBox** a la ventana **MainWindow**.

4. Resalte el control **TextBox** y, en la ventana **Propiedades**, establezca los siguientes valores:

    - Establezca la propiedad **Nombre** en `resultsTextBox`.

    - Establezca la propiedad **Alto** en 250.

    - Establezca la propiedad **Ancho** en 500.

    - En la pestaña **Texto**, especifique una fuente monoespaciada, como Lucida Console o Global Monospace.

5. Resalte el control **Botón** y, en la ventana **Propiedades**, establezca los siguientes valores:

    - Establezca la propiedad **Nombre** en `startButton`.

    - Cambie el valor de la propiedad **Contenido** de **Botón** a **Inicio**.

6. Coloque el cuadro de texto y el botón de manera que ambos aparezcan en la ventana **MainWindow**.

     Para obtener más información sobre el Diseñador XAML de WPF, consulte [Crear una IU con el Diseñador XAML](/visualstudio/xaml-tools/creating-a-ui-by-using-xaml-designer-in-visual-studio).

## <a name="add-a-reference"></a>Agregar una referencia

1. En el **Explorador de soluciones**, resalte el nombre del proyecto.

2. En la barra de menús, elija **Proyecto** > **Agregar referencia**.

     Aparecerá el cuadro de diálogo **Administrador de referencias**.

3. En la parte superior del cuadro de diálogo, compruebe que el proyecto tiene como destino .NET Framework 4.5 o superior.

4. En la categoría **Ensamblados**, elija **Framework** si no está ya seleccionado.

5. En la lista de nombres, seleccione la casilla **System.Net.Http**.

6. Elija el botón **Aceptar** para cerrar el cuadro de diálogo.

## <a name="add-necessary-using-directives"></a>Agregar las directivas using necesarias

1. En el **Explorador de soluciones**, abra el menú contextual de MainWindow.xaml.cs y después elija **Ver código**.

2. Agregue las siguientes directivas `using` en la parte superior del archivo de código si no están ya presentes.

    ```csharp
    using System.Net.Http;
    using System.Net;
    using System.IO;
    ```

## <a name="create-a-synchronous-app"></a>Crear una aplicación sincrónica

1. En la ventana de diseño, MainWindow.xaml, haga doble clic en el botón **Inicio** para crear el controlador de eventos `startButton_Click` en MainWindow.xaml.cs.

2. En MainWindow.xaml.cs, copie el código siguiente en el cuerpo de `startButton_Click`:

    ```csharp
    resultsTextBox.Clear();
    SumPageSizes();
    resultsTextBox.Text += "\r\nControl returned to startButton_Click.";
    ```

    El código llama al método que controla la aplicación, `SumPageSizes`, y muestra un mensaje cuando el control vuelve a `startButton_Click`.

3. El código de la solución sincrónica contiene los cuatro métodos siguientes:

    - `SumPageSizes`, que obtiene una lista de direcciones URL de páginas web de `SetUpURLList` y, a continuación, llama a `GetURLContents` y `DisplayResults` para que procesen cada dirección URL.

    - `SetUpURLList`, que crea y devuelve una lista de direcciones web.

    - `GetURLContents`, que descarga el contenido de cada sitio web y devuelve el contenido como una matriz de bytes.

    - `DisplayResults`, que muestra el número de bytes de la matriz de bytes de cada dirección URL.

    Copie los cuatro métodos siguientes y péguelos bajo el controlador de eventos `startButton_Click` en MainWindow.xaml.cs:

    ```csharp
    private void SumPageSizes()
    {
        // Make a list of web addresses.
        List<string> urlList = SetUpURLList();

        var total = 0;
        foreach (var url in urlList)
        {
            // GetURLContents returns the contents of url as a byte array.
            byte[] urlContents = GetURLContents(url);

            DisplayResults(url, urlContents);

            // Update the total.
            total += urlContents.Length;
        }

        // Display the total count for all of the web addresses.
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }

    private List<string> SetUpURLList()
    {
        var urls = new List<string>
        {
            "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

    private byte[] GetURLContents(string url)
    {
        // The downloaded resource ends up in the variable named content.
        var content = new MemoryStream();

        // Initialize an HttpWebRequest for the current URL.
        var webReq = (HttpWebRequest)WebRequest.Create(url);

        // Send the request to the Internet resource and wait for
        // the response.
        // Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        using (WebResponse response = webReq.GetResponse())
        {
            // Get the data stream that is associated with the specified URL.
            using (Stream responseStream = response.GetResponseStream())
            {
                // Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content);
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
    ```

## <a name="test-the-synchronous-solution"></a>Probar la solución sincrónica

Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.

Debería aparecer un resultado similar a la lista siguiente:

```text
msdn.microsoft.com/library/windows/apps/br211380.aspx        383832
msdn.microsoft.com                                            33964
msdn.microsoft.com/library/hh290136.aspx               225793
msdn.microsoft.com/library/ee256749.aspx               143577
msdn.microsoft.com/library/hh290138.aspx               237372
msdn.microsoft.com/library/hh290140.aspx               128279
msdn.microsoft.com/library/dd470362.aspx               157649
msdn.microsoft.com/library/aa578028.aspx               204457
msdn.microsoft.com/library/ms404677.aspx               176405
msdn.microsoft.com/library/ff730837.aspx               143474

Total bytes returned:  1834802

Control returned to startButton_Click.
```

Tenga en cuenta que los recuentos tardan unos segundos en mostrarse. Durante ese tiempo, el subproceso de interfaz de usuario se bloquea mientras espera a que se descarguen los recursos solicitados. Como resultado, no se puede mover, maximizar, minimizar o ni siquiera cerrar la ventana de la pantalla después de elegir el botón **Inicio**. Estos intentos producirán un error hasta que empiecen a aparecer los recuentos de bytes. Si un sitio web no responde, no se le indicará cuál es el sitio que produjo el error. Incluso resulta difícil dejar de esperar y cerrar el programa.

## <a name="convert-geturlcontents-to-an-asynchronous-method"></a>Convertir GetURLContents en un método asincrónico

1. Para convertir la solución sincrónica a una solución asincrónica, lo mejor es comenzar en `GetURLContents`, ya que las llamadas al método <xref:System.Net.HttpWebRequest> <xref:System.Net.HttpWebRequest.GetResponse%2A> y al método <xref:System.IO.Stream> <xref:System.IO.Stream.CopyTo%2A> son el lugar desde donde la aplicación accede a la web. .NET Framework facilita la conversión proporcionando versiones asincrónicas de ambos métodos.

     Para obtener más información sobre los modelos que se usan en `GetURLContents`, vea <xref:System.Net.WebRequest>.

    > [!NOTE]
    > A medida que siga los pasos de este tutorial, aparecerán varios errores del compilador. Puede hacer caso omiso y continuar con el tutorial.

     Cambie el método al que se llama en la tercera línea de `GetURLContents` de `GetResponse` al método <xref:System.Net.WebRequest.GetResponseAsync%2A> asincrónico basado en tareas.

    ```csharp
    using (WebResponse response = webReq.GetResponseAsync())
    ```

2. `GetResponseAsync` devuelve <xref:System.Threading.Tasks.Task%601>. En este caso, la *variable de devolución de tarea*, `TResult`, tiene un tipo <xref:System.Net.WebResponse>. La tarea es una promesa para generar un objeto `WebResponse` real después de que se descarguen los datos solicitados y la tarea se ejecute hasta completarse.

     Para recuperar el valor `WebResponse` de la tarea, aplique un operador [await](../../../language-reference/operators/await.md) a la llamada a `GetResponseAsync`, como se muestra en el código siguiente.

    ```csharp
    using (WebResponse response = await webReq.GetResponseAsync())
    ```

     El operador `await` suspende la ejecución del método actual, `GetURLContents`, hasta que se complete la tarea esperada. Mientras tanto, el control devuelve al llamador del método actual. En este ejemplo, el método actual es `GetURLContents` y el llamador es `SumPageSizes`. Cuando la tarea finaliza, el objeto `WebResponse` prometido se genera como valor de la tarea esperada y se asigna a la variable `response`.

     La instrucción anterior se puede dividir en las dos instrucciones siguientes para aclarar lo que sucede.

    ```csharp
    //Task<WebResponse> responseTask = webReq.GetResponseAsync();
    //using (WebResponse response = await responseTask)
    ```

     La llamada a `webReq.GetResponseAsync` devuelve `Task(Of WebResponse)` o `Task<WebResponse>`. A continuación, se aplica un operador await a la tarea para recuperar el valor `WebResponse`.

     Si el método asincrónico debe realizar un trabajo que no depende de la finalización de la tarea, el método puede continuar con ese trabajo entre estas dos instrucciones, después de la llamada al método asincrónico y antes de que se aplique el operador `await`. Para obtener ejemplos, vea [Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) y [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. Dado que ha agregado el operador `await` en el paso anterior, se produce un error del compilador. El operador puede usarse únicamente en los métodos marcados con el modificador [async](../../../language-reference/keywords/async.md). Omita el error mientras repita los pasos de conversión para reemplazar la llamada a `CopyTo` con una llamada a `CopyToAsync`.

    - Cambie el nombre del método al que se llama a <xref:System.IO.Stream.CopyToAsync%2A>.

    - El método `CopyTo` o `CopyToAsync` copia bytes a su argumento, `content`, y no devuelve un valor significativo. En la versión sincrónica, la llamada a `CopyTo` es una sencilla instrucción que no devuelve un valor. La versión asincrónica, `CopyToAsync`, devuelve una <xref:System.Threading.Tasks.Task>. La tarea funciona como "Task(void)" y permite que se espere al método. Aplique `Await` o `await` a la llamada a `CopyToAsync`, como se muestra en el código siguiente.

        ```csharp
        await responseStream.CopyToAsync(content);
        ```

         La instrucción anterior abrevia las dos líneas de código siguientes.

        ```csharp
        // CopyToAsync returns a Task, not a Task<T>.
        //Task copyTask = responseStream.CopyToAsync(content);

        // When copyTask is completed, content contains a copy of
        // responseStream.
        //await copyTask;
        ```

4. Lo único que queda por hacer en `GetURLContents` es ajustar la firma del método. Puede usar el operador `await` únicamente en los métodos marcados con el modificador [async](../../../language-reference/keywords/async.md). Agregue el modificador para marcar el método como *método asincrónico*, como se muestra en el código siguiente.

    ```csharp
    private async byte[] GetURLContents(string url)
    ```

5. El tipo de valor devuelto de un método asincrónico solo puede ser <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> o `void` en C#. Normalmente, el tipo de valor devuelto `void` se usa solo en un controlador de eventos asincrónico, en el que se requiere `void`. En otros casos, se usa `Task(T)` si el método completado tiene una instrucción [return](../../../language-reference/keywords/return.md) que devuelve un valor de tipo T, y se usa `Task` si el método completado no devuelve un valor significativo. Puede considerar que el tipo de valor devuelto `Task` significa "Task(void)".

     Para obtener más información, consulte [Tipos de valor devueltos asincrónicos (C#)](./async-return-types.md).

     El método `GetURLContents` tiene una instrucción return, y la instrucción devuelve una matriz de bytes. Por lo tanto, el tipo de valor devuelto de la versión de async es Task(T), donde T es una matriz de bytes. Realice los cambios siguientes en la firma del método:

    - Cambie el tipo de valor devuelto a `Task<byte[]>`.

    - Por convención, los métodos asincrónicos tienen nombres que terminan en "Async", por lo que debe cambiar el nombre del método a `GetURLContentsAsync`.

     En el código siguiente se muestran estos cambios.

    ```csharp
    private async Task<byte[]> GetURLContentsAsync(string url)
    ```

     Con estos pocos cambios, se completa la conversión de `GetURLContents` en un método asincrónico.

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>Convertir SumPageSizes en un método asincrónico

1. Repita los pasos del procedimiento anterior para `SumPageSizes`. Primero, cambie la llamada a `GetURLContents` a una llamada asincrónica.

    - Cambie el nombre del método al que se llama de `GetURLContents` a `GetURLContentsAsync`, si aún no lo ha hecho.

    - Aplique `await` a la tarea que devuelve `GetURLContentsAsync` para obtener el valor de la matriz de bytes.

     En el código siguiente se muestran estos cambios.

    ```csharp
    byte[] urlContents = await GetURLContentsAsync(url);
    ```

     La asignación anterior abrevia las dos líneas de código siguientes.

    ```csharp
    // GetURLContentsAsync returns a Task<T>. At completion, the task
    // produces a byte array.
    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //byte[] urlContents = await getContentsTask;
    ```

2. Realice los cambios siguientes en la firma del método:

    - Marque el método con el modificador `async`.

    - Agregue "Async" al nombre del método.

    - Esta vez no hay ninguna variable de devolución de tarea, T, porque `SumPageSizesAsync` no devuelve un valor para T. (El método no tiene ninguna instrucción `return`). Sin embargo, el método debe devolver `Task` para admitir await. Por tanto, cambie el tipo de valor devuelto del método de `void` a `Task`.

    En el código siguiente se muestran estos cambios.

    ```csharp
    private async Task SumPageSizesAsync()
    ```

     Se completa así la conversión de `SumPageSizes` a `SumPageSizesAsync`.

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>Convertir startButton_Click en un método asincrónico

1. En el controlador de eventos, cambie el nombre del método llamado de `SumPageSizes` a `SumPageSizesAsync`, si aún no lo ha hecho.

2. Dado que `SumPageSizesAsync` es un método asincrónico, cambie el código en el controlador de eventos para esperar el resultado.

     La llamada a `SumPageSizesAsync` refleja la llamada a `CopyToAsync` en `GetURLContentsAsync`. La llamada devuelve `Task`, no `Task(T)`.

     Al igual que en los procedimientos anteriores, puede convertir la llamada usando una o dos instrucciones. En el código siguiente se muestran estos cambios.

    ```csharp
    // One-step async call.
    await SumPageSizesAsync();

    // Two-step async call.
    //Task sumTask = SumPageSizesAsync();
    //await sumTask;
    ```

3. Para evitar volver a entrar accidentalmente en la operación, agregue la instrucción siguiente encima de `startButton_Click` para deshabilitar el botón **Inicio**.

    ```csharp
    // Disable the button until the operation is complete.
    startButton.IsEnabled = false;
    ```

     Puede volver a habilitar el botón al final del controlador de eventos.

    ```csharp
    // Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = true;
    ```

     Para obtener más información sobre la reentrada, consulte [Handling Reentrancy in Async Apps (C#)](./handling-reentrancy-in-async-apps.md) (Controlar la reentrada en aplicaciones asincrónicas [C#]).

4. Finalmente, agregue el modificador `async` a la declaración de modo que el controlador de eventos pueda esperar `SumPagSizesAsync`.

    ```csharp
    private async void startButton_Click(object sender, RoutedEventArgs e)
    ```

     Normalmente, no se cambian los nombres de los controladores de eventos. El tipo de valor devuelto no se cambia a `Task` porque los controladores de eventos deben devolver `void`.

     Así se completa la conversión del proyecto de procesamiento sincrónico a asincrónico.

## <a name="test-the-asynchronous-solution"></a>Probar la solución asincrónica

1. Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.

2. Deberían aparecer resultados similares a los de la solución sincrónica. No obstante, debe tener en cuenta las siguientes diferencias.

    - No todos los resultados se producen al mismo tiempo cuando se completa el procesamiento. Por ejemplo, ambos programas contienen una línea en `startButton_Click` que borra el cuadro de texto. La intención es borrar el cuadro de texto entre ejecuciones si elige el botón **Inicio** por segunda vez, después de que haya aparecido un conjunto de resultados. En la versión sincrónica, el cuadro de texto se borra antes de que aparezcan los recuentos por segunda vez, cuando se completen las descargas y el subproceso de interfaz de usuario esté libre para llevar a cabo otro trabajo. En la versión asincrónica, el cuadro de texto se borra inmediatamente después de que se elija el botón **Inicio**.

    - Lo más importante es que el subproceso de interfaz de usuario no se bloquea durante las descargas. Puede mover o cambiar el tamaño de la ventana mientras se descargan, se cuentan y se muestran los recursos web. Si uno de los sitios web es lento o no responde, puede cancelar la operación eligiendo el botón **Cerrar** (la X en el campo de color rojo en la esquina superior derecha).

## <a name="replace-method-geturlcontentsasync-with-a-net-framework-method"></a>Reemplazar el método GetURLContentsAsync con un método de .NET Framework

1. .NET Framework 4.5 pone a su disposición muchos métodos asincrónicos. Uno de ellos, el método <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29>, hace justo lo que necesita para este tutorial. Se puede usar en lugar del método `GetURLContentsAsync` que creó en un procedimiento anterior.

     El primer paso es crear un objeto `HttpClient` en el método `SumPageSizesAsync`. Agregue la siguiente declaración al principio del método.

    ```csharp
    // Declare an HttpClient object and increase the buffer size. The
    // default buffer size is 65,536.
    HttpClient client =
        new HttpClient() { MaxResponseContentBufferSize = 1000000 };
    ```

2. En `SumPageSizesAsync,` reemplace la llamada a su método `GetURLContentsAsync` con una llamada al método `HttpClient`.

    ```csharp
    byte[] urlContents = await client.GetByteArrayAsync(url);
    ```

3. Quite o marque como comentario el método `GetURLContentsAsync` que escribió.

4. Presione la tecla **F5** para ejecutar el programa y elija el botón **Inicio**.

     El comportamiento de esta versión del proyecto debería coincidir con el comportamiento que se describe en el procedimiento "Para probar la solución asincrónica", pero con incluso menos trabajo por su parte.

## <a name="example-code"></a>código de ejemplo

El código siguiente contiene el ejemplo completo de la conversión de una solución sincrónica a una asincrónica usando el método `GetURLContentsAsync` asincrónico que escribió. Observe que es muy parecida a la solución sincrónica original.

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                byte[] urlContents = await GetURLContentsAsync(url);

                // The previous line abbreviates the following two assignment statements.

                // GetURLContentsAsync returns a Task<T>. At completion, the task
                // produces a byte array.
                //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }
            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())

            // The previous statement abbreviates the following two statements.

            //Task<WebResponse> responseTask = webReq.GetResponseAsync();
            //using (WebResponse response = await responseTask)
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Read the bytes in responseStream and copy them to content.
                    await responseStream.CopyToAsync(content);

                    // The previous statement abbreviates the following two statements.

                    // CopyToAsync returns a Task, not a Task<T>.
                    //Task copyTask = responseStream.CopyToAsync(content);

                    // When copyTask is completed, content contains a copy of
                    // responseStream.
                    //await copyTask;
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

El código siguiente contiene el ejemplo completo de la solución que usa el método `HttpClient`, `GetByteArrayAsync`.

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

// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF
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

            // Disable the button until the operation is complete.
            startButton.IsEnabled = false;

            // One-step async call.
            await SumPageSizesAsync();

            //// Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";

            // Reenable the button in case you want to run the operation again.
            startButton.IsEnabled = true;
        }

        private async Task SumPageSizesAsync()
        {
            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client =
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            var total = 0;

            foreach (var url in urlList)
            {
                // GetByteArrayAsync returns a task. At completion, the task
                // produces a byte array.
                byte[] urlContents = await client.GetByteArrayAsync(url);

                // The following two lines can replace the previous assignment statement.
                //Task<byte[]> getContentsTask = client.GetByteArrayAsync(url);
                //byte[] urlContents = await getContentsTask;

                DisplayResults(url, urlContents);

                // Update the total.
                total += urlContents.Length;
            }

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
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

## <a name="see-also"></a>Vea también

- [Async Sample: Acceso al tutorial web (C# y Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/hh300224(v=vs.110))
- [async](../../../language-reference/keywords/async.md)
- [await](../../../language-reference/operators/await.md)
- [Programación asincrónica con Async y Await (C#)](./index.md)
- [Async Return Types (C#)](./async-return-types.md) (Tipos de valor devuelto de async [C#])
- [Task-based Asynchronous Programming (TAP)](https://www.microsoft.com/download/details.aspx?id=19957) (Programación asincrónica basada en tareas [TAP])
- [Procedimiento para ampliar el tutorial de async usando Task.WhenAll (C#)](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
- [Procedimiento para realizar varias solicitudes web en paralelo con async y await (C#)](./how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)
