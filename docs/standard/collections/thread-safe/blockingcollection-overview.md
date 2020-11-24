---
title: Información general sobre BlockingCollection
description: Obtenga información sobre BlockingCollection<T>, una clase de colección segura para subprocesos en .NET. Esta clase ofrece características como la adición y la toma simultáneas de elementos de muchos subprocesos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BlockingCollection, overview
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
ms.openlocfilehash: 0378d038d6081c7ad04fc233ac151ab2bb223fa5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818667"
---
# <a name="blockingcollection-overview"></a>Información general sobre BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> es una clase de colección segura para subprocesos que proporciona las siguientes características:  
  
- Una implementación del patrón productor-consumidor.  
  
- Agregar y quitar elementos en varios subprocesos de forma simultánea.  
  
- Capacidad máxima opcional.  
  
- Operaciones de inserción y eliminación que se bloquean cuando la colección está vacía o completa.  
  
- Inserción y eliminación de operaciones "try" que no se bloquean o que se bloquean en un período de tiempo especificado.  
  
- Encapsula cualquier tipo de colección que implementa <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.  
  
- Cancelación con tokens de cancelación.  
  
- Dos tipos de enumeraciones con `foreach` (`For Each` en Visual Basic):  
  
    1. Enumeración de solo lectura.  
  
    2. Enumeración que quita los elementos que se enumeran.  
  
## <a name="bounding-and-blocking-support"></a>Compatibilidad con límites y bloqueos  
 <xref:System.Collections.Concurrent.BlockingCollection%601> admite límites y bloqueos. Los límites implican que puede establecer la capacidad máxima de la colección. Los límites son importantes en ciertos escenarios, porque le permiten controlar el tamaño máximo de la colección en memoria y evitan que los subprocesos de producción vayan demasiado por delante de los subprocesos de consumo.  
  
 Varios subprocesos o tareas pueden agregar elementos a la colección de forma simultánea y, si la colección alcanza su capacidad máxima especificada, los subprocesos de producción se bloquearán hasta que se quite un elemento. Varios consumidores pueden quitar elementos de forma simultánea y, si la colección está vacía, los subprocesos de consumo se bloquearán hasta que un productor agregue un elemento. Un subproceso de producción puede llamar a <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> para indicar que no se agregarán más elementos. Los consumidores supervisan la propiedad <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> para saber cuándo está vacía la colección y no se agregarán más elementos. En el ejemplo siguiente, se muestra una clase BlockingCollection sencilla con una capacidad limitada de 100. Una tarea de producción agrega elementos a la colección siempre que alguna condición externa sea true y después llama a <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>. La tarea de consumidor toma elementos hasta que la propiedad <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> es true.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Para obtener un ejemplo completo, vea [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="timed-blocking-operations"></a>Operaciones de bloqueo cronometradas  
 En las operaciones de bloqueo cronometradas <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> en colecciones limitadas, el método intenta agregar o quitar un elemento. Si un elemento está disponible, se coloca en la variable que ha pasado la referencia y el método devuelve true. Si no se recupera ningún elemento después de un período de tiempo de espera especificado, el método devuelve false. El subproceso es libre para realizar otro trabajo útil antes de intentar acceder de nuevo a la colección. Para obtener un ejemplo de acceso de bloqueo cronometrado, vea el segundo ejemplo de [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="cancelling-add-and-take-operations"></a>Cancelar operaciones de agregar y tomar  
 Las operaciones de agregar y tomar se realizan normalmente en un bucle. Puede cancelar un bucle al pasar <xref:System.Threading.CancellationToken> a los métodos <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, y después comprobar el valor de la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token en cada iteración. Si el valor es true, puede decidir si responde a la solicitud de cancelación limpiando algún recurso y saliendo del bucle. En el ejemplo siguiente, se muestra una sobrecarga de <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> que toma un token de cancelación y el código que lo usa:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Para obtener un ejemplo de cómo agregar compatibilidad con la cancelación, vea el segundo ejemplo de [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](how-to-add-and-take-items.md).  
  
## <a name="specifying-the-collection-type"></a>Especificar el tipo de colección  
 Cuando se crea una <xref:System.Collections.Concurrent.BlockingCollection%601>, puede especificar no solo la capacidad limitada, sino también el tipo de colección que se usará. Por ejemplo, puede especificar un objeto <xref:System.Collections.Concurrent.ConcurrentQueue%601> para un comportamiento FIFO (primero en entrar, primero en salir) o un objeto <xref:System.Collections.Concurrent.ConcurrentStack%601> para un comportamiento LIFO (último en entrar, primero en salir). Puede usar cualquier clase de colección que implemente la interfaz <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>. El tipo de colección predeterminado para <xref:System.Collections.Concurrent.BlockingCollection%601> es <xref:System.Collections.Concurrent.ConcurrentQueue%601>. En el ejemplo de código siguiente, se muestra cómo crear una <xref:System.Collections.Concurrent.BlockingCollection%601> de cadenas que tiene una capacidad de 1000 y usa un objeto <xref:System.Collections.Concurrent.ConcurrentBag%601>:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Para obtener más información, vea [Cómo: Agregar la funcionalidad de límite y bloqueo a una colección](how-to-add-bounding-and-blocking.md).  
  
## <a name="ienumerable-support"></a>Compatibilidad con IEnumerable  
 <xref:System.Collections.Concurrent.BlockingCollection%601> proporciona un método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> que permite a los consumidores usar `foreach` (`For Each` en Visual Basic) para quitar elementos hasta que la colección está completa, lo que significa que está vacía y no se agregan más elementos. Para obtener más información, vea [Cómo: Usar ForEach para quitar elementos de BlockingCollection](how-to-use-foreach-to-remove.md).  
  
## <a name="using-many-blockingcollections-as-one"></a>Usar muchas BlockingCollections como una  
 Para escenarios en los que un consumidor necesita tomar elementos de varias colecciones de forma simultánea, se pueden crear matrices de <xref:System.Collections.Concurrent.BlockingCollection%601> y usar los métodos estáticos, como <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A>, que agregarán a cualquiera de las colecciones de la matriz o tomarán desde ellas. Si se bloquea una colección, el método intenta otra de forma inmediata hasta que encuentra una que pueda realizar la operación. Para obtener más información, vea [Cómo: Usar matrices de colecciones de bloqueo en una canalización](how-to-use-arrays-of-blockingcollections.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Colecciones y estructuras de datos](../index.md)
- [Colecciones seguras para subprocesos](index.md)
