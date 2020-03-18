---
title: Estructuras de datos para la programación paralela
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
ms.openlocfilehash: a2271feae78100940b4ecac3c42c9bfefa7e1769
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123148"
---
# <a name="data-structures-for-parallel-programming"></a>Estructuras de datos para la programación paralela
.NET Framework 4 incorpora varios tipos nuevos que son útiles en la programación paralela, incluido un conjunto de clases de colecciones simultáneas, primitivos de sincronización ligera y tipos para la inicialización diferida. Puede usar estos tipos con cualquier código de aplicación multiproceso, como la biblioteca TPL y PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Clases de colecciones simultáneas  
 Las clases de colecciones del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> ofrece operaciones de agregar y quitar seguras para subprocesos que evitan los bloqueos siempre que sea posible y usan el bloqueo específico cuando los bloqueos son necesarios. A diferencia de las colecciones que se introdujeron en las versiones 1.0 y 2.0 de .NET Framework, una clase de colecciones simultáneas no requiere que el código de usuario adopte ningún bloqueo cuando accede a los elementos. Las clases de colecciones simultáneas pueden mejorar significativamente el rendimiento a través de tipos como <xref:System.Collections.ArrayList?displayProperty=nameWithType> y <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (con bloqueo implementado por el usuario) en escenarios donde varios subprocesos agregarán y quitarán elementos de una colección.  
  
 En la tabla siguiente se enumeran las nuevas clases de colecciones simultáneas:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Proporciona capacidades de bloqueo y establecimiento de límites en colecciones seguras para subprocesos que implementan <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Los subprocesos de productor se bloquean si no hay ranuras disponibles o si la colección está llena. Los subprocesos de consumidor se bloquean si la colección está vacía. Este tipo también admite el acceso sin bloqueo de productores y consumidores. <xref:System.Collections.Concurrent.BlockingCollection%601> puede utilizarse como una clase base o una memoria auxiliar para proporcionar el bloqueo y el establecimiento de límite de cualquier clase de colección que admite <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Una implementación de contenedor segura para subprocesos que ofrece operaciones add y get escalables.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Un tipo de diccionario simultáneo y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Un tipo de cola FIFO simultánea y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Un tipo de pila LIFO simultánea y escalable.|  
  
 Para obtener más información, consulte [Colecciones seguras para subprocesos](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Primitivos de sincronización  
 Los nuevos primitivos de sincronización del espacio de nombres <xref:System.Threading?displayProperty=nameWithType> permiten un rendimiento más rápido y una simultaneidad específica al evitar mecanismos de bloqueo caros que se encuentran en el código multithreading heredado. Algunos de los nuevos tipos, como <xref:System.Threading.Barrier?displayProperty=nameWithType> y <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>, no tienen ningún homólogo en versiones anteriores de .NET Framework.  
  
 En la tabla siguiente se enumeran los nuevos tipos de sincronización:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Permite que varios subprocesos funcionen en un algoritmo en paralelo proporcionando un punto en el que cada tarea pueda señalizar su llegada y después bloquearse hasta que llegan algunas tareas o todas. Para más información, consulte [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Simplifica los escenarios de bifurcación y combinación proporcionando un mecanismo sencillo de encuentro. Para más información, vea [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Un primitivo de sincronización similar a <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim> es ligero, pero solo puede utilizarse para la comunicación dentro de un proceso.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Un primitivo de sincronización que limita el número de subprocesos que acceden simultáneamente a un recurso o a un conjunto de recursos. Para más información, vea [Semaphore y SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Un primitivo de bloqueo de exclusión mutua genera el subproceso que trata de obtener un bloqueo para esperar en un bucle, o *girar*, durante un período de tiempo antes de producir su cuanto. En escenarios en los que se prevé que la espera del bloqueo sea corta, <xref:System.Threading.SpinLock> ofrece mayor rendimiento que otras formas de bloqueo. Para más información, vea [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Un tipo pequeño y ligero que girará durante un tiempo especificado y, finalmente, colocará el subproceso en un estado de espera si se supera el número de giros.  Para más información, vea [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Para obtener más información, consulte:  
  
- [Utilizar SpinLock para la sincronización de bajo nivel](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
- [Sincronizar operaciones simultáneas con una clase Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)  
  
## <a name="lazy-initialization-classes"></a>Clases de inicialización diferida  
 Con la inicialización diferida, no se asigna la memoria para un objeto hasta que se necesite. La inicialización diferida puede mejorar el rendimiento al distribuir las asignaciones de objetos uniformemente a lo largo de la duración de un programa. Puede habilitar la inicialización diferida para cualquier tipo personalizado ajustando el tipo <xref:System.Lazy%601>.  
  
 En la tabla siguiente se enumeran los tipos de inicialización diferida:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Proporciona una inicialización diferida segura para subprocesos y ligera.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Proporciona un valor inicializado de forma diferida por cada subproceso, donde cada subproceso invoca de forma diferida la función de inicialización.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Proporciona métodos estáticos que evitan la necesidad de asignar una instancia de inicialización diferida y dedicada. En su lugar, usan referencias para garantizar que los destinos se han inicializado a medida que se accede a ellos.|  
  
 Para obtener más información, vea [Inicialización diferida](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Agregar excepciones  
 El tipo <xref:System.AggregateException?displayProperty=nameWithType> puede usarse para capturar varias excepciones que se producen simultáneamente en subprocesos independientes y devolverlas al subproceso combinado como una única excepción. Los tipos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> y PLINQ usan <xref:System.AggregateException> de forma amplia para este propósito. Para obtener más información, vea [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md) y [Cómo: Controlar excepciones en una consulta PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- <xref:System.Threading?displayProperty=nameWithType>
- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
