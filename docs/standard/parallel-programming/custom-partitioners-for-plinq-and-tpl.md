---
title: "Custom Partitioners for PLINQ and TPL | Microsoft Docs"
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
  - "tasks, partitioners"
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Custom Partitioners for PLINQ and TPL
Para paralelizar una operación en un origen de datos, uno de los pasos esenciales es *crear particiones* del origen en varias secciones a las que se tenga acceso simultáneamente a través de varios subprocesos.  PLINQ y Task Parallel Library \(TPL\) proporcionan particionadores predeterminados que funcionan de forma transparente al escribir una consulta o bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> en paralelo.  En escenarios más avanzados, puede conectar su propio particionador.  
  
## Creación de particiones diferentes  
 Hay muchas maneras de crear particiones de un origen de datos.  En los enfoques más eficaces, varios subprocesos cooperan para procesar la secuencia original, en lugar de separar físicamente el origen en varias subsecuencias.  Para matrices y otros orígenes indizados como colecciones <xref:System.Collections.IList> donde de antemano se conoce la longitud, la *creación de particiones por intervalos* es la forma más simple de crear particiones.  Cada subproceso recibe índices iniciales y finales únicos, para poder procesar el intervalo del origen sin sobrescribir ni ser sobrescrito por otro subproceso.  La única sobrecarga implicada en la creación de particiones por intervalos es el trabajo inicial de crear los intervalos; ninguna sincronización adicional se requiere después de eso.  Por consiguiente, puede proporcionar buen rendimiento siempre que la carga de trabajo se divida uniformemente.  Una desventaja de la creación de particiones por intervalos es que si un subproceso finaliza pronto, no puede ayudar a los demás a finalizar el trabajo.  
  
 Con listas vinculadas u otras colecciones cuya longitud no se conoce, puede utilizar la *creación de particiones por fragmentos*.  En la creación de particiones por fragmentos, cada subproceso o tarea de un bucle o consulta en paralelo utiliza un número de elementos de origen de un fragmento, los procesa y vuelve a recuperar más elementos.  Los particionadores se aseguran de que se distribuyen todos los elementos y no hay ningún duplicado.  Un fragmento puede tener cualquier tamaño.  Por ejemplo, el particionador que se muestra en [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) crea fragmentos que contienen un solo elemento.  Con tal de que los fragmentos no sean demasiado grandes, esta forma de crear particiones mantiene inherentemente el equilibrio de carga porque la asignación de elementos a subprocesos no está predeterminada.  Sin embargo, el particionador incurre en la sobrecarga de sincronización cada vez que el subproceso necesita obtener otro fragmento.  La cantidad de sincronización en que se incurre en estos casos es inversamente proporcional al tamaño de los fragmentos.  
  
 En general, la creación de particiones por intervalos solo es más rápida cuando el tiempo de ejecución del delegado es de poco a moderado, el origen tiene un número grande de elementos y el trabajo total de cada partición es aproximadamente equivalente.  La creación de particiones por fragmentos es, por consiguiente, más rápida en la mayoría de los casos.  En orígenes con un número pequeño de elementos o tiempos de ejecución más largos para el delegado, el rendimiento de la creación de particiones por fragmentos e intervalos es casi igual.  
  
 Los particionadores de TPL también admiten un número de particiones dinámicas.  Esto significa que pueden crear particiones sobre la marcha, por ejemplo, cuando el bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> genera una nueva tarea.  Esta característica permite al particionador escalar junto con el propio bucle.  Los particionadores dinámicos también mantienen inherentemente el equilibrio de carga.  Cuando se crea un particionador personalizado, se debe admitir que la creación de particiones dinámicas se use desde un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A>.  
  
### Configurar particionadores de equilibrio de carga para PLINQ  
 Algunas sobrecargas del método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName> permitían crear particionadores para una matriz u origen <xref:System.Collections.IList> y especificar si debía intentar equilibrar la carga de trabajo entre los subprocesos.  Cuando se configura el particionador para equilibrar la carga, se utiliza la creación de particiones por fragmentos y los elementos se presentan fuera de cada partición en pequeños fragmentos a medida que se solicitan.  Este enfoque ayuda a asegurar que todas las particiones tienen elementos para procesar hasta que todo el bucle o la consulta se completa.  Se puede utilizar una sobrecarga adicional para proporcionar la creación de particiones de equilibrio de carga de cualquier origen <xref:System.Collections.IEnumerable>.  
  
 En general, el equilibrio de carga exige que las particiones soliciten elementos con relativa frecuencia de los particionadores.  Por contraste, el particionador que crea particiones estáticas puede asignar todos los elementos a la vez mediante la creación de particiones por intervalos o por fragmentos.  Esto requiere menos sobrecarga que el equilibrio de carga, pero podría llevar más mucho tiempo ejecutarse si un subproceso termina significativamente con más trabajo que los demás.  De forma predeterminada cuando se pasa IList o una matriz, PLINQ siempre utiliza la creación de particiones por intervalos sin equilibrio de carga.  Para habilitar el equilibrio de carga para PLINQ, use el método `Partitioner.Create`, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 La mejor manera de determinar si utilizar el equilibrio de carga en un escenario determinado es experimentar y medir cuánto tiempo tardan las operaciones en completarse con cargas y configuraciones de equipo representativas.  Por ejemplo, la creación de particiones estáticas podría proporcionar un aumento de velocidad significativo en un equipo multiproceso con pocos núcleos, pero podría ralentizar los equipos que tienen relativamente más núcleos.  
  
 En la tabla siguiente se muestran las sobrecargas disponibles del método <xref:System.Collections.Concurrent.Partitioner.Create%2A>.  Estos particionadores no están limitados a su uso con PLINQ o <xref:System.Threading.Tasks.Task>.  También se pueden utilizar con cualquier construcción paralela personalizada.  
  
|Sobrecarga|Utiliza el equilibrio de carga|  
|----------------|------------------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Siempre|  
|[Create\<TSource\>\(TSource\<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Cuando el argumento booleano se especifica como verdadero|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Cuando el argumento booleano se especifica como verdadero|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nunca|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nunca|  
  
### Configurar particionadores por intervalos estáticos para Parallel.ForEach  
 En un bucle <xref:System.Threading.Tasks.Parallel.For%2A>, el cuerpo del bucle se proporciona al método como un delegado.  El costo de invocar ese delegado es más o menos similar a una llamada al método virtual.  En algunos escenarios, el cuerpo de un bucle paralelo podría ser lo bastante pequeño como para que el costo de la invocación del delegado en cada iteración del bucle fuera significativa.  En tales situaciones, puede utilizar una de las sobrecargas <xref:System.Collections.Concurrent.Partitioner.Create%2A> para crear una <xref:System.Collections.Generic.IEnumerable%601> de particiones por intervalos de los elementos de origen.  Después puede pasar esta colección de intervalos a un método <xref:System.Threading.Tasks.Parallel.ForEach%2A> cuyo cuerpo está compuesto de un bucle `for` normal.  La ventaja de este enfoque es que solo se incurre en el costo de invocación de delegados una vez por intervalo, en lugar de una vez por elemento.  En el siguiente ejemplo se muestra el modelo básico.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Cada subproceso del bucle recibe su propio <xref:System.Tuple%602> que contiene los valores de índice de inicio y de fin del subintervalo especificado.  El bucle `for` interno utiliza los valores `toExclusive` y `fromInclusive` para recorrer directamente la matriz o <xref:System.Collections.IList>.  
  
 Una de las sobrecargas <xref:System.Collections.Concurrent.Partitioner.Create%2A> permite especificar el tamaño y el número de las particiones.  Esta sobrecarga se puede utilizar en escenarios donde el trabajo por elemento es tan bajo que incluso una llamada al método virtual por elemento tiene un impacto notable en el rendimiento.  
  
## Particionadores personalizados  
 En algunos escenarios, valdría la pena o incluso podría ser preciso implementar un particionador propio.  Por ejemplo, podría tener una clase de colección personalizada que puede crear particiones más eficazmente que los particionadores predeterminados, basándose en su conocimiento de la estructura interna de la clase.  O tal vez desee crear particiones por intervalos de tamaños diferentes basándose en su conocimiento de cuánto tiempo tardará en procesar los elementos en ubicaciones diferentes de la colección de origen.  
  
 Para crear un particionador personalizado básico, derive una clase de <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=fullName> e invalide los métodos virtuales, tal y como se describe en la siguiente tabla.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|El subproceso principal llama a este método una vez y devuelve IList\(IEnumerator\(TSource\)\).  Cada subproceso de trabajo del bucle o la consulta puede llamar a `GetEnumerator` en la lista para recuperar <xref:System.Collections.Generic.IEnumerator%601> de una partición distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelve `true` si implementa <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, de lo contrario, `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, se puede llamar a este método opcionalmente en lugar de a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Si los resultados deben ser ordenables o si necesita acceso indizado a los elementos, derive de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> e invalide sus métodos virtuales tal y como se describe en la siguiente tabla.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|El subproceso principal llama a este método una vez y devuelve `IList(IEnumerator(TSource))`.  Cada subproceso de trabajo del bucle o la consulta puede llamar a `GetEnumerator` en la lista para recuperar <xref:System.Collections.Generic.IEnumerator%601> de una partición distinta.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelve `true` si implementa <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; de lo contrario, falso.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Normalmente, solo llama a <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, se puede llamar a este método opcionalmente en lugar de a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 En la siguiente tabla se proporcionan los detalles adicionales sobre cómo los tres tipos de particionadores del equilibrio de carga implementan la clase <xref:System.Collections.Concurrent.OrderablePartitioner%601>.  
  
|Propiedad o método|IList \/ matriz sin equilibrio de carga|IList \/ matriz con equilibrio de carga|IEnumerable|  
|------------------------|---------------------------------------------|---------------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Utiliza la creación de particiones por intervalos|Utiliza la creación de particiones por fragmentos optimizada para la partitionCount especificada|Utiliza la creación de particiones por fragmentos y crea un número de particiones estáticas.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=fullName>|Produce una excepción no admitida|Utiliza la creación de particiones por fragmentos optimizada para las listas y las particiones dinámicas|Utiliza la creación de particiones por fragmentos creando un número de particiones dinámico.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Devuelve `true`|Devuelve `false`|Devuelve `false`|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelve `false`|Devuelve `true`|Devuelve `true`|  
  
### Particiones dinámicas  
 Si piensa utilizar el particionador en un método <xref:System.Threading.Tasks.Parallel.ForEach%2A>, debe poder devolver un número de particiones dinámico.  Esto significa que el particionador pueden proporcionar un enumerador para una nueva partición a petición en cualquier momento durante la ejecución del bucle.  Básicamente, cada vez que el bucle agrega una nueva tarea en paralelo, solicita una nueva partición para esa tarea.  Si exige que los datos se puedan ordenar, derive de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> para que cada elemento de cada partición tenga asignado un índice único.  
  
 Para obtener más información y un ejemplo, vea [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### Contrato para particionadores  
 Cuando implemente un particionador personalizado, siga estas instrucciones para asegurarse de que la interacción es correcta con PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A> en TPL:  
  
-   Si se llama a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> con un argumento de cero o menos para `partitionsCount`, se produce una <xref:System.ArgumentOutOfRangeException>.  Aunque PLINQ y TPL nunca pasarán en una `partitionCount` igual a 0, recomendamos, no obstante, que se proteja ante esa posibilidad.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> siempre deberían devolver el número de particiones `partitionsCount`.  Si particionador se ejecuta fuera de los datos y no puede crear tantas particiones como se solicitan, el método debería devolver un enumerador vacío para cada una de las particiones restantes.  De lo contrario, PLINQ y TPL producirán una <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> nunca deberían devolver `null` \(`Nothing` en Visual Basic\).  Si lo hacen, PLINQ \/ TPL producirán una excepción <xref:System.InvalidOperationException>.  
  
-   Los métodos que devuelven particiones siempre deberían devolver particiones que puedan enumerar completamente y de forma única el origen de datos.  No debería haber ninguna duplicación en el origen de datos ni elementos omitidos a menos que lo requiera específicamente el particionador.  Si no se sigue esta regla, se puede alterar el orden del resultado.  
  
-   Los siguientes captadores get booleanos siempre deben devolver con precisión los siguientes valores para que no se altere el orden de salida:  
  
    -   `KeysOrderedInEachPartition`: cada partición devuelve los elementos con índices de clave en aumento.  
  
    -   `KeysOrderedAcrossPartitions`: Para todas las particiones que se devuelven, los índices de la clave del elemento *i* son más altos que los índices de la clave de la partición *i*\-1.  
  
    -   `KeysNormalized`: todos los índices de clave aumentan consecutivamente, comenzando por cero.  
  
-   Todos los índices deben ser únicos.  No puede haber índices duplicados.  Si no se sigue esta regla, se puede alterar el orden del resultado.  
  
-   Todos los índices deben ser no negativos.  Si no se sigue esta regla, PLINQ\/TPL pueden producir excepciones.  
  
## Vea también  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)