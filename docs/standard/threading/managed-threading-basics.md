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
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="612fb-102">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="612fb-102">Managed Threading Basics</span></span>
<span data-ttu-id="612fb-103">Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subprocesamiento administrado así como para explicar algunas características básicas.</span><span class="sxs-lookup"><span data-stu-id="612fb-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="612fb-104">Para obtener información sobre las clases que proporcionan características adicionales, consulte [objetos y características](../../../docs/standard/threading/threading-objects-and-features.md) y [información general sobre los primitivos de sincronización](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="612fb-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="612fb-105">El resto de los temas de esta sección se tratan temas más avanzados, incluida la interacción del subprocesamiento administrado con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="612fb-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612fb-106">En el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y los datos en programas multiproceso.</span><span class="sxs-lookup"><span data-stu-id="612fb-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="612fb-107">Para más información, consulte [Parallel Programming](../../../docs/standard/parallel-programming/index.md) (Programación en paralelo).</span><span class="sxs-lookup"><span data-stu-id="612fb-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="612fb-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="612fb-108">In This Section</span></span>  
 [<span data-ttu-id="612fb-109">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="612fb-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="612fb-110">Explica las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="612fb-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="612fb-111">Excepciones en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="612fb-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="612fb-112">Describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="612fb-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="612fb-113">Sincronizar datos para subprocesamiento múltiple</span><span class="sxs-lookup"><span data-stu-id="612fb-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="612fb-114">Describe las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="612fb-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="612fb-115">Estados de subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="612fb-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="612fb-116">Describe los Estados de subprocesos básicos y explica cómo detectar si un subproceso se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="612fb-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="612fb-117">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="612fb-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="612fb-118">Explica las diferencias entre los subprocesos de primer plano y fondo.</span><span class="sxs-lookup"><span data-stu-id="612fb-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="612fb-119">Subprocesamiento administrado y no administrado en Windows</span><span class="sxs-lookup"><span data-stu-id="612fb-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="612fb-120">Describe la relación entre subprocesos administrados y no administrados, enumera los administrados equivalentes para las API de subprocesamiento de Windows y describe la interacción entre apartamentos COM y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="612fb-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="612fb-121">Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad</span><span class="sxs-lookup"><span data-stu-id="612fb-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="612fb-122">Describe la colección de elementos no utilizados y de suspensión del subproceso.</span><span class="sxs-lookup"><span data-stu-id="612fb-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="612fb-123">Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos</span><span class="sxs-lookup"><span data-stu-id="612fb-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="612fb-124">Describe los mecanismos de almacenamiento relacionados con subprocesos.</span><span class="sxs-lookup"><span data-stu-id="612fb-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="612fb-125">Cancelación en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="612fb-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="612fb-126">Describe las operaciones sincrónicas asincrónicas o de ejecución prolongada puede cancelarse mediante el uso de un token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="612fb-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="612fb-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="612fb-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="612fb-128">Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="612fb-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="612fb-129">Proporciona una manera segura para implementar multithreading junto con objetos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="612fb-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="612fb-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="612fb-130">Related Sections</span></span>  
 <span data-ttu-id="612fb-131">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización)</span><span class="sxs-lookup"><span data-stu-id="612fb-131">[Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)</span></span>  
 <span data-ttu-id="612fb-132">Describe las clases administradas que se usa para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="612fb-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="612fb-133">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="612fb-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="612fb-134">Describe los problemas comunes con subprocesamiento múltiple y estrategias para evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="612fb-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="612fb-135">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="612fb-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="612fb-136">Describe las Task Parallel Library y PLINQ, que simplifican considerablemente el trabajo de creación de aplicaciones de .NET Framework asincrónicas y multiproceso.</span><span class="sxs-lookup"><span data-stu-id="612fb-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
