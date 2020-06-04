---
title: Async
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: 35df7a464937647c6d110142a3e2801cebbea505
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373172"
---
# <a name="async-visual-basic"></a>Async (Visual Basic)

El `Async` modificador indica que el método o la [expresión lambda](../../programming-guide/language-features/procedures/lambda-expressions.md) que modifica es asincrónico. Estos métodos se conocen como *métodos asincrónicos*.

Un método asincrónico proporciona una manera cómoda de hacer el trabajo de larga duración sin bloquear el subproceso del llamador. El llamador de un método asincrónico puede reanudar el trabajo sin esperar a que el método asincrónico finalice.

> [!NOTE]
> Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012. Para obtener una introducción a la programación asincrónica, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md).

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

Normalmente, un método modificado por la `Async` palabra clave contiene al menos una expresión o instrucción [Await](async.md) . El método se ejecuta sincrónicamente hasta alcanzar el primer `Await`, punto en el que se suspende hasta que la tarea en espera se complete. Mientras tanto, se devuelve el control al llamador del método asincrónico. Si el método no contiene una `Await` expresión o instrucción, el método no se suspende y se ejecuta como un método sincrónico. Una advertencia del compilador alerta de cualquier método asincrónico que no contenga `Await`, porque esa situación podría indicar un error. Para obtener más información, vea el [error del compilador](../error-messages/bc42358.md).

La palabra clave `Async` no está reservada. Es una palabra clave cuando modifica un método o una expresión lambda. En todos los demás contextos, se interpreta como identificador.

## <a name="return-types"></a>Tipos de valor devuelto

Un método asincrónico es un procedimiento [Sub](../../programming-guide/language-features/procedures/sub-procedures.md) o un procedimiento de [función](../../programming-guide/language-features/procedures/function-procedures.md) que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> . El método no puede declarar ningún parámetro [ByRef](byref.md) .

Especifique `Task(Of TResult)` para el tipo de valor devuelto de un método asincrónico si la instrucción [Return](../statements/return-statement.md) del método tiene un operando de tipo TResult. Utilice `Task` si no se devuelve ningún valor significativo al completarse el método. Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, ninguna instrucción `Await` que está en espera de `Task` no genera un valor de resultado.

Las subrutinas asincrónicas se utilizan principalmente para definir controladores de eventos donde se requiere un procedimiento `Sub`. El llamador de una subrutina asincrónica no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.

Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).

## <a name="example"></a>Ejemplo

Los ejemplos siguientes muestran un controlador de eventos asincrónicos, una expresión lambda asincrónica y un método asincrónico. Para obtener un ejemplo completo en el que se usan estos elementos, vea [Tutorial: acceso a la web mediante Async y Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Puede descargar el código del tutorial en [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).

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

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [Await (operador)](../operators/await-operator.md)
- [Programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md)
- [Tutorial: Acceso a la Web usando async y await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
