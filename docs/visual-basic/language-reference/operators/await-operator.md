---
description: 'Más información acerca de: operador Await (Visual Basic)'
title: Await (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: 04e32f31de970b389ae38fc3a4cdc6ab3f873f3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774140"
---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="84b68-103">Await (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b68-103">Await Operator (Visual Basic)</span></span>

<span data-ttu-id="84b68-104">El operador `Await` se aplica a un operando de un método asincrónico o a una expresión lambda para suspender la ejecución del método hasta que la tarea en espera se complete.</span><span class="sxs-lookup"><span data-stu-id="84b68-104">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="84b68-105">La tarea representa el trabajo en curso.</span><span class="sxs-lookup"><span data-stu-id="84b68-105">The task represents ongoing work.</span></span>

<span data-ttu-id="84b68-106">El método en el que `Await` se utiliza debe tener un modificador [Async](../modifiers/async.md) .</span><span class="sxs-lookup"><span data-stu-id="84b68-106">The method in which `Await` is used must have an [Async](../modifiers/async.md) modifier.</span></span> <span data-ttu-id="84b68-107">Este tipo de método, que se define mediante el modificador `Async` y que generalmente contiene una o más expresiones `Await`, se denomina *método asincrónico*.</span><span class="sxs-lookup"><span data-stu-id="84b68-107">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>

> [!NOTE]
> <span data-ttu-id="84b68-108">Las palabras clave `Async` y `Await` se incluyeron en Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="84b68-108">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="84b68-109">Para obtener una introducción a la programación asincrónica, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="84b68-109">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="84b68-110">Normalmente, la tarea a la que se aplica el `Await` operador es el valor devuelto de una llamada a un método que implementa el [modelo asincrónico basado en tareas](https://www.microsoft.com/download/details.aspx?id=19957), es decir, <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="84b68-110">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](https://www.microsoft.com/download/details.aspx?id=19957), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="84b68-111">En el código siguiente, el método <xref:System.Net.Http.HttpClient><xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> devuelve `getContentsTask`, un tipo `Task(Of Byte())`.</span><span class="sxs-lookup"><span data-stu-id="84b68-111">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="84b68-112">La tarea garantiza que la matriz de bytes real se generará cuando finalice la operación.</span><span class="sxs-lookup"><span data-stu-id="84b68-112">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="84b68-113">El operador `Await` se aplica a `getContentsTask` para suspender la ejecución en `SumPageSizesAsync` hasta que se complete `getContentsTask`.</span><span class="sxs-lookup"><span data-stu-id="84b68-113">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="84b68-114">Mientras tanto, el control vuelve al llamador de `SumPageSizesAsync`.</span><span class="sxs-lookup"><span data-stu-id="84b68-114">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="84b68-115">Cuando `getContentsTask` haya finalizado, la expresión `Await` se evalúa como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="84b68-115">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>

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
> <span data-ttu-id="84b68-116">Para obtener el ejemplo completo, vea [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Tutorial: Acceso a la web usando Async y Await).</span><span class="sxs-lookup"><span data-stu-id="84b68-116">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="84b68-117">Puede descargar el ejemplo desde [Ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) en el sitio web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84b68-117">You can download the sample from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) on the Microsoft website.</span></span> <span data-ttu-id="84b68-118">El ejemplo está en el proyecto AsyncWalkthrough_HttpClient.</span><span class="sxs-lookup"><span data-stu-id="84b68-118">The example is in the AsyncWalkthrough_HttpClient project.</span></span>

<span data-ttu-id="84b68-119">Si `Await` se aplica al resultado de una llamada al método que devuelve `Task(Of TResult)`, el tipo de la expresión `Await` será TResult.</span><span class="sxs-lookup"><span data-stu-id="84b68-119">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="84b68-120">Si `Await` se aplica al resultado de una llamada al método que devuelve `Task`, la expresión `Await` no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="84b68-120">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="84b68-121">En el siguiente ejemplo se ilustra la diferencia.</span><span class="sxs-lookup"><span data-stu-id="84b68-121">The following example illustrates the difference.</span></span>

```vb
' Await used with a method that returns a Task(Of TResult).
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()

' Await used with a method that returns a Task.
Await AsyncMethodThatReturnsTask()
```

<span data-ttu-id="84b68-122">Una expresión o instrucción `Await` no bloquea el subproceso en el que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="84b68-122">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="84b68-123">En su lugar, hace que el compilador suscriba el resto del método asincrónico, después de la expresión `Await`, como una continuación de la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="84b68-123">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="84b68-124">A continuación, el control vuelve al llamador del método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="84b68-124">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="84b68-125">Cuando la tarea se completa, invoca su continuación y la ejecución del método asincrónico se reanuda donde se quedó.</span><span class="sxs-lookup"><span data-stu-id="84b68-125">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>

<span data-ttu-id="84b68-126">Una expresión `Await` solo puede aparecer en el cuerpo de un método envolvente inmediato o una expresión lambda marcados con el modificador `Async`.</span><span class="sxs-lookup"><span data-stu-id="84b68-126">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="84b68-127">El término *Await* solo sirve como palabra clave en ese contexto.</span><span class="sxs-lookup"><span data-stu-id="84b68-127">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="84b68-128">En cualquier otra parte, se interpretará como identificador.</span><span class="sxs-lookup"><span data-stu-id="84b68-128">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="84b68-129">Dentro del `Async` método o la expresión lambda, una `Await` expresión no puede aparecer en una expresión de consulta, en el `Catch` `Finally` bloque o de una [instrucción try... Detectar... Finally](../statements/try-catch-finally-statement.md), en la expresión de variable de control de bucle de un `For` `For Each` bucle o, o en el cuerpo de una instrucción [SyncLock](../statements/synclock-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="84b68-129">Within the `Async` method or lambda expression, an `Await` expression cannot occur in a query expression, in the `Catch` or `Finally` block of a [Try…Catch…Finally statement](../statements/try-catch-finally-statement.md), in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../statements/synclock-statement.md) statement.</span></span>

## <a name="exceptions"></a><span data-ttu-id="84b68-130">Excepciones</span><span class="sxs-lookup"><span data-stu-id="84b68-130">Exceptions</span></span>

<span data-ttu-id="84b68-131">La mayoría de los métodos asincrónicos devuelven un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="84b68-131">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="84b68-132">Las propiedades de la tarea devuelta llevan información acerca de su estado e historial, por ejemplo, si la tarea se ha completado, si el método asincrónico produjo una excepción o si se ha cancelado y cuál es el resultado final.</span><span class="sxs-lookup"><span data-stu-id="84b68-132">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="84b68-133">El operador `Await` tiene acceso a esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="84b68-133">The `Await` operator accesses those properties.</span></span>

<span data-ttu-id="84b68-134">Si espera un método asincrónico que devuelve una tarea y causa una excepción, el operador `Await` volverá a generar la excepción.</span><span class="sxs-lookup"><span data-stu-id="84b68-134">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>

<span data-ttu-id="84b68-135">Si espera un método asincrónico que devuelve una tarea y se cancela, el operador `Await` volverá a generar <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="84b68-135">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="84b68-136">Una única tarea en estado de error puede reflejar varias excepciones.</span><span class="sxs-lookup"><span data-stu-id="84b68-136">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="84b68-137">Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84b68-137">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84b68-138">Cuando espera dicha tarea, la operación await vuelve a generar únicamente una de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="84b68-138">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="84b68-139">Sin embargo, no se puede predecir cuál de las excepciones se vuelve a generar.</span><span class="sxs-lookup"><span data-stu-id="84b68-139">However, you can't predict which of the exceptions is rethrown.</span></span>

<span data-ttu-id="84b68-140">Para obtener ejemplos de control de errores en métodos asincrónicos, vea [try... Detectar... Finally](../statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="84b68-140">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../statements/try-catch-finally-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="84b68-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84b68-141">Example</span></span>

<span data-ttu-id="84b68-142">El ejemplo siguiente de Windows Forms muestra el uso de `Await` en un método asincrónico, `WaitAsynchronouslyAsync`.</span><span class="sxs-lookup"><span data-stu-id="84b68-142">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="84b68-143">Compare el comportamiento de dicho método con el de `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="84b68-143">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="84b68-144">Sin un operador `Await`, `WaitSynchronously` se ejecuta sincrónicamente a pesar del uso del modificador `Async` en su definición y una llamada a <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="84b68-144">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> in its body.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="84b68-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="84b68-145">See also</span></span>

- [<span data-ttu-id="84b68-146">Programación asincrónica con Async y Await</span><span class="sxs-lookup"><span data-stu-id="84b68-146">Asynchronous Programming with Async and Await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="84b68-147">Tutorial: Acceso a la Web usando async y await</span><span class="sxs-lookup"><span data-stu-id="84b68-147">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="84b68-148">Asincrónico</span><span class="sxs-lookup"><span data-stu-id="84b68-148">Async</span></span>](../modifiers/async.md)
