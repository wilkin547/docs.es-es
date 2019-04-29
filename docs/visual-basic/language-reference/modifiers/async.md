---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: ad6d671a45cee7d534347d23963bb5035ecc8dac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802718"
---
# <a name="async-visual-basic"></a><span data-ttu-id="76fd5-102">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76fd5-102">Async (Visual Basic)</span></span>
<span data-ttu-id="76fd5-103">El `Async` modificador indica que el método o [expresión lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) que modifica son asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="76fd5-103">The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="76fd5-104">Estos métodos se conocen como *métodos asincrónicos*.</span><span class="sxs-lookup"><span data-stu-id="76fd5-104">Such methods are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="76fd5-105">Un método asincrónico proporciona una manera cómoda de hacer el trabajo de larga duración sin bloquear el subproceso del llamador.</span><span class="sxs-lookup"><span data-stu-id="76fd5-105">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="76fd5-106">El llamador de un método asincrónico puede reanudar el trabajo sin esperar a que el método asincrónico finalice.</span><span class="sxs-lookup"><span data-stu-id="76fd5-106">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76fd5-107">Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="76fd5-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="76fd5-108">Para obtener una introducción a la programación asincrónica, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="76fd5-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="76fd5-109">En el siguiente ejemplo se muestra la estructura de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="76fd5-109">The following example shows the structure of an async method.</span></span> <span data-ttu-id="76fd5-110">Por convención, los nombres de método asincrónico acaban en “Async”.</span><span class="sxs-lookup"><span data-stu-id="76fd5-110">By convention, async method names end in "Async."</span></span>  
  
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
  
 <span data-ttu-id="76fd5-111">Normalmente, un método modificado por la `Async` palabra clave contiene al menos uno [Await](../../../visual-basic/language-reference/modifiers/async.md) expresión o instrucción.</span><span class="sxs-lookup"><span data-stu-id="76fd5-111">Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement.</span></span> <span data-ttu-id="76fd5-112">El método se ejecuta sincrónicamente hasta alcanzar el primer `Await`, punto en el que se suspende hasta que la tarea en espera se complete.</span><span class="sxs-lookup"><span data-stu-id="76fd5-112">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="76fd5-113">Mientras tanto, se devuelve el control al llamador del método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="76fd5-113">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="76fd5-114">Si el método no contiene una expresión o instrucción `Await`, el método no se suspende y se ejecuta como un método sincrónico.</span><span class="sxs-lookup"><span data-stu-id="76fd5-114">If the method doesn’t contain an `Await` expression or statement, the method isn’t suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="76fd5-115">Una advertencia del compilador alerta de cualquier método asincrónico que no contenga `Await`, porque esa situación podría indicar un error.</span><span class="sxs-lookup"><span data-stu-id="76fd5-115">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="76fd5-116">Para obtener más información, consulte el [error del compilador](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="76fd5-116">For more information, see the [compiler error](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span></span>  
  
 <span data-ttu-id="76fd5-117">La palabra clave `Async` no está reservada.</span><span class="sxs-lookup"><span data-stu-id="76fd5-117">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="76fd5-118">Es una palabra clave cuando modifica un método o una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="76fd5-118">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="76fd5-119">En todos los demás contextos, se interpreta como identificador.</span><span class="sxs-lookup"><span data-stu-id="76fd5-119">In all other contexts, it is interpreted as an identifier.</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="76fd5-120">Tipos de valor devueltos</span><span class="sxs-lookup"><span data-stu-id="76fd5-120">Return Types</span></span>  
 <span data-ttu-id="76fd5-121">Un método asincrónico es un [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedimiento, o un [función](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedimiento que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="76fd5-121">An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="76fd5-122">El método no puede declarar ningún [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parámetros.</span><span class="sxs-lookup"><span data-stu-id="76fd5-122">The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="76fd5-123">Especifique `Task(Of TResult)` para el tipo de valor devuelto de un método asincrónico si la [devolver](../../../visual-basic/language-reference/statements/return-statement.md) instrucción del método tiene un operando de tipo TResult.</span><span class="sxs-lookup"><span data-stu-id="76fd5-123">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="76fd5-124">Utilice `Task` si no se devuelve ningún valor significativo al completarse el método.</span><span class="sxs-lookup"><span data-stu-id="76fd5-124">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="76fd5-125">Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, ninguna instrucción `Await` que está en espera de `Task` no genera un valor de resultado.</span><span class="sxs-lookup"><span data-stu-id="76fd5-125">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>  
  
 <span data-ttu-id="76fd5-126">Las subrutinas asincrónicas se utilizan principalmente para definir controladores de eventos donde se requiere un procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="76fd5-126">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="76fd5-127">El llamador de una subrutina asincrónica no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.</span><span class="sxs-lookup"><span data-stu-id="76fd5-127">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="76fd5-128">Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="76fd5-128">For more information and examples, see [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76fd5-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76fd5-129">Example</span></span>  
 <span data-ttu-id="76fd5-130">Los ejemplos siguientes muestran un controlador de eventos asincrónicos, una expresión lambda asincrónica y un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="76fd5-130">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="76fd5-131">Para obtener un ejemplo completo que usa estos elementos, vea [Tutorial: Acceso a web usando Async y Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="76fd5-131">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="76fd5-132">Puede descargar el código del tutorial en [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span><span class="sxs-lookup"><span data-stu-id="76fd5-132">You can download the walkthrough code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76fd5-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="76fd5-133">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="76fd5-134">Await (operador)</span><span class="sxs-lookup"><span data-stu-id="76fd5-134">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="76fd5-135">Programación asincrónica con Async y Await</span><span class="sxs-lookup"><span data-stu-id="76fd5-135">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="76fd5-136">Tutorial: Acceso a web usando Async y Await</span><span class="sxs-lookup"><span data-stu-id="76fd5-136">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
