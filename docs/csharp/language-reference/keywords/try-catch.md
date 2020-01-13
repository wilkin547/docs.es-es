---
title: 'try-catch: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 5289dbe3aff0a9e1f1024a293ff469df44d34a3b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713032"
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="86648-102">try-catch (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="86648-102">try-catch (C# Reference)</span></span>

<span data-ttu-id="86648-103">La instrucción try-catch consta de un bloque `try` seguido de una o más cláusulas `catch` que especifican controladores para diferentes excepciones.</span><span class="sxs-lookup"><span data-stu-id="86648-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>

<span data-ttu-id="86648-104">Cuando se produce una excepción, Common Language Runtime (CLR) busca la instrucción `catch` que controla esta excepción.</span><span class="sxs-lookup"><span data-stu-id="86648-104">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="86648-105">Si el método que se ejecuta actualmente no contiene un bloque `catch`, CLR busca el método que llamó el método actual, y así sucesivamente hasta la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="86648-105">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="86648-106">Si no existe ningún bloque `catch`, CLR muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="86648-106">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>

<span data-ttu-id="86648-107">El bloque `try` contiene el código protegido que puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="86648-107">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="86648-108">El bloque se ejecuta hasta que se produce una excepción o hasta que se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="86648-108">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="86648-109">Por ejemplo, el intento siguiente de convertir un objeto `null` produce la excepción <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="86648-109">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

<span data-ttu-id="86648-110">Aunque la cláusula `catch` puede utilizarse sin argumentos para detectar cualquier tipo de excepción, no se recomienda este uso.</span><span class="sxs-lookup"><span data-stu-id="86648-110">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="86648-111">En general, solo debe convertir las excepciones que sabe cómo recuperar.</span><span class="sxs-lookup"><span data-stu-id="86648-111">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="86648-112">Por lo tanto, debe especificar siempre un argumento de objeto derivado de <xref:System.Exception?displayProperty=nameWithType> Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86648-112">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>

```csharp
catch (InvalidCastException e)
{
}
```

<span data-ttu-id="86648-113">Es posible utilizar más de una cláusula `catch` específica en la misma instrucción try-catch.</span><span class="sxs-lookup"><span data-stu-id="86648-113">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="86648-114">En este caso, el orden de las cláusulas  `catch` es importante, puesto que las cláusulas `catch` se examinan por orden.</span><span class="sxs-lookup"><span data-stu-id="86648-114">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="86648-115">Detectar las excepciones más específicas antes que las menos específicas.</span><span class="sxs-lookup"><span data-stu-id="86648-115">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="86648-116">El compilador genera un error si ordena los bloques de detección para que un bloque posterior nunca pueda alcanzarse.</span><span class="sxs-lookup"><span data-stu-id="86648-116">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>

<span data-ttu-id="86648-117">La utilización de los argumentos `catch` es una manera de filtrar las excepciones que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="86648-117">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="86648-118">También se puede usar una expresión de filtro que examine aún más la excepción para decidir si controlarla.</span><span class="sxs-lookup"><span data-stu-id="86648-118">You can also use an exception filter that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="86648-119">Si la expresión de filtro devuelve false, prosigue la búsqueda de un controlador.</span><span class="sxs-lookup"><span data-stu-id="86648-119">If the exception filter returns false, then the search for a handler continues.</span></span>

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

<span data-ttu-id="86648-120">Los filtros de excepción son preferibles para detectar y volver a producir (se explica a continuación) porque los filtros dejan la pila intacta.</span><span class="sxs-lookup"><span data-stu-id="86648-120">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="86648-121">Si un controlador posterior vuelca la pila, puede ver la procedencia original de la excepción, más que solo la ubicación en la que se volvió a producir.</span><span class="sxs-lookup"><span data-stu-id="86648-121">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="86648-122">Un uso común de las expresiones de filtro de excepciones es el registro.</span><span class="sxs-lookup"><span data-stu-id="86648-122">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="86648-123">Puede crear una función de filtro que siempre devuelva false y que también resulte en un registro, o bien puede registrar excepciones a medida que se produzcan sin tener que controlarlas y volver a generarlas.</span><span class="sxs-lookup"><span data-stu-id="86648-123">You can create a filter that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>

<span data-ttu-id="86648-124">Se puede usar una instrucción [throw](throw.md) en un bloque `catch` para volver a iniciar la excepción detectada por la instrucción `catch`.</span><span class="sxs-lookup"><span data-stu-id="86648-124">A [throw](throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="86648-125">En el ejemplo siguiente se extrae información de origen de una excepción <xref:System.IO.IOException> y, a continuación, se produce la excepción al método principal.</span><span class="sxs-lookup"><span data-stu-id="86648-125">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then 
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

<span data-ttu-id="86648-126">Puede capturar una excepción y producir una excepción diferente.</span><span class="sxs-lookup"><span data-stu-id="86648-126">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="86648-127">Al hacerlo, especifique la excepción que detectó como excepción interna, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="86648-127">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e) 
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

<span data-ttu-id="86648-128">También se puede volver a producir una excepción sin una condición específica es true, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="86648-128">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> <span data-ttu-id="86648-129">También es posible usar un filtro de excepción para obtener un resultado similar de una forma generalmente más limpia (además de no modificar la pila, tal y como se explicó anteriormente en este documento).</span><span class="sxs-lookup"><span data-stu-id="86648-129">It is also possible to use an exception filter to get a similar result in an often cleaner fashion (as well as not modifying the stack, as explained earlier in this document).</span></span> <span data-ttu-id="86648-130">El ejemplo siguiente tiene un comportamiento similar para los autores de llamada que el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="86648-130">The following example has a similar behavior for callers as the previous example.</span></span> <span data-ttu-id="86648-131">La función inicia la excepción `InvalidCastException` de vuelta al autor de la llamada cuando `e.Data` es `null`.</span><span class="sxs-lookup"><span data-stu-id="86648-131">The function throws the `InvalidCastException` back to the caller when `e.Data` is `null`.</span></span>
> 
> ```csharp
> catch (InvalidCastException e) when (e.Data != null) 
> {
>     // Take some action.
> }
> ``` 

<span data-ttu-id="86648-132">Desde dentro de un bloque `try`, solo deben inicializarse las variables que se declaran en el mismo.</span><span class="sxs-lookup"><span data-stu-id="86648-132">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="86648-133">De lo contrario, puede ocurrir una excepción antes de que se complete la ejecución del bloque.</span><span class="sxs-lookup"><span data-stu-id="86648-133">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="86648-134">Por ejemplo, en el siguiente ejemplo de código, la variable `n` se inicializa dentro del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="86648-134">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="86648-135">Un intento de utilizar esta variable fuera del bloque `try` en la instrucción `Write(n)` generará un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="86648-135">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>

```csharp
static void Main() 
{
    int n;
    try 
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

<span data-ttu-id="86648-136">Para obtener más información sobre la captura,vea [try-catch-finally](try-catch-finally.md) (try-catch-finally [Referencia de C#]).</span><span class="sxs-lookup"><span data-stu-id="86648-136">For more information about catch, see [try-catch-finally](try-catch-finally.md).</span></span>

## <a name="exceptions-in-async-methods"></a><span data-ttu-id="86648-137">Excepciones en métodos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="86648-137">Exceptions in async methods</span></span>

<span data-ttu-id="86648-138">Un método asincrónico está marcado por un modificador [async](async.md) y normalmente contiene una o más instrucciones o expresiones await.</span><span class="sxs-lookup"><span data-stu-id="86648-138">An async method is marked  by an  [async](async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="86648-139">Una expresión await aplica el operador [await](../operators/await.md) a <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="86648-139">An await expression applies the [await](../operators/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="86648-140">Cuando el control alcanza un `await` en el método asincrónico, el progreso del método se suspende hasta que la tarea esperada se completa.</span><span class="sxs-lookup"><span data-stu-id="86648-140">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="86648-141">Cuando se completa la tarea, la ejecución puede reanudarse en el método.</span><span class="sxs-lookup"><span data-stu-id="86648-141">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="86648-142">Para más información, vea [Programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md) y [Controlar el flujo en los programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="86648-142">For more information, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>

<span data-ttu-id="86648-143">La tarea completada a la que se aplica `await` puede encontrarse en un estado de error debido a una excepción no controlada en el método que devuelve la tarea.</span><span class="sxs-lookup"><span data-stu-id="86648-143">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="86648-144">La espera de la tarea produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="86648-144">Awaiting the task throws an exception.</span></span> <span data-ttu-id="86648-145">Una tarea también puede terminar en un estado cancelado si se cancela el proceso asincrónico que devuelve.</span><span class="sxs-lookup"><span data-stu-id="86648-145">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="86648-146">La espera de una tarea cancelada devuelve una `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="86648-146">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="86648-147">Para obtener más información sobre cómo cancelar un proceso asincrónico, vea [Ajustar una aplicación asincrónica (C# y Visual Basic)](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="86648-147">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="86648-148">Para detectar la excepción, espere la tarea en un bloque `try` y detéctela en el bloque asociado `catch`.</span><span class="sxs-lookup"><span data-stu-id="86648-148">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="86648-149">Para obtener un ejemplo, vea la sección [Ejemplo de método async](#async-method-example).</span><span class="sxs-lookup"><span data-stu-id="86648-149">For an example, see the [Async method example](#async-method-example) section.</span></span>

<span data-ttu-id="86648-150">Una tarea puede encontrarse en un estado de error debido a que ocurrieron varias excepciones en el método asincrónico esperado.</span><span class="sxs-lookup"><span data-stu-id="86648-150">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="86648-151">Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86648-151">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="86648-152">Cuando espera una tarea de este tipo, solo se captura una de las excepciones y no puede predecir qué excepción se capturará.</span><span class="sxs-lookup"><span data-stu-id="86648-152">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="86648-153">Para obtener un ejemplo, vea la sección [Ejemplo de Task.WhenAll](#taskwhenall-example).</span><span class="sxs-lookup"><span data-stu-id="86648-153">For an example, see the [Task.WhenAll example](#taskwhenall-example) section.</span></span>

## <a name="example"></a><span data-ttu-id="86648-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86648-154">Example</span></span>

<span data-ttu-id="86648-155">En el ejemplo siguiente, el bloque `try` contiene una llamada al método `ProcessString` que puede causar una excepción.</span><span class="sxs-lookup"><span data-stu-id="86648-155">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="86648-156">La cláusula `catch` contiene el controlador de excepciones que muestra un mensaje en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="86648-156">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="86648-157">Cuando la  instrucción `throw` se llama desde dentro `MyMethod`, el sistema busca la instrucción `catch` y muestra el mensaje `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="86648-157">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a><span data-ttu-id="86648-158">Ejemplo de dos bloques catch</span><span class="sxs-lookup"><span data-stu-id="86648-158">Two catch blocks example</span></span>

<span data-ttu-id="86648-159">En el ejemplo siguiente, se utilizan dos bloques de detección y la excepción más específica, que es la que aparece primero, es la que se captura.</span><span class="sxs-lookup"><span data-stu-id="86648-159">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>

<span data-ttu-id="86648-160">Para capturar la excepción menos específica, puede sustituir la instrucción throw en `ProcessString` por la siguiente instrucción: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="86648-160">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>

<span data-ttu-id="86648-161">Si coloca primero el bloque catch menos específico en el ejemplo, aparece el siguiente mensaje de error: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="86648-161">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a><span data-ttu-id="86648-162">Ejemplo de método async</span><span class="sxs-lookup"><span data-stu-id="86648-162">Async method example</span></span>

<span data-ttu-id="86648-163">En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="86648-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="86648-164">Para capturar una excepción que produce una tarea asincrónica, coloque la expresión `await` en un bloque `try` y capture la excepción en un bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="86648-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>

<span data-ttu-id="86648-165">Quite la marca de comentario de la línea `throw new Exception` en el ejemplo para demostrar el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="86648-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="86648-166">La propiedad de la tarea `IsFaulted` se establece en `True`, la propiedad de la tarea `Exception.InnerException` se establece en la excepción, y la excepción se captura en el bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="86648-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>

<span data-ttu-id="86648-167">Quite la marca de comentario de la línea `throw new OperationCanceledException` para ver lo que pasa cuando se cancela un proceso asincrónico.</span><span class="sxs-lookup"><span data-stu-id="86648-167">Uncomment the `throw new OperationCanceledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="86648-168">La propiedad de la tarea `IsCanceled` se establece en `true`, y la excepción se captura en el bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="86648-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="86648-169">En algunas condiciones que no son aplicables a este ejemplo, la propiedad de la tarea `IsFaulted` se establece en `true` y `IsCanceled` se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="86648-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a><span data-ttu-id="86648-170">Ejemplo de Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="86648-170">Task.WhenAll example</span></span>

<span data-ttu-id="86648-171">En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones.</span><span class="sxs-lookup"><span data-stu-id="86648-171">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="86648-172">El bloque `try` espera la tarea devuelta por una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86648-172">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="86648-173">La tarea se completa cuando se hayan completado las tres tareas a las que se aplica el método WhenAll.</span><span class="sxs-lookup"><span data-stu-id="86648-173">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>

<span data-ttu-id="86648-174">Cada una de las tres tareas produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="86648-174">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="86648-175">El bloque `catch` se itera a través de las excepciones, que se encuentran en la propiedad `Exception.InnerExceptions` de la tarea devuelta por <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86648-175">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="86648-176">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="86648-176">C# language specification</span></span>

<span data-ttu-id="86648-177">Para obtener más información, vea la sección sobre la [instrucción try](~/_csharplang/spec/statements.md#the-try-statement) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="86648-177">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="86648-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="86648-178">See also</span></span>

- [<span data-ttu-id="86648-179">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="86648-179">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="86648-180">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="86648-180">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="86648-181">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="86648-181">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="86648-182">Instrucciones try, throw y catch (C++)</span><span class="sxs-lookup"><span data-stu-id="86648-182">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="86648-183">throw</span><span class="sxs-lookup"><span data-stu-id="86648-183">throw</span></span>](throw.md)
- [<span data-ttu-id="86648-184">try-finally</span><span class="sxs-lookup"><span data-stu-id="86648-184">try-finally</span></span>](try-finally.md)
- [<span data-ttu-id="86648-185">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="86648-185">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
