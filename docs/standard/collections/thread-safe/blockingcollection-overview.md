---
title: "Informaci&#243;n general sobre BlockingCollection | Microsoft Docs"
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
  - "BlockingCollection, información general"
ms.assetid: 987ea3d7-0ad5-4238-8b64-331ce4eb3f0b
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre BlockingCollection
<xref:System.Collections.Concurrent.BlockingCollection%601> es una clase de colección segura para subprocesos que proporciona las siguientes características:  
  
-   Implementación del modelo productor\-consumidor.  
  
-   Operaciones simultáneas de agregar y quitar elementos en varios subprocesos.  
  
-   Capacidad máxima opcional.  
  
-   Operaciones de inserción y eliminación que se bloquean cuando la colección está vacía o completa.  
  
-   Operación de inserción y eliminación "try" que no se bloquean o que se bloquean en un período de tiempo especificado.  
  
-   Encapsula los tipos de colección que implementen <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>  
  
-   Cancelación con tokens de cancelación.  
  
-   Dos tipos de enumeración con `foreach` \(`For Each` en Visual Basic\):  
  
    1.  Enumeración de solo lectura.  
  
    2.  Enumeración que quita los elementos a medida que se van enumerando.  
  
## Compatibilidad con delimitación y bloqueo  
 <xref:System.Collections.Concurrent.BlockingCollection%601> admite los enlaces y bloqueos.  Delimitación significa que el usuario puede establecer la capacidad máxima de la colección.  La delimitación es importante en ciertos casos porque permite controlar el tamaño máximo de la colección en memoria y evita que los subprocesos productores vayan muy por delante de los subprocesos consumidores.  
  
 Varios subprocesos o tareas pueden agregar elementos a la colección simultáneamente y, si la colección alcanza la capacidad máxima especificada, los subprocesos productores se bloquean hasta que se quite algún elemento.  Varios consumidores pueden quitar elementos simultáneamente y, si la colección se vacía, los subprocesos consumidores se bloquean hasta que un productor agregue un elemento.  Un subproceso productor puede llamar al método <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A> para indicar que no se van a agregar más elementos.  Los consumidores supervisan la propiedad <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> para determinar cuándo la colección está vacía y no se van a agregar más elementos.  En el siguiente ejemplo se muestra una BlockingCollection sencilla con una capacidad limitada de 100.  Una tarea de productor agrega elementos a la colección siempre que alguna condición externa sea true, y después llama a <xref:System.Collections.Concurrent.BlockingCollection%601.CompleteAdding%2A>.  La tarea de consumidor toma elementos hasta que el valor de la propiedad <xref:System.Collections.Concurrent.BlockingCollection%601.IsCompleted%2A> sea true.  
  
 [!code-csharp[CDS_BlockingCollection#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#04)]
 [!code-vb[CDS_BlockingCollection#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#04)]  
  
 Para obtener un ejemplo completo, vea [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Operaciones de bloqueo con tiempo de espera especificado  
 En operaciones <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> de bloqueo con tiempo de espera especificado en colecciones delimitadas, el método intenta agregar o quitar un elemento.  Si un elemento está disponible se coloca en la variable que se pasó por referencia, y el método devuelve true.  Si no se recupera ningún elemento después de un tiempo de espera especificado, el método devuelve false.  Después, el subproceso puede hacer otro trabajo útil antes de intentar tener acceso a la colección de nuevo.  Para obtener un ejemplo de acceso de bloqueo con tiempo de espera especificado, vea el segundo ejemplo de [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Cancelar operaciones de agregar y quitar  
 Las operaciones de agregar y quitar se realizan normalmente en un bucle.  Para cancelar un bucle, pase un <xref:System.Threading.CancellationToken> al método <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> y, a continuación, compruebe el valor de la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token en cada iteración.  Si el valor es true, puede responder a la solicitud de cancelación limpiando los recursos y saliendo del bucle.  En el siguiente ejemplo, se muestran una sobrecarga del método <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> que toma un token de cancelación, y el código que lo utiliza:  
  
 [!code-csharp[CDS_BlockingCollection#05](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/blockingcollection.cs#05)]
 [!code-vb[CDS_BlockingCollection#05](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/introsnippetsbc.vb#05)]  
  
 Para obtener un ejemplo de cómo agregar compatibilidad con las cancelaciones, vea el segundo ejemplo de [Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md).  
  
## Especificar el tipo de colección  
 Cuando crea una clase <xref:System.Collections.Concurrent.BlockingCollection%601>, puede especificar la capacidad limitada así como el tipo de colección que se va a utilizar.  Por ejemplo, puede especificar <xref:System.Collections.Concurrent.ConcurrentQueue%601> para primero el en\- primer out comportamiento de \(FIFO\), o <xref:System.Collections.Concurrent.ConcurrentStack%601> para el comportamiento de último en entrar, primero en salir de \(LIFO\).  Puede usar cualquier clase de colección que implemente la interfaz <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.  EL tipo de colección predeterminado para <xref:System.Collections.Concurrent.BlockingCollection%601> es <xref:System.Collections.Concurrent.ConcurrentQueue%601>.  En el siguiente ejemplo de código, se muestra cómo crear una colección <xref:System.Collections.Concurrent.BlockingCollection%601> de cadenas que tiene una capacidad de 1000 y utiliza una colección <xref:System.Collections.Concurrent.ConcurrentBag%601>:  
  
```vb  
Dim bc = New BlockingCollection(Of String)(New ConcurrentBag(Of String()), 1000)  
```  
  
```csharp  
BlockingCollection<string> bc = new BlockingCollection<string>(new ConcurrentBag<string>(), 1000 );  
```  
  
 Para obtener más información, vea [Cómo: Agregar la funcionalidad de límite y bloqueo a una colección](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md).  
  
## Compatibilidad con IEnumerable  
 <xref:System.Collections.Concurrent.BlockingCollection%601> proporciona un método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> que permite a los consumidores utilizar `foreach` \(`For Each` en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\) para quitar los elementos hasta que la colección esté completa, lo que significa que está vacía y no se agregará ningún elemento.  Para obtener más información, vea [Cómo: Utilizar ForEach para quitar elementos de BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md).  
  
## Utilizar muchas BlockingCollections como una  
 Para los escenarios en los que un consumidor necesita elementos de varias colecciones simultáneamente, puede crear matrices de <xref:System.Collections.Concurrent.BlockingCollection%601> y utilizar métodos estáticos como <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.AddToAny%2A> que agregarán o quitarán elementos de cualquiera de las colecciones de la matriz.  Si una colección produce un bloqueo, el método prueba con otra inmediatamente, hasta que encuentra una que puede realizar la operación.  Para obtener más información, vea [Cómo: Usar matrices de colecciones de bloqueo en una canalización](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md).  
  
## Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Colecciones y estructuras de datos](../../../../docs/standard/collections/index.md)   
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)