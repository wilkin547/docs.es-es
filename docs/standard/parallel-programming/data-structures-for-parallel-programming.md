---
title: "Estructuras de datos para la programación paralela"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>Estructuras de datos para la programación paralela
.NET Framework versión 4 incorpora a varios tipos nuevos que resultan útiles en programación en paralelo, incluido un conjunto de clases de colección simultáneas, primitivas de sincronización ligeros y tipos para la inicialización diferida. Puede usar estos tipos con cualquier código de aplicación multiproceso, incluidos los Task Parallel Library y PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Clases de colección simultáneas  
 Las clases de colección en el <xref:System.Collections.Concurrent?displayProperty=nameWithType> espacio de nombres proporcionan subprocesos agregar y quitar las operaciones que evitan los bloqueos siempre que sea posible y usar bloqueo específico donde son necesarios los bloqueos. A diferencia de las colecciones que se introdujeron en las versiones 1.0 y 2.0 de .NET Framework, una clase de colección simultáneas no requieren que adopta ningún bloqueo al tener acceso a elementos de código de usuario. Las clases de colección simultáneas pueden mejorar significativamente el rendimiento a través de tipos como <xref:System.Collections.ArrayList?displayProperty=nameWithType> y <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (con bloqueo implementado por el usuario) en escenarios donde varios subprocesos agregarán y quitar elementos de una colección.  
  
 En la tabla siguiente se enumera las nuevas clases de colección simultáneas:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Proporciona capacidades de bloqueo y establecimiento de límites en colecciones seguras para subprocesos que implementan <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Subprocesos de productor se bloquean si no hay ranuras disponibles o si la colección está lleno. Subprocesos de consumidor se bloquean si la colección está vacía. Este tipo también admite el acceso sin bloqueo por productores y consumidores. <xref:System.Collections.Concurrent.BlockingCollection%601>puede utilizarse como una clase base o memoria para proporcionar el bloqueo y establecimiento de límites para cualquier clase de colección que admita auxiliar <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Una implementación de contenedor seguro para subprocesos que proporciona escalable operaciones add y get.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Un tipo de diccionario simultáneo y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Una cola FIFO simultánea y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Una pila LIFO simultánea y escalable.|  
  
 Para obtener más información, consulte [Colecciones seguras para subprocesos](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Primitivas de sincronización  
 Las primitivas de sincronización nueva en la <xref:System.Threading?displayProperty=nameWithType> espacio de nombres permiten un rendimiento más rápido y simultaneidad específica al evitar costosos mecanismos de bloqueo en el código multithreading heredado. Algunos de los nuevos tipos, como <xref:System.Threading.Barrier?displayProperty=nameWithType> y <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> no tienen ningún homólogo no genérico en versiones anteriores de .NET Framework.  
  
 En la tabla siguiente se enumera los nuevos tipos de sincronización:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Permite que varios subprocesos para que funcione en un algoritmo en paralelo proporcionando un punto en el que cada tarea puede señalar su llegada y, a continuación, se bloquea hasta que algunas o todas las tareas hayan llegado. Para más información, consulte [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Simplifica los escenarios de bifurcación y unión proporcionando un mecanismo sencillo de rendezvous. Para obtener más información, consulte [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Primitiva de sincronización similar a <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim>es ligero, pero solo puede utilizarse para la comunicación dentro de un proceso. Para obtener más información, consulte [ManualResetEvent y ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Primitiva de sincronización que limita el número de subprocesos que puede tener acceso simultáneamente a un recurso o un grupo de recursos. Para obtener más información, consulte [Semaphore y SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Una primitiva de bloqueo de exclusión mutua que hace que el subproceso que está intentando adquirir el bloqueo espera en un bucle, o *número*, durante un período de tiempo antes de producir su cuanto. En escenarios donde se espera que la espera para adquirir el bloqueo son cortos, <xref:System.Threading.SpinLock> ofrece un rendimiento mayor que otras formas de bloqueo. Para obtener más información, consulte [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Un tipo pequeño y ligero que girará durante un tiempo especificado y, finalmente, coloca el subproceso en un estado de espera si se supera el número de número.  Para obtener más información, consulte [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Para obtener más información, consulte:  
  
-   [Utilizar SpinLock para la sincronización de bajo nivel](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [Cómo: sincronizar operaciones simultáneas con una clase Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Clases de inicialización diferida  
 Con la inicialización diferida, no se asigna un objeto de la memoria hasta que se necesite. La inicialización diferida puede mejorar el rendimiento al distribuir las asignaciones de objetos uniformemente a través de la duración de un programa. Puede habilitar la inicialización diferida para cualquier tipo personalizado ajustando el tipo <xref:System.Lazy%601>.  
  
 En la tabla siguiente se enumera los tipos de inicialización diferida:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Proporciona ligera y segura para subprocesos y la inicialización diferida.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Proporciona un valor de inicialización diferida en una base por subproceso, con cada subproceso invoca de forma diferida la función de inicialización.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Proporciona métodos estáticos que evitan la necesidad de asignar una instancia dedicada de inicialización diferida. En su lugar, usan referencias para asegurarse de que se hayan inicializado destinos tal y como se accede a estos.|  
  
 Para obtener más información, vea [Inicialización diferida](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Agregar excepciones  
 El <xref:System.AggregateException?displayProperty=nameWithType> tipo permiten capturar varias excepciones que se producen simultáneamente en subprocesos independientes y devuelven al subproceso de unión como una sola excepción. El <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> tipos y PLINQ utilizan <xref:System.AggregateException> ampliamente para este propósito. Para obtener más información, consulte [NIB: Cómo: controlar excepciones iniciadas por tareas](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d) y [Cómo: controlar excepciones en una consulta PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
