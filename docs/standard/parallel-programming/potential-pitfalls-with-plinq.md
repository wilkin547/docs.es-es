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
# <a name="potential-pitfalls-with-plinq"></a>Posibles problemas con PLINQ
En muchos casos, PLINQ puede proporcionar importantes mejoras de rendimiento sobre secuencial LINQ a consultas de objetos. Sin embargo, el trabajo de paralelizar la ejecución de la consulta aumenta la complejidad que puede dar lugar a problemas que, en código secuencial, no son tan comunes o no se encuentran en absoluto. Este tema enumeran algunos procedimientos que se deben evitar al escribir consultas PLINQ.  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>No suponer que la ejecución en paralelo siempre es más rápida  
 En ocasiones, la paralelización hace que una consulta PLINQ se ejecuten más lentamente que su LINQ a equivalente de objetos. La regla básica es que las consultas que tienen algunos elementos de origen y delegados de rápido de usuario son muy poco probable que la velocidad. Sin embargo, dado que hay muchos factores que afectan al rendimiento, se recomienda medir los resultados reales antes de decidir si se usa PLINQ. Para más información, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>Evitar la escritura en ubicaciones de memoria compartida  
 En código secuencial, no es raro leer o escribir en variables estáticas o campos de clase. Sin embargo, cada vez que varios subprocesos tienen acceso simultáneamente a estas variables, hay grandes posibilidades de que se produzcan condiciones de carrera. Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento. Por lo tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en una consulta PLINQ tanto como sea posible.  
  
## <a name="avoid-over-parallelization"></a>Evitar la paralelización excesiva  
 Mediante el uso de la `AsParallel` (operador), se incurre en los costes generales de creación de particiones de la colección de origen y sincronizar los subprocesos de trabajo. El número de procesadores del equipo reduce también las ventajas de la paralelización. Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad. Por lo tanto, debe ser cuidado de no para paralelizar en exceso una consulta.  
  
 El escenario más común en puede ocurrir que la paralelización excesiva está en las consultas anidadas, tal como se muestra en el siguiente fragmento de código.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 En este caso, es mejor paralelizar el origen de datos exterior (clientes) a menos que se aplican una o varias de las condiciones siguientes:  
  
-   El origen de datos interno (cust. Pedidos) se conoce a ser muy largos.  
  
-   Se realiza un cálculo costoso en cada pedido (la operación que se muestra en el ejemplo no es costosa).  
  
-   Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.  
  
 En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición. Para obtener más información, consulte [Cómo: medir el rendimiento de consultas de PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>Evitar llamadas a métodos que no son seguros para subprocesos  
 Escribir en los métodos de instancia no es segura para subprocesos de un PLINQ consulta puede provocar daños en los datos que puede o no pueden pasar desapercibida en su programa. También puede dar lugar a excepciones. En el ejemplo siguiente, varios subprocesos estarían intentando llamar a la `Filestream.Write` método simultáneamente, lo que no es compatible con la clase.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a>Limitar las llamadas a métodos seguros para subprocesos  
 La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les puede llamar simultáneamente desde varios subprocesos. Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.  
  
> [!NOTE]
>  Se puede probar esto usted mismo mediante la inserción de algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas. Aunque este método se utiliza en los ejemplos de documentación para fines de demostración, no debe usarse en consultas PLINQ.  
  
## <a name="avoid-unnecessary-ordering-operations"></a>Evitar operaciones de ordenación innecesarias  
 Cuando PLINQ ejecuta una consulta en paralelo, divide la secuencia de origen en particiones que pueden funcionar simultáneamente en varios subprocesos. De forma predeterminada, el orden en el que se procesan las particiones y se entregan los resultados no es predecible (excepto para operadores como `OrderBy`). Puede indicar a PLINQ que conserve el orden de cualquier secuencia de origen, pero esto tiene un impacto negativo en el rendimiento. El procedimiento recomendado, siempre que sea posible, es estructurar las consultas para que no dependen de conservar el orden. Para más información, consulte cómo [conservar el orden en PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Preferir ForAll a ForEach cuando sea posible  
 Aunque PLINQ ejecuta una consulta en varios subprocesos, si utilizas los resultados en un `foreach` bucle (`For Each` en Visual Basic), los resultados de la consulta se deben volver a combinar en un subproceso y tiene acceso en serie por el enumerador. En algunos casos, esto es inevitable; Sin embargo, siempre que sea posible, utilice la `ForAll` método para habilitar cada subproceso genera sus propios resultados, por ejemplo, al escribir en una colección segura para subprocesos como <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.  
  
 El mismo problema se aplica a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> en otras palabras, `source.AsParallel().Where().ForAll(...)` debe estar fuertemente preferido para  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## <a name="be-aware-of-thread-affinity-issues"></a>Tener en cuenta los problemas de afinidad de los subprocesos  
 Algunas tecnologías, como la interoperabilidad COM para componentes de contenedor uniproceso (STA), Windows Forms y Windows Presentation Foundation (WPF), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado. Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó. Si intenta tener acceso al estado compartido de un control de formularios Windows Forms en una consulta PLINQ, se produce una excepción si se ejecuta en el depurador. (Esta opción puede desactivarse.) Sin embargo, si la consulta se consume en el subproceso de interfaz de usuario, a continuación, tener acceso al control de la `foreach` bucle que enumera la consulta de resultados, ya que el código se ejecuta en un solo subproceso.  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>No suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo  
 Es importante tener en cuenta que las iteraciones individuales en un <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> mayo de bucle pero no tiene que ejecutar en paralelo. Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.  
  
 Por ejemplo, es probable que este código lleve a un interbloqueo:  
  
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
  
 En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento. Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento. Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse. Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.  
  
 En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar. Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.  
  
## <a name="see-also"></a>Vea también  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
