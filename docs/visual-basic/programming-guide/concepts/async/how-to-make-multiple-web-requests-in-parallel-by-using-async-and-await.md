---
title: "Cómo: hacer varias solicitudes Web en paralelo utilizando Async y Await (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
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
ms.openlocfilehash: e4c41cc3813a9f96d944d115c6aaa5c5842a629b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>Cómo: hacer varias solicitudes Web en paralelo utilizando Async y Await (Visual Basic)
En un método asincrónico, se inician las tareas cuando se crean. El [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operador se aplica a la tarea en el punto en el método que no puede continuar el procesamiento hasta que finalice la tarea. A menudo se espera un task en cuanto se crea, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 Sin embargo, puede separar la creación de la tarea de esperar la tarea si el programa tiene otro trabajo para lograr que no dependa de la finalización de la tarea.  
  
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
  
 Entre el inicio de una tarea y esperar, puede iniciar otras tareas. Las tareas adicionales se ejecutan implícitamente en paralelo, pero no hay subprocesos adicionales se crean.  
  
 El programa siguiente inicia tres descargas de web asincrónica y, a continuación, los awaits en el orden en el que se llaman. Observe, al ejecutar el programa, que siempre no finalizan las tareas en el orden en que fueron creadas y esperados. Empiezan a funcionar cuando se crean y uno o más de las tareas podrían finalizar antes de que el método alcanza las expresiones await.  
  
> [!NOTE]
>  Para completar este proyecto, debe tener Visual Studio 2012 o posterior y .NET Framework 4.5 o posterior instalado en el equipo.  
  
 Para obtener otro ejemplo que inicia varias tareas al mismo tiempo, consulte [Cómo: Extender la Async Walkthrough por usando Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
 Puede descargar el código de este ejemplo desde [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=254906).  
  
### <a name="to-set-up-the-project"></a>Para configurar el proyecto  
  
1.  Para configurar una aplicación de WPF, complete los pasos siguientes. Puede encontrar instrucciones detalladas para realizar estos pasos en [Tutorial: obtener acceso a la Web mediante el uso de Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    -   Crear una aplicación WPF que contiene un cuadro de texto y un botón. Asígnele un nombre `startButton`y el cuadro de texto nombre `resultsTextBox`.  
  
    -   Agregue una referencia de <xref:System.Net.Http>.</xref:System.Net.Http>  
  
    -   En el archivo MainWindow.xaml.vb, agregue un `Imports` instrucción para `System.Net.Http`.  
  
### <a name="to-add-the-code"></a>Para agregar el código  
  
1.  En la ventana de diseño, MainWindow.xaml, haga doble clic en el botón para crear el `startButton_Click` MainWindow.xaml.vb de controlador de eventos.  
  
2.  Copie el código siguiente y péguelo en el cuerpo de `startButton_Click` en MainWindow.xaml.vb.  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     El código llama a un método asincrónico, `CreateMultipleTasksAsync`, lo que conduce a la aplicación.  
  
3.  Agregue los siguientes métodos de soporte técnico para el proyecto:  
  
    -   `ProcessURLAsync`utiliza un <xref:System.Net.Http.HttpClient>método para descargar el contenido de un sitio Web como una matriz de bytes.</xref:System.Net.Http.HttpClient> El método de soporte, `ProcessURLAsync` , a continuación, muestra y devuelve la longitud de la matriz.  
  
    -   `DisplayResults`Muestra el número de bytes en la matriz de bytes para cada dirección URL. Esta muestra se muestra cuando cada tarea ha terminado de descargarse.  
  
     Copie los siguientes métodos y pegarlos después de la `startButton_Click` MainWindow.xaml.vb de controlador de eventos.  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
4.  Por último, defina el método `CreateMultipleTasksAsync`, que realiza los pasos siguientes.  
  
    -   El método se declara un `HttpClient` objeto, que debe tener acceso a método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>en `ProcessURLAsync`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>  
  
    -   El método crea e inicia las tres tareas de tipo <xref:System.Threading.Tasks.Task%601>, donde `TResult` es un entero.</xref:System.Threading.Tasks.Task%601> Cuando finalice cada tarea, `DisplayResults` muestra la dirección URL de la tarea y la longitud del contenido descargado. Dado que las tareas ejecutan asincrónicamente, el orden en que aparecen los resultados pueden diferir del orden en que se declaran.  
  
    -   El método espera la finalización de cada tarea. Cada `Await` operador suspende la ejecución de `CreateMultipleTasksAsync` hasta que finalice la tarea esperada. El operador también recupera el valor devuelto de la llamada a `ProcessURLAsync` desde cada tarea completada.  
  
    -   Cuando las tareas se han completado y que se han recuperado los valores enteros, el método suma las longitudes de los sitios Web y muestra el resultado.  
  
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
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
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
  
5.  Presione la tecla F5 para ejecutar el programa y elija el botón **Inicio** .  
  
     Ejecute el programa varias veces para comprobar que las tres tareas no finalizan siempre en el mismo orden y que el orden en el que terminen no es necesariamente el orden en que fueron creadas y esperados.  
  
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
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Acceso a la Web usando Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Programación asincrónica con Async y Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Cómo: ampliar el tutorial de Async usando Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
