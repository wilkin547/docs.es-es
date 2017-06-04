---
title: "Threading Objects and Features | Microsoft Docs"
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
  - "threading [.NET Framework], features"
  - "managed threading"
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Threading Objects and Features
.NET Framework proporciona varios objetos que le ayudarán a crear y administrar aplicaciones multiproceso.  Los subprocesos administrados se representan mediante la clase <xref:System.Threading.Thread>.  La clase <xref:System.Threading.ThreadPool> permite crear y administrar fácilmente tareas multiproceso en segundo plano.  La clase <xref:System.ComponentModel.BackgroundWorker> hace lo mismo para las tareas que interactúan con la interfaz de usuario.  La clase <xref:System.Threading.Timer> ejecuta tareas en segundo plano a intervalos de tiempo definidos.  
  
 Además, hay varias clases que sincronizan las actividades de los subprocesos, incluidas las clases <xref:System.Threading.Semaphore> y <xref:System.Threading.EventWaitHandle> que se incorporaron en la versión 2.0 de .NET Framework.  Las características de estas clases se comparan en [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## En esta sección  
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Explica la clase **ThreadPool** , que permite solicitar a un subproceso que ejecute una tarea sin tener que realizar ninguna tarea de administración de subprocesos.  
  
 [Timers](../../../docs/standard/threading/timers.md)  
 Explica cómo usar la clase **Timer** para especificar que se llame a un delegado en un momento determinado.  
  
 [Monitores](../Topic/Monitors.md)  
 Explica cómo usar la clase **Monitor** para sincronizar el acceso a un miembro o para crear sus propios tipos de administración de subprocesos.  
  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 Describe la clase <xref:System.Threading.WaitHandle>, que es la clase base abstracta para los controladores de espera de eventos, exclusiones mutuas y semáforos, y que habilita la espera para varios eventos de sincronización.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 Describe los identificadores de espera de eventos administrados, que se usan para sincronizar las actividades del subproceso mediante señalización y señales de espera.  
  
 [Mutexes](../../../docs/standard/threading/mutexes.md)  
 Explica cómo usar una clase <xref:System.Threading.Mutex>para sincronizar el acceso a un objeto o para crear sus propios mecanismos de sincronización.  
  
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)  
 Explica cómo usar la clase <xref:System.Threading.Interlocked> para aumentar o reducir un valor y almacenarlo en una única operación atómica.  
  
 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)  
 Define un bloqueo que implementa la semántica de un único escritor y varios lectores.  
  
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 Describe los objetos <xref:System.Threading.Semaphore> y explica cómo usarlos para controlar el acceso a recursos limitados.  
  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Compara las características de las clases de .NET Framework proporcionadas para bloquear y sincronizar los subprocesos administrados.  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 Describe los objetos <xref:System.Threading.Barrier> que implementan el modelo de barrera para coordinar los subprocesos en las operaciones por fases.  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 Describe <xref:System.Threading.SpinLock>, una alternativa ligera a la clase Monitor para algunos escenarios de bajo nivel.  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 Describe <xref:System.Threading.SpinWait>, un primitivo de sincronización de bajo nivel que realiza giros de ocupado antes de iniciar una espera basada en kernel.  
  
## Referencia  
 <xref:System.Threading.Thread>  
 Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Habilita tareas en segundo plano que interactúan con la interfaz de usuario, y se comunican mediante eventos generados en el subproceso de la interfaz de usuario.  
  
## Secciones relacionadas  
 [E\/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md)  
 Describe cómo los puertos de finalización asincrónica de E\/S usan el grupo de subprocesos para solicitar procesamiento solo cuando finaliza una operación de entrada\/salida.  
  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Describe el enfoque recomendado para la programación multiproceso en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] y versiones posteriores.