---
title: Await (operador) (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b50b9c7283ddd4d3f8484854bdffff3d76181c9f
ms.lasthandoff: 03/13/2017

---
# <a name="await-operator-visual-basic"></a>Await (Operador) (Visual Basic)
El operador `Await` se aplica a un operando de un método asincrónico o a una expresión lambda para suspender la ejecución del método hasta que la tarea en espera se complete. La tarea representa el trabajo en curso.  
  
 El método en el que `Await` se utiliza debe tener un [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador. Este tipo de método, definido mediante el `Async` modificador y generalmente contiene uno o más `Await` expresiones, se conoce como un *método asincrónico*.  
  
> [!NOTE]
>  Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012. Para obtener una introducción a la programación asincrónica, vea [la programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Normalmente, la tarea a la que se aplica el `Await` operador es el valor devuelto de una llamada a un método que implementa el [modelo asincrónico basado en tareas](http://go.microsoft.com/fwlink/?LinkId=204847), es decir, un <xref:System.Threading.Tasks.Task>o un <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 En el código siguiente, la <xref:System.Net.Http.HttpClient>método <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>devuelve `getContentsTask`, `Task(Of Byte())`.</xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> </xref:System.Net.Http.HttpClient> La tarea garantiza que la matriz de bytes real se generará cuando finalice la operación. El operador `Await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`. Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`. Cuando `getContentsTask` haya finalizado, la expresión `Await` se evalúa como una matriz de bytes.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  Para obtener un ejemplo completo, vea [Tutorial: obtener acceso a la Web mediante el uso de Async y Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Puede descargar el ejemplo de [ejemplos de código para desarrolladores](http://go.microsoft.com/fwlink/?LinkID=255191&clcid=0x409) en el sitio Web de Microsoft. El ejemplo está en el proyecto AsyncWalkthrough_HttpClient.  
  
 Si `Await` se aplica al resultado de una llamada al método que devuelve `Task(Of TResult)`, el tipo de la expresión `Await` será TResult. Si `Await` se aplica al resultado de una llamada al método que devuelve `Task`, la expresión `Await` no devuelve un valor. En el siguiente ejemplo se ilustra la diferencia.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Una expresión o instrucción `Await` no bloquea el subproceso en el que se ejecuta. En su lugar, hace que el compilador suscriba el resto del método asincrónico, después de la expresión `Await`, como una continuación de la tarea esperada. A continuación, el control vuelve al llamador del método asincrónico. Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.  
  
 Una expresión `Await` solo puede aparecer en el cuerpo de un método envolvente inmediato o una expresión lambda marcados con el modificador `Async`. El término *Await* sirve como palabra clave sólo en ese contexto. En cualquier otra parte, se interpretará como identificador. Dentro de la expresión lambda o de método asincrónico, un `Await` expresión no puede aparecer en una expresión de consulta, en la `catch` o `finally` bloquear de un [intente... Catch... Finalmente](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) instrucción, en la expresión de variable de control de bucle de una `For` o `For Each` bucles, o en el cuerpo de un [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) instrucción.  
  
## <a name="exceptions"></a>Excepciones  
 La mayoría de los métodos de async devuelven <xref:System.Threading.Tasks.Task>o <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final. El operador `Await` tiene acceso a esas propiedades.  
  
 Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `Await` volverá a generar la excepción.  
  
 Si espera un tarea devolviendo un método asincrónico que se cancela, el `Await` operador vuelve a producir un <xref:System.OperationCanceledException>.</xref:System.OperationCanceledException>  
  
 Una única tarea en estado de error puede reflejar varias excepciones.  Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones. Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.  
  
 Para obtener ejemplos de control de errores en los métodos asincrónicos, vea [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente de Windows Forms muestra el uso de `Await` en un método asincrónico, `WaitAsynchronouslyAsync`. Compare el comportamiento de dicho método con el de `WaitSynchronously`. Sin un `Await` (operador), `WaitSynchronously` se ejecuta sincrónicamente a pesar del uso de la `Async` modificador en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>en su cuerpo.</xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>  
  
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
  
## <a name="see-also"></a>Vea también  
 [Programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Tutorial: Obtener acceso a la Web usando Async y Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Async](../../../visual-basic/language-reference/modifiers/async.md)
