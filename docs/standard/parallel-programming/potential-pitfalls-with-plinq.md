---
title: "Potential Pitfalls with PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, pitfalls"
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Potential Pitfalls with PLINQ
En muchos casos, PLINQ puede proporcionar importantes mejoras de rendimiento con respecto a las consultas LINQ to Objects.  Sin embargo, el trabajo de paralelizar la ejecución de las consultas aporta una complejidad que puede conducir a problemas que, en código secuencial, no son tan comunes o que no se producen en absoluto.  En este tema se indican algunas prácticas que se deben evitar al escribir consultas PLINQ.  
  
## No se debe suponer que la ejecución en paralelo es siempre más rápida  
 En ocasiones, la paralelización hace que una consulta PLINQ se ejecute con mayor lentitud que su equivalente LINQ to Objects.  La regla básica es que no es probable que las consultas con pocos elementos de origen y delegados de usuario rápidos vayan mucho más rápido.  Sin embargo, dado que hay muchos factores que afectan al rendimiento, se recomienda medir los resultados reales antes de decidir si se usa PLINQ.  Para obtener más información, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Evitar la escritura en ubicaciones de memoria compartidas  
 En código secuencial, no es raro leer o escribir en variables estáticas o en campos de clase.  Sin embargo, cuando varios subprocesos tienen acceso a estas variables de forma simultánea, hay grandes posibilidades de que se produzcan condiciones de carrera.  Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento.  Por tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en una consulta PLINQ en la medida de lo posible.  
  
## Evitar la paralelización excesiva  
 Si usa el operador `AsParallel`, incurre en costos de sobrecarga al crear particiones de la colección de origen y sincronizar los subprocesos de trabajo.  El número de procesadores del equipo reduce también las ventajas de la paralelización.  Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad.  Por tanto, debe tener cuidado para no paralelizar en exceso una consulta.  
  
 El escenario más común en el que se puede producir un exceso de paralelización son las consultas anidadas, tal como se muestra en el siguiente fragmento de código.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 En este caso, es mejor paralelizar únicamente el origen de datos exterior \(clientes\) a menos que se cumplan una o más de las siguientes condiciones:  
  
-   Se sabe que el origen de datos interno \(cust.Orders\) es muy largo.  
  
-   Se realiza un cálculo caro en cada pedido. \(La operación que se muestra en el ejemplo no es cara.\)  
  
-   Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.  
  
 En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición.  Para obtener más información, vea [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## Evitar llamadas a métodos que no son seguros para subprocesos  
 La escritura en métodos de instancia que no son seguros para subprocesos de una consulta PLINQ puede producir daños en los datos, que pueden pasar o no desapercibidos en el programa.  También puede dar lugar a excepciones.  En el siguiente ejemplo, varios subprocesos estarían intentando llamar simultáneamente al método `Filestream.Write`, lo que la clase no admite.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## Limitar las llamadas a métodos seguros para subprocesos  
 La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les pueden llamar simultáneamente desde varios subprocesos.  Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.  
  
> [!NOTE]
>  Puede comprobarlo si inserta algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas.  Si bien este método se utiliza en los ejemplos de la documentación para realizar una demostración, no debe usarlo en las consultas PLINQ.  
  
## Evitar operaciones de ordenación innecesarias  
 Cuando PLINQ ejecuta una consulta en paralelo, divide la secuencia de origen en particiones con las que se puede trabajar de forma simultánea en varios subprocesos.  De forma predeterminada, el orden en que se procesan las particiones y se entregan los resultados no es predecible \(excepto para operadores como `OrderBy`\).  Puede indicar a PLINQ que conserve la ordenación de las secuencias de origen, pero esto tiene un impacto negativo en el rendimiento.  El procedimiento recomendado, siempre que sea posible, consiste en estructurar las consultas de forma que no dependan del mantenimiento del orden.  Para obtener más información, vea [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## Preferir ForAll a ForEach cuando sea posible  
 Si bien PLINQ ejecuta una consulta en varios subprocesos, si utiliza los resultados en un bucle `foreach` \(`For Each` en Visual Basic\), los resultados de la consulta se deben combinar de nuevo en un único subproceso y el enumerador debe tener acceso a ellos en serie.  En algunos casos, esto es inevitable; sin embargo, siempre que sea posible, utilice el método `ForAll` para permitir que cada subproceso genera sus propios resultados, por ejemplo, escribiendo en una colección segura para subprocesos como <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>.  
  
 El mismo problema se aplica al <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> In Otros Words, `source.AsParallel().Where().ForAll(...)` debe .forall \(...\)a  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## Ser consciente de los problemas de afinidad de los subprocesos  
 Algunas tecnologías, como la interoperabilidad COM para componentes STA \(contenedor uniproceso\), Windows Forms y Windows Presentation Foundation \(WPF\), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado.  Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó.  Si intenta tener acceso al estado compartido de un control Windows Forms en una consulta PLINQ, se produce una excepción si está ejecuta en el depurador. \(Este valor se puede desactivar.\) Sin embargo, si la consulta se utiliza en el subproceso de la interfaz de usuario, puede tener acceso al control desde el bucle `foreach` que enumera los resultados de la consulta, ya que este código se ejecuta en un único subproceso.  
  
## No se debe suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo  
 Es importante tener presente que las iteraciones individuales de un bucle <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> tal vez no tengan que ejecutarse en paralelo.  Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.  
  
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
  
 En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento.  Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento.  Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo, antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse.  Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.  
  
 En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar.  Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)