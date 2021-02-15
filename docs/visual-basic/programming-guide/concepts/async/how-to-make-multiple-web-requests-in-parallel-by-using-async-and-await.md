---
description: 'Más información sobre: Cómo: hacer varias solicitudes web en paralelo mediante Async y Await (Visual Basic)'
title: Procedimiento para realizar varias solicitudes web en paralelo con async y await
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: e1137424911b77ba94a760a4b4b034e45ef83462
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474348"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic) (Realización de solicitudes web en paralelo mediante Async y Await [Visual Basic])

En un método asincrónico, las tareas se inician en el momento de crearse. El operador [Await](../../../language-reference/operators/await-operator.md) se aplica a la tarea en el punto del método en el que el procesamiento no puede continuar hasta que finalice la tarea. A menudo se espera una tarea en cuanto se crea, como se muestra en el ejemplo siguiente.

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

Pero puede separar la creación de la tarea de la espera si el programa tiene otro trabajo por efectuar que no dependa de la finalización de la tarea.

```vb
' The following line creates and starts the task.
Dim myTask = someWebAccessMethodAsync(url)

' While the task is running, you can do other work that does not depend
' on the results of the task.
' . . . . .

' The application of Await suspends the rest of this method until the task is
' complete.
Dim result = Await myTask
```

Entre el inicio de una tarea y la espera puede iniciar otras tareas. Las tareas adicionales se ejecutan implícitamente en paralelo, pero no se crean subprocesos adicionales.

El programa siguiente inicia tres descargas web asincrónicas y las espera en el orden en el que se han llamado. Observe que, al ejecutar el programa, las tareas no siempre finalizan en el orden en que se han creado y esperado. Empiezan a ejecutarse en el momento de crearse y una o más tareas podrían finalizar antes de que el método llegue a las expresiones await.

> [!NOTE]
> Para llevar a cabo este proyecto, debe tener instalados en el equipo Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior.

Para ver otro ejemplo en el que se inician varias tareas al mismo tiempo, vea [Cómo: ampliar el tutorial de Async mediante Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).

Puede descargar el código de este ejemplo en [Muestras de código para desarrollador](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).

### <a name="to-set-up-the-project"></a>Para configurar el proyecto

1. Para configurar una aplicación WPF, lleve a cabo los siguientes pasos. Puede encontrar instrucciones detalladas para estos pasos en [Tutorial: acceso a la web mediante Async y Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).

    - Cree una aplicación WPF que contenga un cuadro de texto y un botón. Asigne al botón el nombre `startButton` y, al cuadro de texto, `resultsTextBox`.

    - Agregue una referencia para <xref:System.Net.Http>.

    - En el archivo MainWindow. Xaml. VB, agregue una `Imports` instrucción para `System.Net.Http` .

### <a name="to-add-the-code"></a>Para agregar el código

1. En la ventana de diseño, MainWindow. XAML, haga doble clic en el botón para crear el `startButton_Click` controlador de eventos en MainWindow. Xaml. VB.

2. Copie el código siguiente y péguelo en el cuerpo de `startButton_Click` en MainWindow. Xaml. VB.

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     El código llama a un método asincrónico, `CreateMultipleTasksAsync`, que dirige la aplicación.

3. Agregue los siguientes métodos de soporte técnico al proyecto:

    - `ProcessURLAsync` usa un método <xref:System.Net.Http.HttpClient> para descargar el contenido de un sitio web como una matriz de bytes. Luego, el método de soporte, `ProcessURLAsync`, muestra y devuelve la longitud de la matriz.

    - `DisplayResults` muestra el número de bytes de la matriz de bytes de cada dirección URL. En esta pantalla se muestra cuándo se ha terminado la descarga de cada tarea.

     Copie los métodos siguientes y péguelos después del `startButton_Click` controlador de eventos en MainWindow. Xaml. VB.

    ```vb
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
    ```

4. Por último, defina el método `CreateMultipleTasksAsync`, que lleva a cabo los siguientes pasos.

    - El método declara un objeto `HttpClient`, que necesita para tener acceso al método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> en `ProcessURLAsync`.

    - El método crea e inicia tres tareas de tipo <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero. A medida que finaliza cada tarea, `DisplayResults` muestra la dirección URL de la tarea y la longitud del contenido descargado. Dado que las tareas se ejecutan de manera asincrónica, el orden en que aparecen los resultados puede ser diferente del orden en que se han declarado.

    - El método espera la finalización de cada tarea. Cada operador `Await` suspende la ejecución de `CreateMultipleTasksAsync` hasta que finalice la tarea esperada. El operador también recupera el valor devuelto de la llamada a `ProcessURLAsync` desde cada tarea finalizada.

    - Una vez concluidas las tareas y recuperados los valores enteros, el método suma las longitudes de los sitios web y muestra el resultado.

     Copie el método siguiente y péguelo en la solución.

    ```vb
    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function
    ```

5. Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .

     Ejecute el programa varias veces para comprobar que las tres tareas no finalizan siempre en el mismo orden y que el orden en el que finalizan no es necesariamente el orden en que se han creado y esperado.

## <a name="example"></a>Ejemplo

El código siguiente contiene el ejemplo completo.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
        resultsTextBox.Clear()
        Await CreateMultipleTasksAsync()
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
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

- [Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Ampliación del tutorial de Async mediante Task.WhenAll [Visual Basic])
