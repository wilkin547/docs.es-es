---
title: "Cancelar una tarea asincrónica o una lista de tareas (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a>Cancelar una tarea asincrónica o una lista de tareas (Visual Basic)
Puede configurar un botón que puede usar para cancelar una aplicación asincrónica si no desea esperar a que finalice. Al seguir los ejemplos de este tema, puede agregar un botón de cancelación para una aplicación que descarga el contenido de un sitio Web o una lista de sitios Web.  
  
 Los ejemplos utilizan la interfaz de usuario que [Fine su aplicación de Async (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) describe.  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
##  <a name="BKMK_CancelaTask"></a>Cancelar una tarea  
 El primer ejemplo se asocia el **cancelar** botón con una tarea única descarga. Si elige el botón mientras la aplicación descarga el contenido, se cancela la descarga.  
  
### <a name="downloading-the-example"></a>Descargar el ejemplo  
 Puede descargar el proyecto de Windows Presentation Foundation (WPF) completo de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046) y, a continuación, siga estos pasos.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  En el **Abrir proyecto** cuadro de diálogo, abra la carpeta que contiene el código de ejemplo descomprime y, a continuación, abra el archivo de solución (.sln) para AsyncFineTuningVB.  
  
4.  En **el Explorador de soluciones**, abra el menú contextual para el **CancelATask** del proyecto y, a continuación, elija **establecer como proyecto de inicio**.  
  
5.  Elija la tecla F5 para ejecutar el proyecto.  
  
     Presione las teclas Ctrl + F5 para ejecutar el proyecto sin depurarlo.  
  
 Si no desea descargar el proyecto, puede revisar los archivos MainWindow.xaml.vb al final de este tema.  
  
### <a name="building-the-example"></a>Compilar el ejemplo  
 Agregan los siguientes cambios un **cancelar** botón a una aplicación que descarga un sitio Web. Si no desea descargar o generar el ejemplo, puede revisar el producto final en la sección "Ejemplos completos" al final de este tema. Asteriscos marcan los cambios en el código.  
  
 Para generar el ejemplo usted mismo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **StarterCode** como el **proyecto de inicio** en lugar de **CancelATask**.  
  
 A continuación, agregue los siguientes cambios en el archivo MainWindow.xaml.vb de ese proyecto.  
  
1.  Declarar un `CancellationTokenSource` variable, `cts`, en el ámbito para todos los métodos que tienen acceso a él.  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  Agregue el siguiente controlador de eventos para el **cancelar** botón. El controlador de eventos utiliza el <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>método para informar a `cts` cuando el usuario solicita la cancelación.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  Realice los siguientes cambios en el evento controlador para la **iniciar** botón, `startButton_Click`.  
  
    -   Crear una instancia de la `CancellationTokenSource`, `cts`.  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   En la llamada a `AccessTheWebAsync`, que descarga el contenido de un sitio Web especificado, enviar el <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>propiedad de `cts` como argumento.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> El `Token` propiedad propaga el mensaje si se solicita la cancelación. Agregue un bloque catch que muestra un mensaje si el usuario decide cancelar la operación de descarga. El código siguiente muestra los cambios.  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  En `AccessTheWebAsync`, utilice el <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>sobrecarga de la `GetAsync` método en el <xref:System.Net.Http.HttpClient>tipo para descargar el contenido de un sitio Web.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> Pasar `ct`, el <xref:System.Threading.CancellationToken>parámetro de `AccessTheWebAsync`, como el segundo argumento.</xref:System.Threading.CancellationToken> El token lleva el mensaje si el usuario elige el **cancelar** botón.  
  
     El código siguiente muestra los cambios en `AccessTheWebAsync`.  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  Si no cancela el programa, produce el siguiente resultado.  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     Si elige la **cancelar** botón antes de que el programa termina de descargar el contenido, el programa produce el siguiente resultado.  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <a name="BKMK_CancelaListofTasks"></a>Cancelar una lista de tareas  
 Puede ampliar el ejemplo anterior para cancelar muchas tareas asociando el mismo `CancellationTokenSource` instancia con cada tarea. Si elige la **cancelar** botón, cancela todas las tareas que aún no están completadas.  
  
### <a name="downloading-the-example"></a>Descargar el ejemplo  
 Puede descargar el proyecto de Windows Presentation Foundation (WPF) completo de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046) y, a continuación, siga estos pasos.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  En el **Abrir proyecto** cuadro de diálogo, abra la carpeta que contiene el código de ejemplo descomprime y, a continuación, abra el archivo de solución (.sln) para AsyncFineTuningVB.  
  
4.  En **el Explorador de soluciones**, abra el menú contextual para el **CancelAListOfTasks** del proyecto y, a continuación, elija **establecer como proyecto de inicio**.  
  
5.  Elija la tecla F5 para ejecutar el proyecto.  
  
     Presione las teclas Ctrl + F5 para ejecutar el proyecto sin depurarlo.  
  
 Si no desea descargar el proyecto, puede revisar los archivos MainWindow.xaml.vb al final de este tema.  
  
### <a name="building-the-example"></a>Compilar el ejemplo  
 Para ampliar el ejemplo usted mismo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelATask** como el **proyecto de inicio**. Agregue los siguientes cambios a ese proyecto. Asteriscos marcan los cambios en el programa.  
  
1.  Agregue un método para crear una lista de las direcciones web.  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
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
    ```  
  
2.  Llame al método `AccessTheWebAsync`.  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  Agregue el siguiente bucle en `AccessTheWebAsync` para procesar cada dirección web en la lista.  
  
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
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  Porque `AccessTheWebAsync` muestra las longitudes, el método no es necesario devolver nada. Quite la instrucción return y cambie el tipo de valor devuelto del método a <xref:System.Threading.Tasks.Task>en lugar de <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
     Llame al método desde `startButton_Click` mediante una instrucción en lugar de una expresión.  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  Si no cancela el programa, produce el siguiente resultado.  
  
    ```  
  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
  
    ```  
  
     Si elige la **cancelar** botón antes de las descargas, la salida contiene las longitudes de las descargas que se completó antes de la cancelación.  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <a name="BKMK_CompleteExamples"></a>Ejemplos completos  
 Las secciones siguientes contienen el código para cada uno de los ejemplos anteriores. Tenga en cuenta que debe agregar una referencia para <xref:System.Net.Http>.</xref:System.Net.Http>  
  
 Puede descargar los proyectos de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
### <a name="cancel-a-task-example"></a>Cancelar un tarea de ejemplo  
 El código siguiente es el archivo MainWindow.xaml.vb completo para el ejemplo que se cancela una tarea individual.  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
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
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
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
  
### <a name="cancel-a-list-of-tasks-example"></a>Cancelar una lista de ejemplo de tareas  
 El código siguiente es el archivo MainWindow.xaml.vb completo para el ejemplo que se cancela una lista de tareas.  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
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
 <xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource>   
 <xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken>   
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Ajustar una aplicación asincrónica (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Ejemplo ASYNC: Ajustar la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046)
