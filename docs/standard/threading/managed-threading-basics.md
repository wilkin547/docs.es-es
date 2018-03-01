---
title: "Principios básicos del subprocesamiento administrado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 035834959aa5f9340727327b22cae93b3f21b056
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="f7dbe-102">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="f7dbe-102">Managed Threading Basics</span></span>
<span data-ttu-id="f7dbe-103">Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subproceso administrado así como para explicar algunas características básicas.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="f7dbe-104">Para obtener información sobre las clases que proporcionan características adicionales, vea [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md) e [Información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="f7dbe-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="f7dbe-105">En el resto de los temas de esta sección se tratan cuestiones más avanzadas, incluida la interacción del subproceso administrado con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7dbe-106">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="f7dbe-107">Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).</span><span class="sxs-lookup"><span data-stu-id="f7dbe-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7dbe-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f7dbe-108">In This Section</span></span>  
 [<span data-ttu-id="f7dbe-109">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="f7dbe-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="f7dbe-110">Se explican las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="f7dbe-111">Excepciones en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="f7dbe-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="f7dbe-112">Se describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="f7dbe-113">Sincronizar datos para subprocesamiento múltiple</span><span class="sxs-lookup"><span data-stu-id="f7dbe-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="f7dbe-114">Se describen las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="f7dbe-115">Estados de subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="f7dbe-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="f7dbe-116">Se describen los estados de subprocesos básicos y se explica cómo detectar si un subproceso está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="f7dbe-117">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="f7dbe-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="f7dbe-118">Se explican las diferencias entre los subprocesos en primer y segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="f7dbe-119">Subprocesamiento administrado y no administrado en Windows</span><span class="sxs-lookup"><span data-stu-id="f7dbe-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="f7dbe-120">Se describe la relación entre subprocesos administrados y no administrados, se enumeran los administrados equivalentes para las API de subprocesos de Windows y se describe la interacción entre apartamentos COM y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="f7dbe-121">Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7dbe-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="f7dbe-122">Se describe la recolección de elementos no utilizados y la suspensión del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="f7dbe-123">Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos</span><span class="sxs-lookup"><span data-stu-id="f7dbe-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="f7dbe-124">Se describen los mecanismos de almacenamiento relacionados con subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="f7dbe-125">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="f7dbe-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="f7dbe-126">Se describe cómo se pueden cancelar las operaciones asincrónicas o las operaciones sincrónicas de larga ejecución con un token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f7dbe-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="f7dbe-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="f7dbe-128">Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="f7dbe-129">Proporciona una manera segura de implementar multithreading junto con objetos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f7dbe-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f7dbe-130">Related Sections</span></span>  
 <span data-ttu-id="f7dbe-131">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)</span><span class="sxs-lookup"><span data-stu-id="f7dbe-131">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)</span></span>  
 <span data-ttu-id="f7dbe-132">Se describen las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="f7dbe-133">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="f7dbe-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="f7dbe-134">Se describen los problemas comunes con multithreading y las estrategias para evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="f7dbe-135">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="f7dbe-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="f7dbe-136">Describe la biblioteca TPL y PLINQ, que simplifican significativamente el trabajo de crear aplicaciones de .NET Framework asincrónicas y multiproceso.</span><span class="sxs-lookup"><span data-stu-id="f7dbe-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
