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
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716251"
---
# <a name="potential-pitfalls-with-plinq"></a>Posibles problemas con PLINQ

En muchos casos, PLINQ puede proporcionar importantes mejoras de rendimiento con respecto a las consultas secuenciales LINQ to Objects. Sin embargo, el trabajo de paralelizar la ejecución de consultas aporta una complejidad que puede conducir a problemas que, en código secuencial, no son tan comunes o no se producen en ningún caso. En este tema se indican algunas prácticas que se deben evitar al escribir consultas PLINQ.

## <a name="dont-assume-that-parallel-is-always-faster"></a>No suponer que la ejecución en paralelo siempre es más rápida

En ocasiones, la paralelización hace que una consulta PLINQ se ejecute más lentamente que su equivalente LINQ to Objects. La regla de oro básica es que es poco probable que las consultas que tienen pocos elementos de origen y delegados de usuario rápidos se agilicen demasiado. Sin embargo, dado que hay muchos factores que afectan al rendimiento, se recomienda medir los resultados reales antes de decidir si usar PLINQ. Para más información, consulte [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).

## <a name="avoid-writing-to-shared-memory-locations"></a>Evitar la escritura en ubicaciones de memoria compartida

En código secuencial, no es raro leer o escribir en variables estáticas o campos de clase. Sin embargo, cada vez que varios subprocesos tienen acceso simultáneamente a estas variables, hay grandes posibilidades de que se produzcan condiciones de carrera. Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento. Por tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en una consulta PLINQ en la medida de lo posible.

## <a name="avoid-over-parallelization"></a>Evitar la paralelización excesiva

Si usa el método `AsParallel`, incurrirá en costos de sobrecarga al crear particiones de la colección de origen y sincronizar los subprocesos de trabajo. El número de procesadores del equipo reduce también las ventajas de la paralelización. Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad. Por tanto, debe tener cuidado para no paralelizar en exceso una consulta.

El escenario más común en el que se puede producir un exceso de paralelización son las consultas anidadas, como se muestra en el siguiente fragmento de código.

[!code-csharp[PLINQ#20](~/samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

En este caso, es mejor paralelizar únicamente el origen de datos exterior (clientes), a menos que se cumplan una o varias de las siguientes condiciones:

- Se sabe que el origen de datos interno (cust.Orders) es muy largo.

- Se realiza un cálculo costoso en cada pedido (la operación que se muestra en el ejemplo no es costosa).

- Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.

En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición. Para obtener más información, vea [Cómo: Medir el rendimiento de consultas PLINQ](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).

## <a name="avoid-calls-to-non-thread-safe-methods"></a>Evitar llamadas a métodos que no son seguros para subprocesos

La escritura en métodos de instancia que no son seguros para subprocesos de una consulta PLINQ puede producir daños en los datos, que pueden pasar o no inadvertidos para el programa. También puede dar lugar a excepciones. En el siguiente ejemplo, varios subprocesos estarían intentando llamar simultáneamente al método `FileStream.Write`, lo que no se admite en la clase.

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a>Limitar las llamadas a métodos seguros para subprocesos

La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les puede llamar simultáneamente desde varios subprocesos. Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.

> [!NOTE]
> Puede comprobarlo si inserta algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas. Aunque este método se usa en los ejemplos de la documentación para fines de demostración, no debe usarlo en consultas PLINQ.

## <a name="avoid-unnecessary-ordering-operations"></a>Evitar operaciones de ordenación innecesarias

Cuando PLINQ ejecuta una consulta en paralelo, divide la secuencia de origen en particiones que pueden funcionar simultáneamente en varios subprocesos. De forma predeterminada, el orden en el que se procesan las particiones y se entregan los resultados no es predecible (excepto para operadores como `OrderBy`). Puede indicar a PLINQ que conserve el orden de cualquier secuencia de origen, pero esto tiene un impacto negativo en el rendimiento. El procedimiento recomendado, siempre que sea posible, es estructurar las consultas para que no dependan de la conservación del orden. Para más información, consulte cómo [conservar el orden en PLINQ](order-preservation-in-plinq.md).

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Preferir ForAll en lugar de ForEach cuando sea posible

Aunque PLINQ ejecuta una consulta en varios subprocesos, si utiliza los resultados en un bucle `foreach` (`For Each` en Visual Basic), los resultados de la consulta se deben volver a combinar en un subproceso y el enumerador debe acceder a ellos en serie. En algunos casos, esto es inevitable; sin embargo, siempre que sea posible, utilice el método `ForAll` para habilitar cada subproceso para generar sus propios resultados, por ejemplo, al escribir en una colección segura para subprocesos como <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.

Este mismo problema es aplicable a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. En otras palabras, `source.AsParallel().Where().ForAll(...)` debe tener máxima prioridad con respecto a `Parallel.ForEach(source.AsParallel().Where(), ...)`.

## <a name="be-aware-of-thread-affinity-issues"></a>Tener en cuenta los problemas de afinidad de los subprocesos

Algunas tecnologías, como la interoperabilidad COM para componentes de contenedor uniproceso (STA), Windows Forms y Windows Presentation Foundation (WPF), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado. Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó. Si intenta tener acceso al estado compartido de un control de formularios Windows Forms en una consulta PLINQ, se produce una excepción si se ejecuta en el depurador. (Esta opción puede desactivarse). Sin embargo, si la consulta se usa en el subproceso de interfaz de usuario, entonces puede acceder al control del bucle `foreach` que enumera los resultados de la consulta, ya que el código se ejecuta en un solo subproceso.

## <a name="dont-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>No suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo

Es importante tener en cuenta que las iteraciones individuales de un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> pueden ejecutarse en paralelo, pero no tiene que ser así necesariamente. Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.

Por ejemplo, es probable que este código lleve a un interbloqueo:

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

En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento. Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento. Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse. Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.

En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar. Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.

## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](parallel-linq-plinq.md)
