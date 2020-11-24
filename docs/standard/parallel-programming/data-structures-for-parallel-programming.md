---
title: Estructuras de datos para la programación paralela
ms.date: 03/30/2017
helpviewer_keywords:
- data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
ms.openlocfilehash: c7f974c5626cf1efc6bf62c423043089d5c32e7c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829536"
---
# <a name="data-structures-for-parallel-programming"></a>Estructuras de datos para la programación paralela

En .NET se proporcionan varios tipos que son útiles para la programación en paralelo, incluido un conjunto de clases de colecciones simultáneas, primitivos de sincronización ligera y tipos para la inicialización diferida. Puede usar estos tipos con cualquier código de aplicación multiproceso, como la biblioteca TPL y PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Clases de colecciones simultáneas  
 Las clases de colecciones del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> ofrece operaciones de agregar y quitar seguras para subprocesos que evitan los bloqueos siempre que sea posible y usan el bloqueo específico cuando los bloqueos son necesarios. Una clase de colección simultánea no necesita que el código de usuario tome ningún bloqueo cuando accede a los elementos. Las clases de colecciones simultáneas pueden mejorar significativamente el rendimiento a través de tipos como <xref:System.Collections.ArrayList?displayProperty=nameWithType> y <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (con bloqueo implementado por el usuario) en escenarios donde varios subprocesos agregarán y quitarán elementos de una colección.  
  
 En la tabla siguiente se enumeran las clases de colección simultáneas:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Proporciona capacidades de bloqueo y establecimiento de límites en colecciones seguras para subprocesos que implementan <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Los subprocesos de productor se bloquean si no hay ranuras disponibles o si la colección está llena. Los subprocesos de consumidor se bloquean si la colección está vacía. Este tipo también admite el acceso sin bloqueo de productores y consumidores. <xref:System.Collections.Concurrent.BlockingCollection%601> puede utilizarse como una clase base o una memoria auxiliar para proporcionar el bloqueo y el establecimiento de límite de cualquier clase de colección que admite <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Una implementación de contenedor segura para subprocesos que ofrece operaciones add y get escalables.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Un tipo de diccionario simultáneo y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Un tipo de cola FIFO simultánea y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Un tipo de pila LIFO simultánea y escalable.|  
  
 Para obtener más información, consulte [Colecciones seguras para subprocesos](../collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Primitivos de sincronización  
 Los primitivos de sincronización del espacio de nombres <xref:System.Threading?displayProperty=nameWithType> permiten un rendimiento más rápido y una simultaneidad específica al evitar mecanismos de bloqueo costosos que se encuentran en el código de multithreading heredado.
  
 En la tabla siguiente se enumeran los tipos de sincronización:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Permite que varios subprocesos funcionen en un algoritmo en paralelo proporcionando un punto en el que cada tarea pueda señalizar su llegada y después bloquearse hasta que llegan algunas tareas o todas. Para más información, consulte [Barrier](../threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Simplifica los escenarios de bifurcación y combinación proporcionando un mecanismo sencillo de encuentro. Para más información, vea [CountdownEvent](../threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Un primitivo de sincronización similar a <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim> es ligero, pero solo puede utilizarse para la comunicación dentro de un proceso.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Un primitivo de sincronización que limita el número de subprocesos que acceden simultáneamente a un recurso o a un conjunto de recursos. Para más información, vea [Semaphore y SemaphoreSlim](../threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Un primitivo de bloqueo de exclusión mutua genera el subproceso que trata de obtener un bloqueo para esperar en un bucle, o *girar*, durante un período de tiempo antes de producir su cuanto. En escenarios en los que se prevé que la espera del bloqueo sea corta, <xref:System.Threading.SpinLock> ofrece mayor rendimiento que otras formas de bloqueo. Para más información, vea [SpinLock](../threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Un tipo pequeño y ligero que girará durante un tiempo especificado y, finalmente, colocará el subproceso en un estado de espera si se supera el número de giros.  Para más información, vea [SpinWait](../threading/spinwait.md).|  
  
 Para más información, consulte:  
  
- [Cómo: Utilizar SpinLock para la sincronización de bajo nivel](../threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
- [Procedimiento: Sincronizar operaciones simultáneas con una clase Barrier](../threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Clases de inicialización diferida  
 Con la inicialización diferida, no se asigna la memoria para un objeto hasta que se necesite. La inicialización diferida puede mejorar el rendimiento al distribuir las asignaciones de objetos uniformemente a lo largo de la duración de un programa. Puede habilitar la inicialización diferida para cualquier tipo personalizado ajustando el tipo <xref:System.Lazy%601>.  
  
 En la tabla siguiente se enumeran los tipos de inicialización diferida:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Proporciona una inicialización diferida segura para subprocesos y ligera.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Proporciona un valor inicializado de forma diferida por cada subproceso, donde cada subproceso invoca de forma diferida la función de inicialización.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Proporciona métodos estáticos que evitan la necesidad de asignar una instancia de inicialización diferida y dedicada. En su lugar, usan referencias para garantizar que los destinos se han inicializado a medida que se accede a ellos.|  
  
 Para obtener más información, vea [Inicialización diferida](../../framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Agregar excepciones  
 El tipo <xref:System.AggregateException?displayProperty=nameWithType> puede usarse para capturar varias excepciones que se producen simultáneamente en subprocesos independientes y devolverlas al subproceso combinado como una única excepción. Los tipos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> y PLINQ usan <xref:System.AggregateException> de forma amplia para este propósito. Para obtener más información, vea [Control de excepciones](exception-handling-task-parallel-library.md) y [Cómo: Controlar excepciones en una consulta PLINQ](how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- <xref:System.Threading?displayProperty=nameWithType>
- [Programación en paralelo](index.md)
