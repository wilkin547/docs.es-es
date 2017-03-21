---
title: "Cancelar las tareas asincrónicas restantes cuando se una completa (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
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
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a>Cancelar las tareas asincrónicas restantes cuando se una completa (Visual Basic)
Mediante el uso de la <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>método junto con un <xref:System.Threading.CancellationToken>, puede cancelar todas las tareas restantes cuando se completa una tarea.</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> El `WhenAny` método toma un argumento que es una colección de tareas. El método inicia todas las tareas y devuelve una sola tarea. La tarea está completa cuando se complete cualquier tarea de la colección.  
  
 Este ejemplo muestra cómo utilizar un token de cancelación junto con `WhenAny` para retener la primera tarea para finalizar de la colección de tareas y cancelar las tareas restantes. Cada tarea descarga el contenido de un sitio Web. En el ejemplo se muestra la longitud del contenido de la primera descarga completa y cancela las otras descargas.  
  
> [!NOTE]
>  Para ejecutar los ejemplos, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior, instalado en el equipo.  
  
## <a name="downloading-the-example"></a>Descargar el ejemplo  
 Puede descargar el proyecto de Windows Presentation Foundation (WPF) completo de [ejemplo Async: bien para la optimización de la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046) y, a continuación, siga estos pasos.  
  
1.  Descomprima el archivo descargado y, a continuación, inicie Visual Studio.  
  
2.  En la barra de menús, elija **Archivo**, **Abrir**, **Proyecto o solución**.  
  
3.  En el **Abrir proyecto** cuadro de diálogo, abra la carpeta que contiene el código de ejemplo descomprime y, a continuación, abra el archivo de solución (.sln) para AsyncFineTuningVB.  
  
4.  En **el Explorador de soluciones**, abra el menú contextual para el **CancelAfterOneTask** del proyecto y, a continuación, elija **establecer como proyecto de inicio**.  
  
5.  Elija la tecla F5 para ejecutar el proyecto.  
  
     Presione las teclas Ctrl + F5 para ejecutar el proyecto sin depurarlo.  
  
6.  Ejecute el programa varias veces para comprobar que las diferentes descargas fin primero.  
  
 Si no desea descargar el proyecto, puede revisar el archivo MainWindow.xaml.vb al final de este tema.  
  
## <a name="building-the-example"></a>Compilar el ejemplo  
 El ejemplo de este tema se agrega al proyecto que se desarrolla en [cancelar una tarea asincrónica o una lista de tareas](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) para cancelar una lista de tareas. El ejemplo utiliza la interfaz de usuario, aunque el **cancelar** botón no se utiliza explícitamente.  
  
 Para generar el ejemplo usted mismo, paso a paso, siga las instrucciones de la sección "Descargar el ejemplo", pero elija **CancelAListOfTasks** como el **proyecto de inicio**. Agregue los cambios en este tema para ese proyecto.  
  
 En el archivo MainWindow.xaml.vb de la **CancelAListOfTasks** proyecto, inicie la transición moviendo los pasos de procesamiento para cada sitio Web desde el bucle en `AccessTheWebAsync` al siguiente método asincrónico.  
  
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
  
 En `AccessTheWebAsync`, este ejemplo utiliza una consulta, el <xref:System.Linq.Enumerable.ToArray%2A>(método) y el `WhenAny` método para crear e iniciar una matriz de tareas.</xref:System.Linq.Enumerable.ToArray%2A> La aplicación de `WhenAny` a la matriz devuelve una única tarea que, cuando se espera, se evalúa como la primera tarea para llegar a la finalización de la matriz de tareas.  
  
 Realice los siguientes cambios en `AccessTheWebAsync`. Asteriscos marcan los cambios en el archivo de código.  
  
1.  Convierta en comentario o elimine el bucle.  
  
2.  Crear una consulta que, cuando se ejecuta, genera una colección de tareas genéricas. Cada llamada a `ProcessURLAsync` devuelve un <xref:System.Threading.Tasks.Task%601>donde `TResult` es un entero.</xref:System.Threading.Tasks.Task%601>  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
3.  Llame a `ToArray` para ejecutar la consulta e iniciar las tareas. La aplicación de la `WhenAny` método en el paso siguiente sería ejecutar la consulta e iniciar las tareas sin usar `ToArray`, pero no otros métodos. La práctica más segura es forzar explícitamente la ejecución de la consulta.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
4.  Llamar a `WhenAny` en la colección de tareas. `WhenAny`Devuelve un `Task(Of Task(Of Integer))` o `Task<Task<int>>`.  Es decir, `WhenAny` devuelve una tarea que se evalúa como un único `Task(Of Integer)` o `Task<int>` cuando lo esperado. Esa única tarea es la primera tarea en la colección para finalizar. La tarea que finalizó primero se asigna a `firstFinishedTask`. El tipo de `firstFinishedTask` es <xref:System.Threading.Tasks.Task%601>donde `TResult` es un entero, ya que es el tipo de valor devuelto de `ProcessURLAsync`.</xref:System.Threading.Tasks.Task%601>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  En este ejemplo, le interesa solo en la tarea que finaliza primero. Por lo tanto, utilice <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>para cancelar las tareas restantes.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  Por último, await `firstFinishedTask` para recuperar la longitud del contenido descargado.  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 Ejecute el programa varias veces para comprobar que las diferentes descargas fin primero.  
  
## <a name="complete-example"></a>Ejemplo completo  
 El código siguiente es el archivo MainWindow.xaml.vb o MainWindow.xaml.cs completo para el ejemplo. Asteriscos marcan los elementos que se agregaron para este ejemplo.  
  
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
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
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
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
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
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [Ajustar una aplicación asincrónica (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Ejemplo ASYNC: Ajustar la aplicación](http://go.microsoft.com/fwlink/?LinkId=255046)
