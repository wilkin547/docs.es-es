---
title: "Objetos y características de subprocesos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0cb36c004c46e22256928b3b2432da59fb3e6fa2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="4919e-102">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="4919e-102">Threading Objects and Features</span></span>
<span data-ttu-id="4919e-103">.NET Framework proporciona varios objetos que le ayudarán a crear y administrar aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="4919e-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="4919e-104">Los subprocesos administrados se representan mediante la clase <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="4919e-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="4919e-105">La clase <xref:System.Threading.ThreadPool> permite crear y administrar fácilmente tareas multiproceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4919e-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="4919e-106">La clase <xref:System.ComponentModel.BackgroundWorker> hace lo mismo para las tareas que interactúan con la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4919e-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="4919e-107">La clase <xref:System.Threading.Timer> ejecuta tareas en segundo plano a intervalos de tiempo definidos.</span><span class="sxs-lookup"><span data-stu-id="4919e-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="4919e-108">Además, hay varias clases que sincronizan las actividades de los subprocesos, incluidas las clases <xref:System.Threading.Semaphore> y <xref:System.Threading.EventWaitHandle> que se incorporaron en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4919e-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="4919e-109">Las características de estas clases se comparan en [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización).</span><span class="sxs-lookup"><span data-stu-id="4919e-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4919e-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4919e-110">In This Section</span></span>  
 <span data-ttu-id="4919e-111">[The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md) (Clase ThreadPool administrada)</span><span class="sxs-lookup"><span data-stu-id="4919e-111">[The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)</span></span>  
 <span data-ttu-id="4919e-112">Explica la clase **ThreadPool**, que permite solicitar a un subproceso que ejecute una tarea sin tener que realizar ninguna tarea de administración de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4919e-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 <span data-ttu-id="4919e-113">[Timers](../../../docs/standard/threading/timers.md) (Temporizadores)</span><span class="sxs-lookup"><span data-stu-id="4919e-113">[Timers](../../../docs/standard/threading/timers.md)</span></span>  
 <span data-ttu-id="4919e-114">Explica cómo usar la clase **Timer** para especificar que se llame a un delegado en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="4919e-114">Explains how to use a **Timer** to specify a delegate to be called at a specified time.</span></span>  
  
 <span data-ttu-id="4919e-115">[Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db) (Clases Monitor)</span><span class="sxs-lookup"><span data-stu-id="4919e-115">[Monitors](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)</span></span>  
 <span data-ttu-id="4919e-116">Explica cómo usar la clase **Monitor** para sincronizar el acceso a un miembro o para crear sus propios tipos de administración de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4919e-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 <span data-ttu-id="4919e-117">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="4919e-117">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>  
 <span data-ttu-id="4919e-118">Describe la clase <xref:System.Threading.WaitHandle>, que es la clase base abstracta para los controladores de espera de eventos, exclusiones mutuas y semáforos, y que habilita la espera para varios eventos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="4919e-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="4919e-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="4919e-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="4919e-120">Describe los identificadores de espera de eventos administrados, que se usan para sincronizar las actividades del subproceso mediante señalización y señales de espera.</span><span class="sxs-lookup"><span data-stu-id="4919e-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 <span data-ttu-id="4919e-121">[Mutexes](../../../docs/standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="4919e-121">[Mutexes](../../../docs/standard/threading/mutexes.md)</span></span>  
 <span data-ttu-id="4919e-122">Explica cómo usar una clase <xref:System.Threading.Mutex> para sincronizar el acceso a un objeto o para crear sus propios mecanismos de sincronización.</span><span class="sxs-lookup"><span data-stu-id="4919e-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 <span data-ttu-id="4919e-123">[Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md) (Operaciones Interlocked)</span><span class="sxs-lookup"><span data-stu-id="4919e-123">[Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)</span></span>  
 <span data-ttu-id="4919e-124">Explica cómo usar la clase <xref:System.Threading.Interlocked> para aumentar o reducir un valor y almacenarlo en una única operación atómica.</span><span class="sxs-lookup"><span data-stu-id="4919e-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 <span data-ttu-id="4919e-125">[Reader-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md) (Clase ReaderWriterLockSlim)</span><span class="sxs-lookup"><span data-stu-id="4919e-125">[Reader-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)</span></span>  
 <span data-ttu-id="4919e-126">Define un bloqueo que implementa la semántica de un único escritor y varios lectores.</span><span class="sxs-lookup"><span data-stu-id="4919e-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 <span data-ttu-id="4919e-127">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="4919e-127">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)</span></span>  
 <span data-ttu-id="4919e-128">Describe los objetos <xref:System.Threading.Semaphore> y explica cómo usarlos para controlar el acceso a recursos limitados.</span><span class="sxs-lookup"><span data-stu-id="4919e-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 <span data-ttu-id="4919e-129">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)</span><span class="sxs-lookup"><span data-stu-id="4919e-129">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)</span></span>  
 <span data-ttu-id="4919e-130">Compara las características de las clases de .NET Framework proporcionadas para bloquear y sincronizar los subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="4919e-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 <span data-ttu-id="4919e-131">[Barrier](../../../docs/standard/threading/barrier.md) (Barrera)</span><span class="sxs-lookup"><span data-stu-id="4919e-131">[Barrier](../../../docs/standard/threading/barrier.md)</span></span>  
 <span data-ttu-id="4919e-132">Describe los objetos <xref:System.Threading.Barrier> que implementan el modelo de barrera para coordinar los subprocesos en las operaciones por fases.</span><span class="sxs-lookup"><span data-stu-id="4919e-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="4919e-133">SpinLock</span><span class="sxs-lookup"><span data-stu-id="4919e-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="4919e-134">Describe <xref:System.Threading.SpinLock>, una alternativa ligera a la clase Monitor para algunos escenarios de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="4919e-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="4919e-135">SpinWait</span><span class="sxs-lookup"><span data-stu-id="4919e-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="4919e-136">Describe <xref:System.Threading.SpinWait>, un primitivo de sincronización de bajo nivel que realiza giros de ocupado antes de iniciar una espera basada en kernel.</span><span class="sxs-lookup"><span data-stu-id="4919e-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4919e-137">Referencia</span><span class="sxs-lookup"><span data-stu-id="4919e-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="4919e-138">Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="4919e-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="4919e-139">Habilita tareas en segundo plano que interactúan con la interfaz de usuario, y se comunican mediante eventos generados en el subproceso de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4919e-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4919e-140">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4919e-140">Related Sections</span></span>  
 <span data-ttu-id="4919e-141">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)</span><span class="sxs-lookup"><span data-stu-id="4919e-141">[Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md)</span></span>  
 <span data-ttu-id="4919e-142">Describe cómo los puertos de finalización asincrónica de E/S usan el grupo de subprocesos para solicitar procesamiento solo cuando finaliza una operación de entrada/salida.</span><span class="sxs-lookup"><span data-stu-id="4919e-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="4919e-143">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="4919e-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="4919e-144">Describe el enfoque recomendado para la programación multiproceso en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4919e-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
