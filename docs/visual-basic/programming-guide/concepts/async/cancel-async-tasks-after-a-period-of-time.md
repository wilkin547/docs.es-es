---
title: Cancelar tareas asincrónicas tras un período de tiempo
ms.date: 07/20/2015
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
ms.openlocfilehash: 048d4c19d459905ea579ede96c69230e718d55aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396693"
---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>Cancelación de tareas asincrónicas tras un período de tiempo (Visual Basic)

Puede cancelar una operación asincrónica después de un período de tiempo con el método <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType> si no quiere esperar a que finalice la operación. Este método programa la cancelación de las tareas asociadas que no se completen en el período de tiempo designado por la expresión `CancelAfter`.

Este ejemplo se agrega al código que se desarrolla en [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios web y mostrar la longitud del contenido de cada uno de ellos.

> [!NOTE]
> Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalados en el equipo.

## <a name="downloading-the-example"></a>Descargar el ejemplo

Puede descargar el proyecto completo de Windows Presentation Foundation (WPF) en [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación [C# y Visual Basic]) y después seguir estos pasos.

1. Descomprima el archivo descargado y, a continuación, inicie Visual Studio.

2. En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.

3. En el cuadro de diálogo **Abrir proyecto**, abra la carpeta que contiene el código de ejemplo que descomprimió y después abra el archivo de la solución (.sln) para AsyncFineTuningVB.

4. En el **Explorador de soluciones**, abra el menú contextual del proyecto **CancelAfterTime** y, después, elija **Establecer como proyecto de inicio**.

5. Pulse la tecla F5 para ejecutar el proyecto.

     Presione las teclas Ctrl+F5 para ejecutar el proyecto sin depurarlo.

6. Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web.

 Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.

## <a name="building-the-example"></a>Compilación del ejemplo

El ejemplo de este tema se agrega al proyecto que se desarrolla en [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) para cancelar una lista de tareas. En el ejemplo se usa la misma interfaz de usuario, aunque el botón **Cancelar** no se usa explícitamente.

Para generar su propio ejemplo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como **Proyecto de inicio**. Agregue los cambios de este tema a ese proyecto.

Para especificar un tiempo máximo antes de que las tareas se marquen como canceladas, agregue una llamada a `CancelAfter` en `startButton_Click`, tal y como se muestra en el ejemplo siguiente. La adición se marca con asteriscos.

```vb
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

    ' Instantiate the CancellationTokenSource.
    cts = New CancellationTokenSource()

    resultsTextBox.Clear()

    Try
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        ' can adjust the time.)
        cts.CancelAfter(2500)

        Await AccessTheWebAsync(cts.Token)
        resultsTextBox.Text &= vbCrLf & "Downloads complete."

    Catch ex As OperationCanceledException
        resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

    Catch ex As Exception
        resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
    End Try

    ' Set the CancellationTokenSource to Nothing when the download is complete.
    cts = Nothing
End Sub
```

Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios web, para ningún sitio web o para algunos sitios web. La siguiente salida es un ejemplo:

```console
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a>Ejemplo completo

El código siguiente es el texto completo del archivo MainWindow.xaml.vb para el ejemplo. Los asteriscos marcan los elementos que se han agregado a este ejemplo.

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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
            ' can adjust the time.)
            cts.CancelAfter(2500)

            Await AccessTheWebAsync(cts.Token)
            resultsTextBox.Text &= vbCrLf & "Downloads complete."

        Catch ex As OperationCanceledException
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf

        Catch ex As Exception
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf
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

        ' Process each element in the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
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

' Length of the downloaded string: 35990.

' Length of the downloaded string: 407399.

' Length of the downloaded string: 226091.

' Downloads canceled.
```

## <a name="see-also"></a>Vea también

- [Programación asincrónica con Async y Await (Visual Basic)](index.md)
- [Tutorial: Acceso a web usando Async y Await (C# y Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md) (Cancelación de una tarea asincrónica o de una lista de tareas [Visual Basic])
- [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Ajuste de una aplicación asincrónica [Visual Basic])
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Ejemplo asincrónico: Ajustar la aplicación)
