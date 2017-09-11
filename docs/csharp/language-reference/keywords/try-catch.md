---
title: try-catch (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b7ec6c96ac21ba2115d1e7eead5700b6dbfcc952
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-c-reference"></a><span data-ttu-id="365e0-102">try-catch (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="365e0-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="365e0-103">La instrucción try-catch consta de un bloque `try` seguido de una o más cláusulas `catch` que especifican controladores para diferentes excepciones.</span><span class="sxs-lookup"><span data-stu-id="365e0-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="365e0-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="365e0-104">Remarks</span></span>  
 <span data-ttu-id="365e0-105">Cuando se produce una excepción, Common Language Runtime (CLR) busca la instrucción `catch` que controla esta excepción.</span><span class="sxs-lookup"><span data-stu-id="365e0-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="365e0-106">Si el método que se ejecuta actualmente no contiene un bloque `catch`, CLR busca el método que llamó el método actual, y así sucesivamente hasta la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="365e0-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="365e0-107">Si no existe ningún bloque `catch`, CLR muestra al usuario un mensaje de excepción no controlada y detiene la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="365e0-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="365e0-108">El bloque `try` contiene el código protegido que puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="365e0-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="365e0-109">El bloque se ejecuta hasta que se produce una excepción o hasta que se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="365e0-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="365e0-110">Por ejemplo, el intento siguiente de convertir un objeto `null` produce la excepción <xref:System.NullReferenceException>:</span><span class="sxs-lookup"><span data-stu-id="365e0-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="365e0-111">Aunque la cláusula `catch` puede utilizarse sin argumentos para detectar cualquier tipo de excepción, no se recomienda este uso.</span><span class="sxs-lookup"><span data-stu-id="365e0-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="365e0-112">En general, solo debe convertir las excepciones que sabe cómo recuperar.</span><span class="sxs-lookup"><span data-stu-id="365e0-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="365e0-113">Por lo tanto, debe especificar siempre un argumento de objeto derivado de <xref:System.Exception?displayProperty=fullName> Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="365e0-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=fullName> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="365e0-114">Es posible utilizar más de una cláusula `catch` específica en la misma instrucción try-catch.</span><span class="sxs-lookup"><span data-stu-id="365e0-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="365e0-115">En este caso, el orden de las cláusulas  `catch` es importante, puesto que las cláusulas `catch` se examinan por orden.</span><span class="sxs-lookup"><span data-stu-id="365e0-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="365e0-116">Detectar las excepciones más específicas antes que las menos específicas.</span><span class="sxs-lookup"><span data-stu-id="365e0-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="365e0-117">El compilador genera un error si ordena los bloques de detección para que un bloque posterior nunca pueda alcanzarse.</span><span class="sxs-lookup"><span data-stu-id="365e0-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="365e0-118">La utilización de los argumentos `catch` es una manera de filtrar las excepciones que desea controlar.</span><span class="sxs-lookup"><span data-stu-id="365e0-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="365e0-119">También puede utilizar una expresión de predicado que examine aún más la excepción para decidir si controlarla.</span><span class="sxs-lookup"><span data-stu-id="365e0-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="365e0-120">Si la expresión de predicado devuelve false, prosigue la búsqueda de un controlador.</span><span class="sxs-lookup"><span data-stu-id="365e0-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="365e0-121">Los filtros de excepción son preferibles para detectar y volver a producir (se explica a continuación) porque los filtros dejan la pila intacta.</span><span class="sxs-lookup"><span data-stu-id="365e0-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="365e0-122">Si un controlador posterior vuelca la pila, puede ver la procedencia original de la excepción, más que solo la ubicación en la que se volvió a producir.</span><span class="sxs-lookup"><span data-stu-id="365e0-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="365e0-123">Un uso común de las expresiones de filtro de excepciones es el registro.</span><span class="sxs-lookup"><span data-stu-id="365e0-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="365e0-124">Puede crear una función de predicado que siempre devuelva false y que también resulte en un registro o puede registrar excepciones a medida que se produzcan sin tener que controlarlas y volver a producirlas.</span><span class="sxs-lookup"><span data-stu-id="365e0-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="365e0-125">Se puede usar una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) en un bloque `catch` para volver a iniciar la excepción detectada por la instrucción `catch`.</span><span class="sxs-lookup"><span data-stu-id="365e0-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="365e0-126">En el ejemplo siguiente se extrae información de origen de una excepción <xref:System.IO.IOException> y, a continuación, se produce la excepción al método principal.</span><span class="sxs-lookup"><span data-stu-id="365e0-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
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
  
 <span data-ttu-id="365e0-127">Puede capturar una excepción y producir una excepción diferente.</span><span class="sxs-lookup"><span data-stu-id="365e0-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="365e0-128">Al hacerlo, especifique la excepción que detectó como excepción interna, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="365e0-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="365e0-129">También se puede volver a producir una excepción sin una condición específica es true, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="365e0-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="365e0-130">Desde dentro de un bloque `try`, solo deben inicializarse las variables que se declaran en el mismo.</span><span class="sxs-lookup"><span data-stu-id="365e0-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="365e0-131">De lo contrario, puede ocurrir una excepción antes de que se complete la ejecución del bloque.</span><span class="sxs-lookup"><span data-stu-id="365e0-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="365e0-132">Por ejemplo, en el siguiente ejemplo de código, la variable `n` se inicializa dentro del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="365e0-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="365e0-133">Un intento de utilizar esta variable fuera del bloque `try` en la instrucción `Write(n)` generará un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="365e0-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
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
  
 <span data-ttu-id="365e0-134">Para obtener más información sobre la captura,vea [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md) (try-catch-finally [Referencia de C#]).</span><span class="sxs-lookup"><span data-stu-id="365e0-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="365e0-135">Excepciones en métodos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="365e0-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="365e0-136">Un método asincrónico está marcado por un modificador [async](../../../csharp/language-reference/keywords/async.md) y normalmente contiene una o más instrucciones o expresiones await.</span><span class="sxs-lookup"><span data-stu-id="365e0-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="365e0-137">Una expresión await aplica el operador [await](../../../csharp/language-reference/keywords/await.md) a <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="365e0-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="365e0-138">Cuando el control alcanza un `await` en el método asincrónico, el progreso del método se suspende hasta que la tarea esperada se completa.</span><span class="sxs-lookup"><span data-stu-id="365e0-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="365e0-139">Cuando se completa la tarea, la ejecución puede reanudarse en el método.</span><span class="sxs-lookup"><span data-stu-id="365e0-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="365e0-140">Para más información, vea [Programación asincrónica con Async y Await](../../../csharp/programming-guide/concepts/async/index.md) y [Controlar el flujo en los programas asincrónicos](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="365e0-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="365e0-141">La tarea completada a la que se aplica `await` puede encontrarse en un estado de error debido a una excepción no controlada en el método que devuelve la tarea.</span><span class="sxs-lookup"><span data-stu-id="365e0-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="365e0-142">La espera de la tarea produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="365e0-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="365e0-143">Una tarea también puede terminar en un estado cancelado si se cancela el proceso asincrónico que devuelve.</span><span class="sxs-lookup"><span data-stu-id="365e0-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="365e0-144">La espera de una tarea cancelada devuelve una `OperationCanceledException`.</span><span class="sxs-lookup"><span data-stu-id="365e0-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="365e0-145">Para obtener más información sobre cómo cancelar un proceso asincrónico, vea [Ajustar una aplicación asincrónica (C# y Visual Basic)](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span><span class="sxs-lookup"><span data-stu-id="365e0-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](http://msdn.microsoft.com/library/daaa32ea-c84c-4761-8230-c8292ffebd74).</span></span>  
  
 <span data-ttu-id="365e0-146">Para detectar la excepción, espere la tarea en un bloque `try` y detéctela en el bloque asociado `catch`.</span><span class="sxs-lookup"><span data-stu-id="365e0-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="365e0-147">Para obtener un ejemplo, vea la sección "Ejemplo".</span><span class="sxs-lookup"><span data-stu-id="365e0-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="365e0-148">Una tarea puede encontrarse en un estado de error debido a que ocurrieron varias excepciones en el método asincrónico esperado.</span><span class="sxs-lookup"><span data-stu-id="365e0-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="365e0-149">Por ejemplo, la tarea podría ser el resultado de una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="365e0-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="365e0-150">Cuando espera una tarea de este tipo, solo se captura una de las excepciones y no puede predecir qué excepción se capturará.</span><span class="sxs-lookup"><span data-stu-id="365e0-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="365e0-151">Para obtener un ejemplo, vea la sección "Ejemplo".</span><span class="sxs-lookup"><span data-stu-id="365e0-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="365e0-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="365e0-152">Example</span></span>  
 <span data-ttu-id="365e0-153">En el ejemplo siguiente, el bloque `try` contiene una llamada al método `ProcessString` que puede causar una excepción.</span><span class="sxs-lookup"><span data-stu-id="365e0-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="365e0-154">La cláusula `catch` contiene el controlador de excepciones que muestra un mensaje en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="365e0-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="365e0-155">Cuando la  instrucción `throw` se llama desde dentro `MyMethod`, el sistema busca la instrucción `catch` y muestra el mensaje `Exception caught`.</span><span class="sxs-lookup"><span data-stu-id="365e0-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 <span data-ttu-id="365e0-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="365e0-156">[!code-cs[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="365e0-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="365e0-157">Example</span></span>  
 <span data-ttu-id="365e0-158">En el ejemplo siguiente, se utilizan dos bloques de detección y la excepción más específica, que es la que aparece primero, es la que se captura.</span><span class="sxs-lookup"><span data-stu-id="365e0-158">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="365e0-159">Para capturar la excepción menos específica, puede sustituir la instrucción throw en `ProcessString` por la siguiente instrucción: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="365e0-159">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="365e0-160">Si coloca primero el bloque catch menos específico en el ejemplo, aparece el siguiente mensaje de error: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="365e0-160">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 <span data-ttu-id="365e0-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="365e0-161">[!code-cs[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="365e0-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="365e0-162">Example</span></span>  
 <span data-ttu-id="365e0-163">En el ejemplo siguiente se muestra el control de excepciones de los métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="365e0-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="365e0-164">Para capturar una excepción que produce una tarea asincrónica, coloque la expresión `await` en un bloque `try` y capture la excepción en un bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="365e0-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="365e0-165">Quite la marca de comentario de la línea `throw new Exception` en el ejemplo para demostrar el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="365e0-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="365e0-166">La propiedad de la tarea `IsFaulted` se establece en `True`, la propiedad de la tarea `Exception.InnerException` se establece en la excepción, y la excepción se captura en el bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="365e0-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="365e0-167">Quite la marca de comentario de la línea `throw new OperationCancelledException` para ver lo que pasa cuando se cancela un proceso asincrónico.</span><span class="sxs-lookup"><span data-stu-id="365e0-167">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="365e0-168">La propiedad de la tarea `IsCanceled` se establece en `true`, y la excepción se captura en el bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="365e0-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="365e0-169">En algunas condiciones que no son aplicables a este ejemplo, la propiedad de la tarea `IsFaulted` se establece en `true` y `IsCanceled` se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="365e0-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 <span data-ttu-id="365e0-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="365e0-170">[!code-cs[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="365e0-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="365e0-171">Example</span></span>  
 <span data-ttu-id="365e0-172">En el ejemplo siguiente se muestra el control de excepciones en el que varias tareas pueden producir varias excepciones.</span><span class="sxs-lookup"><span data-stu-id="365e0-172">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="365e0-173">El bloque `try` espera la tarea devuelta por una llamada a <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="365e0-173">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="365e0-174">La tarea se completa cuando se hayan completado las tres tareas a las que se aplica el método WhenAll.</span><span class="sxs-lookup"><span data-stu-id="365e0-174">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="365e0-175">Cada una de las tres tareas produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="365e0-175">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="365e0-176">El bloque `catch` se itera a través de las excepciones, que se encuentran en la propiedad `Exception.InnerExceptions` de la tarea devuelta por <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="365e0-176">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="365e0-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="365e0-177">[!code-cs[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="365e0-178">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="365e0-178">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="365e0-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="365e0-179">See Also</span></span>  
 <span data-ttu-id="365e0-180">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-180">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="365e0-181">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-181">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="365e0-182">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-182">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="365e0-183">[Instrucciones try, throw y catch (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="365e0-183">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="365e0-184">[Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-184">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="365e0-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-185">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="365e0-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span><span class="sxs-lookup"><span data-stu-id="365e0-186">[try-finally](../../../csharp/language-reference/keywords/try-finally.md) </span></span>  
 [<span data-ttu-id="365e0-187">Cómo: Iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="365e0-187">How to: Explicitly Throw Exceptions</span></span>](https://msdn.microsoft.com/library/xhcbs8fz)

