---
title: "recolección de elementos no utilizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: "36"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1636bf1cf047e7505be7567f5b5061df25d899c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection"></a><span data-ttu-id="0fb0c-102">recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="0fb0c-102">Garbage Collection</span></span>
<span data-ttu-id="0fb0c-103">El recolector de elementos no utilizados de .NET administra la asignación y liberación de la memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="0fb0c-104">Cada vez que se crea un objeto nuevo, el Common Language Runtime asigna al objeto memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="0fb0c-105">Siempre que haya espacio de direcciones disponible en el montón nativo, el motor en tiempo de ejecución continúa asignando espacio a los objetos nuevos.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="0fb0c-106">No obstante, la memoria no es infinita.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-106">However, memory is not infinite.</span></span> <span data-ttu-id="0fb0c-107">En ocasiones, el recolector de elementos no utilizados debe realizar una recolección para liberar alguna memoria.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="0fb0c-108">El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección, según las asignaciones que se estén realizando.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="0fb0c-109">Cuando el recolector de elementos no utilizados realiza una recolección, comprueba si en el montón administrado hay objetos que la aplicación ya no utiliza y realiza las operaciones necesarias para reclamar su memoria.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="0fb0c-110">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0fb0c-110">Related Topics</span></span>  
  
|<span data-ttu-id="0fb0c-111">Título</span><span class="sxs-lookup"><span data-stu-id="0fb0c-111">Title</span></span>|<span data-ttu-id="0fb0c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fb0c-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0fb0c-113">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="0fb0c-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="0fb0c-114">Describe cómo funciona la recolección de elementos no utilizados, cómo se asignan los objetos en el montón administrado y otros conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="0fb0c-115">Recolección de elementos no utilizados y rendimiento</span><span class="sxs-lookup"><span data-stu-id="0fb0c-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="0fb0c-116">Describe las comprobaciones de rendimiento que se pueden utilizar para diagnosticar los problemas con la recolección de elementos no utilizados y los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="0fb0c-117">Colecciones inducidas</span><span class="sxs-lookup"><span data-stu-id="0fb0c-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="0fb0c-118">Describe cómo hacer que se produzca una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="0fb0c-119">Modos de latencia</span><span class="sxs-lookup"><span data-stu-id="0fb0c-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="0fb0c-120">Describe los modos que determinan la tendencia a la intrusión de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="0fb0c-121">Optimización de hospedaje web compartido</span><span class="sxs-lookup"><span data-stu-id="0fb0c-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="0fb0c-122">Describe cómo optimizar la recolección de elementos no utilizados en servidores compartidos entre varios sitios web pequeños.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="0fb0c-123">Notificaciones de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="0fb0c-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="0fb0c-124">Describe cómo se determina cuándo una recolección de elementos no utilizados completa está próxima y cuándo se ha completado.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="0fb0c-125">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="0fb0c-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="0fb0c-126">Describe cómo supervisar el uso de la CPU y la memoria por un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="0fb0c-127">Referencias débiles</span><span class="sxs-lookup"><span data-stu-id="0fb0c-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="0fb0c-128">Describe las características que permiten al recolector de elementos no utilizados recoger un objeto y, mientras tanto, permitir que la aplicación tenga acceso a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="0fb0c-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="0fb0c-129">Referencia</span><span class="sxs-lookup"><span data-stu-id="0fb0c-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="0fb0c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fb0c-130">See Also</span></span>  
 [<span data-ttu-id="0fb0c-131">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="0fb0c-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
