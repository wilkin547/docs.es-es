---
title: "Cancelar tareas asincrónicas tras un período de tiempo (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6708bd92d8dc2455b9dcb8e02dcc0a4455e00cda
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>Cancelar tareas asincrónicas tras un período de tiempo (Visual Basic)
Puede cancelar una operación asincrónica después de un período de tiempo utilizando la <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>método si no desea esperar a que termine la operación.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> Este método programa la cancelación de las tareas asociadas que están incompletas en el período de tiempo designado por el `CancelAfter` expresión.  
  
 En este ejemplo se agrega al código que se desarrolla en [cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) para descargar una lista de sitios Web y mostrar la longitud del contenido de cada uno de ellos.  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalado en su equipo.  
  
## <a name="downloading-the-example"></a>Descargar el ejemplo  
 Puede descargar el proyecto de Windows Presentation Foundation (WPF) completo de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046) y, a continuación, siga estos pasos.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  En el **Abrir proyecto** cuadro de diálogo, abra la carpeta que contiene el código de ejemplo descomprime y, a continuación, abra el archivo de solución (.sln) para AsyncFineTuningVB.  
  
4.  En **el Explorador de soluciones**, abra el menú contextual para el **CancelAfterTime** del proyecto y, a continuación, elija **establecer como proyecto de inicio**.  
  
5.  Elija la tecla F5 para ejecutar el proyecto.  
  
     Presione las teclas Ctrl + F5 para ejecutar el proyecto sin depurarlo.  
  
6.  Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios Web, no hay sitios Web o algunos sitios web.  
  
 Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.  
  
## <a name="building-the-example"></a>Compilar el ejemplo  
 El ejemplo de este tema se agrega al proyecto que se desarrolla en [cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) para cancelar una lista de tareas. El ejemplo utiliza la interfaz de usuario, aunque el **cancelar** botón no se utiliza explícitamente.  
  
 Para generar el ejemplo usted mismo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como el **proyecto de inicio**. Agregue los cambios en este tema para ese proyecto.  
  
 Para especificar un tiempo máximo antes de que las tareas se marcan como canceladas, agregue una llamada a `CancelAfter` a `startButton_Click`, como se muestra en el ejemplo siguiente. La adición se marca con asteriscos.  
  
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
  
 Ejecute el programa varias veces para comprobar que la salida puede mostrar resultados para todos los sitios Web, no hay sitios Web o algunos sitios web. La salida siguiente es un ejemplo.  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a>Ejemplo completo  
 El código siguiente es el texto completo del archivo MainWindow.xaml.vb para el ejemplo. Asteriscos marcan los elementos que se agregaron para este ejemplo.  
  
 Tenga en cuenta que debe agregar una referencia para <xref:System.Net.Http>.</xref:System.Net.Http>  
  
 Puede descargar el proyecto de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Tutorial: Acceso a la Web usando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)   
 [Ajustar una aplicación asincrónica (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Ejemplo ASYNC: Ajustar la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046)
