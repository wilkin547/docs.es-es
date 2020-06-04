---
title: Cancelar las tareas asincrónicas restantes cuando se completa una
ms.date: 07/20/2015
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
ms.openlocfilehash: be716e98263c865adad3c197236467b2f48d7740
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396680"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a>Cancel Remaining Async Tasks after One Is Complete (Visual Basic) (Cancelación de tareas asincrónicas restantes [Visual Basic])

Mediante el método <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> junto con <xref:System.Threading.CancellationToken>, puede cancelar todas las tareas restantes cuando se completa una tarea. El método `WhenAny` toma un argumento que es una colección de tareas. El método inicia todas las tareas y devuelve una sola tarea. La tarea se completa cuando se complete cualquier tarea de la colección.

En este ejemplo se muestra cómo usar un token de cancelación junto con `WhenAny` para retener la primera tarea para finalizar de la colección de tareas y cancelar las tareas restantes. Cada tarea descarga el contenido de un sitio web. En el ejemplo se muestra la longitud del contenido de la primera descarga completa y se cancelan las otras descargas.

> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior, y .NET Framework 4.5 o posterior, instalado en el equipo.

## <a name="downloading-the-example"></a>Descargar el ejemplo

Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]) y después seguir estos pasos.

1. Descomprima el archivo descargado y, a continuación, inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.

3. En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.

4. En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterOneTask** y, después, elija **Establecer como proyecto de inicio**.

5. Pulse la tecla F5 para ejecutar el proyecto.

    Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.

6. Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.

Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.

## <a name="building-the-example"></a>Compilar el ejemplo

En el ejemplo de este tema se agrega al proyecto desarrollado en [cancelar una tarea asincrónica o una lista de tareas](cancel-an-async-task-or-a-list-of-tasks.md) para cancelar una lista de tareas. En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.

Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**. Agregue los cambios de este tema a ese proyecto.

En el archivo MainWindow. Xaml. VB del proyecto **CancelAListOfTasks** , inicie la transición moviendo los pasos de procesamiento de cada sitio web del bucle `AccessTheWebAsync` al siguiente método asincrónico.

```vb
' ***Bundle the processing steps for a website into one async method.
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

    ' GetAsync returns a Task(Of HttpResponseMessage).
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

    ' Retrieve the website contents from the HttpResponseMessage.
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

    Return urlContents.Length
End Function
```

En `AccessTheWebAsync`, este ejemplo usa una consulta, el método <xref:System.Linq.Enumerable.ToArray%2A> y el método `WhenAny` para crear e iniciar una matriz de tareas. La aplicación de `WhenAny` a la matriz devuelve una única tarea que, cuando se espera, se evalúa como la primera tarea que llega a la finalización de la matriz de tareas.

Realice los siguientes cambios en `AccessTheWebAsync`. Los asteriscos marcan los cambios en el archivo de código.

1. Convierta en comentario o elimine el bucle.

2. Cree una consulta que, cuando se ejecute, genere una colección de tareas genéricas. Cada llamada a `ProcessURLAsync` devuelve un <xref:System.Threading.Tasks.Task%601> donde `TResult` es un entero.

    ```vb
    ' ***Create a query that, when executed, returns a collection of tasks.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client, ct)
    ```

3. Llame a `ToArray` para ejecutar la consulta e iniciar las tareas. La aplicación del método `WhenAny` en el paso siguiente ejecutaría la consulta e iniciaría las tareas sin usar `ToArray`, pero es posible que otros métodos no lo hagan. La práctica más segura es forzar explícitamente la ejecución de la consulta.

    ```vb
    ' ***Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Llame a `WhenAny` en la colección de tareas. `WhenAny` devuelve una `Task(Of Task(Of Integer))` o `Task<Task<int>>`.  Es decir, `WhenAny` devuelve una tarea que se evalúa como una única `Task(Of Integer)` o `Task<int>` cuando se espera. Esa única tarea es la primera tarea de la colección en finalizar. La tarea que finalizó primero se asigna a `firstFinishedTask`. El tipo de `firstFinishedTask` es <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero, ya que es el tipo de valor devuelto de `ProcessURLAsync`.

    ```vb
    ' ***Call WhenAny and then await the result. The task that finishes
    ' first is assigned to firstFinishedTask.
    Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)
    ```

5. En este ejemplo, solo le interesa la tarea que finaliza primero. Por lo tanto, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> para cancelar las tareas restantes.

    ```vb
    ' ***Cancel the rest of the downloads. You just want the first one.
    cts.Cancel()
    ```

6. Por último, espere a `firstFinishedTask` para recuperar la longitud del contenido descargado.

    ```vb
    Dim length = Await firstFinishedTask
    resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    ```

Ejecute el programa varias veces para comprobar que finalizan primero descargas diferentes.

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el archivo completo MainWindow. Xaml. vb o MainWindow.xaml.cs para el ejemplo. Los asteriscos marcan los elementos que se han agregado a este ejemplo.

Observe que debe agregar una referencia para <xref:System.Net.Http>.

Puede descargar el proyecto de [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]).

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
            resultsTextBox.Text &= vbCrLf & "Download complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
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

        '' Comment out or delete the loop.
        ''For Each url In urlList
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).
        ''    ' Argument ct carries the message if the Cancel button is chosen.
        ''    ' Note that the Cancel button can cancel all remaining downloads.
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ''    ' Retrieve the website contents from the HttpResponseMessage.
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ''    resultsTextBox.Text &=
        ''        vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        ''Next

        ' ***Create a query that, when executed, returns a collection of tasks.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client, ct)

        ' ***Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' ***Call WhenAny and then await the result. The task that finishes
        ' first is assigned to firstFinishedTask.
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)

        ' ***Cancel the rest of the downloads. You just want the first one.
        cts.Cancel()

        ' ***Await the first completed task and display the results
        ' Run the program several times to demonstrate that different
        ' websites can finish first.
        Dim length = Await firstFinishedTask
        resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    End Function

    ' ***Bundle the processing steps for a website into one async method.
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

' Length of the downloaded website:  158856

' Download complete.
```

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])
- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación)
