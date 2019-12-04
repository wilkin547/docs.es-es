---
title: 'Walkthrough: Acceso a web usando Async y Await'
ms.date: 07/20/2015
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
ms.openlocfilehash: 7f649f1f16da545c4587f0ed76b8f1a443ee8744
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715854"
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)

Puede escribir programas asincrónicos de manera más fácil e intuitiva usando las características async/await. Puede escribir código asincrónico parecido al código sincrónico y dejar que el compilador gestione las difíciles funciones de devolución de llamada y continuaciones que normalmente implica el código asincrónico.

Para obtener más información sobre la característica Async, consulte [programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).

Este tutorial comienza con una aplicación sincrónica de Windows Presentation Foundation (WPF) que suma el número de bytes de una lista de sitios web. A continuación, el tutorial convierte la aplicación en una solución asincrónica mediante el uso de las características nuevas.

Si no quiere compilar las aplicaciones por su cuenta, puede descargar "Async Sample: Accessing the Web Walkthrough (C# and Visual Basic)" (Muestra de Async: obtener acceso al tutorial web [C# y Visual Basic]) de [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

En este tutorial, se realizarán las siguientes tareas:

> [!div class="checklist"]
>
> - [Crear una aplicación de WPF](#create-a-wpf-application)
> - [Diseñar un MainWindow de WPF sencillo](#design-a-simple-wpf-mainwindow)
> - [Agregar una referencia](#add-a-reference)
> - [Agregar instrucciones Imports necesarias](#add-necessary-imports-statements)
> - [Crear una aplicación sincrónica](#create-a-synchronous-application)
> - [Probar la solución sincrónica](#test-the-synchronous-solution)
> - [Convertir GetURLContents en un método asincrónico](#convert-geturlcontents-to-an-asynchronous-method)
> - [Convertir SumPageSizes en un método asincrónico](#convert-sumpagesizes-to-an-asynchronous-method)
> - [Convertir startButton_Click en un método asincrónico](#convert-startbutton_click-to-an-asynchronous-method)
> - [Probar la solución asincrónica](#test-the-asynchronous-solution)
> - [Reemplazar el método GetURLContentsAsync por un método .NET Framework](#replace-the-geturlcontentsasync-method-with-a-net-framework-method)

Vea la sección [ejemplo](#example) para ver el ejemplo asincrónico completo.

## <a name="prerequisites"></a>Requisitos previos

Debe tener Visual Studio 2012 o posterior instalado en el equipo. Para obtener más información, vea la página de [descargas](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) de Visual Studio.

## <a name="create-a-wpf-application"></a>Crear una aplicación WPF

1. Inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.

    Aparece el cuadro de diálogo **Nuevo proyecto** .

3. En el panel **plantillas instaladas** , elija Visual Basic y, a continuación, elija **aplicación WPF** en la lista de tipos de proyecto.

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

2. En la barra de menús, elija **Proyecto**, **Agregar referencia**.

    Aparecerá el cuadro de diálogo **Administrador de referencias**.

3. En la parte superior del cuadro de diálogo, compruebe que el proyecto tiene como destino .NET Framework 4.5 o superior.

4. En el área **Ensamblados**, elija **Framework** si no está ya seleccionado.

5. En la lista de nombres, seleccione la casilla **System.Net.Http**.

6. Elija el botón **Aceptar** para cerrar el cuadro de diálogo.

## <a name="add-necessary-imports-statements"></a>Agregar instrucciones Imports necesarias

1. En **Explorador de soluciones**, abra el menú contextual de MainWindow. Xaml. VB y, a continuación, elija **Ver código**.

2. Agregue las siguientes instrucciones de `Imports` en la parte superior del archivo de código si aún no están presentes.

    ```vb
    Imports System.Net.Http
    Imports System.Net
    Imports System.IO
    ```

## <a name="create-a-synchronous-application"></a>Crear una aplicación sincrónica

1. En la ventana de diseño, MainWindow. XAML, haga doble clic en el botón **Inicio** para crear el controlador de eventos `startButton_Click` en MainWindow. Xaml. VB.

2. En MainWindow. Xaml. VB, copie el código siguiente en el cuerpo de `startButton_Click`:

    ```vb
    resultsTextBox.Clear()
    SumPageSizes()
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."
    ```

    El código llama al método que controla la aplicación, `SumPageSizes`, y muestra un mensaje cuando el control vuelve a `startButton_Click`.

3. El código de la solución sincrónica contiene los cuatro métodos siguientes:

    - `SumPageSizes`, que obtiene una lista de direcciones URL de páginas web de `SetUpURLList` y, a continuación, llama a `GetURLContents` y `DisplayResults` para que procesen cada dirección URL.

    - `SetUpURLList`, que crea y devuelve una lista de direcciones web.

    - `GetURLContents`, que descarga el contenido de cada sitio web y devuelve el contenido como una matriz de bytes.

    - `DisplayResults`, que muestra el número de bytes de la matriz de bytes de cada dirección URL.

    Copie los cuatro métodos siguientes y péguelos en el controlador de eventos `startButton_Click` en MainWindow. Xaml. VB:

    ```vb
    Private Sub SumPageSizes()

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetURLContents returns the contents of url as a byte array.
            Dim urlContents As Byte() = GetURLContents(url)

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)
    End Sub

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Function GetURLContents(url As String) As Byte()

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.
        Using response As WebResponse = webReq.GetResponse()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                responseStream.CopyTo(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

## <a name="test-the-synchronous-solution"></a>Probar la solución sincrónica

1. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .

    Debería aparecer un resultado similar a la lista siguiente:

    ```console
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

1. Para convertir la solución sincrónica en una solución asincrónica, el mejor lugar para comenzar es `GetURLContents` porque las llamadas al método <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> y al método <xref:System.IO.Stream.CopyTo%2A?displayProperty=nameWithType> son donde la aplicación accede a la Web. .NET Framework facilita la conversión proporcionando versiones asincrónicas de ambos métodos.

    Para obtener más información sobre los modelos que se usan en `GetURLContents`, vea <xref:System.Net.WebRequest>.

    > [!NOTE]
    > A medida que siga los pasos de este tutorial, aparecerán varios errores del compilador. Puede hacer caso omiso y continuar con el tutorial.

    Cambie el método al que se llama en la tercera línea de `GetURLContents` de `GetResponse` al método <xref:System.Net.WebRequest.GetResponseAsync%2A> asincrónico basado en tareas.

    ```vb
    Using response As WebResponse = webReq.GetResponseAsync()
    ```

2. `GetResponseAsync` devuelve <xref:System.Threading.Tasks.Task%601>. En este caso, la *variable de devolución de tarea*, `TResult`, tiene un tipo <xref:System.Net.WebResponse>. La tarea es una promesa para generar un objeto `WebResponse` real después de que se descarguen los datos solicitados y la tarea se ejecute hasta completarse.

    Para recuperar el valor `WebResponse` de la tarea, aplique un operador [Await](../../../../visual-basic/language-reference/operators/await-operator.md) a la llamada a `GetResponseAsync`, como se muestra en el código siguiente.

    ```vb
    Using response As WebResponse = Await webReq.GetResponseAsync()
    ```

    El operador `Await` suspende la ejecución del método actual, `GetURLContents`, hasta que se complete la tarea esperada. Mientras tanto, el control devuelve al llamador del método actual. En este ejemplo, el método actual es `GetURLContents` y el llamador es `SumPageSizes`. Cuando la tarea finaliza, el objeto `WebResponse` prometido se genera como valor de la tarea esperada y se asigna a la variable `response`.

    La instrucción anterior se puede dividir en las dos instrucciones siguientes para aclarar lo que sucede.

    ```vb
    Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
    Using response As WebResponse = Await responseTask
    ```

    La llamada a `webReq.GetResponseAsync` devuelve `Task(Of WebResponse)` o `Task<WebResponse>`. A continuación, se aplica un operador `Await` a la tarea para recuperar el valor de `WebResponse`.

    Si el método asincrónico debe realizar un trabajo que no depende de la finalización de la tarea, el método puede continuar con ese trabajo entre estas dos instrucciones, después de la llamada al método asincrónico y antes de que se aplique el operador await. Para obtener ejemplos, vea [Cómo: hacer varias solicitudes web en paralelo mediante Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) y [Cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

3. Dado que ha agregado el operador `Await` en el paso anterior, se produce un error del compilador. El operador solo se puede usar en métodos marcados con el modificador [Async](../../../../visual-basic/language-reference/modifiers/async.md) . Omita el error mientras repita los pasos de conversión para reemplazar la llamada a `CopyTo` con una llamada a `CopyToAsync`.

    - Cambie el nombre del método al que se llama a <xref:System.IO.Stream.CopyToAsync%2A>.

    - El método `CopyTo` o `CopyToAsync` copia bytes a su argumento, `content`, y no devuelve un valor significativo. En la versión sincrónica, la llamada a `CopyTo` es una sencilla instrucción que no devuelve un valor. La versión asincrónica, `CopyToAsync`, devuelve una <xref:System.Threading.Tasks.Task>. La tarea funciona como "Task(void)" y permite que se espere al método. Aplique `Await` o `await` a la llamada a `CopyToAsync`, como se muestra en el código siguiente.

        ```vb
        Await responseStream.CopyToAsync(content)
        ```

         La instrucción anterior abrevia las dos líneas de código siguientes.

        ```vb
        ' CopyToAsync returns a Task, not a Task<T>.
        Dim copyTask As Task = responseStream.CopyToAsync(content)

        ' When copyTask is completed, content contains a copy of
        ' responseStream.
        Await copyTask
        ```

4. Lo único que queda por hacer en `GetURLContents` es ajustar la firma del método. Solo puede utilizar el operador `Await` en métodos marcados con el modificador [Async](../../../../visual-basic/language-reference/modifiers/async.md) . Agregue el modificador para marcar el método como *método asincrónico*, como se muestra en el código siguiente.

    ```vb
    Private Async Function GetURLContents(url As String) As Byte()
    ```

5. El tipo de valor devuelto de un método asincrónico solo se puede <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>. En Visual Basic, el método debe ser `Function`, que devuelve `Task` o `Task(Of T)`, o el método debe ser `Sub`. Normalmente, un método `Sub` se usa solo en un controlador de eventos Async, donde se requiere `Sub`. En otros casos, se usa `Task(T)` si el método completado tiene una instrucción [Return](../../../../visual-basic/language-reference/statements/return-statement.md) que devuelve un valor de tipo t, y se usa `Task` si el método completado no devuelve un valor significativo.

    Para obtener más información, vea [tipos de valor devueltos Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

    El método `GetURLContents` tiene una instrucción return, y la instrucción devuelve una matriz de bytes. Por lo tanto, el tipo de valor devuelto de la versión de async es Task(T), donde T es una matriz de bytes. Realice los cambios siguientes en la firma del método:

    - Cambie el tipo de valor devuelto a `Task(Of Byte())`.

    - Por convención, los métodos asincrónicos tienen nombres que terminan en "Async", por lo que debe cambiar el nombre del método a `GetURLContentsAsync`.

    En el código siguiente se muestran estos cambios.

    ```vb
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())
    ```

    Con estos pocos cambios, se completa la conversión de `GetURLContents` en un método asincrónico.

## <a name="convert-sumpagesizes-to-an-asynchronous-method"></a>Convertir SumPageSizes en un método asincrónico

1. Repita los pasos del procedimiento anterior para `SumPageSizes`. Primero, cambie la llamada a `GetURLContents` a una llamada asincrónica.

    - Cambie el nombre del método al que se llama de `GetURLContents` a `GetURLContentsAsync`, si aún no lo ha hecho.

    - Aplique `Await` a la tarea que devuelve `GetURLContentsAsync` para obtener el valor de la matriz de bytes.

    En el código siguiente se muestran estos cambios.

    ```vb
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)
    ```

    La asignación anterior abrevia las dos líneas de código siguientes.

    ```vb
    ' GetURLContentsAsync returns a task. At completion, the task
    ' produces a byte array.
    Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    Dim urlContents As Byte() = Await getContentsTask
    ```

2. Realice los cambios siguientes en la firma del método:

    - Marque el método con el modificador `Async`.

    - Agregue "Async" al nombre del método.

    - No hay ninguna variable de devolución de tarea, T, esta vez porque `SumPageSizesAsync` no devuelve un valor para T. (el método no tiene ninguna instrucción `Return`). Sin embargo, el método debe devolver una `Task` para que sea Await. Por lo tanto, cambie el tipo de método de `Sub` a `Function`. El tipo de valor devuelto de la función es `Task`.

    En el código siguiente se muestran estos cambios.

    ```vb
    Private Async Function SumPageSizesAsync() As Task
    ```

    Se completa así la conversión de `SumPageSizes` a `SumPageSizesAsync`.

## <a name="convert-startbutton_click-to-an-asynchronous-method"></a>Convertir startButton_Click en un método asincrónico

1. En el controlador de eventos, cambie el nombre del método llamado de `SumPageSizes` a `SumPageSizesAsync`, si aún no lo ha hecho.

2. Dado que `SumPageSizesAsync` es un método asincrónico, cambie el código en el controlador de eventos para esperar el resultado.

    La llamada a `SumPageSizesAsync` refleja la llamada a `CopyToAsync` en `GetURLContentsAsync`. La llamada devuelve `Task`, no `Task(T)`.

    Al igual que en los procedimientos anteriores, puede convertir la llamada usando una o dos instrucciones. En el código siguiente se muestran estos cambios.

    ```vb
    ' One-step async call.
    Await SumPageSizesAsync()

    ' Two-step async call.
    Dim sumTask As Task = SumPageSizesAsync()
    Await sumTask
    ```

3. Para evitar volver a entrar accidentalmente en la operación, agregue la instrucción siguiente encima de `startButton_Click` para deshabilitar el botón **Inicio**.

    ```vb
    ' Disable the button until the operation is complete.
    startButton.IsEnabled = False
    ```

    Puede volver a habilitar el botón al final del controlador de eventos.

    ```vb
    ' Reenable the button in case you want to run the operation again.
    startButton.IsEnabled = True
    ```

    Para obtener más información sobre la reentrada, consulte [control de la reentrada en aplicaciones asincrónicas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).

4. Finalmente, agregue el modificador `Async` a la declaración de modo que el controlador de eventos pueda esperar `SumPagSizesAsync`.

    ```vb
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
    ```

    Normalmente, no se cambian los nombres de los controladores de eventos. El tipo de valor devuelto no se cambia a `Task` porque los controladores de eventos deben ser `Sub` procedimientos en Visual Basic.

    Así se completa la conversión del proyecto de procesamiento sincrónico a asincrónico.

## <a name="test-the-asynchronous-solution"></a>Probar la solución asincrónica

1. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .

2. Deberían aparecer resultados similares a los de la solución sincrónica. No obstante, debe tener en cuenta las siguientes diferencias.

    - No todos los resultados se producen al mismo tiempo cuando se completa el procesamiento. Por ejemplo, ambos programas contienen una línea en `startButton_Click` que borra el cuadro de texto. La intención es borrar el cuadro de texto entre ejecuciones si elige el botón **Inicio** por segunda vez, después de que haya aparecido un conjunto de resultados. En la versión sincrónica, el cuadro de texto se borra antes de que aparezcan los recuentos por segunda vez, cuando se completen las descargas y el subproceso de interfaz de usuario esté libre para llevar a cabo otro trabajo. En la versión asincrónica, el cuadro de texto se borra inmediatamente después de que se elija el botón **Inicio**.

    - Lo más importante es que el subproceso de interfaz de usuario no se bloquea durante las descargas. Puede mover o cambiar el tamaño de la ventana mientras se descargan, se cuentan y se muestran los recursos web. Si uno de los sitios web es lento o no responde, puede cancelar la operación eligiendo el botón **Cerrar** (la X en el campo de color rojo en la esquina superior derecha).

## <a name="replace-the-geturlcontentsasync-method-with-a-net-framework-method"></a>Reemplazar el método GetURLContentsAsync por un método .NET Framework

1. El .NET Framework proporciona muchos métodos asincrónicos que puede usar. Uno de ellos, el método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29?displayProperty=nameWithType>, hace exactamente lo que necesita para este tutorial. Se puede usar en lugar del método `GetURLContentsAsync` que creó en un procedimiento anterior.

    El primer paso es crear un objeto <xref:System.Net.Http.HttpClient> en el método `SumPageSizesAsync`. Agregue la siguiente declaración al principio del método.

    ```vb
    ' Declare an HttpClient object and increase the buffer size. The
    ' default buffer size is 65,536.
    Dim client As HttpClient =
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}
    ```

2. En `SumPageSizesAsync,` reemplace la llamada a su método `GetURLContentsAsync` con una llamada al método `HttpClient`.

    ```vb
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ```

3. Quite o marque como comentario el método `GetURLContentsAsync` que escribió.

4. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .

    El comportamiento de esta versión del proyecto debería coincidir con el comportamiento que se describe en el procedimiento "Para probar la solución asincrónica", pero con incluso menos trabajo por su parte.

## <a name="example"></a>Ejemplo

El siguiente es el ejemplo completo de la solución asincrónica convertida que usa el método de `GetURLContentsAsync` asincrónico. Observe que es muy parecida a la solución sincrónica original.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)

            ' The previous line abbreviates the following two assignment statements.

            '//<snippet21>
            ' GetURLContentsAsync returns a task. At completion, the task
            ' produces a byte array.
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()

            ' The previous statement abbreviates the following two statements.

            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()
            'Using response As WebResponse = Await responseTask

            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                Await responseStream.CopyToAsync(content)

                ' The previous statement abbreviates the following two statements.

                ' CopyToAsync returns a Task, not a Task<T>.
                'Dim copyTask As Task = responseStream.CopyToAsync(content)

                ' When copyTask is completed, content contains a copy of
                ' responseStream.
                'Await copyTask
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

El código siguiente contiene el ejemplo completo de la solución que usa el método `HttpClient`, `GetByteArrayAsync`.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' Disable the button until the operation is complete.
        startButton.IsEnabled = False

        ' One-step async call.
        Await SumPageSizesAsync()

        ' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."

        ' Reenable the button in case you want to run the operation again.
        startButton.IsEnabled = True
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        Dim total = 0
        For Each url In urlList
            ' GetByteArrayAsync returns a task. At completion, the task
            ' produces a byte array.
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

            ' The following two lines can replace the previous assignment statement.
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
            'Dim urlContents As Byte() = Await getContentsTask

            DisplayResults(url, urlContents)

            ' Update the total.
            total += urlContents.Length
        Next

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub

End Class
```

## <a name="see-also"></a>Vea también

- [Muestra de Async: obtener acceso al tutorial web [C# y Visual Basic]](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)
- [Await (operador)](../../../language-reference/operators/await-operator.md)
- [Async](../../../language-reference/modifiers/async.md)
- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [Async Return Types (Visual Basic)](async-return-types.md) (Tipos de valor devuelto de Async [Visual Basic])
- [Task-based Asynchronous Programming (TAP)](https://www.microsoft.com/download/details.aspx?id=19957) (Programación asincrónica basada en tareas [TAP])
- [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])
- [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Realización de solicitudes web en paralelo mediante Async y Await [Visual Basic])
