---
title: Cancelar una tarea asincrónica o una lista de tareas
ms.date: 07/20/2015
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
ms.openlocfilehash: 2956582cd0c8e044fcd37ffab13686489a7c854c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347969"
---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a>Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)

Puede configurar un botón para cancelar una aplicación asincrónica si no quiere esperar a que termine. Mediante los ejemplos de este tema, puede agregar un botón de cancelación a una aplicación que descargue el contenido de un sitio web o una lista de sitios web.

En los ejemplos se usa la interfaz de usuario que describe la [optimización de la aplicación asincrónica (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) .

> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.

## <a name="BKMK_CancelaTask"></a> Cancelar una tarea

En el primer ejemplo se asocia el botón **Cancelar** a una sola tarea de descarga. Si elige el botón mientras la aplicación descarga contenido, se cancela la descarga.

### <a name="downloading-the-example"></a>Descargar el ejemplo

Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) y después seguir estos pasos.

1. Descomprima el archivo descargado y, a continuación, inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.

3. En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.

4. En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelATask** y, después, elija **Establecer como proyecto de inicio**.

5. Pulse la tecla F5 para ejecutar el proyecto.

     Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.

 Si no desea descargar el proyecto, puede revisar los archivos MainWindow. Xaml. VB que se encuentra al final de este tema.

### <a name="building-the-example"></a>Compilar el ejemplo

Los cambios siguientes agregan un botón **Cancelar** a una aplicación que descarga un sitio web. Si no quiere descargar ni generar el ejemplo, puede revisar el producto final en la sección "Ejemplos completos" al final de este tema. Los cambios en el código se marcan con asteriscos.

Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **StarterCode** como **Proyecto de inicio** en lugar de **CancelATask**.

Después, agregue los siguientes cambios al archivo MainWindow. Xaml. VB de ese proyecto.

1. Declare una variable de `CancellationTokenSource`, `cts`, que esté en el ámbito de todos los métodos que acceden a ella.

    ```vb
    Class MainWindow

        ' ***Declare a System.Threading.CancellationTokenSource.
        Dim cts As CancellationTokenSource
    ```

2. Agregue el controlador de eventos siguiente para el botón **Cancelar**. El controlador de eventos usa el método <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> para notificar `cts` cuando el usuario solicita la cancelación.

    ```vb
    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub
    ```

3. Realice los siguientes cambios en el controlador de eventos para el botón **Iniciar**, `startButton_Click`.

    - Cree una instancia de `CancellationTokenSource`, `cts`.

      ```vb
      ' ***Instantiate the CancellationTokenSource.
      cts = New CancellationTokenSource()
      ```

    - En la llamada a `AccessTheWebAsync`, que descarga el contenido de un sitio web especificado, envíe la propiedad <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> de `cts` como un argumento. La propiedad `Token` propaga el mensaje si se solicita la cancelación. Agregue un bloque catch que muestre un mensaje si el usuario decide cancelar la operación de descarga. En el código siguiente se muestran los cambios.

      ```vb
      Try
          ' ***Send a token to carry the message if cancellation is requested.
          Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

          resultsTextBox.Text &=
              vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

          ' *** If cancellation is requested, an OperationCanceledException results.
      Catch ex As OperationCanceledException
          resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

      Catch ex As Exception
          resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
      End Try
      ```

4. En `AccessTheWebAsync`, use la sobrecarga <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=nameWithType> del método `GetAsync` en el tipo <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web. Pase `ct`, el parámetro <xref:System.Threading.CancellationToken> de `AccessTheWebAsync`, como el segundo argumento. El token lleva el mensaje si el usuario elige el botón **Cancelar**.

    En el código siguiente se muestran los cambios en `AccessTheWebAsync`.

    ```vb
    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &= vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
    ```

5. Si no cancela el programa, se genera el siguiente resultado:

    ```console
    Ready to download.
    Length of the downloaded string: 158125.
    ```

    Si elige el botón **Cancelar** antes de que el programa termine de descargar el contenido, el programa genera el siguiente resultado:

    ```console
    Ready to download.
    Download canceled.
    ```

## <a name="BKMK_CancelaListofTasks"></a> Cancelar una lista de tareas

Puede ampliar el ejemplo anterior para cancelar muchas tareas asociando la misma instancia de `CancellationTokenSource` a cada tarea. Si elige el botón **Cancelar**, cancela todas las tareas que aún no se han completado.

### <a name="downloading-the-example"></a>Descargar el ejemplo

Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) y después seguir estos pasos.

1. Descomprima el archivo descargado y, a continuación, inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.

3. En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.

4. En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAListOfTasks** y, después, elija **Establecer como proyecto de inicio**.

5. Pulse la tecla F5 para ejecutar el proyecto.

     Pulse las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.

 Si no desea descargar el proyecto, puede revisar los archivos MainWindow. Xaml. VB que se encuentra al final de este tema.

### <a name="building-the-example"></a>Compilar el ejemplo

Para ampliar el ejemplo personalmente, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelATask** como el **Proyecto de inicio**. Agregue los siguientes cambios a ese proyecto. Los cambios en el programa se marcan con asteriscos.

1. Agregue un método para crear una lista de direcciones web.

    ```vb
    ' ***Add a method that creates a list of web addresses.
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
    ```

2. Llame al método en `AccessTheWebAsync`.

    ```vb
    ' ***Call SetUpURLList to make a list of web addresses.
    Dim urlList As List(Of String) = SetUpURLList()
    ```

3. Agregue el siguiente bucle en `AccessTheWebAsync` para procesar cada dirección web de la lista.

    ```vb
    ' ***Add a loop to process the list of web addresses.
    For Each url In urlList
        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' Argument ct carries the message if the Cancel button is chosen.
        ' ***Note that the Cancel button can cancel all remaining downloads.
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        resultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
    Next
    ```

4. Como `AccessTheWebAsync` muestra las duraciones, el método no tiene que devolver nada. Quite la instrucción Return y cambie el tipo de valor devuelto del método a <xref:System.Threading.Tasks.Task> en lugar de <xref:System.Threading.Tasks.Task%601>.

    ```vb
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task
    ```

    Llame al método desde `startButton_Click` mediante una instrucción en lugar de una expresión.

    ```vb
    Await AccessTheWebAsync(cts.Token)
    ```

5. Si no cancela el programa, se genera el siguiente resultado:

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Length of the downloaded string: 158124.

    Length of the downloaded string: 204890.

    Length of the downloaded string: 175488.

    Length of the downloaded string: 145790.

    Downloads complete.
    ```

    Si elige el botón **Cancelar** antes de que se completen las descargas, la salida contiene las duraciones de las descargas completadas antes de la cancelación.

    ```console
    Length of the downloaded string: 35939.

    Length of the downloaded string: 237682.

    Length of the downloaded string: 128607.

    Downloads canceled.
    ```

## <a name="BKMK_CompleteExamples"></a> Ejemplos completos

Las secciones siguientes contienen el código para cada uno de los ejemplos anteriores. Observe que debe agregar una referencia para <xref:System.Net.Http>.

Puede descargar los proyectos en [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

### <a name="cancel-a-task-example"></a>Ejemplo de cancelación de una tarea

El código siguiente es el archivo MainWindow. Xaml. VB completo para el ejemplo que cancela una sola tarea.

```vb
' Add an Imports directive and a reference for System.Net.Http.
Imports System.Net.Http

' Add the following Imports directive for System.Threading.
Imports System.Threading

Class MainWindow

    ' ***Declare a System.Threading.CancellationTokenSource.
    Dim cts As CancellationTokenSource

    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)
        ' ***Instantiate the CancellationTokenSource.
        cts = New CancellationTokenSource()

        resultsTextBox.Clear()

        Try
            ' ***Send a token to carry the message if cancellation is requested.
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

            ' *** If cancellation is requested, an OperationCanceledException results.
        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf
        End Try

        ' ***Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' ***Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' ***Provide a parameter for the CancellationToken.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)

        Dim client As HttpClient = New HttpClient()

        resultsTextBox.Text &=
            vbCrLf & "Ready to download." & vbCrLf

        ' You might need to slow things down to have a chance to cancel.
        Await Task.Delay(250)

        ' GetAsync returns a Task(Of HttpResponseMessage).
        ' ***The ct argument carries the message if the Cancel button is chosen.
        Dim response As HttpResponseMessage = Await client.GetAsync("https://msdn.microsoft.com/library/dd470362.aspx", ct)

        ' Retrieve the website contents from the HttpResponseMessage.
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

        ' The result of the method is the length of the downloaded website.
        Return urlContents.Length
    End Function
End Class

' Output for a successful download:

' Ready to download.

' Length of the downloaded string: 158125.

' Or, if you cancel:

' Ready to download.

' Download canceled.
```

### <a name="cancel-a-list-of-tasks-example"></a>Ejemplo de cancelación de una lista de tareas

El código siguiente es el archivo MainWindow. Xaml. VB completo para el ejemplo que cancela una lista de tareas.

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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).
            Await AccessTheWebAsync(cts.Token)
            '  ***Small change in the display lines.
            resultsTextBox.Text &= vbCrLf & "Downloads complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
        End Try

        ' Set the CancellationTokenSource to Nothing when the download is complete.
        cts = Nothing
    End Sub

    ' Add an event handler for the Cancel button.
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)

        If cts IsNot Nothing Then
            cts.Cancel()
        End If
    End Sub

    ' Provide a parameter for the CancellationToken.
    ' ***Change the return type to Task because the method has no return statement.
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task

        Dim client As HttpClient = New HttpClient()

        ' ***Call SetUpURLList to make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' ***Add a loop to process the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' ***Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
    End Function

    ' ***Add a method that creates a list of web addresses.
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

' Output if you do not choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Length of the downloaded string: 158124.

' Length of the downloaded string: 204890.

' Length of the downloaded string: 175488.

' Length of the downloaded string: 145790.

' Downloads complete.

'  Sample output if you choose to cancel:

' Length of the downloaded string: 35939.

' Length of the downloaded string: 237682.

' Length of the downloaded string: 128607.

' Downloads canceled.
```

## <a name="see-also"></a>Vea también

- <xref:System.Threading.CancellationTokenSource>
- <xref:System.Threading.CancellationToken>
- [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])
- [Ejemplo de async: Ajuste de la aplicación](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
