---
title: Particionadores personalizados para PLINQ y TPL
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
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Particionadores personalizados para PLINQ y TPL
Para paralelizar una operación en un origen de datos, uno de los pasos esenciales es *partición* el origen en varias secciones que pueden acceder varios subprocesos simultáneamente. PLINQ y la biblioteca (TPL) proporcionan particionadores predeterminados que funcionan de manera transparente al escribir una consulta en paralelo o <xref:System.Threading.Tasks.Parallel.ForEach%2A> bucle. Para escenarios más avanzados, puede conectar su propio particionador.  
  
## <a name="kinds-of-partitioning"></a>Tipos de particiones  
 Hay muchas maneras de dividir un origen de datos. En los enfoques más eficaces, varios subprocesos cooperan para el proceso de la secuencia de origen original, en lugar de separar físicamente el origen en varias secuencias secundarias. Para matrices y otros orígenes indizados como <xref:System.Collections.IList> colecciones donde la longitud se conoce de antemano, *creación de particiones range* es el tipo más sencillo de creación de particiones. Cada subproceso recibe único de apertura y cierre índices, para que pueda procesar su intervalo de origen sin sobrescribir ni ningún otro subproceso que se va a sobrescribir. La única sobrecarga implicada en la partición de intervalo es el trabajo inicial de crear los intervalos; se necesita ninguna sincronización adicional después de eso. Por lo tanto, puede proporcionar un buen rendimiento siempre y cuando la carga de trabajo se divide por igual. Una desventaja de particionamiento de intervalo es que si un subproceso finaliza al principio, no puede ayudar a los demás subprocesos finalizar su trabajo.  
  
 Para listas vinculadas u otras colecciones cuya longitud no se conoce, puede usar *fragmento particiones*. En particiones de fragmentos, cada subproceso o tarea en un bucle paralelo o consulta consume un número de elementos de origen de un fragmento, procesarlos y, a continuación, vuelve a estar al recuperar los elementos adicionales. Los particionadores se aseguran de que todos los elementos se distribuyen y que no haya duplicados. Un fragmento puede tener cualquier tamaño. Por ejemplo, el particionador que se muestra en [Cómo: implementar las particiones dinámicas](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) crea fragmentos que contienen un solo elemento. Siempre que los fragmentos no son demasiado grandes, este tipo de particiones es inherentemente el equilibrio de carga porque la asignación de elementos a los subprocesos no se ha determinado previamente. Sin embargo, la clase partitioner evitar la sobrecarga de sincronización cada vez que el subproceso necesita obtener otro fragmento. La cantidad de sincronización que se incurre en estos casos es inversamente proporcional al tamaño de los fragmentos.  
  
 En general, la partición de intervalos solo es más rápido cuando el tiempo de ejecución del delegado es poco a moderado y el origen tiene un gran número de elementos y el trabajo total de cada partición es aproximadamente equivalente. Creación de particiones de fragmentos, por tanto, es generalmente más rápido en la mayoría de los casos. En orígenes con un número pequeño de elementos o el tiempo de ejecución para el delegado, a continuación, el rendimiento de fragmento y particiones de intervalo es casi igual.  
  
 Los particionadores de TPL también admiten un número de particiones dinámico. Esto significa que se pueden crear particiones sobre la marcha, por ejemplo, cuando el <xref:System.Threading.Tasks.Parallel.ForEach%2A> bucle genera una nueva tarea. Esta característica permite al particionador escalar junto con el propio bucle. Los particionadores dinámicos también son inherentemente el equilibrio de carga. Cuando se crea un particionador personalizado, debe admitir la creación de particiones dinámicas para poder usarse desde un <xref:System.Threading.Tasks.Parallel.ForEach%2A> bucle.  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Configurar particionadores para PLINQ de equilibrio de carga  
 Algunas sobrecargas de la <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> método le permite crear un particionador para una matriz o <xref:System.Collections.IList> de origen y especifique si debe intentar equilibrar la carga de trabajo entre los subprocesos. Cuando se configura el particionador para equilibrar la carga, fragmento las particiones se emplean y los elementos se entregan a cada partición en pequeños fragmentos conforme se solicitan. Este enfoque ayuda a garantizar que todas las particiones tienen elementos para procesar hasta que todo el bucle o se completa la consulta. Una sobrecarga adicional puede usarse para proporcionar equilibrio de carga de partición de cualquier <xref:System.Collections.IEnumerable> origen.  
  
 En general, el equilibrio de carga requiere las particiones para solicitar elementos relativamente con frecuencia de la clase partitioner. Por el contrario, un particionador que crea particiones estáticas puede asignar los elementos a cada particionador todos a la vez mediante el uso de intervalo o creación de particiones de fragmento. Esto requiere menos sobrecarga de equilibrio de carga, pero es posible que tarde más tiempo en ejecutarse si un subproceso termina significativamente con más trabajo que las demás. De forma predeterminada cuando se pasa una interfaz IList o una matriz, PLINQ siempre utiliza la creación de particiones de intervalo sin equilibrio de carga. Para habilitar Equilibrio de carga para PLINQ, use la `Partitioner.Create` método, tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 La mejor manera de determinar si utilizar carga equilibrio en un escenario determinado es experimentar y medir el tiempo que tarda la finalización bajo carga representativa y configuraciones de equipo de operaciones. Por ejemplo, la creación de particiones estático podría proporcionar un aumento significativo en un equipo de varios núcleos que tenga solo unos pocos núcleos, pero podría dar como resultado una ralentización en equipos que tienen relativamente más núcleos.  
  
 En la tabla siguiente se enumera las sobrecargas disponibles de la <xref:System.Collections.Concurrent.Partitioner.Create%2A> método. Estos particionadores no están limitados a utilizar únicamente con PLINQ o <xref:System.Threading.Tasks.Task>. También se puede utilizar con cualquier construcción paralela personalizada.  
  
|Sobrecarga|Usa el equilibrio de carga|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Always|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Cuando se especifica el argumento de tipo Boolean como true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Cuando se especifica el argumento de tipo Boolean como true|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nunca|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Configurar particionadores por intervalos estáticos para Parallel.ForEach  
 En un <xref:System.Threading.Tasks.Parallel.For%2A> de bucles for, el cuerpo del bucle se proporciona al método como un delegado. El costo de invocar ese delegado es aproximadamente el mismo que una llamada al método virtual. En algunos escenarios, el cuerpo de un bucle paralelo podría ser lo suficientemente pequeño como para que el costo de la invocación del delegado en cada iteración del bucle, pasa a ser significativo. En estas situaciones, puede usar uno de los <xref:System.Collections.Concurrent.Partitioner.Create%2A> sobrecargas para crear un <xref:System.Collections.Generic.IEnumerable%601> de particiones por rangos de los elementos de origen. A continuación, puede pasar esta colección de intervalos para un <xref:System.Threading.Tasks.Parallel.ForEach%2A> método cuyo cuerpo se compone de una normal `for` bucle. La ventaja de este enfoque es que el costo de invocación del delegado se incurre en una sola vez por intervalo, en lugar de una vez por cada elemento. En el ejemplo siguiente se muestra el patrón básico.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Cada subproceso del bucle recibe su propio <xref:System.Tuple%602> que contiene las iniciales y finales de los valores de índice en el intervalo secundario especificado. Interna `for` bucle utiliza el `fromInclusive` y `toExclusive` valores para recorrer la matriz o <xref:System.Collections.IList> directamente.  
  
 Uno de los <xref:System.Collections.Concurrent.Partitioner.Create%2A> sobrecargas le permite especificar el tamaño de las particiones y el número de particiones. Esta sobrecarga puede usarse en escenarios donde el trabajo por cada elemento es tan bajo que incluso un método virtual llamada por cada elemento tiene un impacto perceptible en el rendimiento.  
  
## <a name="custom-partitioners"></a>Particionadores personalizados  
 En algunos casos, podría ser merece la pena o incluso necesarios para implementar a un particionador propio. Por ejemplo, podría tener una clase de colección personalizada que puede crear particiones de forma más eficaz que el valor predeterminado particionadores puede, según su conocimiento de la estructura interna de la clase. O bien, puede que desee crear particiones de intervalo de tamaños diferentes basándose en su conocimiento de cuánto tiempo se tardará en procesar los elementos en ubicaciones distintas de la colección de origen.  
  
 Para crear un particionador personalizado básico, derive una clase de <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> e invalidar los métodos virtuales, tal como se describe en la tabla siguiente.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Este método se llama una vez por el subproceso principal y devuelve un IList(IEnumerator(TSource)). Puede llamar cada subproceso de trabajo en el bucle o consulta `GetEnumerator` en la lista para recuperar un <xref:System.Collections.Generic.IEnumerator%601> a través de una partición distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devolver `true` si implementa <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, en caso contrario, `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, opcionalmente, puede llamar a este método en lugar de <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Si los resultados deben ser que se puede ordenar o necesite acceso indizado en los elementos, a continuación, se derivan de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> e invalidar sus métodos virtuales como se describe en la tabla siguiente.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Este método se llama una vez por el subproceso principal y devuelve un `IList(IEnumerator(TSource))`. Puede llamar cada subproceso de trabajo en el bucle o consulta `GetEnumerator` en la lista para recuperar un <xref:System.Collections.Generic.IEnumerator%601> a través de una partición distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devolver `true` si implementa <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; de lo contrario, false.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Normalmente, esto simplemente llama <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, opcionalmente, puede llamar a este método en lugar de <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 En la tabla siguiente proporciona detalles adicionales sobre cómo los tres tipos de equilibrio de carga particionadores implementan la <xref:System.Collections.Concurrent.OrderablePartitioner%601> clase.  
  
|Método o propiedad|IList / matriz sin equilibrio de carga|IList / matriz con equilibrio de carga|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Utiliza la creación de particiones de intervalo|La creación de particiones de fragmentos de usos optimizada para la partitionCount especificada|Fragmento utiliza creación de particiones mediante la creación de un número estático de particiones.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Excepción produce no admitidos|La creación de particiones de fragmentos de usos optimizada para las listas y las particiones dinámicas|Fragmento utiliza creación de particiones mediante la creación de un número de particiones dinámico.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Devuelve `true`|Devuelve `false`|Devuelve `false`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelve `false`|Devuelve `true`|Devuelve `true`|  
  
### <a name="dynamic-partitions"></a>Particiones dinámicas  
 Si piensa que el particionador para usarse en un <xref:System.Threading.Tasks.Parallel.ForEach%2A> método, debe poder devolver un número de particiones dinámico. Esto significa que el particionador pueden proporcionar un enumerador para una nueva partición a petición en cualquier momento durante la ejecución del bucle. Básicamente, siempre que el bucle agrega una nueva tarea en paralelo, solicita una nueva partición de esa tarea. Si necesita que se puede pedir a los datos, a continuación, se derivan de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> para que se asigna a cada elemento en cada partición de un índice único.  
  
 Para obtener más información y un ejemplo, vea [Cómo: implementar las particiones dinámicas](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### <a name="contract-for-partitioners"></a>Contrato para particionadores  
 Al implementar un particionador personalizado, siga estas instrucciones para ayudar a garantizar la interacción correcta con PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A> en la biblioteca TPL:  
  
-   Si <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> se llama con un argumento de cero o menos, para `partitionsCount`, producir <xref:System.ArgumentOutOfRangeException>. Aunque PLINQ y TPL nunca pasarán en una `partitionCount` igual a 0, no obstante, se recomienda que se protege contra la posibilidad.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> siempre debe devolver `partitionsCount` número de particiones. Si la clase partitioner agota los datos y no puede crear tantas particiones como se ha solicitado, el método debe devolver un enumerador vacío para cada una de las particiones restantes. De lo contrario, PLINQ y TPL producirán un <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> nunca deberían devolver `null` (`Nothing` en Visual Basic). Si lo hacen, PLINQ / TPL producirán un <xref:System.InvalidOperationException>.  
  
-   Métodos que devuelven particiones siempre deberían devolver particiones que pueden enumerar completamente y de forma única el origen de datos. No debería haber ninguna duplicación en el origen de datos o elementos omitidos a menos que lo requiera específicamente el diseño de la clase partitioner. Si no se respeta esta regla, se puede alterar el orden de salida.  
  
-   Los siguientes captadores booleanos deben devolver siempre con precisión los siguientes valores para que no se altere el orden de salida:  
  
    -   `KeysOrderedInEachPartition`: Cada partición devuelve elementos con cada vez mayores índices de clave.  
  
    -   `KeysOrderedAcrossPartitions`: Para todas las particiones que se devuelven, los índices de clave de partición *i* son más altos que los índices de clave de partición *i*-1.  
  
    -   `KeysNormalized`: Todos los índices de clave son aumentar ininterrumpidamente sin espacios, empezando desde cero.  
  
-   Todos los índices deben ser únicos. No puede haber índices duplicados. Si no se respeta esta regla, se puede alterar el orden de salida.  
  
-   Todos los índices no deben ser negativos. Si no se respeta esta regla, PLINQ/TPL pueden producir excepciones.  
  
## <a name="see-also"></a>Vea también  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)  
 [Implementar las particiones dinámicas](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [Implementar un particionador para particionamiento estático](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
