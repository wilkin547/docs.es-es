---
title: Async
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: 73d433c66750ead3a97b1c283cc26b4c43f078df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351624"
---
# <a name="async-visual-basic"></a>Async (Visual Basic)

The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous. Such methods are referred to as *async methods*.

Un método asincrónico proporciona una manera cómoda de hacer el trabajo de larga duración sin bloquear el subproceso del llamador. El llamador de un método asincrónico puede reanudar el trabajo sin esperar a que el método asincrónico finalice.

> [!NOTE]
> Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012. For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).

En el siguiente ejemplo se muestra la estructura de un método asincrónico. Por convención, los nombres de método asincrónico acaban en “Async”.

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

Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement. El método se ejecuta sincrónicamente hasta alcanzar el primer `Await`, punto en el que se suspende hasta que la tarea en espera se complete. Mientras tanto, se devuelve el control al llamador del método asincrónico. If the method doesn't contain an `Await` expression or statement, the method isn't suspended and executes as a synchronous method does. Una advertencia del compilador alerta de cualquier método asincrónico que no contenga `Await`, porque esa situación podría indicar un error. For more information, see the [compiler error](../error-messages/bc42358.md).

La palabra clave `Async` no está reservada. Es una palabra clave cuando modifica un método o una expresión lambda. En todos los demás contextos, se interpreta como identificador.

## <a name="return-types"></a>Tipos de valor devueltos

An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>. The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.

You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult. Utilice `Task` si no se devuelve ningún valor significativo al completarse el método. Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, ninguna instrucción `Await` que está en espera de `Task` no genera un valor de resultado.

Las subrutinas asincrónicas se utilizan principalmente para definir controladores de eventos donde se requiere un procedimiento `Sub`. El llamador de una subrutina asincrónica no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.

Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Ejemplo

Los ejemplos siguientes muestran un controlador de eventos asincrónicos, una expresión lambda asincrónica y un método asincrónico. For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Puede descargar el código del tutorial en [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

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
'      Dim result As Byte() = Await GetURLContents("https://msdn.com")
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

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [Await (operador)](../../../visual-basic/language-reference/operators/await-operator.md)
- [Programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Tutorial: Acceso a Web mediante Async y Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
