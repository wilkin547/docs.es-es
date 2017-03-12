---
title: "Async (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Async"
helpviewer_keywords: 
  - "Async [Visual Basic]"
  - "Async (palabra clave) [Visual Basic]"
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Async (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El modificador `Async` indica que el método o la [expresión lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) que modifica son asincrónicos.  Estos métodos se conocen como *métodos asincrónicos*.  
  
 Un método asincrónico proporciona una manera cómoda de hacer el trabajo de larga duración sin bloquear el subproceso del llamador.  El llamador de un método asincrónico puede reanudar el trabajo sin esperar a que el método asincrónico finalice.  
  
> [!NOTE]
>  Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.  Para obtener una introducción a la programación asincrónica, vea [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 En el siguiente ejemplo se muestra la estructura de un método asincrónico.  Por convención, los nombres de método asincrónico acaban en “Async”.  
  
```vb  
  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 Normalmente, un método modificado por la palabra clave `Async` contiene al menos una expresión o instrucción [Await](../../../visual-basic/language-reference/modifiers/async.md).  El método se ejecuta sincrónicamente hasta alcanzar el primer `Await`, punto en el que se suspende hasta que la tarea en espera se complete.  Mientras tanto, se devuelve el control al llamador del método asincrónico.  Si el método no contiene una expresión o instrucción `Await`, el método no se suspende y se ejecuta como un método sincrónico.  Una advertencia del compilador alerta de cualquier método asincrónico que no contenga `Await`, porque esa situación podría indicar un error.  Para obtener más información, vea [error del compilador](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 La palabra clave `Async` no está reservada.  Es una palabra clave cuando modifica un método o una expresión lambda.  En todos los demás contextos, se interpreta como identificador.  
  
## Tipos de valor devueltos  
 Un método asincrónico es un procedimiento [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) o [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) que tiene un tipo de valor devuelto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  El método no puede declarar ningún parámetro [ByRef](../../../visual-basic/language-reference/modifiers/byref.md).  
  
 Se puede especificar `Task(Of TResult)` para el tipo de valor devuelto de un método asincrónico si la instrucción [Return](../../../visual-basic/language-reference/statements/return-statement.md) del método contiene un operando de tipo TResult.  Utilice `Task` si no se devuelve ningún valor significativo al completarse el método.  Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, ninguna instrucción `Await` que está en espera de `Task` no genera un valor de resultado.  
  
 Las subrutinas asincrónicas se utilizan principalmente para definir controladores de eventos donde se requiere un procedimiento `Sub`.  El llamador de una subrutina asincrónica no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.  
  
 Para obtener más información y ejemplos, vea [Tipos de valor devueltos de Async](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Ejemplo  
 Los ejemplos siguientes muestran un controlador de eventos asincrónicos, una expresión lambda asincrónica y un método asincrónico.  Para obtener un ejemplo completo en el que se usan estos elementos, vea [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Puede descargar el código del tutorial en [Ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=255191).  
  
```vb  
  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
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
  
```  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [Await \(Operador\)](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)