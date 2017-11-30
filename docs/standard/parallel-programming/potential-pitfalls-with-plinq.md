---
title: Posibles problemas con PLINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="adebf-102">Posibles problemas con PLINQ</span><span class="sxs-lookup"><span data-stu-id="adebf-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="adebf-103">En muchos casos, PLINQ puede proporcionar importantes mejoras de rendimiento sobre secuencial LINQ a consultas de objetos.</span><span class="sxs-lookup"><span data-stu-id="adebf-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="adebf-104">Sin embargo, el trabajo de paralelizar la ejecución de la consulta aumenta la complejidad que puede dar lugar a problemas que, en código secuencial, no son tan comunes o no se encuentran en absoluto.</span><span class="sxs-lookup"><span data-stu-id="adebf-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="adebf-105">Este tema enumeran algunos procedimientos que se deben evitar al escribir consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="adebf-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="adebf-106">No suponer que la ejecución en paralelo siempre es más rápida</span><span class="sxs-lookup"><span data-stu-id="adebf-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="adebf-107">En ocasiones, la paralelización hace que una consulta PLINQ se ejecuten más lentamente que su LINQ a equivalente de objetos.</span><span class="sxs-lookup"><span data-stu-id="adebf-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="adebf-108">La regla básica es que las consultas que tienen algunos elementos de origen y delegados de rápido de usuario son muy poco probable que la velocidad.</span><span class="sxs-lookup"><span data-stu-id="adebf-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="adebf-109">Sin embargo, dado que hay muchos factores que afectan al rendimiento, se recomienda medir los resultados reales antes de decidir si se usa PLINQ.</span><span class="sxs-lookup"><span data-stu-id="adebf-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="adebf-110">Para más información, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="adebf-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="adebf-111">Evitar la escritura en ubicaciones de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="adebf-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="adebf-112">En código secuencial, no es raro leer o escribir en variables estáticas o campos de clase.</span><span class="sxs-lookup"><span data-stu-id="adebf-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="adebf-113">Sin embargo, cada vez que varios subprocesos tienen acceso simultáneamente a estas variables, hay grandes posibilidades de que se produzcan condiciones de carrera.</span><span class="sxs-lookup"><span data-stu-id="adebf-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="adebf-114">Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="adebf-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="adebf-115">Por lo tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en una consulta PLINQ tanto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="adebf-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="adebf-116">Evitar la paralelización excesiva</span><span class="sxs-lookup"><span data-stu-id="adebf-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="adebf-117">Mediante el uso de la `AsParallel` (operador), se incurre en los costes generales de creación de particiones de la colección de origen y sincronizar los subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="adebf-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="adebf-118">El número de procesadores del equipo reduce también las ventajas de la paralelización.</span><span class="sxs-lookup"><span data-stu-id="adebf-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="adebf-119">Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad.</span><span class="sxs-lookup"><span data-stu-id="adebf-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="adebf-120">Por lo tanto, debe ser cuidado de no para paralelizar en exceso una consulta.</span><span class="sxs-lookup"><span data-stu-id="adebf-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="adebf-121">El escenario más común en puede ocurrir que la paralelización excesiva está en las consultas anidadas, tal como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="adebf-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="adebf-122">En este caso, es mejor paralelizar el origen de datos exterior (clientes) a menos que se aplican una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="adebf-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="adebf-123">El origen de datos interno (cust. Pedidos) se conoce a ser muy largos.</span><span class="sxs-lookup"><span data-stu-id="adebf-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="adebf-124">Se realiza un cálculo costoso en cada pedido</span><span class="sxs-lookup"><span data-stu-id="adebf-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="adebf-125">(la operación que se muestra en el ejemplo no es costosa).</span><span class="sxs-lookup"><span data-stu-id="adebf-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="adebf-126">Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.</span><span class="sxs-lookup"><span data-stu-id="adebf-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="adebf-127">En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición.</span><span class="sxs-lookup"><span data-stu-id="adebf-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="adebf-128">Para obtener más información, consulte [Cómo: medir el rendimiento de consultas de PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span><span class="sxs-lookup"><span data-stu-id="adebf-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="adebf-129">Evitar llamadas a métodos que no son seguros para subprocesos</span><span class="sxs-lookup"><span data-stu-id="adebf-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="adebf-130">Escribir en los métodos de instancia no es segura para subprocesos de un PLINQ consulta puede provocar daños en los datos que puede o no pueden pasar desapercibida en su programa.</span><span class="sxs-lookup"><span data-stu-id="adebf-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="adebf-131">También puede dar lugar a excepciones.</span><span class="sxs-lookup"><span data-stu-id="adebf-131">It can also lead to exceptions.</span></span> <span data-ttu-id="adebf-132">En el ejemplo siguiente, varios subprocesos estarían intentando llamar a la `Filestream.Write` método simultáneamente, lo que no es compatible con la clase.</span><span class="sxs-lookup"><span data-stu-id="adebf-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="adebf-133">Limitar las llamadas a métodos seguros para subprocesos</span><span class="sxs-lookup"><span data-stu-id="adebf-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="adebf-134">La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les puede llamar simultáneamente desde varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="adebf-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="adebf-135">Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.</span><span class="sxs-lookup"><span data-stu-id="adebf-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adebf-136">Se puede probar esto usted mismo mediante la inserción de algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas.</span><span class="sxs-lookup"><span data-stu-id="adebf-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="adebf-137">Aunque este método se utiliza en los ejemplos de documentación para fines de demostración, no debe usarse en consultas PLINQ.</span><span class="sxs-lookup"><span data-stu-id="adebf-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="adebf-138">Evitar operaciones de ordenación innecesarias</span><span class="sxs-lookup"><span data-stu-id="adebf-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="adebf-139">Cuando PLINQ ejecuta una consulta en paralelo, divide la secuencia de origen en particiones que pueden funcionar simultáneamente en varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="adebf-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="adebf-140">De forma predeterminada, el orden en el que se procesan las particiones y se entregan los resultados no es predecible (excepto para operadores como `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="adebf-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="adebf-141">Puede indicar a PLINQ que conserve el orden de cualquier secuencia de origen, pero esto tiene un impacto negativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="adebf-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="adebf-142">El procedimiento recomendado, siempre que sea posible, es estructurar las consultas para que no dependen de conservar el orden.</span><span class="sxs-lookup"><span data-stu-id="adebf-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="adebf-143">Para más información, consulte cómo [conservar el orden en PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="adebf-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="adebf-144">Preferir ForAll a ForEach cuando sea posible</span><span class="sxs-lookup"><span data-stu-id="adebf-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="adebf-145">Aunque PLINQ ejecuta una consulta en varios subprocesos, si utilizas los resultados en un `foreach` bucle (`For Each` en Visual Basic), los resultados de la consulta se deben volver a combinar en un subproceso y tiene acceso en serie por el enumerador.</span><span class="sxs-lookup"><span data-stu-id="adebf-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="adebf-146">En algunos casos, esto es inevitable; Sin embargo, siempre que sea posible, utilice la `ForAll` método para habilitar cada subproceso genera sus propios resultados, por ejemplo, al escribir en una colección segura para subprocesos como <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="adebf-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="adebf-147">El mismo problema se aplica a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> en otras palabras, `source.AsParallel().Where().ForAll(...)` debe estar fuertemente preferido para</span><span class="sxs-lookup"><span data-stu-id="adebf-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="adebf-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="adebf-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="adebf-149">Tener en cuenta los problemas de afinidad de los subprocesos</span><span class="sxs-lookup"><span data-stu-id="adebf-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="adebf-150">Algunas tecnologías, como la interoperabilidad COM para componentes de contenedor uniproceso (STA), Windows Forms y Windows Presentation Foundation (WPF), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado.</span><span class="sxs-lookup"><span data-stu-id="adebf-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="adebf-151">Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó.</span><span class="sxs-lookup"><span data-stu-id="adebf-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="adebf-152">Si intenta tener acceso al estado compartido de un control de formularios Windows Forms en una consulta PLINQ, se produce una excepción si se ejecuta en el depurador.</span><span class="sxs-lookup"><span data-stu-id="adebf-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="adebf-153">(Esta opción puede desactivarse.) Sin embargo, si la consulta se consume en el subproceso de interfaz de usuario, a continuación, tener acceso al control de la `foreach` bucle que enumera la consulta de resultados, ya que el código se ejecuta en un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="adebf-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="adebf-154">No suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo</span><span class="sxs-lookup"><span data-stu-id="adebf-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="adebf-155">Es importante tener en cuenta que las iteraciones individuales en un <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> mayo de bucle pero no tiene que ejecutar en paralelo.</span><span class="sxs-lookup"><span data-stu-id="adebf-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="adebf-156">Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.</span><span class="sxs-lookup"><span data-stu-id="adebf-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="adebf-157">Por ejemplo, es probable que este código lleve a un interbloqueo:</span><span class="sxs-lookup"><span data-stu-id="adebf-157">For example, this code is likely to deadlock:</span></span>  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
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
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
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
  
 <span data-ttu-id="adebf-158">En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento.</span><span class="sxs-lookup"><span data-stu-id="adebf-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="adebf-159">Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento.</span><span class="sxs-lookup"><span data-stu-id="adebf-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="adebf-160">Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="adebf-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="adebf-161">Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.</span><span class="sxs-lookup"><span data-stu-id="adebf-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="adebf-162">En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar.</span><span class="sxs-lookup"><span data-stu-id="adebf-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="adebf-163">Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="adebf-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adebf-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="adebf-164">See Also</span></span>  
 [<span data-ttu-id="adebf-165">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="adebf-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
