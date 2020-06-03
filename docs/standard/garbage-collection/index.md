---
title: Recolección de elementos no utilizados de .NET
ms.date: 04/21/2020
ms.technology: dotnet-standard
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
ms.openlocfilehash: ef7e078c6ef2f0b4081c49aa0db09316e79f0702
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286059"
---
# <a name="garbage-collection"></a><span data-ttu-id="c70df-102">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="c70df-102">Garbage collection</span></span>

<span data-ttu-id="c70df-103">El recolector de elementos no utilizados de .NET administra la asignación y liberación de la memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c70df-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="c70df-104">Cada vez que se crea un objeto nuevo, el Common Language Runtime asigna al objeto memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="c70df-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="c70df-105">Siempre que haya espacio de direcciones disponible en el montón nativo, el motor en tiempo de ejecución continúa asignando espacio a los objetos nuevos.</span><span class="sxs-lookup"><span data-stu-id="c70df-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="c70df-106">No obstante, la memoria no es infinita.</span><span class="sxs-lookup"><span data-stu-id="c70df-106">However, memory is not infinite.</span></span> <span data-ttu-id="c70df-107">En ocasiones, el recolector de elementos no utilizados debe realizar una recolección para liberar alguna memoria.</span><span class="sxs-lookup"><span data-stu-id="c70df-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="c70df-108">El motor de optimización del recolector de elementos no utilizados determina cuál es el mejor momento para realizar una recolección, según las asignaciones que se estén realizando.</span><span class="sxs-lookup"><span data-stu-id="c70df-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="c70df-109">Cuando el recolector de elementos no utilizados realiza una recolección, comprueba si en el montón administrado hay objetos que la aplicación ya no utiliza y realiza las operaciones necesarias para reclamar su memoria.</span><span class="sxs-lookup"><span data-stu-id="c70df-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c70df-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c70df-110">In this section</span></span>
  
|<span data-ttu-id="c70df-111">Title</span><span class="sxs-lookup"><span data-stu-id="c70df-111">Title</span></span>|<span data-ttu-id="c70df-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c70df-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c70df-113">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="c70df-113">Fundamentals of garbage collection</span></span>](fundamentals.md)|<span data-ttu-id="c70df-114">Describe cómo funciona la recolección de elementos no utilizados, cómo se asignan los objetos en el montón administrado y otros conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="c70df-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="c70df-115">Recolección de elementos no utilizados de estación de trabajo y de servidor</span><span class="sxs-lookup"><span data-stu-id="c70df-115">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="c70df-116">Describe las diferencias entre la recolección de elementos no utilizados para aplicaciones cliente y la recolección de elementos no utilizados del servidor para aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="c70df-116">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="c70df-117">Recolección de elementos no utilizados en segundo plano</span><span class="sxs-lookup"><span data-stu-id="c70df-117">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="c70df-118">Describe la recolección de elementos no utilizados en segundo plano, que es la recolección de objetos de generación 0 y 1 mientras se lleva a cabo la recolección de generación 2.</span><span class="sxs-lookup"><span data-stu-id="c70df-118">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="c70df-119">El montón de objetos grandes</span><span class="sxs-lookup"><span data-stu-id="c70df-119">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="c70df-120">Describe el montón de objetos grandes y cómo se lleva a cabo la recolección de elementos no utilizados de los objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="c70df-120">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="c70df-121">Recolección de elementos no utilizados y rendimiento</span><span class="sxs-lookup"><span data-stu-id="c70df-121">Garbage collection and performance</span></span>](performance.md)|<span data-ttu-id="c70df-122">Describe las comprobaciones de rendimiento que se pueden utilizar para diagnosticar los problemas con la recolección de elementos no utilizados y los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c70df-122">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="c70df-123">Colecciones inducidas</span><span class="sxs-lookup"><span data-stu-id="c70df-123">Induced collections</span></span>](induced.md)|<span data-ttu-id="c70df-124">Describe cómo hacer que se produzca una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c70df-124">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="c70df-125">Modos de latencia</span><span class="sxs-lookup"><span data-stu-id="c70df-125">Latency modes</span></span>](latency.md)|<span data-ttu-id="c70df-126">Describe los modos que determinan la tendencia a la intrusión de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c70df-126">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="c70df-127">Optimización de hospedaje web compartido</span><span class="sxs-lookup"><span data-stu-id="c70df-127">Optimization for shared web hosting</span></span>](optimization-for-shared-web-hosting.md)|<span data-ttu-id="c70df-128">Describe cómo optimizar la recolección de elementos no utilizados en servidores compartidos entre varios sitios web pequeños.</span><span class="sxs-lookup"><span data-stu-id="c70df-128">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="c70df-129">Notificaciones de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="c70df-129">Garbage collection notifications</span></span>](notifications.md)|<span data-ttu-id="c70df-130">Describe cómo se determina cuándo una recolección de elementos no utilizados completa está próxima y cuándo se ha completado.</span><span class="sxs-lookup"><span data-stu-id="c70df-130">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="c70df-131">Supervisión de recursos de dominio de aplicación</span><span class="sxs-lookup"><span data-stu-id="c70df-131">Application domain resource monitoring</span></span>](app-domain-resource-monitoring.md)|<span data-ttu-id="c70df-132">Describe cómo supervisar el uso de la CPU y la memoria por un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c70df-132">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="c70df-133">Referencias débiles</span><span class="sxs-lookup"><span data-stu-id="c70df-133">Weak references</span></span>](weak-references.md)|<span data-ttu-id="c70df-134">Describe las características que permiten al recolector de elementos no utilizados recoger un objeto y, mientras tanto, permitir que la aplicación tenga acceso a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="c70df-134">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="c70df-135">Referencia</span><span class="sxs-lookup"><span data-stu-id="c70df-135">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="c70df-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c70df-136">See also</span></span>

- [<span data-ttu-id="c70df-137">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="c70df-137">Clean up unmanaged resources</span></span>](unmanaged.md)
