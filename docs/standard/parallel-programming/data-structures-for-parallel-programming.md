---
title: "Data Structures for Parallel Programming | Microsoft Docs"
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
  - "data structures, multi-threading"
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Data Structures for Parallel Programming
.NET Framework versión 4 incorpora varios tipos nuevos que resultan útiles para la programación en paralelo, entre los que se incluye un conjunto de clases de colección simultáneas, primitivas de sincronización ligeras y tipos de inicialización diferida.  Puede usar estos tipos con cualquier código de aplicación multiproceso, incluso con la biblioteca TPL \(Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas\) y PLINQ.  
  
## Clases de colección simultáneas  
 Las clases de colección del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=fullName> proporcionan operaciones Add y Remove seguras para subprocesos que evitan los bloqueos en la medida de lo posible y, cuando es necesario, usan bloqueos específicos.  A diferencia de las colecciones que se incorporaron en las versiones 1.0 y 2.0 de .NET Framework, una clase de colección simultánea no requiere que el código de usuario tome ningún bloqueo cuando obtiene acceso a los elementos.  Las clases de colección simultáneas pueden mejorar significativamente el rendimiento frente a tipos como <xref:System.Collections.ArrayList?displayProperty=fullName> y <xref:System.Collections.Generic.List%601?displayProperty=fullName> \(con bloqueo implementado por el usuario\) en escenarios en lo que varios subprocesos agregan y quitan elementos de una colección.  
  
 En la tabla siguiente se muestran las nuevas clases de colección simultáneas:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>|Proporciona capacidades de bloqueo y establecimiento de límites en colecciones seguras para subprocesos que implementan <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName>.  Los subprocesos de productor se bloquean si no hay ranuras disponibles o si la colección está completa.  Los subprocesos de consumidor se bloquean si la colección está vacía.  Este tipo también permite el acceso sin bloqueo de los subprocesos de consumidor y productor.  <xref:System.Collections.Concurrent.BlockingCollection%601> puede usarse como clase base o memoria auxiliar para proporcionar el bloqueo y el establecimiento de límites de cualquier clase de colección que admita <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>|Implementación de un contenedor seguro para subprocesos que proporciona operaciones Add y Get escalables.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>|Tipo de diccionario simultáneo y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>|Cola FIFO simultánea y escalable.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>|Pila LIFO simultánea y escalable.|  
  
 Para obtener más información, vea [Colecciones seguras para subprocesos](../../../docs/standard/collections/thread-safe/index.md).  
  
## Primitivas de sincronización  
 Las nuevas primitivas de sincronización del espacio de nombres <xref:System.Threading?displayProperty=fullName> proporcionan una simultaneidad específica y un mayor rendimiento ya que evitan los costosos mecanismos de bloqueo que se encuentran en el código multithreading heredado.  Algunos de los nuevos tipos, como <xref:System.Threading.Barrier?displayProperty=fullName> y <xref:System.Threading.CountdownEvent?displayProperty=fullName>, no tienen equivalente en versiones anteriores de .NET Framework.  
  
 En la tabla siguiente, se muestran los nuevos tipos de sincronización:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=fullName>|Permite que varios subprocesos trabajen en un algoritmo en paralelo proporcionando un punto en el que cada tarea puede señalar su llegada y bloquearse hasta que algunas o todas las tareas hayan llegado.  Para obtener más información, vea [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=fullName>|Simplifica los escenarios de bifurcación y unión proporcionando un mecanismo de encuentro sencillo.  Para obtener más información, vea [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>|Primitiva de sincronización similar a <xref:System.Threading.ManualResetEvent?displayProperty=fullName>.  <xref:System.Threading.ManualResetEventSlim> es un objeto ligero, pero solo puede usarse en la comunicación que tiene lugar dentro de un proceso.  Para obtener más información, vea [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=fullName>|Primitiva de sincronización que limita el número de subprocesos que pueden obtener acceso a la vez a un recurso o grupo de recursos.  Para obtener más información, vea [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=fullName>|Primitiva de bloqueo de exclusión mutua que hace que el subproceso que está intentando adquirir el bloqueo espere en un bucle o *ciclo* durante un período de tiempo antes de que se produzca su cuanto.  En escenarios en los que se prevé que la espera del bloqueo será breve, <xref:System.Threading.SpinLock> proporciona mayor rendimiento que otras formas de bloqueo.  Para obtener más información, vea [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=fullName>|Tipo pequeño y ligero que iterará en ciclos durante un período especificado y situará el subproceso en estado de espera si el recuento de ciclos se supera.  Para obtener más información, vea [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Para obtener más información, vea:  
  
-   [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## Clases de inicialización diferida  
 Con la inicialización diferida, la memoria de un objeto no se asigna hasta que es necesario.  La inicialización diferida puede mejorar el rendimiento al extender las asignaciones de objetos uniformemente a lo largo de la duración de un programa.  Puede habilitar la inicialización diferida en cualquier tipo personalizado encapsulando el tipo <xref:System.Lazy%601>.  
  
 En la tabla siguiente, se muestran los tipos de inicialización diferida:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=fullName>|Proporciona una inicialización diferida ligera y segura para subprocesos.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=fullName>|Proporciona un valor de inicialización diferida por cada subproceso, donde cada subproceso invoca de forma diferida la función de inicialización.|  
|<xref:System.Threading.LazyInitializer?displayProperty=fullName>|Proporciona métodos estáticos que evitan tener que asignar una instancia de inicialización diferida dedicada.  En su lugar, usan referencias para garantizar que los destinos se han inicializado a medida que se va obteniendo acceso a ellos.|  
  
 Para obtener más información, vea [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Excepciones agregadas  
 El tipo <xref:System.AggregateException?displayProperty=fullName> se puede utilizar para capturar varias excepciones que se producen simultáneamente en diferentes subprocesos y devolverlas al subproceso de unión como una sola excepción.  Los tipos <xref:System.Threading.Tasks.Task?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> así como la PLINQ usan <xref:System.AggregateException> en gran medida con este propósito.  Para obtener más información, vea [NIB: How to: Handle Exceptions Thrown by Tasks](http://msdn.microsoft.com/es-es/d6c47ec8-9de9-4880-beb3-ff19ae51565d) y [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 <xref:System.Threading?displayProperty=fullName>   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)