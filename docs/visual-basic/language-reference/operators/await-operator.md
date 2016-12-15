---
title: "Await (Operador) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Await"
helpviewer_keywords: 
  - "Await [Visual Basic]"
  - "Await (operador) [Visual Basic]"
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
caps.handback.revision: 30
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Await (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El operador `Await` se aplica a un operando de un método asincrónico o a una expresión lambda para suspender la ejecución del método hasta que la tarea en espera se complete.  La tarea representa el trabajo en curso.  
  
 El método en el que se utiliza `Await` debe tener un modificador [Async](../../../visual-basic/language-reference/modifiers/async.md).  Este tipo de método, que se define mediante el modificador `Async` y generalmente contiene una o más expresiones `Await`, se denomina *método asincrónico*.  
  
> [!NOTE]
>  Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.  Para obtener una introducción a la programación asincrónica, vea [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Normalmente, la tarea a la que se aplica el operador `Await` es el valor devuelto de una llamada a un método que implementa el [patrón asincrónico basado en tareas](http://go.microsoft.com/fwlink/?LinkId=204847), es decir, un elemento <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  
  
 En el código siguiente, el método <xref:System.Net.Http.HttpClient> <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> devuelve `getContentsTask`, un tipo `Task(Of Byte())`.  La tarea garantiza que la matriz de bytes real se generará cuando finalice la operación.  El operador `Await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`.  Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`.  Cuando `getContentsTask` haya finalizado, la expresión `Await` se evalúa como una matriz de bytes.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Para obtener el ejemplo completo, vea [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Puede descargar el ejemplo desde [Ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) en el sitio web de Microsoft.  El ejemplo está en el proyecto AsyncWalkthrough\_HttpClient.  
  
 Si `Await` se aplica al resultado de una llamada al método que devuelve `Task(Of TResult)`, el tipo de la expresión `Await` será TResult.  Si `Await` se aplica al resultado de una llamada al método que devuelve `Task`, la expresión `Await` no devuelve un valor.  En el siguiente ejemplo se ilustra la diferencia.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Una expresión o instrucción `Await` no bloquea el subproceso en el que se ejecuta.  En su lugar, hace que el compilador suscriba el resto del método asincrónico, después de la expresión `Await`, como una continuación de la tarea esperada.  A continuación, el control vuelve al llamador del método asincrónico.  Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.  
  
 Una expresión `Await` solo puede aparecer en el cuerpo de un método envolvente inmediato o una expresión lambda marcados con el modificador `Async`.  El término *Await* solo sirve como palabra clave en ese contexto.  En cualquier otra parte, se interpretará como identificador.  Dentro del método asincrónico o de la expresión lambda, una expresión `Await` no puede aparecer en una expresión de consulta, en el bloque `catch` o `finally` de una instrucción [Try… Catch… Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md), en la expresión variable de control de un bucle `For` o `For Each`, o en el cuerpo de una instrucción [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md).  
  
## Excepciones  
 La mayoría de los métodos asincrónicos devuelven un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.  Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final.  El operador `Await` tiene acceso a esas propiedades.  
  
 Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `Await` volverá a generar la excepción.  
  
 Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `Await` volverá a generar <xref:System.OperationCanceledException>.  
  
 Una única tarea en estado de error puede reflejar varias excepciones.  Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.  Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones.  Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.  
  
 Para obtener ejemplos de control de errores en métodos asincrónicos, vea [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## Ejemplo  
 El ejemplo siguiente de Windows Forms muestra el uso de `Await` en un método asincrónico, `WaitAsynchronouslyAsync`.  Compare el comportamiento de dicho método con el de `WaitSynchronously`.  Sin un operador `Await`, `WaitSynchronously` se ejecuta sincrónicamente a pesar del uso del modificador `Async` en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> en el cuerpo.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## Vea también  
 [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Walkthrough: Acceso a web usando Async y Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)