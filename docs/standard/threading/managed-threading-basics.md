---
title: Principios básicos del subprocesamiento administrado
description: Vea vínculos a otros artículos de subprocesamiento administrado, que tratan temas tales como las excepciones, la sincronización de datos, los subprocesos en primer plano y en segundo plano, el almacenamiento local, etc.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
ms.openlocfilehash: d4a4ceabf29bd0f6f537e59ba477f9da686b1ef5
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769098"
---
# <a name="managed-threading-basics"></a><span data-ttu-id="08481-103">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="08481-103">Managed threading basics</span></span>

<span data-ttu-id="08481-104">Los cinco primeros temas de esta sección están diseñados para ayudarle a determinar cuándo se debe utilizar un subproceso administrado así como para explicar algunas características básicas.</span><span class="sxs-lookup"><span data-stu-id="08481-104">The first five topics of this section are designed to help you determine when to use managed threading and to explain some basic features.</span></span> <span data-ttu-id="08481-105">Para obtener información sobre las clases que proporcionan características adicionales, vea [Objetos y características de subprocesos](threading-objects-and-features.md) e [Información general sobre los primitivos de sincronización](overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="08481-105">For information on classes that provide additional features, see [Threading Objects and Features](threading-objects-and-features.md) and [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="08481-106">En el resto de los temas de esta sección se tratan cuestiones más avanzadas, incluida la interacción del subproceso administrado con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="08481-106">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08481-107">En .NET Framework 4, la biblioteca TPL y PLINQ proporcionan API para el paralelismo de tareas y datos en programas multiproceso.</span><span class="sxs-lookup"><span data-stu-id="08481-107">In the .NET Framework 4, the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="08481-108">Para más información, consulte [Programación en paralelo](../parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="08481-108">For more information, see [Parallel Programming](../parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08481-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="08481-109">In this section</span></span>

 [<span data-ttu-id="08481-110">Subprocesos y subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="08481-110">Threads and Threading</span></span>](threads-and-threading.md)  
 <span data-ttu-id="08481-111">Se explican las ventajas y desventajas de varios subprocesos y se describen los escenarios en los que puede crear subprocesos o utilizar subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="08481-111">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="08481-112">Excepciones en subprocesos administrados</span><span class="sxs-lookup"><span data-stu-id="08481-112">Exceptions in Managed Threads</span></span>](exceptions-in-managed-threads.md)  
 <span data-ttu-id="08481-113">Se describe el comportamiento de las excepciones no controladas en subprocesos de distintas versiones de .NET Framework, en particular las situaciones que pueden provocar la finalización de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="08481-113">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="08481-114">Sincronizar datos para subprocesamiento múltiple</span><span class="sxs-lookup"><span data-stu-id="08481-114">Synchronizing Data for Multithreading</span></span>](synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="08481-115">Se describen las estrategias de sincronización de datos en las clases que se utilizarán con varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="08481-115">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="08481-116">Subprocesos de primer y segundo plano</span><span class="sxs-lookup"><span data-stu-id="08481-116">Foreground and Background Threads</span></span>](foreground-and-background-threads.md)  
 <span data-ttu-id="08481-117">Se explican las diferencias entre los subprocesos en primer y segundo plano.</span><span class="sxs-lookup"><span data-stu-id="08481-117">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="08481-118">Subprocesamiento administrado y no administrado en Windows</span><span class="sxs-lookup"><span data-stu-id="08481-118">Managed and Unmanaged Threading in Windows</span></span>](managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="08481-119">Se describe la relación entre subprocesos administrados y no administrados, se enumeran los administrados equivalentes para las API de subprocesos de Windows y se describe la interacción entre apartamentos COM y subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="08481-119">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="08481-120">Almacenamiento local para el subproceso: Campos estáticos relacionados con subprocesos y ranuras de datos</span><span class="sxs-lookup"><span data-stu-id="08481-120">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="08481-121">Se describen los mecanismos de almacenamiento relacionados con subprocesos.</span><span class="sxs-lookup"><span data-stu-id="08481-121">Describes thread-relative storage mechanisms.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="08481-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="08481-122">Reference</span></span>

 <xref:System.Threading.Thread>  
 <span data-ttu-id="08481-123">Proporciona documentación de referencia para la clase **Thread**, que representa un subproceso administrado, independientemente de que provenga de código no administrado o que se creara en una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="08481-123">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="08481-124">Proporciona una manera segura de implementar multithreading junto con objetos de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="08481-124">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08481-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="08481-125">Related sections</span></span>

 [<span data-ttu-id="08481-126">Información general sobre las primitivas de sincronización</span><span class="sxs-lookup"><span data-stu-id="08481-126">Overview of Synchronization Primitives</span></span>](overview-of-synchronization-primitives.md)  
 <span data-ttu-id="08481-127">Se describen las clases administradas utilizadas para sincronizar las actividades de varios subprocesos.</span><span class="sxs-lookup"><span data-stu-id="08481-127">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="08481-128">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="08481-128">Managed Threading Best Practices</span></span>](managed-threading-best-practices.md)  
 <span data-ttu-id="08481-129">Se describen los problemas comunes con multithreading y las estrategias para evitar problemas.</span><span class="sxs-lookup"><span data-stu-id="08481-129">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="08481-130">Programación en paralelo</span><span class="sxs-lookup"><span data-stu-id="08481-130">Parallel Programming</span></span>](../parallel-programming/index.md)  
 <span data-ttu-id="08481-131">Describe la biblioteca TPL y PLINQ, que simplifican significativamente el trabajo de crear aplicaciones de .NET Framework asincrónicas y multiproceso.</span><span class="sxs-lookup"><span data-stu-id="08481-131">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
