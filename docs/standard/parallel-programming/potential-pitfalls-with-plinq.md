---
title: Posibles problemas con PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
ms.openlocfilehash: 3ddc0c013335e6a7b4708a5dd8be0b2247b2f60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74716251"
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="7c3d2-102">Posibles problemas con PLINQ</span><span class="sxs-lookup"><span data-stu-id="7c3d2-102">Potential pitfalls with PLINQ</span></span>

<span data-ttu-id="7c3d2-103">En muchos casos, PLINQ puede proporcionar importantes mejoras de rendimiento con respecto a las consultas secuenciales LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="7c3d2-104">Sin embargo, el trabajo de paralelizar la ejecución de consultas aporta una complejidad que puede conducir a problemas que, en código secuencial, no son tan comunes o no se producen en ningún caso.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="7c3d2-105">En este tema se indican algunas prácticas que se deben evitar al escribir consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>

## <a name="dont-assume-that-parallel-is-always-faster"></a><span data-ttu-id="7c3d2-106">No suponer que la ejecución en paralelo siempre es más rápida</span><span class="sxs-lookup"><span data-stu-id="7c3d2-106">Don't assume that parallel is always faster</span></span>

<span data-ttu-id="7c3d2-107">En ocasiones, la paralelización hace que una consulta PLINQ se ejecute más lentamente que su equivalente LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="7c3d2-108">La regla de oro básica es que es poco probable que las consultas que tienen pocos elementos de origen y delegados de usuario rápidos se agilicen demasiado.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="7c3d2-109">Sin embargo, dado que hay muchos factores que afectan al rendimiento, se recomienda medir los resultados reales antes de decidir si usar PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="7c3d2-110">Para más información, consulte [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d2-110">For more information, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>

## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="7c3d2-111">Evitar la escritura en ubicaciones de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="7c3d2-111">Avoid writing to shared memory locations</span></span>

<span data-ttu-id="7c3d2-112">En código secuencial, no es raro leer o escribir en variables estáticas o campos de clase.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="7c3d2-113">Sin embargo, cada vez que varios subprocesos tienen acceso simultáneamente a estas variables, hay grandes posibilidades de que se produzcan condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="7c3d2-114">Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="7c3d2-115">Por tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en una consulta PLINQ en la medida de lo posible.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>

## <a name="avoid-over-parallelization"></a><span data-ttu-id="7c3d2-116">Evitar la paralelización excesiva</span><span class="sxs-lookup"><span data-stu-id="7c3d2-116">Avoid over-parallelization</span></span>

<span data-ttu-id="7c3d2-117">Si usa el método `AsParallel`, incurrirá en costos de sobrecarga al crear particiones de la colección de origen y sincronizar los subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-117">By using the `AsParallel` method, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="7c3d2-118">El número de procesadores del equipo reduce también las ventajas de la paralelización.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="7c3d2-119">Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="7c3d2-120">Por tanto, debe tener cuidado para no paralelizar en exceso una consulta.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-120">Therefore, you must be careful not to over-parallelize a query.</span></span>

<span data-ttu-id="7c3d2-121">El escenario más común en el que se puede producir un exceso de paralelización son las consultas anidadas, como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>

[!code-csharp[PLINQ#20](~/samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

<span data-ttu-id="7c3d2-122">En este caso, es mejor paralelizar únicamente el origen de datos exterior (clientes), a menos que se cumplan una o varias de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="7c3d2-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>

- <span data-ttu-id="7c3d2-123">Se sabe que el origen de datos interno (cust.Orders) es muy largo.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-123">The inner data source (cust.Orders) is known to be very long.</span></span>

- <span data-ttu-id="7c3d2-124">Se realiza un cálculo costoso en cada pedido</span><span class="sxs-lookup"><span data-stu-id="7c3d2-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="7c3d2-125">(la operación que se muestra en el ejemplo no es costosa).</span><span class="sxs-lookup"><span data-stu-id="7c3d2-125">(The operation shown in the example is not expensive.)</span></span>

- <span data-ttu-id="7c3d2-126">Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>

<span data-ttu-id="7c3d2-127">En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="7c3d2-128">Para obtener más información, vea [Cómo: Medir el rendimiento de consultas PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d2-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>

## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="7c3d2-129">Evitar llamadas a métodos que no son seguros para subprocesos</span><span class="sxs-lookup"><span data-stu-id="7c3d2-129">Avoid calls to non-thread-safe methods</span></span>

<span data-ttu-id="7c3d2-130">La escritura en métodos de instancia que no son seguros para subprocesos de una consulta PLINQ puede producir daños en los datos, que pueden pasar o no inadvertidos para el programa.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="7c3d2-131">También puede dar lugar a excepciones.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-131">It can also lead to exceptions.</span></span> <span data-ttu-id="7c3d2-132">En el siguiente ejemplo, varios subprocesos estarían intentando llamar simultáneamente al método `FileStream.Write`, lo que no se admite en la clase.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-132">In the following example, multiple threads would be attempting to call the `FileStream.Write` method simultaneously, which is not supported by the class.</span></span>

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="7c3d2-133">Limitar las llamadas a métodos seguros para subprocesos</span><span class="sxs-lookup"><span data-stu-id="7c3d2-133">Limit calls to thread-safe methods</span></span>

<span data-ttu-id="7c3d2-134">La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les puede llamar simultáneamente desde varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="7c3d2-135">Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>

> [!NOTE]
> <span data-ttu-id="7c3d2-136">Puede comprobarlo si inserta algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="7c3d2-137">Aunque este método se usa en los ejemplos de la documentación para fines de demostración, no debe usarlo en consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>

## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="7c3d2-138">Evitar operaciones de ordenación innecesarias</span><span class="sxs-lookup"><span data-stu-id="7c3d2-138">Avoid unnecessary ordering operations</span></span>

<span data-ttu-id="7c3d2-139">Cuando PLINQ ejecuta una consulta en paralelo, divide la secuencia de origen en particiones que pueden funcionar simultáneamente en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="7c3d2-140">De forma predeterminada, el orden en el que se procesan las particiones y se entregan los resultados no es predecible (excepto para operadores como `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="7c3d2-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="7c3d2-141">Puede indicar a PLINQ que conserve el orden de cualquier secuencia de origen, pero esto tiene un impacto negativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="7c3d2-142">El procedimiento recomendado, siempre que sea posible, es estructurar las consultas para que no dependan de la conservación del orden.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="7c3d2-143">Para más información, consulte cómo [conservar el orden en PLINQ](order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d2-143">For more information, see [Order Preservation in PLINQ](order-preservation-in-plinq.md).</span></span>

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="7c3d2-144">Preferir ForAll en lugar de ForEach cuando sea posible</span><span class="sxs-lookup"><span data-stu-id="7c3d2-144">Prefer ForAll to ForEach when it is possible</span></span>

<span data-ttu-id="7c3d2-145">Aunque PLINQ ejecuta una consulta en varios subprocesos, si utiliza los resultados en un bucle `foreach` (`For Each` en Visual Basic), los resultados de la consulta se deben volver a combinar en un subproceso y el enumerador debe acceder a ellos en serie.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="7c3d2-146">En algunos casos, esto es inevitable; sin embargo, siempre que sea posible, utilice el método `ForAll` para habilitar cada subproceso para generar sus propios resultados, por ejemplo, al escribir en una colección segura para subprocesos como <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7c3d2-147">Este mismo problema es aplicable a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7c3d2-148">En otras palabras, `source.AsParallel().Where().ForAll(...)` debe tener máxima prioridad con respecto a `Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-148">In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to `Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>

## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="7c3d2-149">Tener en cuenta los problemas de afinidad de los subprocesos</span><span class="sxs-lookup"><span data-stu-id="7c3d2-149">Be aware of thread affinity issues</span></span>

<span data-ttu-id="7c3d2-150">Algunas tecnologías, como la interoperabilidad COM para componentes de contenedor uniproceso (STA), Windows Forms y Windows Presentation Foundation (WPF), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="7c3d2-151">Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="7c3d2-152">Si intenta tener acceso al estado compartido de un control de formularios Windows Forms en una consulta PLINQ, se produce una excepción si se ejecuta en el depurador.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="7c3d2-153">(Esta opción puede desactivarse). Sin embargo, si la consulta se usa en el subproceso de interfaz de usuario, entonces puede acceder al control del bucle `foreach` que enumera los resultados de la consulta, ya que el código se ejecuta en un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>

## <a name="dont-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="7c3d2-154">No suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo</span><span class="sxs-lookup"><span data-stu-id="7c3d2-154">Don't assume that iterations of ForEach, For, and ForAll always execute in parallel</span></span>

<span data-ttu-id="7c3d2-155">Es importante tener en cuenta que las iteraciones individuales de un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> pueden ejecutarse en paralelo, pero no tiene que ser así necesariamente.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>, or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="7c3d2-156">Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>

<span data-ttu-id="7c3d2-157">Por ejemplo, es probable que este código lleve a un interbloqueo:</span><span class="sxs-lookup"><span data-stu-id="7c3d2-157">For example, this code is likely to deadlock:</span></span>

```vb
Dim mre = New ManualResetEventSlim()
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll(Sub(j)
   If j = Environment.ProcessorCount Then
       Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Set()
   Else
       Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Wait()
   End If
End Sub) ' deadlocks
```

```csharp
ManualResetEventSlim mre = new ManualResetEventSlim();
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll((j) =>
{
    if (j == Environment.ProcessorCount)
    {
        Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Set();
    }
    else
    {
        Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Wait();
    }
}); //deadlocks
```

<span data-ttu-id="7c3d2-158">En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="7c3d2-159">Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="7c3d2-160">Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="7c3d2-161">Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>

<span data-ttu-id="7c3d2-162">En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="7c3d2-163">Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="7c3d2-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c3d2-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c3d2-164">See also</span></span>

- [<span data-ttu-id="7c3d2-165">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="7c3d2-165">Parallel LINQ (PLINQ)</span></span>](parallel-linq-plinq.md)
