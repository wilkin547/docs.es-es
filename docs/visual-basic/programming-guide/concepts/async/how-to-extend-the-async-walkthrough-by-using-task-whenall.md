---
title: "Cómo: ampliar el tutorial de Async usando Task.WhenAll (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
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
ms.openlocfilehash: 46c5cb9328f2fa1a4ffc5116d318bc3286419e13
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>Cómo: ampliar el tutorial de Async usando Task.WhenAll (Visual Basic)
Puede mejorar el rendimiento de la solución de async en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) utilizando el <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>método.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Este método espera asincrónica varias operaciones asincrónicas, que se representan como una colección de tareas.  
  
 Habrá observado en el tutorial que descarguen los sitios Web a distintas tasas. A veces uno de los sitios Web es muy lento, lo que retrasa las descargas restantes. Cuando se ejecuta las soluciones asincrónicas que se compilación en el tutorial, puede finalizar el programa fácilmente si no desea esperar, pero sería una mejor opción iniciar las descargas al mismo tiempo y dejar más rápido que descargas continúen sin esperar a que se retrasa.  
  
 Aplicar el `Task.WhenAll` método a una colección de tareas. La aplicación de `WhenAll` devuelve una única tarea que no está completa hasta que se complete cada tarea en la colección. Se muestran las tareas ejecutar en paralelo, pero no hay subprocesos adicionales se crean. Pueden completar las tareas en cualquier orden.  
  
> [!IMPORTANT]
>  Los procedimientos siguientes describen las extensiones para las aplicaciones asincrónicas que se desarrollan en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Puede desarrollar las aplicaciones realizar el tutorial o descargar el código de [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=255191).  
>   
>  Para ejecutar el ejemplo, debe tener Visual Studio 2012 o posterior instalado en su equipo.  
  
### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>Para agregar Task.WhenAll a la solución GetURLContentsAsync  
  
1.  Agregue el `ProcessURLAsync` método a la primera aplicación que se desarrolla en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    -   Si descargó el código de [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=255191), abra el proyecto AsyncWalkthrough y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow.xaml.vb.  
  
    -   Si el código desarrollado por completar el tutorial, agregue `ProcessURLAsync` a la aplicación que incluye el `GetURLContentsAsync` método. El archivo MainWindow.xaml.vb para esta aplicación es el primer ejemplo en la sección "Código ejemplos desde el tutorial completo".  
  
     El `ProcessURLAsync` método consolida las acciones en el cuerpo de la `For Each` un bucle en `SumPageSizesAsync` en el tutorial original. El método de forma asincrónica descarga el contenido de un sitio Web especificado como una matriz de bytes y, a continuación, muestra y devuelve la longitud de la matriz de bytes.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)  
  
        Dim byteArray = Await GetURLContentsAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  Convierta en comentario o elimine la `For Each` un bucle en `SumPageSizesAsync`, como se muestra en el código siguiente.  
  
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
  
3.  Crear una colección de tareas. El código siguiente define una [consulta](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) que, cuando ejecute el <xref:System.Linq.Enumerable.ToArray%2A>método, se crea una colección de tareas que descargar el contenido de cada sitio Web.</xref:System.Linq.Enumerable.ToArray%2A> Las tareas se inician cuando se evalúa la consulta.  
  
     Agregue el código siguiente al método `SumPageSizesAsync` después de la declaración de `urlList`.  
  
    ```vb  
    ' Create a query.   
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  Aplicar `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll`Devuelve una única tarea que finaliza cuando se hayan completado todas las tareas de la colección de tareas.  
  
     En el ejemplo siguiente, la `Await` expresión espera la finalización de la única tarea que `WhenAll` devuelve. La expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio Web descargado. Agregue el código siguiente a `SumPageSizesAsync`, simplemente después del código que agregó en el paso anterior.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  Por último, utilice la <xref:System.Linq.Enumerable.Sum%2A>método para calcular la suma de las longitudes de todas las páginas Web.</xref:System.Linq.Enumerable.Sum%2A> Agregue la línea siguiente a `SumPageSizesAsync`.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>Para agregar Task.WhenAll a la solución HttpClient.GetByteArrayAsync  
  
1.  Agregue la siguiente versión de `ProcessURLAsync` a la segunda aplicación que se desarrolla en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    -   Si descargó el código de [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=255191), abra el proyecto AsyncWalkthrough_HttpClient y, a continuación, agregue `ProcessURLAsync` al archivo MainWindow.xaml.vb.  
  
    -   Si el código desarrollado por completar el tutorial, agregue `ProcessURLAsync` a la aplicación que utiliza la `HttpClient.GetByteArrayAsync` (método). El archivo MainWindow.xaml.vb para esta aplicación es el segundo ejemplo de la sección "Código ejemplos desde el tutorial completo".  
  
     El `ProcessURLAsync` método consolida las acciones en el cuerpo de la `For Each` un bucle en `SumPageSizesAsync` en el tutorial original. El método de forma asincrónica descarga el contenido de un sitio Web especificado como una matriz de bytes y, a continuación, muestra y devuelve la longitud de la matriz de bytes.  
  
     La única diferencia respecto a la `ProcessURLAsync` método en el procedimiento anterior es el uso de la <xref:System.Net.Http.HttpClient>instancia, `client`.</xref:System.Net.Http.HttpClient>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
    ```  
  
2.  Convierta en comentario o elimine la `For Each` un bucle en `SumPageSizesAsync`, como se muestra en el código siguiente.  
  
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
  
3.  Definir una [consulta](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) que, cuando ejecute el <xref:System.Linq.Enumerable.ToArray%2A>método, se crea una colección de tareas que descargar el contenido de cada sitio Web.</xref:System.Linq.Enumerable.ToArray%2A> Las tareas se inician cuando se evalúa la consulta.  
  
     Agregue el código siguiente al método `SumPageSizesAsync` después de la declaración de `client` y `urlList`.  
  
    ```vb  
    ' Create a query.  
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
        From url In urlList Select ProcessURLAsync(url, client)  
  
    ' Use ToArray to execute the query and start the download tasks.  
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
    ```  
  
4.  A continuación, aplique `Task.WhenAll` a la colección de tareas, `downloadTasks`. `Task.WhenAll`Devuelve una única tarea que finaliza cuando se hayan completado todas las tareas de la colección de tareas.  
  
     En el ejemplo siguiente, la `Await` expresión espera la finalización de la única tarea que `WhenAll` devuelve. Cuando haya finalizado, el `Await` expresión se evalúa como una matriz de enteros, donde cada entero es la longitud de un sitio Web descargado. Agregue el código siguiente a `SumPageSizesAsync`, simplemente después del código que agregó en el paso anterior.  
  
    ```vb  
    ' Await the completion of all the running tasks.  
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)  
  
    '' The previous line is equivalent to the following two statements.  
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)  
    'Dim lengths As Integer() = Await whenAllTask  
    ```  
  
5.  Por último, utilice la <xref:System.Linq.Enumerable.Sum%2A>método para obtener la suma de las longitudes de todas las páginas Web.</xref:System.Linq.Enumerable.Sum%2A> Agregue la línea siguiente a `SumPageSizesAsync`.  
  
    ```vb  
    Dim total = lengths.Sum()  
    ```  
  
### <a name="to-test-the-taskwhenall-solutions"></a>Para probar las soluciones Task.WhenAll  
  
-   Para cualquier solución, elija la tecla F5 para ejecutar el programa y, a continuación, elija la **iniciar** botón. El resultado debe ser similar de las soluciones de async en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sin embargo, tenga en cuenta que los sitios Web aparecen en un orden diferente cada vez.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra las extensiones para el proyecto que usa el `GetURLContentsAsync` método para descargar el contenido de la web.  
  
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
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
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
                "http://www.msdn.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName></xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>   
 [Tutorial: Acceso a la Web usando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
