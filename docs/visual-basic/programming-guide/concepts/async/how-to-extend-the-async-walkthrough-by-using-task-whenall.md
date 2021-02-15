---
description: 'Más información acerca de cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)'
title: Procedimiento para ampliar el tutorial de async mediante Task.WhenAll
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: fc303d6b2ed64cb2003c06724fcd21000d0b3abf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474387"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])

Puede mejorar el rendimiento de la solución asincrónica en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md) mediante el <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> método. Este método espera de forma asincrónica varias operaciones asincrónicas, que se representan como una colección de tareas.

Es posible que en el tutorial observara que los sitios web se descargan a distintas velocidades. A veces uno de los sitios web es muy lento, lo que retrasa las descargas restantes. Cuando ejecute las soluciones asincrónicas que se compilan en el tutorial, puede finalizar el programa fácilmente si no quiere esperar, pero una mejor opción sería iniciar todas las descargas al mismo tiempo y dejar que las más rápidas continúen sin tener que esperar a la que se retrasa.

El método `Task.WhenAll` se aplica a una colección de tareas. La aplicación de `WhenAll` devuelve una única tarea que no está completa hasta que se completen todas las tareas de la colección. La tarea parece ejecutarse en paralelo, pero no se crean subprocesos adicionales. Las tareas se pueden completar en cualquier orden.

> [!IMPORTANT]
> En los procedimientos siguientes se describen las extensiones para las aplicaciones asincrónicas desarrolladas en el [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md). Puede desarrollar las aplicaciones completando el tutorial o descargando el código de [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).
>
> Para ejecutar el ejemplo, debe tener instalado Visual Studio 2012 o una versión posterior en el equipo.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>Para agregar Task.WhenAll a la solución GetURLContentsAsync

1. Agregue el `ProcessURLAsync` método a la primera aplicación que se desarrolla en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Si descargó el código de  [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto AsyncWalkthrough y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow. Xaml. VB.

    - Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que incluye el método `GetURLContentsAsync`. El archivo MainWindow. Xaml. VB para esta aplicación es el primer ejemplo de la sección "ejemplos de código completo desde el tutorial".

     El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `For Each` de `SumPageSizesAsync` en el tutorial original. El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Convierta en comentario o elimine el bucle `For Each` de `SumPageSizesAsync`, como se muestra en el código siguiente.

    ```vb
    'Dim total = 0
    'For Each url In urlList

    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

    '    ' The previous line abbreviates the following two assignment statements.

    '    ' GetURLContentsAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Cree una colección de tareas. El código siguiente define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web. Las tareas se inician cuando se evalúa la consulta.

     Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.

     En el ejemplo siguiente, la expresión `Await` espera la finalización de la única tarea que devuelve `WhenAll`. La expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado. Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para calcular la suma de las longitudes de todos los sitios web. Agregue la línea siguiente a `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>Para agregar Task.WhenAll a la solución HttpClient.GetByteArrayAsync

1. Agregue la siguiente versión de `ProcessURLAsync` a la segunda aplicación que se desarrolla en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Si descargó el código de [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), abra el proyecto de AsyncWalkthrough_HttpClient y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow. Xaml. VB.

    - Si desarrolló el código completando el tutorial, agregue `ProcessURLAsync` a la aplicación que usa el método `HttpClient.GetByteArrayAsync`. El archivo MainWindow. Xaml. VB para esta aplicación es el segundo ejemplo de la sección "ejemplos de código completo desde el tutorial".

     El método `ProcessURLAsync` consolida las acciones en el cuerpo del bucle `For Each` de `SumPageSizesAsync` en el tutorial original. El método descarga de forma asincrónica el contenido de un sitio web especificado como una matriz de bytes y, después, muestra y devuelve la longitud de la matriz de bytes.

     La única diferencia respecto al método `ProcessURLAsync` del procedimiento anterior es el uso de la instancia <xref:System.Net.Http.HttpClient>, `client`.

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Convierta en comentario o elimine el bucle `For Each` de `SumPageSizesAsync`, como se muestra en el código siguiente.

    ```vb
    'Dim total = 0
    'For Each url In urlList
    '    ' GetByteArrayAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

    '    ' The following two lines can replace the previous assignment statement.
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Define una [consulta](../linq/index.md) que, cuando la ejecute el método <xref:System.Linq.Enumerable.ToArray%2A>, crea una colección de tareas que descargan el contenido de cada sitio web. Las tareas se inician cuando se evalúa la consulta.

     Agregue el código siguiente en el método `SumPageSizesAsync` después de la declaración de `client` y `urlList`.

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Después, aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll` devuelve una única tarea que finaliza cuando se completan todas las tareas de la colección de tareas.

     En el ejemplo siguiente, la expresión `Await` espera la finalización de la única tarea que devuelve `WhenAll`. Cuando se completa, la expresión `Await` se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio web descargado. Agregue el código siguiente a `SumPageSizesAsync`, después del código que agregó en el paso anterior.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Por último, use el método <xref:System.Linq.Enumerable.Sum%2A> para obtener la suma de las longitudes de todos los sitios web. Agregue la línea siguiente a `SumPageSizesAsync`.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>Para probar las soluciones Task.WhenAll

Para cualquiera de las soluciones, presione la tecla F5 para ejecutar el programa y después haga clic en el botón **Start**. La salida debe parecerse a la salida de las soluciones asincrónicas en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md). Pero tenga en cuenta que los sitios web cada vez aparecen en un orden diferente.

## <a name="example"></a>Ejemplo

El código siguiente muestra las extensiones para el proyecto que usa el método `GetURLContentsAsync` para descargar el contenido de la web.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        'Dim total = 0
        'For Each url In urlList

        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

        '    ' The previous line abbreviates the following two assignment statements.

        '    ' GetURLContentsAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    ' The actions from the foreach loop are moved to this async method.
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                ' CopyToAsync returns a Task, not a Task<T>.
                Await responseStream.CopyToAsync(content)
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

## <a name="example"></a>Ejemplo

El código siguiente muestra las extensiones para el proyecto que usa el método `HttpClient.GetByteArrayAsync` para descargar el contenido de la web.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        ''<snippet7>
        'Dim total = 0
        'For Each url In urlList
        '    ' GetByteArrayAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    '<snippet31>
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
        '    '</snippet31>

        '    ' The following two lines can replace the previous assignment statement.
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://www.msdn.com",
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

    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
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

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
