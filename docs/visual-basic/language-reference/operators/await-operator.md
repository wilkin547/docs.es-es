---
title: Await (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: e0c617ce32f80bdde1bcfda31da40ae610e07452
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74712348"
---
# <a name="await-operator-visual-basic"></a>Await (Operador) (Visual Basic)

El operador `Await` se aplica a un operando de un método asincrónico o a una expresión lambda para suspender la ejecución del método hasta que la tarea en espera se complete. La tarea representa el trabajo en curso.

El método en el que se utiliza `Await` debe tener un modificador [Async](../../../visual-basic/language-reference/modifiers/async.md) . Este tipo de método, que se define mediante el modificador `Async` y que generalmente contiene una o más expresiones `Await`, se denomina *método asincrónico*.

> [!NOTE]
> Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012. Para obtener una introducción a la programación asincrónica, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md).

Normalmente, la tarea a la que se aplica el operador `Await` es el valor devuelto de una llamada a un método que implementa el [modelo asincrónico basado en tareas](https://www.microsoft.com/download/details.aspx?id=19957), es decir, un <xref:System.Threading.Tasks.Task> o un <xref:System.Threading.Tasks.Task%601>.

En el código siguiente, el método <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> devuelve `getContentsTask`, un tipo `Task(Of Byte())`. La tarea garantiza que la matriz de bytes real se generará cuando finalice la operación. El operador `Await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`. Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`. Cuando `getContentsTask` haya finalizado, la expresión `Await` se evalúa como una matriz de bytes.

```vb
Private Async Function SumPageSizesAsync() As Task

    ' To use the HttpClient type in desktop apps, you must include a using directive and add a
    ' reference for the System.Net.Http namespace.
    Dim client As HttpClient = New HttpClient()
    ' . . .
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    Dim urlContents As Byte() = Await getContentsTask

    ' Equivalently, now that you see how it works, you can write the same thing in a single line.
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ' . . .
End Function
```

> [!IMPORTANT]
> Para obtener el ejemplo completo, vea [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web usando Async y Await). Puede descargar el ejemplo desde [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) en el sitio web de Microsoft. El ejemplo está en el proyecto AsyncWalkthrough_HttpClient.

Si `Await` se aplica al resultado de una llamada al método que devuelve `Task(Of TResult)`, el tipo de la expresión `Await` será TResult. Si `Await` se aplica al resultado de una llamada al método que devuelve `Task`, la expresión `Await` no devuelve un valor. En el siguiente ejemplo se ilustra la diferencia.

```vb
' Await used with a method that returns a Task(Of TResult).
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()

' Await used with a method that returns a Task.
Await AsyncMethodThatReturnsTask()
```

Una expresión o instrucción `Await` no bloquea el subproceso en el que se ejecuta. En su lugar, hace que el compilador suscriba el resto del método asincrónico, después de la expresión `Await`, como una continuación de la tarea esperada. A continuación, el control vuelve al llamador del método asincrónico. Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.

Una expresión `Await` solo puede aparecer en el cuerpo de un método envolvente inmediato o una expresión lambda marcados con el modificador `Async`. El término *Await* solo sirve como palabra clave en ese contexto. En cualquier otra parte, se interpretará como identificador. Dentro del método asincrónico o de la expresión lambda, una expresión de `Await` no puede aparecer en una expresión de consulta, en el bloque de `catch` o `finally` de una [instrucción try... Detectar... Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) , en la expresión de variable de control de bucle de un bucle `For` o `For Each`, o en el cuerpo de una instrucción [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) .

## <a name="exceptions"></a>Excepciones

La mayoría de los métodos asincrónicos devuelven un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final. El operador `Await` tiene acceso a esas propiedades.

Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `Await` volverá a generar la excepción.

Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `Await` volverá a generar <xref:System.OperationCanceledException>.

Una única tarea en estado de error puede reflejar varias excepciones.  Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>. Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones. Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.

Para obtener ejemplos de control de errores en métodos asincrónicos, vea [try... Detectar... Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente de Windows Forms muestra el uso de `Await` en un método asincrónico, `WaitAsynchronouslyAsync`. Compare el comportamiento de dicho método con el de `WaitSynchronously`. Sin un operador `Await`, `WaitSynchronously` se ejecuta sincrónicamente a pesar del uso del modificador `Async` en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> en el cuerpo.

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

- [Programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Tutorial: Acceso a Web mediante Async y Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Async](../../../visual-basic/language-reference/modifiers/async.md)
