---
title: Utilizar el modelo asincrónico basado en tareas
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
ms.openlocfilehash: 64a9b963ce6a8554a581f9d5d0f77cf4edfa71b4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289465"
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a><span data-ttu-id="4da7c-102">Utilizar el modelo asincrónico basado en tareas</span><span class="sxs-lookup"><span data-stu-id="4da7c-102">Consuming the Task-based Asynchronous Pattern</span></span>

<span data-ttu-id="4da7c-103">Cuando se utiliza el modelo asincrónico basado en tareas (TAP) para trabajar con operaciones asincrónicas, puede utilizar las devoluciones de llamada para conseguir esperas sin bloqueos.</span><span class="sxs-lookup"><span data-stu-id="4da7c-103">When you use the Task-based Asynchronous Pattern (TAP) to work with asynchronous operations, you can use callbacks to achieve waiting without blocking.</span></span>  <span data-ttu-id="4da7c-104">Para las tareas, esto se consigue con métodos como <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-104">For tasks, this is achieved through methods such as <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4da7c-105">La compatibilidad asincrónica basada en lenguaje oculta las devoluciones de llamada al permitir que las operaciones asincrónicas se puedan esperar en el flujo de control normal y que el código generado por el compilador proporcione esta misma compatibilidad de nivel de API.</span><span class="sxs-lookup"><span data-stu-id="4da7c-105">Language-based asynchronous support hides callbacks by allowing asynchronous operations to be awaited within normal control flow, and compiler-generated code provides this same API-level support.</span></span>

## <a name="suspending-execution-with-await"></a><span data-ttu-id="4da7c-106">Suspender la ejecución con Await</span><span class="sxs-lookup"><span data-stu-id="4da7c-106">Suspending Execution with Await</span></span>
 <span data-ttu-id="4da7c-107">A partir de .NET Framework 4.5, se puede utilizar la palabra clave [await](../../csharp/language-reference/operators/await.md) de C# y el [operador Await](../../visual-basic/language-reference/operators/await-operator.md) de Visual Basic para esperar asincrónicamente los objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-107">Starting with the .NET Framework 4.5, you can use the [await](../../csharp/language-reference/operators/await.md) keyword in C# and the [Await Operator](../../visual-basic/language-reference/operators/await-operator.md) in Visual Basic to asynchronously await <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects.</span></span> <span data-ttu-id="4da7c-108">Cuando se espera una clase <xref:System.Threading.Tasks.Task>, la expresión `await` es de tipo `void`.</span><span class="sxs-lookup"><span data-stu-id="4da7c-108">When you're awaiting a <xref:System.Threading.Tasks.Task>, the `await` expression is of type `void`.</span></span> <span data-ttu-id="4da7c-109">Cuando se espera una clase <xref:System.Threading.Tasks.Task%601>, la expresión `await` es de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="4da7c-109">When you're awaiting a <xref:System.Threading.Tasks.Task%601>, the `await` expression is of type `TResult`.</span></span> <span data-ttu-id="4da7c-110">Debe producirse una expresión `await` dentro del cuerpo de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4da7c-110">An `await` expression must occur inside the body of an asynchronous method.</span></span> <span data-ttu-id="4da7c-111">Para obtener más información sobre la compatibilidad del lenguaje C# y Visual Basic en .NET Framework 4.5, consulte las especificaciones del lenguaje C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4da7c-111">For more information about C# and Visual Basic language support in the .NET Framework 4.5, see the C# and Visual Basic language specifications.</span></span>

 <span data-ttu-id="4da7c-112">En realidad, la funcionalidad de await instala una devolución de llamada en la tarea mediante una continuación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-112">Under the covers, the await functionality installs a callback on the task by using a continuation.</span></span>  <span data-ttu-id="4da7c-113">Esta devolución de llamada reanuda el método asincrónico en el punto de suspensión.</span><span class="sxs-lookup"><span data-stu-id="4da7c-113">This callback resumes the asynchronous method at the point of suspension.</span></span> <span data-ttu-id="4da7c-114">Cuando se reanuda el método asincrónico, si la operación de espera finalizó correctamente y fue un objeto <xref:System.Threading.Tasks.Task%601>, se devuelve su `TResult`.</span><span class="sxs-lookup"><span data-stu-id="4da7c-114">When the asynchronous method is resumed, if the awaited operation completed successfully and was a <xref:System.Threading.Tasks.Task%601>, its `TResult` is returned.</span></span>  <span data-ttu-id="4da7c-115">Si las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> por la que esperaba finalizaron con el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>, se produce una excepción <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-115">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state, an <xref:System.OperationCanceledException> exception is thrown.</span></span>  <span data-ttu-id="4da7c-116">Si las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> por la que esperaba finalizaron con el estado <xref:System.Threading.Tasks.TaskStatus.Faulted>, se produce la excepción que causó el error.</span><span class="sxs-lookup"><span data-stu-id="4da7c-116">If the <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> that was awaited ended in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state, the exception that caused it to fault is thrown.</span></span> <span data-ttu-id="4da7c-117">Un objeto `Task` puede producir un error como resultado de múltiples excepciones, pero solo una de estas excepciones se propaga.</span><span class="sxs-lookup"><span data-stu-id="4da7c-117">A `Task` can fault as a result of multiple exceptions, but only one of these exceptions is propagated.</span></span> <span data-ttu-id="4da7c-118">Sin embargo, la propiedad <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> devuelve una excepción <xref:System.AggregateException> que contiene todos los errores.</span><span class="sxs-lookup"><span data-stu-id="4da7c-118">However, the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property returns an <xref:System.AggregateException> exception that contains all the errors.</span></span>

 <span data-ttu-id="4da7c-119">Si un contexto de sincronización (objeto <xref:System.Threading.SynchronizationContext>) está asociado con el subproceso que ejecutaba el método asincrónico en el momento de la suspensión (por ejemplo, si la propiedad <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> no es `null`), el método asincrónico se reanuda en ese mismo contexto de sincronización con el método <xref:System.Threading.SynchronizationContext.Post%2A> del contexto.</span><span class="sxs-lookup"><span data-stu-id="4da7c-119">If a synchronization context (<xref:System.Threading.SynchronizationContext> object) is associated with the thread that was executing the asynchronous method at the time of suspension (for example, if the <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> property is not `null`), the asynchronous method resumes on that same synchronization context by using the context’s <xref:System.Threading.SynchronizationContext.Post%2A> method.</span></span> <span data-ttu-id="4da7c-120">De lo contrario, se basa en el programador de tareas (objeto <xref:System.Threading.Tasks.TaskScheduler>) que era actual en el momento de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="4da7c-120">Otherwise, it relies on the task scheduler (<xref:System.Threading.Tasks.TaskScheduler> object) that was current at the time of suspension.</span></span> <span data-ttu-id="4da7c-121">Normalmente, se trata del programador de tareas predeterminado (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), que tiene como destino el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4da7c-121">Typically, this is the default task scheduler (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>), which targets the thread pool.</span></span> <span data-ttu-id="4da7c-122">El programador de tareas determina si la operación asincrónica en espera debe reanudarse donde ha completado o si se debe programar la reanudación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-122">This task scheduler determines whether the awaited asynchronous operation should resume where it completed or whether the resumption should be scheduled.</span></span> <span data-ttu-id="4da7c-123">Normalmente, el programador predeterminado permite que la continuación se ejecute en el subproceso que ha completado la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="4da7c-123">The default scheduler typically allows the continuation to run on the thread that the awaited operation completed.</span></span>

 <span data-ttu-id="4da7c-124">Cuando se llama a un método asincrónico, ejecuta sincrónicamente el cuerpo de la función hasta que la primera expresión de espera en una instancia esperable que todavía no se ha completado, momento en el que la invocación se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="4da7c-124">When an asynchronous method is called, it synchronously executes the body of the function up until the first await expression on an awaitable instance that has not yet completed, at which point the invocation returns to the caller.</span></span> <span data-ttu-id="4da7c-125">Si el método asincrónico no devuelve `void`, se devuelve un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> para representar el cálculo en curso.</span><span class="sxs-lookup"><span data-stu-id="4da7c-125">If the asynchronous method does not return `void`, a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> object is returned to represent the ongoing computation.</span></span> <span data-ttu-id="4da7c-126">En un método asincrónico distinto de void, si se encuentra una instrucción de devolución o se alcanza el final del cuerpo del método, la tarea se completa en el estado final <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-126">In a non-void asynchronous method, if a return statement is encountered or the end of the method body is reached, the task is completed in the <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> final state.</span></span> <span data-ttu-id="4da7c-127">Si una excepción no controlada hace que el control abandone el cuerpo del método asincrónico, la tarea finaliza en el estado <xref:System.Threading.Tasks.TaskStatus.Faulted>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-127">If an unhandled exception causes control to leave the body of the asynchronous method, the task ends in the <xref:System.Threading.Tasks.TaskStatus.Faulted> state.</span></span> <span data-ttu-id="4da7c-128">Si esa excepción es una clase <xref:System.OperationCanceledException>, en su lugar, la tarea finaliza con el estado <xref:System.Threading.Tasks.TaskStatus.Canceled>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-128">If that exception is an <xref:System.OperationCanceledException>, the task instead ends in the <xref:System.Threading.Tasks.TaskStatus.Canceled> state.</span></span> <span data-ttu-id="4da7c-129">De esta manera, el resultado o excepción se publica finalmente.</span><span class="sxs-lookup"><span data-stu-id="4da7c-129">In this manner, the result or exception is eventually published.</span></span>

 <span data-ttu-id="4da7c-130">Hay diversas variaciones importantes de este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4da7c-130">There are several important variations of this behavior.</span></span>  <span data-ttu-id="4da7c-131">Por motivos de rendimiento, si ya ha completado una tarea en el momento en que se esperaba, no se obtiene el control y la función continúa ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="4da7c-131">For performance reasons, if a task has already completed by the time the task is awaited, control is not yielded, and the function continues to execute.</span></span>  <span data-ttu-id="4da7c-132">Además, volver al contexto original no siempre es el comportamiento deseado y se puede cambiar. Esto se describe con más detalle en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="4da7c-132">Additionally, returning to the original context isn't always the desired behavior and can be changed; this is described in more detail in the next section.</span></span>

### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a><span data-ttu-id="4da7c-133">Configurar la suspensión y reanudación con Yield y ConfigureAwait</span><span class="sxs-lookup"><span data-stu-id="4da7c-133">Configuring Suspension and Resumption with Yield and ConfigureAwait</span></span>
 <span data-ttu-id="4da7c-134">Varios métodos proporcionan más control sobre la ejecución de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4da7c-134">Several methods provide more control over an asynchronous method’s execution.</span></span> <span data-ttu-id="4da7c-135">Por ejemplo, puede usar el método <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> para introducir un punto de rendimiento en el método asincrónico:</span><span class="sxs-lookup"><span data-stu-id="4da7c-135">For example, you can use the <xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType> method to introduce a yield point into the asynchronous method:</span></span>

```csharp
public class Task : …
{
    public static YieldAwaitable Yield();
    …
}
```

 <span data-ttu-id="4da7c-136">Esto es equivalente a volver a registrar o programar de manera asincrónica al contexto actual.</span><span class="sxs-lookup"><span data-stu-id="4da7c-136">This is equivalent to asynchronously posting or scheduling back to the current context.</span></span>

```csharp
Task.Run(async delegate
{
    for(int i=0; i<1000000; i++)
    {
        await Task.Yield(); // fork the continuation into a separate work item
        ...
    }
});
```

 <span data-ttu-id="4da7c-137">También puede usar el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> para controlar mejor la suspensión y reanudación de un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4da7c-137">You can also use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method for better control over suspension and resumption in an asynchronous method.</span></span>  <span data-ttu-id="4da7c-138">Como se mencionó anteriormente, de forma predeterminada, se captura el contexto actual en el momento en que se suspende un método asincrónico, y ese contexto capturado se utiliza para invocar la continuación del método asincrónico tras la reanudación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-138">As mentioned previously, by default, the current context is captured at the time an asynchronous  method is suspended, and that captured context is used to invoke the asynchronous  method’s continuation upon resumption.</span></span>  <span data-ttu-id="4da7c-139">En muchos casos, este es el comportamiento exacto que desea.</span><span class="sxs-lookup"><span data-stu-id="4da7c-139">In many cases, this is the exact behavior you want.</span></span>  <span data-ttu-id="4da7c-140">En otros casos, es posible que no le preocupe el contexto de continuación y puede lograr un mejor rendimiento al evitar dichos registros en el contexto original.</span><span class="sxs-lookup"><span data-stu-id="4da7c-140">In other cases, you may not care about the continuation context, and you can achieve better performance by avoiding such posts back to the original context.</span></span>  <span data-ttu-id="4da7c-141">Para habilitar esto, use el método <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> para informar a la operación await que no capture ni se reanude en el contexto, pero que continúe la ejecución siempre que haya completado la operación asincrónica que se estaba esperando:</span><span class="sxs-lookup"><span data-stu-id="4da7c-141">To enable this, use the <xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType> method to inform the await operation not to capture and resume on the context, but to continue execution wherever the asynchronous operation that was being awaited completed:</span></span>

```csharp
await someTask.ConfigureAwait(continueOnCapturedContext:false);
```

## <a name="canceling-an-asynchronous-operation"></a><span data-ttu-id="4da7c-142">Cancelar una operación asincrónica</span><span class="sxs-lookup"><span data-stu-id="4da7c-142">Canceling an Asynchronous Operation</span></span>
 <span data-ttu-id="4da7c-143">A partir de .NET Framework 4, los métodos de TAP que admiten cancelación proporcionan al menos una sobrecarga que acepta un token de cancelación (objeto <xref:System.Threading.CancellationToken>).</span><span class="sxs-lookup"><span data-stu-id="4da7c-143">Starting with the .NET Framework 4, TAP methods that support cancellation provide at least one overload that accepts a cancellation token (<xref:System.Threading.CancellationToken> object).</span></span>

 <span data-ttu-id="4da7c-144">Se crea un token de cancelación a través de un origen de token de cancelación (objeto <xref:System.Threading.CancellationTokenSource>).</span><span class="sxs-lookup"><span data-stu-id="4da7c-144">A cancellation token is created through a cancellation token source (<xref:System.Threading.CancellationTokenSource> object).</span></span>  <span data-ttu-id="4da7c-145">La propiedad <xref:System.Threading.CancellationTokenSource.Token%2A> del origen devuelve el token de cancelación que se señalará cuando se llame al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> de origen.</span><span class="sxs-lookup"><span data-stu-id="4da7c-145">The source’s <xref:System.Threading.CancellationTokenSource.Token%2A> property returns the cancellation token that will be signaled when the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method is called.</span></span>  <span data-ttu-id="4da7c-146">Por ejemplo, si desea descargar una única página web y desea poder cancelar la operación, cree un objeto <xref:System.Threading.CancellationTokenSource>, pase su token para el método TAP y luego llame al método <xref:System.Threading.CancellationTokenSource.Cancel%2A> de origen cuando esté listo para cancelar la operación:</span><span class="sxs-lookup"><span data-stu-id="4da7c-146">For example, if you want to download a single webpage and you want to be able to cancel the operation, you create a <xref:System.Threading.CancellationTokenSource> object, pass its token to the TAP method, and then call the source’s <xref:System.Threading.CancellationTokenSource.Cancel%2A> method when you're ready to cancel the operation:</span></span>

```csharp
var cts = new CancellationTokenSource();
string result = await DownloadStringAsync(url, cts.Token);
… // at some point later, potentially on another thread
cts.Cancel();
```

 <span data-ttu-id="4da7c-147">Para cancelar varias invocaciones asincrónicas, puede pasar el mismo token para todas las llamadas:</span><span class="sxs-lookup"><span data-stu-id="4da7c-147">To cancel multiple asynchronous invocations, you can pass the same token to all invocations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));
    // at some point later, potentially on another thread
    …
    cts.Cancel();
```

 <span data-ttu-id="4da7c-148">O bien, puede pasar el mismo token a un subconjunto de operaciones selectivo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-148">Or, you can pass the same token to a selective subset of operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
    byte [] data = await DownloadDataAsync(url, cts.Token);
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);
    … // at some point later, potentially on another thread
    cts.Cancel();
```

 <span data-ttu-id="4da7c-149">Las solicitudes de cancelación se pueden iniciar desde cualquier subproceso.</span><span class="sxs-lookup"><span data-stu-id="4da7c-149">Cancellation requests may be initiated from any thread.</span></span>

 <span data-ttu-id="4da7c-150">Puede pasar el valor <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> a cualquier método que acepta un token de cancelación para indicar que nunca se le solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-150">You can pass the <xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType> value to any method that accepts a cancellation token to indicate that cancellation will never be requested.</span></span>  <span data-ttu-id="4da7c-151">Esto hace que la propiedad <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> devuelva `false`, y el método llamado puede optimizarse en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="4da7c-151">This causes the <xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType> property to return `false`, and the called method can optimize accordingly.</span></span>  <span data-ttu-id="4da7c-152">Con fines de prueba, también puede pasar un token de cancelación cancelado previamente cuyas instancias se crean mediante el constructor que acepta un valor booleano para indicar si el token debe iniciarse en un estado ya cancelado o que no se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="4da7c-152">For testing purposes, you can also pass in a pre-canceled cancellation token that is instantiated by using the constructor that accepts a Boolean value to indicate whether the token should start in an already-canceled or not-cancelable state.</span></span>

 <span data-ttu-id="4da7c-153">Este enfoque de cancelación tiene varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="4da7c-153">This approach to cancellation has several advantages:</span></span>

- <span data-ttu-id="4da7c-154">Puede pasar el mismo token de cancelación a cualquier número de operaciones sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="4da7c-154">You can pass the same cancellation token to any number of asynchronous and synchronous operations.</span></span>

- <span data-ttu-id="4da7c-155">La misma solicitud de cancelación puede extenderse a cualquier número de agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="4da7c-155">The same cancellation request may be proliferated to any number of listeners.</span></span>

- <span data-ttu-id="4da7c-156">El desarrollador de la API asincrónica tiene todo el control de si se puede solicitar la cancelación y cuándo puede surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="4da7c-156">The developer of the asynchronous API is in complete control of whether cancellation may be requested and when it may take effect.</span></span>

- <span data-ttu-id="4da7c-157">El código que utiliza la API puede determinar de forma selectiva las llamadas asincrónicas que se propagarán las solicitudes de cancelación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-157">The code that consumes the API may selectively determine the asynchronous invocations that cancellation requests will be propagated to.</span></span>

## <a name="monitoring-progress"></a><span data-ttu-id="4da7c-158">Supervisar el progreso</span><span class="sxs-lookup"><span data-stu-id="4da7c-158">Monitoring Progress</span></span>
 <span data-ttu-id="4da7c-159">Algunos métodos asincrónicos exponen progreso a través de una interfaz de progreso pasada al método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4da7c-159">Some asynchronous methods expose progress through a progress interface passed into the asynchronous method.</span></span>  <span data-ttu-id="4da7c-160">Por ejemplo, considere una función que se descarga de manera asincrónica una cadena de texto y que genera las actualizaciones de progreso que incluyen el porcentaje de descarga que se ha completado hasta el momento.</span><span class="sxs-lookup"><span data-stu-id="4da7c-160">For example, consider a function which asynchronously downloads a string of text, and along the way raises progress updates that include the percentage of the download that has completed thus far.</span></span>  <span data-ttu-id="4da7c-161">Este método se puede utilizar en una aplicación de Windows Presentation Foundation (WPF) como sigue:</span><span class="sxs-lookup"><span data-stu-id="4da7c-161">Such a method could be consumed in a Windows Presentation Foundation (WPF) application as follows:</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,
            new Progress<int>(p => pbDownloadProgress.Value = p));
    }
    finally { btnDownload.IsEnabled = true; }
}
```

<a name="combinators"></a>
## <a name="using-the-built-in-task-based-combinators"></a><span data-ttu-id="4da7c-162">Usar los combinadores integrados basados en tareas</span><span class="sxs-lookup"><span data-stu-id="4da7c-162">Using the Built-in Task-based Combinators</span></span>
 <span data-ttu-id="4da7c-163">El espacio de nombres <xref:System.Threading.Tasks> incluye varios métodos para crear tareas y trabajar con ellas.</span><span class="sxs-lookup"><span data-stu-id="4da7c-163">The <xref:System.Threading.Tasks> namespace includes several methods for composing and working with tasks.</span></span>

### <a name="taskrun"></a><span data-ttu-id="4da7c-164">Task.Run</span><span class="sxs-lookup"><span data-stu-id="4da7c-164">Task.Run</span></span>
 <span data-ttu-id="4da7c-165">La clase <xref:System.Threading.Tasks.Task> incluye varios métodos <xref:System.Threading.Tasks.Task.Run%2A> que le permiten descargar trabajo con facilidad como las clases <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> en el grupo de subprocesos; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-165">The <xref:System.Threading.Tasks.Task> class includes several <xref:System.Threading.Tasks.Task.Run%2A> methods that let you easily offload work as a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> to the thread pool, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    textBox1.Text = await Task.Run(() =>
    {
        // … do compute-bound work here
        return answer;
    });
}
```

 <span data-ttu-id="4da7c-166">Algunos de estos métodos <xref:System.Threading.Tasks.Task.Run%2A>, como la sobrecarga <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, existen como forma abreviada del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-166">Some of these <xref:System.Threading.Tasks.Task.Run%2A> methods, such as the <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType> overload, exist as shorthand for the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="4da7c-167">Otras sobrecargas, como <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, habilitan el uso de await en el trabajo descargado; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-167">Other overloads, such as <xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>, enable you to use await within the offloaded work, for example:</span></span>

```csharp
public async void button1_Click(object sender, EventArgs e)
{
    pictureBox1.Image = await Task.Run(async() =>
    {
        using(Bitmap bmp1 = await DownloadFirstImageAsync())
        using(Bitmap bmp2 = await DownloadSecondImageAsync())
        return Mashup(bmp1, bmp2);
    });
}
```

 <span data-ttu-id="4da7c-168">Tales sobrecargas, lógicamente, son equivalentes al uso del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> junto con el método de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> en la biblioteca TPL.</span><span class="sxs-lookup"><span data-stu-id="4da7c-168">Such overloads are logically equivalent to using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method in conjunction with the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension method in the Task Parallel Library.</span></span>

### <a name="taskfromresult"></a><span data-ttu-id="4da7c-169">Task.FromResult</span><span class="sxs-lookup"><span data-stu-id="4da7c-169">Task.FromResult</span></span>
 <span data-ttu-id="4da7c-170">Utilice el método <xref:System.Threading.Tasks.Task.FromResult%2A> en escenarios donde los datos estén disponibles y solo debe devolverse desde un método de devolución de tarea de elevación en un método <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="4da7c-170">Use the <xref:System.Threading.Tasks.Task.FromResult%2A> method in scenarios where data may already be available and just needs to be returned from a task-returning method lifted into a <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public Task<int> GetValueAsync(string key)
{
    int cachedValue;
    return TryGetCachedValue(out cachedValue) ?
        Task.FromResult(cachedValue) :
        GetValueAsyncInternal();
}

private async Task<int> GetValueAsyncInternal(string key)
{
    …
}
```

### <a name="taskwhenall"></a><span data-ttu-id="4da7c-171">Task.WhenAll</span><span class="sxs-lookup"><span data-stu-id="4da7c-171">Task.WhenAll</span></span>
 <span data-ttu-id="4da7c-172">Utilice el método <xref:System.Threading.Tasks.Task.WhenAll%2A> para esperar asincrónicamente en varias operaciones asincrónicas que se representan como tareas.</span><span class="sxs-lookup"><span data-stu-id="4da7c-172">Use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method to asynchronously wait on multiple asynchronous operations that are represented as tasks.</span></span>  <span data-ttu-id="4da7c-173">El método tiene varias sobrecargas que admiten un conjunto de tareas no genéricas o un conjunto no uniforme de tareas genéricas (por ejemplo, esperando de forma asincrónica varias operaciones que devuelven void o esperando de forma asincrónica varios métodos que devuelven valores, donde cada valor puede tener un tipo diferente) y para admitir un conjunto uniforme de tareas genéricas (como esperar de forma asincrónica para varios métodos que devuelven `TResult`).</span><span class="sxs-lookup"><span data-stu-id="4da7c-173">The method has multiple overloads that support a set of non-generic tasks or a non-uniform set of generic tasks (for example, asynchronously waiting for multiple void-returning operations, or asynchronously waiting for multiple value-returning methods where each value may have a different type) and to support a uniform set of generic tasks (such as asynchronously waiting for multiple `TResult`-returning methods).</span></span>

 <span data-ttu-id="4da7c-174">Supongamos que desea enviar mensajes de correo electrónico a varios clientes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-174">Let's say you want to send email messages to several customers.</span></span> <span data-ttu-id="4da7c-175">Puede superponer el envío de los mensajes, para que no esté esperando que se complete un mensaje antes de enviar el siguiente.</span><span class="sxs-lookup"><span data-stu-id="4da7c-175">You can overlap sending the messages so you're not waiting for one message to complete before sending the next.</span></span> <span data-ttu-id="4da7c-176">También puede averiguar cuando se completan las operaciones de envío y si se ha producido algún error:</span><span class="sxs-lookup"><span data-stu-id="4da7c-176">You can also find out when the send operations have completed and whether any errors have occurred:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
await Task.WhenAll(asyncOps);
```

 <span data-ttu-id="4da7c-177">Este código no controla explícitamente las excepciones que pueden aparecer, pero permite que las excepciones se propaguen fuera de `await` en la tarea resultante de <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-177">This code doesn't explicitly handle exceptions that may occur, but lets exceptions propagate out of the `await` on the resulting task from <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span></span>  <span data-ttu-id="4da7c-178">Para controlar las excepciones, puede utilizar código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="4da7c-178">To handle the exceptions, you can use code such as the following:</span></span>

```csharp
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    ...
}
```

 <span data-ttu-id="4da7c-179">En este caso, si se produce un error en cualquier operación asincrónica, todas las excepciones se consolidarán en una excepción <xref:System.AggregateException>, que se almacena en la clase <xref:System.Threading.Tasks.Task> devuelta por el método <xref:System.Threading.Tasks.Task.WhenAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-179">In this case, if any asynchronous operation fails, all the exceptions will be consolidated in an <xref:System.AggregateException> exception, which is stored in the <xref:System.Threading.Tasks.Task> that is returned from the <xref:System.Threading.Tasks.Task.WhenAll%2A> method.</span></span>  <span data-ttu-id="4da7c-180">Sin embargo, solo una de esas excepciones se propaga por la palabra clave `await`.</span><span class="sxs-lookup"><span data-stu-id="4da7c-180">However, only one of those exceptions is propagated by the `await` keyword.</span></span>  <span data-ttu-id="4da7c-181">Si desea examinar todas las excepciones, puede volver a escribir el código anterior como sigue:</span><span class="sxs-lookup"><span data-stu-id="4da7c-181">If you want to examine all the exceptions, you can rewrite the previous code as follows:</span></span>

```csharp
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();
try
{
    await Task.WhenAll(asyncOps);
}
catch(Exception exc)
{
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

 <span data-ttu-id="4da7c-182">Veamos un ejemplo de descarga de varios archivos desde la web de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4da7c-182">Let's consider an example of downloading multiple files from the web asynchronously.</span></span>  <span data-ttu-id="4da7c-183">En este caso, todas las operaciones asincrónicas tienen tipos de resultado homogéneos, y es fácil acceder a los resultados:</span><span class="sxs-lookup"><span data-stu-id="4da7c-183">In this case, all the asynchronous operations have homogeneous result types, and it's easy to access the results:</span></span>

```csharp
string [] pages = await Task.WhenAll(
    from url in urls select DownloadStringAsync(url));
```

 <span data-ttu-id="4da7c-184">Puede utilizar las mismas técnicas de control de excepciones que se explicaron en el escenario anterior que devuelve void:</span><span class="sxs-lookup"><span data-stu-id="4da7c-184">You can use the same exception-handling techniques we discussed in the previous void-returning scenario:</span></span>

```csharp
Task [] asyncOps =
    (from url in urls select DownloadStringAsync(url)).ToArray();
try
{
    string [] pages = await Task.WhenAll(asyncOps);
    ...
}
catch(Exception exc)
{
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))
    {
        … // work with faulted and faulted.Exception
    }
}
```

### <a name="taskwhenany"></a><span data-ttu-id="4da7c-185">Task.WhenAny</span><span class="sxs-lookup"><span data-stu-id="4da7c-185">Task.WhenAny</span></span>
 <span data-ttu-id="4da7c-186">Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para esperar de manera asincrónica solo una de varias operaciones asincrónicas que se representan como tareas para completar.</span><span class="sxs-lookup"><span data-stu-id="4da7c-186">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to asynchronously wait for just one of multiple asynchronous operations represented as tasks to complete.</span></span>  <span data-ttu-id="4da7c-187">Este método actúa en cuatro casos de uso principales:</span><span class="sxs-lookup"><span data-stu-id="4da7c-187">This method serves four primary use cases:</span></span>

- <span data-ttu-id="4da7c-188">Redundancia:  Realizar una operación varias veces y seleccionar la que se complete primero (por ejemplo, ponerse en contacto con varios servicios web de cotización bursátil que generen un único resultado y seleccionar el que se complete más rápido).</span><span class="sxs-lookup"><span data-stu-id="4da7c-188">Redundancy:  Performing an operation multiple times and selecting the one that completes first (for example, contacting multiple stock quote web services that will produce a single result and selecting the one that completes the fastest).</span></span>

- <span data-ttu-id="4da7c-189">Intercalación:  Iniciar varias operaciones y esperar a que todas ellas se completen, pero procesarlas a medida que se completan.</span><span class="sxs-lookup"><span data-stu-id="4da7c-189">Interleaving:  Launching multiple operations and waiting for all of them to complete, but processing them as they complete.</span></span>

- <span data-ttu-id="4da7c-190">Limitación:  Permitir que comiencen otras operaciones a medida que otras se completan.</span><span class="sxs-lookup"><span data-stu-id="4da7c-190">Throttling:  Allowing additional operations to begin as others complete.</span></span>  <span data-ttu-id="4da7c-191">Esto es una extensión del escenario de intercalación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-191">This is an extension of the interleaving scenario.</span></span>

- <span data-ttu-id="4da7c-192">Salida anticipada:  Por ejemplo, una operación representada por la tarea t1 puede agruparse en una tarea <xref:System.Threading.Tasks.Task.WhenAny%2A> con otra tarea t2 y se puede esperar en la tarea <xref:System.Threading.Tasks.Task.WhenAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-192">Early bailout:  For example, an operation represented by task t1 can be grouped in a <xref:System.Threading.Tasks.Task.WhenAny%2A> task with another task t2, and you can wait on the <xref:System.Threading.Tasks.Task.WhenAny%2A> task.</span></span> <span data-ttu-id="4da7c-193">La tarea t2 podría representar un tiempo de espera o cancelación, o alguna otra señal que hace que la tarea <xref:System.Threading.Tasks.Task.WhenAny%2A> se complete antes de que finalice t1.</span><span class="sxs-lookup"><span data-stu-id="4da7c-193">Task t2 could represent a time-out, or cancellation, or some other signal that causes the <xref:System.Threading.Tasks.Task.WhenAny%2A> task to complete before t1 completes.</span></span>

#### <a name="redundancy"></a><span data-ttu-id="4da7c-194">Redundancia</span><span class="sxs-lookup"><span data-stu-id="4da7c-194">Redundancy</span></span>
 <span data-ttu-id="4da7c-195">Considere un caso en el que quiera tomar la decisión de comprar o no una acción.</span><span class="sxs-lookup"><span data-stu-id="4da7c-195">Consider a case where you want to make a decision about whether to buy a stock.</span></span>  <span data-ttu-id="4da7c-196">Hay varios servicios web de recomendación bursátil en los que confía, pero según la carga diaria, cada servicio puede acabar ralentizándose en momentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-196">There are several stock recommendation web services that you trust, but depending on daily load, each service can end up being slow at different times.</span></span>  <span data-ttu-id="4da7c-197">Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para recibir una notificación cuando se complete cualquier operación:</span><span class="sxs-lookup"><span data-stu-id="4da7c-197">You can use the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to receive a notification when any operation completes:</span></span>

```csharp
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol),
    GetBuyRecommendation2Async(symbol),
    GetBuyRecommendation3Async(symbol)
};
Task<bool> recommendation = await Task.WhenAny(recommendations);
if (await recommendation) BuyStock(symbol);
```

 <span data-ttu-id="4da7c-198">A diferencia de <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve los resultados desajustados de todas las tareas que se han completado correctamente, <xref:System.Threading.Tasks.Task.WhenAny%2A> devuelve la tarea completada.</span><span class="sxs-lookup"><span data-stu-id="4da7c-198">Unlike <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns the unwrapped results of all tasks that completed successfully, <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task that completed.</span></span> <span data-ttu-id="4da7c-199">Si se produce un error en una tarea, es importante saber que se produjo un error y, si una tarea se realiza correctamente, es importante saber con qué tarea está asociado el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="4da7c-199">If a task fails, it’s important to know that it failed, and if a task succeeds, it’s important to know which task the return value is associated with.</span></span>  <span data-ttu-id="4da7c-200">Por lo tanto, necesitará acceder al resultado de la tarea devuelta o esperarla aún más, tal como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4da7c-200">Therefore, you need to access the result of the returned task, or further await it, as  this example shows.</span></span>

 <span data-ttu-id="4da7c-201">Al igual que con <xref:System.Threading.Tasks.Task.WhenAll%2A>, tendrá que ser capaz de alojar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="4da7c-201">As with <xref:System.Threading.Tasks.Task.WhenAll%2A>, you have to be able to accommodate exceptions.</span></span>  <span data-ttu-id="4da7c-202">Dado que recibe de vuelta la tarea de completa, puede esperar que se hayan propagado los errores en la tarea devuelta y `try/catch` adecuadamente; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-202">Because you receive the completed task back, you can await the returned task to have errors propagated, and `try/catch` them appropriately; for example:</span></span>

```csharp
Task<bool> [] recommendations = …;
while(recommendations.Count > 0)
{
    Task<bool> recommendation = await Task.WhenAny(recommendations);
    try
    {
        if (await recommendation) BuyStock(symbol);
        break;
    }
    catch(WebException exc)
    {
        recommendations.Remove(recommendation);
    }
}
```

 <span data-ttu-id="4da7c-203">Además, aunque una primera tarea se complete correctamente, las tareas subsiguientes pueden producir un error.</span><span class="sxs-lookup"><span data-stu-id="4da7c-203">Additionally, even if a first task completes successfully, subsequent tasks may fail.</span></span>  <span data-ttu-id="4da7c-204">En este punto, tiene varias opciones para tratar las excepciones:  Puede esperar hasta que se hayan completado todas las tareas iniciadas, en cuyo caso puede utilizar el método <xref:System.Threading.Tasks.Task.WhenAll%2A>, o bien decidir que todas las excepciones son importantes y deben haber iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="4da7c-204">At this point, you have several options for dealing with exceptions:  You can wait until all the launched tasks have completed, in which case you can use the <xref:System.Threading.Tasks.Task.WhenAll%2A> method, or you can decide that all exceptions are important and must be logged.</span></span>  <span data-ttu-id="4da7c-205">Para ello, puede usar las continuaciones para recibir una notificación cuando se hayan completado las tareas de forma asincrónica:</span><span class="sxs-lookup"><span data-stu-id="4da7c-205">For this, you can use continuations to receive a notification when tasks have completed asynchronously:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => { if (t.IsFaulted) Log(t.Exception); });
}
```

 <span data-ttu-id="4da7c-206">O bien</span><span class="sxs-lookup"><span data-stu-id="4da7c-206">or:</span></span>

```csharp
foreach(Task recommendation in recommendations)
{
    var ignored = recommendation.ContinueWith(
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);
}
```

 <span data-ttu-id="4da7c-207">o incluso:</span><span class="sxs-lookup"><span data-stu-id="4da7c-207">or even:</span></span>

```csharp
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)
{
    foreach(var task in tasks)
    {
        try { await task; }
        catch(Exception exc) { Log(exc); }
    }
}
…
LogCompletionIfFailed(recommendations);
```

 <span data-ttu-id="4da7c-208">Por último, puede querer cancelar todas las operaciones restantes:</span><span class="sxs-lookup"><span data-stu-id="4da7c-208">Finally, you may want to cancel all the remaining operations:</span></span>

```csharp
var cts = new CancellationTokenSource();
var recommendations = new List<Task<bool>>()
{
    GetBuyRecommendation1Async(symbol, cts.Token),
    GetBuyRecommendation2Async(symbol, cts.Token),
    GetBuyRecommendation3Async(symbol, cts.Token)
};

Task<bool> recommendation = await Task.WhenAny(recommendations);
cts.Cancel();
if (await recommendation) BuyStock(symbol);
```

#### <a name="interleaving"></a><span data-ttu-id="4da7c-209">Intercalación</span><span class="sxs-lookup"><span data-stu-id="4da7c-209">Interleaving</span></span>
 <span data-ttu-id="4da7c-210">Considere un caso donde descarga imágenes de la web y procesa cada imagen (por ejemplo, agregando la imagen a un control de interfaz de usuario).</span><span class="sxs-lookup"><span data-stu-id="4da7c-210">Consider a case where you're downloading images from the web and processing each image (for example, adding the image to a UI control).</span></span>  <span data-ttu-id="4da7c-211">Tendrá que realizar el procesamiento secuencialmente en el subproceso de interfaz de usuario, pero quiere descargar las imágenes lo más simultáneamente como sea posible.</span><span class="sxs-lookup"><span data-stu-id="4da7c-211">You have to do the processing sequentially on the UI thread, but you want to download the images as concurrently as possible.</span></span> <span data-ttu-id="4da7c-212">Además, no desea mantener la adición de las imágenes en la interfaz de usuario hasta que todas se hayan descargado, sino que desea agregarlas a medida que se realizan:</span><span class="sxs-lookup"><span data-stu-id="4da7c-212">Also, you don’t want to hold up adding the images to the UI until they’re all downloaded—you want to add them as they complete:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

 <span data-ttu-id="4da7c-213">También puede aplicar la intercalación en un escenario que implica el procesamiento de cálculo intensivo en la clase <xref:System.Threading.ThreadPool> de las imágenes descargadas; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-213">You can also apply interleaving to a scenario that involves computationally intensive processing on the <xref:System.Threading.ThreadPool> of the downloaded images; for example:</span></span>

```csharp
List<Task<Bitmap>> imageTasks =
    (from imageUrl in urls select GetBitmapAsync(imageUrl)
         .ContinueWith(t => ConvertImage(t.Result)).ToList();
while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch{}
}
```

#### <a name="throttling"></a><span data-ttu-id="4da7c-214">Limitación de peticiones</span><span class="sxs-lookup"><span data-stu-id="4da7c-214">Throttling</span></span>
 <span data-ttu-id="4da7c-215">Considere el ejemplo de intercalación, excepto en que el usuario descarga tantas imágenes que las descargas tienen que limitarse; por ejemplo, desea que solo un número específico de descargas ocurra al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4da7c-215">Consider the interleaving example, except that the user is downloading so many images that the downloads have to be throttled; for example, you want only a specific number of downloads to happen concurrently.</span></span> <span data-ttu-id="4da7c-216">Para lograr esto, puede iniciar un subconjunto de operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="4da7c-216">To achieve this, you can start a subset of the asynchronous operations.</span></span>  <span data-ttu-id="4da7c-217">Cuando se completen las operaciones, puede iniciar operaciones adicionales que ocupen su lugar:</span><span class="sxs-lookup"><span data-stu-id="4da7c-217">As operations complete, you can start additional operations to take their place:</span></span>

```csharp
const int CONCURRENCY_LEVEL = 15;
Uri [] urls = …;
int nextIndex = 0;
var imageTasks = new List<Task<Bitmap>>();
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)
{
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
    nextIndex++;
}

while(imageTasks.Count > 0)
{
    try
    {
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);
        imageTasks.Remove(imageTask);

        Bitmap image = await imageTask;
        panel.AddImage(image);
    }
    catch(Exception exc) { Log(exc); }

    if (nextIndex < urls.Length)
    {
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));
        nextIndex++;
    }
}
```

#### <a name="early-bailout"></a><span data-ttu-id="4da7c-218">Salida anticipada</span><span class="sxs-lookup"><span data-stu-id="4da7c-218">Early Bailout</span></span>
 <span data-ttu-id="4da7c-219">Considere que está esperando asincrónicamente que una operación se complete mientras se responde simultáneamente a la solicitud de cancelación de un usuario (por ejemplo, el usuario hace clic en un botón Cancelar).</span><span class="sxs-lookup"><span data-stu-id="4da7c-219">Consider that you're waiting asynchronously for an operation to complete while simultaneously responding to a user’s cancellation request (for example, the user clicked a cancel button).</span></span> <span data-ttu-id="4da7c-220">El código siguiente muestra este escenario:</span><span class="sxs-lookup"><span data-stu-id="4da7c-220">The following code illustrates this scenario:</span></span>

```csharp
private CancellationTokenSource m_cts;

public void btnCancel_Click(object sender, EventArgs e)
{
    if (m_cts != null) m_cts.Cancel();
}

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();
    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        if (imageDownload.IsCompleted)
        {
            Bitmap image = await imageDownload;
            panel.AddImage(image);
        }
        else imageDownload.ContinueWith(t => Log(t));
    }
    finally { btnRun.Enabled = true; }
}

private static async Task UntilCompletionOrCancellation(
    Task asyncOp, CancellationToken ct)
{
    var tcs = new TaskCompletionSource<bool>();
    using(ct.Register(() => tcs.TrySetResult(true)))
        await Task.WhenAny(asyncOp, tcs.Task);
    return asyncOp;
}
```

 <span data-ttu-id="4da7c-221">Esta implementación permite volver a la interfaz de usuario en cuanto decide abandonar la operación, pero no se cancelan las operaciones asincrónicas subyacentes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-221">This implementation re-enables the user interface as soon as you decide to bail out, but doesn't cancel the underlying asynchronous operations.</span></span>  <span data-ttu-id="4da7c-222">Otra alternativa sería cancelar las operaciones pendientes cuando decide abandone la operación, pero no se restablece la interfaz de usuario hasta que las operaciones se hayan finalizado, posiblemente debido a una finalización anticipada debido a la solicitud de cancelación:</span><span class="sxs-lookup"><span data-stu-id="4da7c-222">Another alternative would be to cancel the pending operations when you decide to bail out, but not reestablish the user interface until the operations actually complete, potentially due to ending early due to the cancellation request:</span></span>

```csharp
private CancellationTokenSource m_cts;

public async void btnRun_Click(object sender, EventArgs e)
{
    m_cts = new CancellationTokenSource();

    btnRun.Enabled = false;
    try
    {
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);
        Bitmap image = await imageDownload;
        panel.AddImage(image);
    }
    catch(OperationCanceledException) {}
    finally { btnRun.Enabled = true; }
}
```

 <span data-ttu-id="4da7c-223">Otro ejemplo de recursividad temprana conlleva usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> junto con el método <xref:System.Threading.Tasks.Task.Delay%2A>, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="4da7c-223">Another example of early bailout involves using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method in conjunction with the <xref:System.Threading.Tasks.Task.Delay%2A> method, as discussed in the next section.</span></span>

### <a name="taskdelay"></a><span data-ttu-id="4da7c-224">Task.Delay</span><span class="sxs-lookup"><span data-stu-id="4da7c-224">Task.Delay</span></span>
 <span data-ttu-id="4da7c-225">Puede usar el método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> para introducir pausas en una ejecución del método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4da7c-225">You can use the <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method to introduce pauses into an asynchronous method’s execution.</span></span>  <span data-ttu-id="4da7c-226">Esto es útil para muchos tipos de funcionalidad, incluida la generación de bucles de sondeo y el retraso del control de entrada de usuario durante un período predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4da7c-226">This is useful for many kinds of functionality, including building polling loops and delaying the handling of user input for a predetermined period of time.</span></span>  <span data-ttu-id="4da7c-227">El método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> también puede resultar útil junto con <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> para implementar tiempos de espera con awaits.</span><span class="sxs-lookup"><span data-stu-id="4da7c-227">The <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> method can also be useful in combination with <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> for implementing time-outs on awaits.</span></span>

 <span data-ttu-id="4da7c-228">Si una tarea que forma parte de una operación asincrónica mayor (por ejemplo, un servicio web ASP.NET) tarda demasiado tiempo en completarse, la operación global podría verse afectada, especialmente si no se puede completar.</span><span class="sxs-lookup"><span data-stu-id="4da7c-228">If a task that’s part of a larger asynchronous operation (for example, an ASP.NET web service) takes too long to complete, the overall operation could suffer, especially if it fails to ever complete.</span></span>  <span data-ttu-id="4da7c-229">Por este motivo, es importante poder agotar el tiempo de espera al esperar a una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4da7c-229">For this reason, it’s important to be able to time out when waiting on an asynchronous operation.</span></span>  <span data-ttu-id="4da7c-230">Los métodos <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> sincrónicos aceptan valores de tiempo de espera, pero <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> y los métodos <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> mencionados anteriormente no los aceptan.</span><span class="sxs-lookup"><span data-stu-id="4da7c-230">The synchronous <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> methods accept time-out values, but the corresponding <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> and the previously mentioned <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>/<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> methods do not.</span></span>  <span data-ttu-id="4da7c-231">En su lugar, puede usar <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> en combinación con la implementación de un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4da7c-231">Instead, you can use <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> in combination to implement a time-out.</span></span>

 <span data-ttu-id="4da7c-232">Por ejemplo, en la aplicación de la interfaz de usuario, supongamos que desea descargar una imagen y deshabilitar la interfaz de usuario mientras se descarga la imagen.</span><span class="sxs-lookup"><span data-stu-id="4da7c-232">For example, in your UI application, let's say that you want to download an image and disable the UI while the image is downloading.</span></span> <span data-ttu-id="4da7c-233">Sin embargo, si la descarga tarda mucho tiempo, quiere volver a habilitar la interfaz de usuario y descartar la descarga:</span><span class="sxs-lookup"><span data-stu-id="4da7c-233">However, if the download takes too long, you want to re-enable the UI and discard the download:</span></span>

```csharp
public async void btnDownload_Click(object sender, EventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap> download = GetBitmapAsync(url);
        if (download == await Task.WhenAny(download, Task.Delay(3000)))
        {
            Bitmap bmp = await download;
            pictureBox.Image = bmp;
            status.Text = "Downloaded";
        }
        else
        {
            pictureBox.Image = null;
            status.Text = "Timed out";
            var ignored = download.ContinueWith(
                t => Trace("Task finally completed"));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

 <span data-ttu-id="4da7c-234">Lo mismo se aplica a varias descargas, porque <xref:System.Threading.Tasks.Task.WhenAll%2A> devuelve una tarea:</span><span class="sxs-lookup"><span data-stu-id="4da7c-234">The same applies to multiple downloads, because <xref:System.Threading.Tasks.Task.WhenAll%2A> returns a task:</span></span>

```csharp
public async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.Enabled = false;
    try
    {
        Task<Bitmap[]> downloads =
            Task.WhenAll(from url in urls select GetBitmapAsync(url));
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))
        {
            foreach(var bmp in downloads) panel.AddImage(bmp);
            status.Text = "Downloaded";
        }
        else
        {
            status.Text = "Timed out";
            downloads.ContinueWith(t => Log(t));
        }
    }
    finally { btnDownload.Enabled = true; }
}
```

## <a name="building-task-based-combinators"></a><span data-ttu-id="4da7c-235">Crear combinadores basados en tareas</span><span class="sxs-lookup"><span data-stu-id="4da7c-235">Building Task-based Combinators</span></span>
 <span data-ttu-id="4da7c-236">Como una tarea se puede representar completamente una operación asincrónica y proporciona funcionalidades sincrónicas y asincrónicas para combinarse con la operación y recuperar sus resultados, entre otros, puede crear bibliotecas útiles de combinadores que componen tareas para crear patrones más grandes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-236">Because a task is able to completely represent an asynchronous operation and provide synchronous and asynchronous capabilities for joining with the operation, retrieving its results, and so on, you can build useful libraries of combinators that compose tasks to build larger patterns.</span></span>  <span data-ttu-id="4da7c-237">Como se describe en la sección anterior, .NET Framework incluye varios combinadores integrados, pero también puede crear los suyos propios.</span><span class="sxs-lookup"><span data-stu-id="4da7c-237">As discussed in the previous section, the .NET Framework includes several built-in combinators, but you can also build your own.</span></span> <span data-ttu-id="4da7c-238">Las secciones siguientes proporcionan varios ejemplos de tipos y métodos de combinadores posibles.</span><span class="sxs-lookup"><span data-stu-id="4da7c-238">The following sections provide several examples of potential combinator methods and types.</span></span>

### <a name="retryonfault"></a><span data-ttu-id="4da7c-239">RetryOnFault</span><span class="sxs-lookup"><span data-stu-id="4da7c-239">RetryOnFault</span></span>
 <span data-ttu-id="4da7c-240">En muchas situaciones, puede querer reintentar la operación si se produce un error en un intento anterior.</span><span class="sxs-lookup"><span data-stu-id="4da7c-240">In many situations, you may want to retry an operation if a previous attempt fails.</span></span>  <span data-ttu-id="4da7c-241">Para el código sincrónico, podría crear un método del asistente como `RetryOnFault` en el ejemplo siguiente para lograr esto:</span><span class="sxs-lookup"><span data-stu-id="4da7c-241">For synchronous code, you might build a helper method such as `RetryOnFault` in the following example to accomplish this:</span></span>

```csharp
public static T RetryOnFault<T>(
    Func<T> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return function(); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="4da7c-242">Puede crear un método del asistente prácticamente idéntico para las operaciones asincrónicas que se implementan con TAP y, por tanto, devolver las tareas:</span><span class="sxs-lookup"><span data-stu-id="4da7c-242">You can build an almost identical helper method for asynchronous operations that are implemented with TAP and thus return tasks:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
    }
    return default(T);
}
```

 <span data-ttu-id="4da7c-243">Después puede usar este combinador para codificar los reintentos en la lógica de la aplicación; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-243">You can then use this combinator to encode retries into the application’s logic; for example:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3);
```

 <span data-ttu-id="4da7c-244">Puede ampliar aún más la función `RetryOnFault`.</span><span class="sxs-lookup"><span data-stu-id="4da7c-244">You could extend the `RetryOnFault` function further.</span></span> <span data-ttu-id="4da7c-245">Por ejemplo, la función puede aceptar otro `Func<Task>` que se invocará entre reintentos para determinar cuándo volver a intentar la operación, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-245">For example, the function could accept another `Func<Task>` that will be invoked between retries to determine when to try the operation again; for example:</span></span>

```csharp
public static async Task<T> RetryOnFault<T>(
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)
{
    for(int i=0; i<maxTries; i++)
    {
        try { return await function().ConfigureAwait(false); }
        catch { if (i == maxTries-1) throw; }
        await retryWhen().ConfigureAwait(false);
    }
    return default(T);
}
```

 <span data-ttu-id="4da7c-246">Después, puede utilizar la función siguiente para esperar un segundo antes de reintentar la operación:</span><span class="sxs-lookup"><span data-stu-id="4da7c-246">You could then use the function as follows to wait for a second before retrying the operation:</span></span>

```csharp
// Download the URL, trying up to three times in case of failure,
// and delaying for a second between retries
string pageContents = await RetryOnFault(
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));
```

### <a name="needonlyone"></a><span data-ttu-id="4da7c-247">NeedOnlyOne</span><span class="sxs-lookup"><span data-stu-id="4da7c-247">NeedOnlyOne</span></span>
 <span data-ttu-id="4da7c-248">A veces, puede sacar partido de la redundancia para mejorar la latencia y las posibilidades de éxito de una operación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-248">Sometimes, you can take advantage of redundancy to improve an operation’s latency and chances for success.</span></span>  <span data-ttu-id="4da7c-249">Considere la posibilidad de varios servicios web que proporcionan cotizaciones bursátiles, pero a lo largo del día cada servicio puede proporcionar diferentes niveles de calidad y tiempos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4da7c-249">Consider multiple web services that provide stock quotes, but at various times of the day, each service may provide different levels of quality and response times.</span></span>  <span data-ttu-id="4da7c-250">Para tratar estas fluctuaciones, pueden emitir solicitudes a todos los servicios web y tan pronto como obtiene una respuesta de uno, cancelar las solicitudes restantes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-250">To deal with these fluctuations, you may issue requests to all the web services, and as soon as you get a response from one, cancel the remaining requests.</span></span>  <span data-ttu-id="4da7c-251">Puede implementar una función del asistente para que resulte más fácil de implementar este patrón común de iniciar varias operaciones, esperar alguna y, después, cancelar el resto.</span><span class="sxs-lookup"><span data-stu-id="4da7c-251">You can implement a helper function to make it easier to implement this common pattern of launching multiple operations, waiting for any, and then canceling the rest.</span></span> <span data-ttu-id="4da7c-252">La función `NeedOnlyOne` del ejemplo siguiente muestra este escenario:</span><span class="sxs-lookup"><span data-stu-id="4da7c-252">The `NeedOnlyOne` function in the following example illustrates this scenario:</span></span>

```csharp
public static async Task<T> NeedOnlyOne(
    params Func<CancellationToken,Task<T>> [] functions)
{
    var cts = new CancellationTokenSource();
    var tasks = (from function in functions
                 select function(cts.Token)).ToArray();
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);
    cts.Cancel();
    foreach(var task in tasks)
    {
        var ignored = task.ContinueWith(
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);
    }
    return completed;
}
```

 <span data-ttu-id="4da7c-253">Después puede utilizar esta función como sigue:</span><span class="sxs-lookup"><span data-stu-id="4da7c-253">You can then use this function as follows:</span></span>

```csharp
double currentPrice = await NeedOnlyOne(
    ct => GetCurrentPriceFromServer1Async("msft", ct),
    ct => GetCurrentPriceFromServer2Async("msft", ct),
    ct => GetCurrentPriceFromServer3Async("msft", ct));
```

### <a name="interleaved-operations"></a><span data-ttu-id="4da7c-254">Operaciones intercaladas</span><span class="sxs-lookup"><span data-stu-id="4da7c-254">Interleaved Operations</span></span>
 <span data-ttu-id="4da7c-255">Hay un posible problema de rendimiento con el uso del método <xref:System.Threading.Tasks.Task.WhenAny%2A> para admitir un escenario de intercalación cuando se trabaja con conjuntos de tareas muy grandes.</span><span class="sxs-lookup"><span data-stu-id="4da7c-255">There is a potential performance problem with using the <xref:System.Threading.Tasks.Task.WhenAny%2A> method to support an interleaving scenario when you're working with very large sets of tasks.</span></span> <span data-ttu-id="4da7c-256">Todas las llamadas a <xref:System.Threading.Tasks.Task.WhenAny%2A> resultan en el registro de una continuación con cada tarea.</span><span class="sxs-lookup"><span data-stu-id="4da7c-256">Every call to <xref:System.Threading.Tasks.Task.WhenAny%2A> results in a continuation being registered with each task.</span></span> <span data-ttu-id="4da7c-257">Para un número N de tareas, el resultado son O(N<sup>2</sup>) continuaciones creadas durante la vigencia de la operación de intercalación.</span><span class="sxs-lookup"><span data-stu-id="4da7c-257">For N number of tasks, this results in O(N<sup>2</sup>) continuations created over the lifetime of the interleaving operation.</span></span> <span data-ttu-id="4da7c-258">Si trabaja con un conjunto de tareas grande, puede usar un combinador (`Interleaved` en el ejemplo siguiente) para solucionar el problema de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="4da7c-258">If you're working with a large set of tasks, you can use a combinator (`Interleaved` in the following example) to address the performance issue:</span></span>

```csharp
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)
{
    var inputTasks = tasks.ToList();
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)
                   select new TaskCompletionSource<T>()).ToList();
    int nextTaskIndex = -1;
    foreach (var inputTask in inputTasks)
    {
        inputTask.ContinueWith(completed =>
        {
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];
            if (completed.IsFaulted)
                source.TrySetException(completed.Exception.InnerExceptions);
            else if (completed.IsCanceled)
                source.TrySetCanceled();
            else
                source.TrySetResult(completed.Result);
        }, CancellationToken.None,
           TaskContinuationOptions.ExecuteSynchronously,
           TaskScheduler.Default);
    }
    return from source in sources
           select source.Task;
}
```

 <span data-ttu-id="4da7c-259">Después puede usar el combinador para procesar los resultados de las tareas a medida que se completan; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4da7c-259">You can then use the combinator to process the results of tasks as they complete; for example:</span></span>

```csharp
IEnumerable<Task<int>> tasks = ...;
foreach(var task in Interleaved(tasks))
{
    int result = await task;
    …
}
```

### <a name="whenallorfirstexception"></a><span data-ttu-id="4da7c-260">WhenAllOrFirstException</span><span class="sxs-lookup"><span data-stu-id="4da7c-260">WhenAllOrFirstException</span></span>
 <span data-ttu-id="4da7c-261">En ciertos escenarios de dispersión y recopilación, puede querer esperar a todas las tareas de un conjunto, a menos que una de ellas falle, en cuyo caso deseará detener la espera en cuanto se produzca la excepción.</span><span class="sxs-lookup"><span data-stu-id="4da7c-261">In certain scatter/gather scenarios, you might want to wait for all tasks in a set, unless one of them faults, in which case you want to stop waiting as soon as the exception occurs.</span></span>  <span data-ttu-id="4da7c-262">Puede conseguirlo con un método de combinador como `WhenAllOrFirstException` en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4da7c-262">You can accomplish that with a combinator method such as `WhenAllOrFirstException` in the following example:</span></span>

```csharp
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)
{
    var inputs = tasks.ToList();
    var ce = new CountdownEvent(inputs.Count);
    var tcs = new TaskCompletionSource<T[]>();

    Action<Task> onCompleted = (Task completed) =>
    {
        if (completed.IsFaulted)
            tcs.TrySetException(completed.Exception.InnerExceptions);
        if (ce.Signal() && !tcs.Task.IsCompleted)
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());
    };

    foreach (var t in inputs) t.ContinueWith(onCompleted);
    return tcs.Task;
}
```

## <a name="building-task-based-data-structures"></a><span data-ttu-id="4da7c-263">Crear estructuras de datos basadas en tareas</span><span class="sxs-lookup"><span data-stu-id="4da7c-263">Building Task-based Data Structures</span></span>
 <span data-ttu-id="4da7c-264">Además de la capacidad de generar combinadores basados en tareas personalizadas, disponer de una estructura de datos de <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> que representa tanto los resultados de una operación asincrónica y la sincronización necesaria para unirse a ella la convierte en un tipo muy eficaz para crear estructuras de datos personalizadas para usarse en escenarios asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="4da7c-264">In addition to the ability to build custom task-based combinators, having a data structure in <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> that represents both the results of an asynchronous operation and the necessary synchronization to join with it makes it a very powerful type on which to build custom data structures to be used in asynchronous scenarios.</span></span>

### <a name="asynccache"></a><span data-ttu-id="4da7c-265">AsyncCache</span><span class="sxs-lookup"><span data-stu-id="4da7c-265">AsyncCache</span></span>
 <span data-ttu-id="4da7c-266">Un aspecto importante de una tarea es que se puede entregar a varios consumidores, todos ellos pueden esperar a que finalice, registrar las continuaciones con ella, obtener sus resultados o excepciones (en el caso de <xref:System.Threading.Tasks.Task%601>), y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="4da7c-266">One important aspect of a task is that it may be handed out to multiple consumers, all of whom may await it, register continuations with it, get its result or exceptions (in the case of <xref:System.Threading.Tasks.Task%601>), and so on.</span></span>  <span data-ttu-id="4da7c-267">Esto hace que <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> sean perfectos para usarse en una infraestructura de almacenamiento en caché asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4da7c-267">This makes <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> perfectly suited to be used in an asynchronous caching infrastructure.</span></span>  <span data-ttu-id="4da7c-268">Este es un ejemplo de una caché asincrónica pequeña pero muy eficaz creada a partir del objeto <xref:System.Threading.Tasks.Task%601>:</span><span class="sxs-lookup"><span data-stu-id="4da7c-268">Here’s an example of a small but powerful asynchronous cache built on top of <xref:System.Threading.Tasks.Task%601>:</span></span>

```csharp
public class AsyncCache<TKey, TValue>
{
    private readonly Func<TKey, Task<TValue>> _valueFactory;
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;

    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)
    {
        if (valueFactory == null) throw new ArgumentNullException("loader");
        _valueFactory = valueFactory;
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();
    }

    public Task<TValue> this[TKey key]
    {
        get
        {
            if (key == null) throw new ArgumentNullException("key");
            return _map.GetOrAdd(key, toAdd =>
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;
        }
    }
}
```

 <span data-ttu-id="4da7c-269">La clase [AsyncCache\<TKey,TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) acepta como delegado para su constructor una función que adopta un elemento `TKey` y devuelve un elemento <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="4da7c-269">The [AsyncCache\<TKey,TValue>](https://devblogs.microsoft.com/pfxteam/parallelextensionsextras-tour-12-asynccache/) class accepts as a delegate to its constructor a function that takes a `TKey` and returns a <xref:System.Threading.Tasks.Task%601>.</span></span>  <span data-ttu-id="4da7c-270">Todos los valores a los que se accedió previamente desde la memoria caché se almacenan en el diccionario interno y `AsyncCache` asegura que solo una tarea se genera por clave, incluso si se tiene acceso a la memoria caché al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4da7c-270">Any previously accessed values from the cache are stored in the internal dictionary, and the `AsyncCache` ensures that only one task is generated per key, even if the cache is accessed concurrently.</span></span>

 <span data-ttu-id="4da7c-271">Por ejemplo, puede crear una caché de páginas web descargadas:</span><span class="sxs-lookup"><span data-stu-id="4da7c-271">For example, you can build a cache for downloaded web pages:</span></span>

```csharp
private AsyncCache<string,string> m_webPages =
    new AsyncCache<string,string>(DownloadStringAsync);
```

 <span data-ttu-id="4da7c-272">Después puede utilizar esta caché en métodos asincrónicos siempre que necesite el contenido de una página web.</span><span class="sxs-lookup"><span data-stu-id="4da7c-272">You can then use this cache in asynchronous methods whenever you need the contents of a web page.</span></span> <span data-ttu-id="4da7c-273">La clase `AsyncCache` garantiza que está descargando el menor número de páginas posible y almacena en caché los resultados.</span><span class="sxs-lookup"><span data-stu-id="4da7c-273">The `AsyncCache` class ensures that you’re downloading as few pages as possible, and caches the results.</span></span>

```csharp
private async void btnDownload_Click(object sender, RoutedEventArgs e)
{
    btnDownload.IsEnabled = false;
    try
    {
        txtContents.Text = await m_webPages["https://www.microsoft.com"];
    }
    finally { btnDownload.IsEnabled = true; }
}
```

### <a name="asyncproducerconsumercollection"></a><span data-ttu-id="4da7c-274">AsyncProducerConsumerCollection</span><span class="sxs-lookup"><span data-stu-id="4da7c-274">AsyncProducerConsumerCollection</span></span>
 <span data-ttu-id="4da7c-275">También puede usar tareas para crear estructuras de datos para la coordinación de actividades asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="4da7c-275">You can also use tasks to build data structures for coordinating asynchronous activities.</span></span>  <span data-ttu-id="4da7c-276">Considere uno de los patrones de diseño paralelo clásico: productor-consumidor.</span><span class="sxs-lookup"><span data-stu-id="4da7c-276">Consider one of the classic parallel design patterns: producer/consumer.</span></span>  <span data-ttu-id="4da7c-277">En este patrón, los productores generan datos consumidos por los consumidores, y los productores y los consumidores pueden ejecutarlos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4da7c-277">In this pattern, producers generate data that is consumed by consumers, and the producers and consumers may run in parallel.</span></span> <span data-ttu-id="4da7c-278">Por ejemplo, el consumidor procesa el elemento 1, que fue generado previamente por un productor que ahora está produciendo el elemento 2.</span><span class="sxs-lookup"><span data-stu-id="4da7c-278">For example, the consumer processes item 1, which was previously generated by a producer who is now producing item 2.</span></span>  <span data-ttu-id="4da7c-279">Para el modelo productor-consumidor, necesita invariablemente alguna estructura de datos para almacenar los trabajos creados por los productores, para que los consumidores puedan recibir notificaciones de nuevos datos y encontrarlos si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="4da7c-279">For the producer/consumer pattern, you invariably need some data structure to store the work created by producers so that the consumers may be notified of new data and find it when available.</span></span>

 <span data-ttu-id="4da7c-280">A continuación se muestra una estructura de datos simple creada sobre las tareas, que permite el uso de métodos asincrónicos como productores y consumidores:</span><span class="sxs-lookup"><span data-stu-id="4da7c-280">Here’s a simple data structure built on top of tasks that enables asynchronous methods to be used as producers and consumers:</span></span>

```csharp
public class AsyncProducerConsumerCollection<T>
{
    private readonly Queue<T> m_collection = new Queue<T>();
    private readonly Queue<TaskCompletionSource<T>> m_waiting =
        new Queue<TaskCompletionSource<T>>();

    public void Add(T item)
    {
        TaskCompletionSource<T> tcs = null;
        lock (m_collection)
        {
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();
            else m_collection.Enqueue(item);
        }
        if (tcs != null) tcs.TrySetResult(item);
    }

    public Task<T> Take()
    {
        lock (m_collection)
        {
            if (m_collection.Count > 0)
            {
                return Task.FromResult(m_collection.Dequeue());
            }
            else
            {
                var tcs = new TaskCompletionSource<T>();
                m_waiting.Enqueue(tcs);
                return tcs.Task;
            }
        }
    }
}
```

 <span data-ttu-id="4da7c-281">Con esta estructura de datos en su lugar, puede escribir código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="4da7c-281">With that data structure in place, you can write code such as the following:</span></span>

```csharp
private static AsyncProducerConsumerCollection<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.Take();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Add(data);
}
```

<span data-ttu-id="4da7c-282">El espacio de nombres <xref:System.Threading.Tasks.Dataflow> incluye el tipo <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>, que se puede usar de forma similar, pero sin tener que crear un tipo de colección personalizado:</span><span class="sxs-lookup"><span data-stu-id="4da7c-282">The <xref:System.Threading.Tasks.Dataflow> namespace includes the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> type, which you can use in a similar manner, but without having to build a custom collection type:</span></span>

```csharp
private static BufferBlock<int> m_data = …;
…
private static async Task ConsumerAsync()
{
    while(true)
    {
        int nextItem = await m_data.ReceiveAsync();
        ProcessNextItem(nextItem);
    }
}
…
private static void Produce(int data)
{
    m_data.Post(data);
}
```

> [!NOTE]
> <span data-ttu-id="4da7c-283">El espacio de nombres <xref:System.Threading.Tasks.Dataflow> está disponible en .NET Framework 4.5 mediante **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="4da7c-283">The <xref:System.Threading.Tasks.Dataflow> namespace is available in the .NET Framework 4.5 through **NuGet**.</span></span> <span data-ttu-id="4da7c-284">Para instalar el ensamblado que contiene el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en Visual Studio, elija **Administrar paquetes NuGet** en el menú Proyecto y busque en línea el paquete Microsoft.Tpl.Dataflow.</span><span class="sxs-lookup"><span data-stu-id="4da7c-284">To install the assembly that contains the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in Visual Studio, choose **Manage NuGet Packages** from the Project menu, and search online for the Microsoft.Tpl.Dataflow package.</span></span>

## <a name="see-also"></a><span data-ttu-id="4da7c-285">Vea también</span><span class="sxs-lookup"><span data-stu-id="4da7c-285">See also</span></span>

- [<span data-ttu-id="4da7c-286">Modelo asincrónico basado en tareas (TAP)</span><span class="sxs-lookup"><span data-stu-id="4da7c-286">Task-based Asynchronous Pattern (TAP)</span></span>](task-based-asynchronous-pattern-tap.md)
- [<span data-ttu-id="4da7c-287">Implementar el modelo asincrónico basado en tareas</span><span class="sxs-lookup"><span data-stu-id="4da7c-287">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="4da7c-288">Interoperabilidad con otros tipos y patrones asincrónicos</span><span class="sxs-lookup"><span data-stu-id="4da7c-288">Interop with Other Asynchronous Patterns and Types</span></span>](interop-with-other-asynchronous-patterns-and-types.md)
