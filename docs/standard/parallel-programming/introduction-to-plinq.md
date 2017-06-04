---
title: "Introduction to PLINQ | Microsoft Docs"
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
  - "PLINQ queries, introduction to"
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Introduction to PLINQ
## ¿Qué es una consulta paralela?  
 Language\-Integrated Query \(LINQ\) se incorporó en [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)].  Representa un modelo unificado para consultar cualquier origen de datos <xref:System.Collections.IEnumerable?displayProperty=fullName> o <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> con seguridad de tipos.  LINQ to Objects es el nombre para los consultas LINQ que se ejecutan con las colecciones en memoria, como <xref:System.Collections.Generic.List%601>, y las matrices.  En este artículo se supone que tiene un conocimiento básico de LINQ.  Para obtener más información, vea [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).  
  
 Parallel LINQ \(PLINQ\) es una implementación paralela del modelo LINQ.  Una consulta PLINQ se parece de muchas maneras a una consulta LINQ to Objects no paralela.  Las consultas PLINQ, al igual que las consultas [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] secuenciales, funcionan con cualquier origen de datos <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> en memoria y usan la ejecución diferida, lo que significa que no empiezan a ejecutarse hasta que se enumere la consulta.  La diferencia primaria es que PLINQ intenta realizar el uso completo de todos los procesadores en el sistema.  Para hacer esto, divide el origen de datos en segmentos y, a continuación, ejecuta la consulta en cada segmento en subprocesos de trabajo independientes en paralelo en varios procesadores.  En muchos casos, la ejecución en paralelo significa que la consulta se ejecuta bastante más rápidamente.  
  
 A través de la ejecución en paralelo, PLINQ puede lograr mejoras de rendimiento significativas respecto al código heredado para ciertos tipos de consultas, a menudo con solo agregar la operación de consulta <xref:System.Linq.ParallelEnumerable.AsParallel%2A> al origen de datos.  Sin embargo, el paralelismo puede presentar sus propias complejidades y no todas las operaciones de consulta se ejecutan más rápidamente en PLINQ.  De hecho, la ejecución en paralelo realmente reduce la velocidad de ciertas consultas.  Por consiguiente, debería entender en qué grado afectan a las consultas en paralelo ciertos aspectos como la ordenación.  Para obtener más información, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
> [!NOTE]
>  En esta documentación, se utilizan expresiones lambda para definir delegados en la PLINQ.  Si no está familiarizado con expresiones lambda en C\# o Visual Basic, vea [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 El resto de este artículo proporciona información general de las clases PLINQ principales y describe cómo crear las consultas PLINQ.  Cada sección contiene vínculos a ejemplos de código e información más detallada.  
  
## La clase ParallelEnumerable  
 La clase <xref:System.Linq.ParallelEnumerable?displayProperty=fullName> expone casi toda la funcionalidad de PLINQ.  Esta clase y el resto de tipos del espacio de nombres <xref:System.Linq?displayProperty=fullName> se compilan en el ensamblado System.Core.dll.  Los proyectos predeterminados de C\# y Visual Basic en Visual Studio hacen referencia el ensamblado e importan el espacio de nombres.  
  
 <xref:System.Linq.ParallelEnumerable> incluye implementaciones de todos los operadores de consulta estándar que admite LINQ to Objects, aunque no intenta ejecutar cada una en paralelo.  Si no está familiarizado con [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)], vea [Introduction to LINQ](../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
 Además de los operadores de consulta estándar, la clase <xref:System.Linq.ParallelEnumerable> contiene un conjunto de métodos que habilitan los comportamientos específicos de la ejecución en paralelo.  Estos métodos específicos de PLINQ se muestran en la siguiente tabla.  
  
|Operador ParallelEnumerable|Descripción|  
|---------------------------------|-----------------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|Punto de entrada para PLINQ.  Especifica que el resto de la consulta se debería ejecutar en paralelo, si es posible.|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|Especifica que el resto de la consulta se debería ejecutar secuencialmente, como un consulta LINQ no paralela.|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|Especifica que PLINQ debería conservar la clasificación de la secuencia de origen para el resto de la consulta, o hasta que se cambie la clasificación, por ejemplo mediante una cláusula orderby \(Order By en Visual Basic\).|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|Especifica que no es necesario que PLINQ conserve la clasificación de la secuencia de origen durante el resto de la consulta.|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|Especifica que PLINQ debería supervisar periódicamente el estado del token de cancelación proporcionado y cancelar la ejecución si se solicita.|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|Especifica el número máximo de procesadores que PLINQ debería usar para ejecutar la consulta en paralelo.|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|Proporciona una sugerencia sobre cómo PLINQ debe, si es posible, volver a combinar los resultados paralelos en solo una secuencia en el subproceso utilizado.|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|Especifica si PLINQ debería ejecutar la consulta en paralelo incluso cuando el comportamiento predeterminado sería ejecutarla secuencialmente.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Un método de enumeración multiproceso que, a diferencia de iterar por los resultados de la consulta, permite volver a procesar los resultados en paralelo sin volver a combinar primero el subproceso de consumidor.|  
|Sobrecarga <xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Una sobrecarga que es exclusiva de PLINQ y habilita la agregación intermedia sobre las particiones locales de subprocesos, más una última función de agregación para combinar los resultados de todas las particiones.|  
  
## El modelo de opción  
 Al escribir una consulta, elija PLINQ invocando el método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName> en el origen de datos, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 El método de extensión <xref:System.Linq.ParallelEnumerable.AsParallel%2A> enlaza a los operadores de consulta subsiguientes, en este caso, `where` y `select`, a las implementaciones de <xref:System.Linq.ParallelEnumerable?displayProperty=fullName>.  
  
## Modos de ejecución  
 De forma predeterminada, PLINQ es conservador.  En tiempo de ejecución, la infraestructura PLINQ analiza la estructura general de la consulta.  Si es probable que la consulta produzca aumentos de velocidad por la ejecución en paralelo, PLINQ divide la secuencia de origen en tareas que se pueden ejecutar simultáneamente.  Si no es seguro para ejecutar una consulta en paralelo, PLINQ simplemente ejecuta la consulta de forma secuencial.  Si PLINQ puede elegir entre un algoritmo paralelo potencialmente costoso o un algoritmo secuencial poco costoso, elige el algoritmo secuencial de forma predeterminada.  Puede usar el método <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> y la enumeración <xref:System.Linq.ParallelExecutionMode?displayProperty=fullName> para indicar a PLINQ que seleccione el algoritmo paralelo.  Esto resulta útil cuando sabe por las pruebas y mediciones que una consulta determinada se ejecuta más rápidamente en paralelo.  Para obtener más información, vea [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
## Grado de paralelismo  
 De forma predeterminada, PLINQ usa todos los procesadores en el equipo host hasta un máximo de 64.  Puede indicar a PLINQ que no utilice más que un número especificado de procesadores usando el método <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>.  Esto resulta útil si desea asegurarse de que los otros procesos que se ejecutan en el equipo reciben cierta cantidad de tiempo de CPU.  El siguiente fragmento de código limita la consulta a usar un máximo de dos procesadores.  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 En los casos donde una consulta está realizando una cantidad significativa de trabajo enlazado sin cálculo, como la E\/S de archivo, podría ser beneficioso especificar un grado de paralelismo mayor que el número de núcleos del equipo.  
  
## Consultar en paralelo ordenadas frente a no ordenadas  
 En algunas consultas, un operador de consulta debe generar resultados que conservan el orden de la secuencia de origen.  PLINQ proporciona el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> para este propósito.  <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> es distinto de <xref:System.Linq.ParallelEnumerable.AsSequential%2A>.  Una secuencia <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> se sigue procesando en paralelo, pero sus resultados se almacenan en búfer y se ordenan.  Dado que la preservación del orden implica normalmente trabajo adicional, una secuencia <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> se podría procesar más despacio que la secuencia <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> predeterminada.  El hecho de que una operación en paralelo ordenada especial sea más rápida que una versión secuencial de la operación depende de muchos factores.  
  
 El siguiente ejemplo de código muestra las opciones que se deben elegir para conservar el orden.  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 Para obtener más información, vea [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## Consultas paralelas frente a consultas secuenciales  
 Algunas operaciones requieren que los datos de origen se entreguen de una manera secuencial.  Los operadores de consulta <xref:System.Linq.ParallelEnumerable> revierten automáticamente al modo secuencial cuando es necesario.  Para los operadores de consulta definidos por el usuario y los delegados de usuario que requieren la ejecución secuencial, PLINQ proporciona el método <xref:System.Linq.ParallelEnumerable.AsSequential%2A>.  Al usar <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, se ejecutan secuencialmente todos los operadores subsiguientes en la consulta hasta que se llame de nuevo a <xref:System.Linq.ParallelEnumerable.AsParallel%2A>.  Para obtener más información, vea [How to: Combine Parallel and Sequential LINQ Queries](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md).  
  
## Opciones para combinar los resultados de la consulta  
 Cuando una consulta PLINQ se ejecuta en paralelo, sus resultados de cada subproceso de trabajo deben volver a combinarse en el subproceso principal para su uso en un bucle `foreach` \(`For Each` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) o la inserción en una lista o matriz.  En algunos casos, podría ser beneficioso especificar un tipo determinado de operación de combinación, por ejemplo, para empezar a generar resultados más rápidamente.  Para este propósito, PLINQ admite el método <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> y la enumeración <xref:System.Linq.ParallelMergeOptions>.  Para obtener más información, vea [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
## El operador ForAll  
 En las consultas secuenciales de [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)], la ejecución se difiere hasta que la consulta se enumere en un bucle `foreach` \(`For Each` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) o al invocar un método como <xref:System.Linq.ParallelEnumerable.ToList%2A>, <xref:System.Linq.ParallelEnumerable.ToArray%2A> o <xref:System.Linq.ParallelEnumerable.ToDictionary%2A>.  En PLINQ, también se puede usar `foreach` para ejecutar la consulta e iterar por los resultados.  Sin embargo, el propio bucle `foreach` no se ejecuta en paralelo y, por consiguiente, requiere que el resultado de todas las tareas paralelas se vuelva a combinar en el subproceso en el que se está ejecutando el bucle.  En PLINQ, puede usar `foreach` cuando deba conservar el orden final de los resultados de la consulta, y también cada vez que procese los resultados en serie, por ejemplo cuando está llamando a `Console.WriteLine` para cada elemento.  Para una ejecución más rápida de la consulta cuando no se requiere la conservación del orden y cuando el propio procesamiento de los resultados se puede ejecutar en paralelo, use el método <xref:System.Linq.ParallelEnumerable.ForAll%2A> para ejecutar una consulta PLINQ.  <xref:System.Linq.ParallelEnumerable.ForAll%2A> no realiza este paso final de la combinación.  En el ejemplo de código siguiente, se muestra cómo se utiliza el método <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> se usa en este caso porque está optimizado para varios subprocesos que agregan elementos simultáneamente sin intentar quitar ningún elemento.  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 En la siguiente ilustración, se muestra la diferencia entre `foreach` y <xref:System.Linq.ParallelEnumerable.ForAll%2A> con respecto a la ejecución de una consulta.  
  
 ![ForAll frente a ForEach](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS\_ISVNT\_ALLvsEACH")  
  
## Cancelación  
 PLINQ se integra con los tipos de cancelación en [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]. \(Para obtener más información, vea [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)\). Por consiguiente, a diferencia de las consultas secuenciales LINQ to Objects, las consultas PLINQ pueden cancelarse.  Crear una consulta PLINQ cancelable, use el operador <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la consulta y proporcione una instancia de <xref:System.Threading.CancellationToken> como argumento.  Cuando se establece en true la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token, PLINQ lo observará, detendrá el procesamiento en todos los subprocesos y generará una excepción <xref:System.OperationCanceledException>.  
  
 Es posible que una consulta PLINQ continúe procesando algunos elementos una vez establecido el token de cancelación.  
  
 Para lograr una sensibilidad mayor, puede responder también a las solicitudes de cancelación en los delegados de usuario de ejecución prolongada.  Para obtener más información, vea [How to: Cancel a PLINQ Query](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## Excepciones  
 Cuando se ejecuta una consulta PLINQ, se podrían producir simultáneamente varias excepciones de diferentes subprocesos.  Asimismo, el código para controlar la excepción podría encontrarse un subproceso diferente al del código que produjo la excepción.  PLINQ usa el tipo <xref:System.AggregateException> para encapsular todas las excepciones producidas por una consulta y vuelve a calcular las referencias de esas excepciones para el subproceso que realiza la llamada.  En el subproceso que realiza la llamada, solo se requiere un bloque try\-catch.  Sin embargo, puede iterar por todas las excepciones encapsuladas en <xref:System.AggregateException> y detectar cualquiera de la que se pueda recuperar de forma segura.  En casos raros, se pueden producir algunas excepciones que no se encapsulan en <xref:System.AggregateException> y los objetos <xref:System.Threading.ThreadAbortException> tampoco se encapsulan.  
  
 Cuando las excepciones pueden propagarse de nuevo al subproceso de unión, es posible que una consulta continúe procesando algunos elementos después de que se haya producido la excepción.  
  
 Para obtener más información, vea [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## Particionadores personalizados  
 En ciertos casos, puede mejorar el rendimiento de las consultas si escribe un particionador personalizado que se aprovecha de alguna característica de los datos de origen.  En la consulta, el propio particionador personalizado es el objeto enumerable que se consulta.  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ admite un número de particiones fijo \(aunque los datos se pueden reasignar dinámicamente a esas particiones durante el tiempo de ejecución para el equilibrio de carga\).  <xref:System.Threading.Tasks.Parallel.For%2A> y <xref:System.Threading.Tasks.Parallel.ForEach%2A> solo admiten la creación dinámica de particiones, lo que significa que el número de particiones cambia en tiempo de ejecución.  Para obtener más información, vea [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Medir el rendimiento de PLINQ  
 En muchos casos, una consulta se puede ejecutar en paralelo, pero la sobrecarga de preparar la consulta paralela supera a la ventaja de rendimiento obtenida.  Si una consulta no realiza muchos cálculos o si el origen de datos es pequeño, una consulta PLINQ puede ser más lenta que una consulta secuencial LINQ to Objects.  Puede usar el Analizador de rendimiento de procesamiento paralelo en Visual Studio Team Server para comparar el rendimiento de varias consultas, buscar los cuellos de botella del procesamiento y determinar si su consulta se está ejecutando en paralelo o secuencialmente.  Para obtener más información, vea [Visualizador de simultaneidad](../Topic/Concurrency%20Visualizer.md) y [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)