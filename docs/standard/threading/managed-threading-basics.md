---
title: Principios básicos del subprocesamiento administrado
description: Vea vínculos a otros artículos de subprocesamiento administrado, que tratan temas tales como las excepciones, la sincronización de datos, los subprocesos en primer plano y en segundo plano, el almacenamiento local, etc.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET], multiple threads
- threading [.NET], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: ca3073cca9887265b4bacb4f8dfeb01203f82621
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189139"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="d4d42-103">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="d4d42-103">Managed threading basics</span></span>

<span data-ttu-id="d4d42-104">Los cinco primeros artículos de esta sección están diseñados para ayudarle a determinar cuándo usar un subproceso administrado y para explicar algunas características básicas.</span><span class="sxs-lookup"><span data-stu-id="d4d42-104">The first five articles of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="d4d42-105">Para obtener información sobre las clases que proporcionan características adicionales, vea [Objetos y características de subprocesos](threading-objects-and-features.md) e [Información general sobre los primitivos de sincronización](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="d4d42-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="d4d42-106">En el resto de los artículos de esta sección se describen temas más avanzados, incluida la interacción del subproceso administrado con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="d4d42-106">The remaining articles in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4d42-107">A partir de .NET Framework 4, la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso.</span><span class="sxs-lookup"><span data-stu-id="d4d42-107">Starting with .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="d4d42-108">Para más información, consulte [Programación en paralelo](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="d4d42-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4d42-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d4d42-109">In this section</span></span>

 [<span data-ttu-id="d4d42-110">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="d4d42-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="d4d42-111">Se explican las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d4d42-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="d4d42-112">Excepciones en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="d4d42-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="d4d42-113">Se describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET, en concreto las situaciones que pueden provocar la finalización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d4d42-113">Describes the behavior of unhandled exceptions in threads for different versions of .NET, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="d4d42-114">Sincronizar datos para subprocesamiento múltiple</span><span class="sxs-lookup"><span data-stu-id="d4d42-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="d4d42-115">Se describen las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d4d42-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="d4d42-116">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="d4d42-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="d4d42-117">Se explican las diferencias entre los subprocesos en primer y segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d4d42-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="d4d42-118">Subprocesamiento administrado y no administrado en Windows</span><span class="sxs-lookup"><span data-stu-id="d4d42-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="d4d42-119">Se describe la relación entre subprocesos administrados y no administrados, se enumeran los administrados equivalentes para las API de subprocesos de Windows y se describe la interacción entre apartamentos COM y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="d4d42-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="d4d42-120">Almacenamiento local para el subproceso: Campos estáticos relacionados con subprocesos y ranuras de datos</span><span class="sxs-lookup"><span data-stu-id="d4d42-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="d4d42-121">Se describen los mecanismos de almacenamiento relacionados con subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d4d42-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4d42-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="d4d42-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="d4d42-123">Proporciona documentación de referencia para la clase **Thread** , que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="d4d42-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="d4d42-124">Proporciona una manera segura de implementar multithreading junto con objetos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d4d42-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4d42-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d4d42-125">Related sections</span></span>

 [<span data-ttu-id="d4d42-126">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="d4d42-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="d4d42-127">Se describen las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d4d42-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="d4d42-128">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="d4d42-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="d4d42-129">Se describen los problemas comunes con multithreading y las estrategias para evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="d4d42-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="d4d42-130">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="d4d42-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="d4d42-131">Se describe la biblioteca TPL y PLINQ, que simplifican considerablemente el trabajo de crear aplicaciones de .NET asincrónicas y multiproceso.</span><span class="sxs-lookup"><span data-stu-id="d4d42-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET applications.</span></span>
