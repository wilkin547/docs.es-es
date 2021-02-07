---
description: 'Más información acerca de: Async (Visual Basic)'
title: Async
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: a20c80ace06e386e7c106acc2b7e6258abca13b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701162"
---
# <a name="async-visual-basic"></a><span data-ttu-id="1dfb0-103">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1dfb0-103">Async (Visual Basic)</span></span>

<span data-ttu-id="1dfb0-104">El `Async` modificador indica que el método o la [expresión lambda](../../programming-guide/language-features/procedures/lambda-expressions.md) que modifica es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-104">The `Async` modifier indicates that the method or [lambda expression](../../programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="1dfb0-105">Estos métodos se conocen como *métodos asincrónicos*.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-105">Such methods are referred to as *async methods*.</span></span>

<span data-ttu-id="1dfb0-106">Un método asincrónico proporciona una manera cómoda de hacer el trabajo de larga duración sin bloquear el subproceso del llamador.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-106">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="1dfb0-107">El llamador de un método asincrónico puede reanudar el trabajo sin esperar a que el método asincrónico finalice.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-107">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfb0-108">Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-108">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="1dfb0-109">Para obtener una introducción a la programación asincrónica, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb0-109">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="1dfb0-110">En el siguiente ejemplo se muestra la estructura de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-110">The following example shows the structure of an async method.</span></span> <span data-ttu-id="1dfb0-111">Por convención, los nombres de método asincrónico acaban en “Async”.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-111">By convention, async method names end in "Async."</span></span>

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

<span data-ttu-id="1dfb0-112">Normalmente, un método modificado por la `Async` palabra clave contiene al menos una expresión o instrucción [Await](async.md) .</span><span class="sxs-lookup"><span data-stu-id="1dfb0-112">Typically, a method modified by the `Async` keyword contains at least one [Await](async.md) expression or statement.</span></span> <span data-ttu-id="1dfb0-113">El método se ejecuta sincrónicamente hasta alcanzar el primer `Await`, punto en el que se suspende hasta que la tarea en espera se complete.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-113">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="1dfb0-114">Mientras tanto, se devuelve el control al llamador del método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-114">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="1dfb0-115">Si el método no contiene una `Await` expresión o instrucción, el método no se suspende y se ejecuta como un método sincrónico.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-115">If the method doesn't contain an `Await` expression or statement, the method isn't suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="1dfb0-116">Una advertencia del compilador alerta de cualquier método asincrónico que no contenga `Await`, porque esa situación podría indicar un error.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-116">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="1dfb0-117">Para obtener más información, vea el [error del compilador](../error-messages/bc42358.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb0-117">For more information, see the [compiler error](../error-messages/bc42358.md).</span></span>

<span data-ttu-id="1dfb0-118">La palabra clave `Async` no está reservada.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-118">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="1dfb0-119">Es una palabra clave cuando modifica un método o una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-119">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="1dfb0-120">En todos los demás contextos, se interpreta como identificador.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-120">In all other contexts, it is interpreted as an identifier.</span></span>

## <a name="return-types"></a><span data-ttu-id="1dfb0-121">Tipos de valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dfb0-121">Return Types</span></span>

<span data-ttu-id="1dfb0-122">Un método asincrónico es un procedimiento [Sub](../../programming-guide/language-features/procedures/sub-procedures.md) o un procedimiento de [función](../../programming-guide/language-features/procedures/function-procedures.md) que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="1dfb0-122">An async method is either a [Sub](../../programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="1dfb0-123">El método no puede declarar ningún parámetro [ByRef](byref.md) .</span><span class="sxs-lookup"><span data-stu-id="1dfb0-123">The method cannot declare any [ByRef](byref.md) parameters.</span></span>

<span data-ttu-id="1dfb0-124">Especifique `Task(Of TResult)` para el tipo de valor devuelto de un método asincrónico si la instrucción [Return](../statements/return-statement.md) del método tiene un operando de tipo TResult.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-124">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="1dfb0-125">Utilice `Task` si no se devuelve ningún valor significativo al completarse el método.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-125">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="1dfb0-126">Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, ninguna instrucción `Await` que está en espera de `Task` no genera un valor de resultado.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-126">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>

<span data-ttu-id="1dfb0-127">Las subrutinas asincrónicas se utilizan principalmente para definir controladores de eventos donde se requiere un procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-127">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="1dfb0-128">El llamador de una subrutina asincrónica no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-128">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="1dfb0-129">Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb0-129">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="1dfb0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1dfb0-130">Example</span></span>

<span data-ttu-id="1dfb0-131">Los ejemplos siguientes muestran un controlador de eventos asincrónicos, una expresión lambda asincrónica y un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="1dfb0-131">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="1dfb0-132">Para obtener un ejemplo completo en el que se usan estos elementos, vea [Tutorial: acceso a la web mediante Async y Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="1dfb0-132">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="1dfb0-133">Puede descargar el código del tutorial en [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="1dfb0-133">You can download the walkthrough code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1dfb0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dfb0-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="1dfb0-135">Await (Operador)</span><span class="sxs-lookup"><span data-stu-id="1dfb0-135">Await Operator</span></span>](../operators/await-operator.md)
- [<span data-ttu-id="1dfb0-136">Programación asincrónica con Async y Await</span><span class="sxs-lookup"><span data-stu-id="1dfb0-136">Asynchronous Programming with Async and Await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="1dfb0-137">Tutorial: Acceso a la Web usando async y await</span><span class="sxs-lookup"><span data-stu-id="1dfb0-137">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
