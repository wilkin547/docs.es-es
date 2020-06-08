---
title: Particionadores personalizados para PLINQ y TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
ms.openlocfilehash: 50553aab30d5a1bc5880ae0fe39c34508e57d0e5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276730"
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Particionadores personalizados para PLINQ y TPL

Para paralelizar una operación en un origen de datos, uno de los pasos esenciales es *particionar* el origen en varias secciones a las que pueden acceder varios subprocesos al mismo tiempo. PLINQ y la biblioteca TPL proporcionan particionadores predeterminados que funcionan de manera transparente al escribir un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> o una consulta en paralelo. Para escenarios más avanzados, puede conectar su propio particionador.

## <a name="kinds-of-partitioning"></a>Tipos de particiones

Hay muchas maneras de particionar un origen de datos. En los enfoques más eficaces, varios subprocesos cooperan para procesar la secuencia de origen original, en lugar de separar físicamente el origen en varias secuencias secundarias. Para matrices y otros orígenes indexados como colecciones <xref:System.Collections.IList> donde la longitud se conoce de antemano, la *creación de particiones por rangos* es el tipo más sencillo de creación de particiones. Cada subproceso recibe índices exclusivos de apertura y cierre, para poder procesar su rango del origen sin sobrescribir subprocesos ni ser sobrescrito por algún subproceso. La única sobrecarga implicada en la creación de particiones por rangos es el trabajo inicial de crear los rangos; después de eso, no se requiere ninguna sincronización adicional. Por lo tanto, puede proporcionar un buen rendimiento siempre y cuando la carga de trabajo se divida de manera uniforme. Una desventaja de la creación de particiones por rangos es que, si un subproceso finaliza de forma anticipada, no puede ayudar a los otros subprocesos a finalizar su trabajo.

Para listas vinculadas u otras colecciones cuya longitud no se conoce, puede usar la *creación de particiones por fragmentos*. En la creación de particiones por fragmentos, cada subproceso o tarea de una consulta o bucle paralelos consumen algunos elementos de origen de un fragmento, los procesan y vuelven a activarse para recuperar elementos adicionales. El particionador garantiza que todos los elementos se distribuyan y que no se dupliquen. Un fragmento puede tener cualquier tamaño. Por ejemplo, el particionador que se muestra en [Cómo: Implementar las particiones dinámicas](how-to-implement-dynamic-partitions.md) crea fragmentos que contienen un solo elemento. Siempre que los fragmentos no sean demasiado grandes, este tipo de creación de particiones tiene un equilibrio de carga inherente, porque la asignación de elementos a los subprocesos no es predeterminada. Sin embargo, el particionador no incurre en sobrecarga de sincronización cada vez que el subproceso necesita obtener otro fragmento. La cantidad de sincronización en que se incurre en estos casos es inversamente proporcional al tamaño de los fragmentos.

En general, la creación de particiones por rangos solo es más rápida cuando el tiempo de ejecución del delegado es de bajo a moderado y el origen tiene un gran número de elementos y el trabajo total de cada partición es más o menos equivalente. Por tanto, la creación de particiones por fragmentos suele ser más rápida en la mayoría de los casos. En los orígenes con un número reducido de elementos o con tiempos de ejecución más largos para el delegado, el rendimiento de la creación de particiones por fragmentos y rangos es prácticamente el mismo.

Los particionadores de TPL también admiten un número de particiones dinámico. Esto significa que se pueden crear particiones sobre la marcha, por ejemplo, cuando el bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A> genera una nueva tarea. Esta característica permite al particionador escalarse junto con el propio bucle. Los particionadores dinámicos también tienen un equilibrio de carga inherente. Cuando se crea un particionador personalizado, debe admitir la creación de particiones dinámicas para poder usarlas desde un bucle <xref:System.Threading.Tasks.Parallel.ForEach%2A>.

### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Configuración de particionadores de equilibrio de carga para PLINQ

Algunas sobrecargas del método <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> permiten crear un particionador para una matriz o un origen <xref:System.Collections.IList> y especificar si debe intentar equilibrar la carga de trabajo entre los subprocesos. Cuando se configura el particionador para equilibrar la carga, se emplea la creación de particiones por fragmentos, y los elementos se entregan a cada partición en pequeños fragmentos a medida que se solicitan. Este enfoque ayuda a garantizar que todas las particiones tienen elementos para procesar hasta que se completa totalmente un bucle o una consulta. Se puede usar una sobrecarga adicional para proporcionar particiones de equilibrio de carga de cualquier origen <xref:System.Collections.IEnumerable>.

En general, el equilibrio de carga requiere que las particiones soliciten elementos con relativa frecuencia desde el particionador. Por el contrario, un particionador que crea particiones estáticas puede asignar todos los elementos a cada particionador al mismo tiempo mediante el uso de la creación de particiones por rangos o por fragmentos. Esto requiere menos sobrecarga que el equilibrio de carga, pero es posible que tarde más tiempo en ejecutarse si un subproceso termina significativamente con más trabajo que los demás. De forma predeterminada, cuando se pasa una interfaz IList o una matriz, PLINQ siempre utiliza la creación de particiones por rangos sin equilibrio de carga. Para habilitar el equilibrio de carga para PLINQ, use el método `Partitioner.Create`, tal como se muestra en el ejemplo siguiente.

[!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
[!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]

La mejor forma de determinar si usar el equilibrio de carga en un escenario concreto es experimentar y medir el tiempo que las operaciones tardan en completarse con cargas representativas y configuraciones de equipos. Por ejemplo, el particionamiento estático podría proporcionar un aumento significativo de la velocidad en un equipo de varios núcleos que tenga solo unos pocos núcleos, pero podría dar como resultado una ralentización de los equipos que tienen relativamente muchos núcleos.

En la siguiente tabla se enumeran las sobrecargas disponibles del método <xref:System.Collections.Concurrent.Partitioner.Create%2A>. Estos particionadores no están limitados para utilizarse solo con PLINQ o <xref:System.Threading.Tasks.Task>. También se pueden utilizar con cualquier construcción paralela personalizada.

|Sobrecarga|Usa el equilibrio de carga|
|--------------|-------------------------|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Siempre|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Cuando el argumento Boolean se especifica como true|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Cuando el argumento Boolean se especifica como true|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nunca|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nunca|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nunca|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nunca|

### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Configuración de particionadores por rangos estáticos para Parallel.ForEach

En un bucle <xref:System.Threading.Tasks.Parallel.For%2A>, el cuerpo del bucle se proporciona al método como un delegado. El costo de invocar ese delegado es aproximadamente el mismo que una llamada al método virtual. En algunos escenarios, el cuerpo de un bucle paralelo podría ser lo suficientemente pequeño como para que el costo de la invocación del delegado en cada iteración del bucle sea significativo. En estas situaciones, puede usar una de las sobrecargas <xref:System.Collections.Concurrent.Partitioner.Create%2A> para crear una interfaz <xref:System.Collections.Generic.IEnumerable%601> de particiones por rangos de los elementos de origen. A continuación, puede pasar esta colección de intervalos a un método <xref:System.Threading.Tasks.Parallel.ForEach%2A> cuyo cuerpo se compone de un bucle `for` normal. La ventaja de este enfoque es que se incurre en el costo de invocación del delegado solo una vez por rango, en lugar de una vez por elemento. En el siguiente ejemplo se muestra el patrón básico.

[!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
[!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]

Cada subproceso del bucle recibe su propio <xref:System.Tuple%602> que contiene los valores de índice de inicio y fin en el subrango especificado. El bucle `for` interno usa los valores `fromInclusive` y `toExclusive` para recorrer en bucle la matriz o <xref:System.Collections.IList> directamente.

Una de las sobrecargas <xref:System.Collections.Concurrent.Partitioner.Create%2A> le permite especificar el tamaño de las particiones y el número de particiones. Esta sobrecarga puede usarse en escenarios en los que el trabajo por elemento es tan bajo que incluso una llamada a un método virtual por elemento tiene un impacto considerable en el rendimiento.

## <a name="custom-partitioners"></a>Particionadores personalizados

En algunos casos, podría merecer la pena o incluso ser necesario implementar un particionador propio. Por ejemplo, podría tener una clase de colección personalizada que puede crear particiones de forma más eficaz que los particionadores predeterminados, según su conocimiento de la estructura interna de la clase. O bien, puede que desee crear particiones por rangos de tamaños diferentes basándose en su conocimiento de cuánto tiempo se tardará en procesar los elementos en ubicaciones distintas de la colección de origen.

Para crear un particionador personalizado básico, derive una clase de <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> e invalide los métodos virtuales, tal como se describe en la tabla siguiente.

|||
|-|-|
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|El subproceso principal llama una vez a este método y se devuelve IList(IEnumerator(TSource)). Cada subproceso de trabajo del bucle o la consulta puede llamar a `GetEnumerator` en la lista para recuperar <xref:System.Collections.Generic.IEnumerator%601> a través de una partición distinta.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelva `true` si implementa <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>; en caso contrario, `false`.|
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, opcionalmente, se puede llamar a este método en lugar de a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

Si los resultados se pueden ordenar o precisa de acceso indexado a los elementos, realice una derivación de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> e invalide los métodos virtuales como se describe en la tabla siguiente.

|||
|-|-|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|El subproceso principal llama una vez a este método y se devuelve `IList(IEnumerator(TSource))`. Cada subproceso de trabajo del bucle o la consulta puede llamar a `GetEnumerator` en la lista para recuperar <xref:System.Collections.Generic.IEnumerator%601> a través de una partición distinta.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelva `true` si implementa <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>; de lo contrario, false.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|Normalmente, esto simplemente llama a <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Si <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> es `true`, opcionalmente, se puede llamar a este método en lugar de a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|

En la tabla siguiente se proporcionan detalles adicionales sobre cómo los tres tipos de particionadores de equilibrio de carga implementan la clase <xref:System.Collections.Concurrent.OrderablePartitioner%601>.

|Método/propiedad|IList/matriz sin equilibrio de carga|IList/matriz con equilibrio de carga|IEnumerable|
|----------------------|-------------------------------------------|----------------------------------------|-----------------|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Usa la creación de particiones por rangos|Usa la creación de particiones por fragmentos optimizada para listas de la clase partitionCount especificada|Usa la creación de particiones por fragmentos mediante la creación de un número estático de particiones.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Genera una excepción no admitida|Usa la creación de particiones por fragmentos para listas y particiones dinámicas|Usa la creación de particiones por fragmentos mediante la creación de un número dinámico de particiones.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Devuelve `true`|Devuelve `false`|Devuelve `false`|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Devuelve `true`|Devuelve `true`|Devuelve `true`|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Devuelve `false`|Devuelve `true`|Devuelve `true`|

### <a name="dynamic-partitions"></a>Particiones dinámicas

Si pretende que el particionador se use en un método <xref:System.Threading.Tasks.Parallel.ForEach%2A>, debe tener la capacidad de devolver un número dinámico de particiones. Esto significa que el particionador puede proporcionar un enumerador para una nueva partición a petición en cualquier momento durante la ejecución del bucle. Básicamente, siempre que el bucle agrega una nueva tarea en paralelo, solicita una nueva partición de esa tarea. Si necesita que los datos se puedan ordenar, realice la derivación de <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>, para que a cada elemento de cada partición se le asigne un índice único.

Para obtener más información y un ejemplo, vea [Cómo: Implementar las particiones dinámicas](how-to-implement-dynamic-partitions.md).

### <a name="contract-for-partitioners"></a>Contrato para particionadores

Al implementar un particionador personalizado, siga estas instrucciones para ayudar a garantizar la interacción correcta con PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A> en la biblioteca TPL:

- Si se llama a <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> con un argumento de cero o menos para `partitionsCount`, se produce <xref:System.ArgumentOutOfRangeException>. Aunque PLINQ y TPL nunca pasarán una clase `partitionCount` igual a 0, no obstante, se recomienda adoptar medidas preventivas para evitar esta posibilidad.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> siempre deben devolver una serie de particiones `partitionsCount`. Si el particionador agota los datos y no puede crear tantas particiones como se han solicitado, el método debe devolver un enumerador vacío para cada una de las particiones restantes. De lo contrario, PLINQ y TPL producirán una excepción <xref:System.InvalidOperationException>.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> y <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> nunca deberían devolver `null` (`Nothing` en Visual Basic). Si lo hacen, PLINQ/TPL producirán una excepción <xref:System.InvalidOperationException>.

- Los métodos que devuelven particiones siempre deberían devolver particiones que puedan enumerar completamente y de forma única el origen de datos. No debería haber ninguna duplicación del origen de datos ni elementos omitidos a menos que lo requiera específicamente el diseño del particionador. Si no se respeta esta regla, se puede alterar el orden de salida.

- Los siguientes captadores booleanos deben devolver siempre con precisión los siguientes valores para que no se altere el orden de salida:

  - `KeysOrderedInEachPartition`: cada partición devuelve elementos con índices de claves crecientes.

  - `KeysOrderedAcrossPartitions`: para todas las particiones que se devuelven, los índices de clave de la partición *i* son más altos que los índices de clave de la partición *i*-1.

  - `KeysNormalized`: todos los índices de claves aumentan ininterrumpidamente sin espacios, empezando desde cero.

- Todos los índices deben ser únicos. No puede haber índices duplicados. Si no se respeta esta regla, se puede alterar el orden de salida.

- Todos los índices deben ser no negativos. Si no se respeta esta regla, PLINQ/TPL pueden producir excepciones.

## <a name="see-also"></a>Vea también

- [Programación en paralelo](index.md)
- [Implementar las particiones dinámicas](how-to-implement-dynamic-partitions.md)
- [Implementar un particionador para particionamiento estático](how-to-implement-a-partitioner-for-static-partitioning.md)
