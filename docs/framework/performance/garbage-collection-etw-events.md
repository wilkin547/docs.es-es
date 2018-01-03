---
title: "Eventos ETW de recolección de elementos no utilizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 133d48baa9613ea698b6d6a21f0dfe88a798859c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="ab351-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="ab351-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="ab351-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="ab351-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="ab351-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="ab351-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="ab351-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="ab351-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="ab351-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="ab351-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="ab351-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="ab351-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="ab351-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="ab351-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="ab351-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="ab351-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="ab351-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="ab351-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="ab351-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="ab351-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="ab351-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="ab351-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="ab351-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="ab351-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="ab351-122">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="ab351-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="ab351-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-123">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-128">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-128">Event</span></span>|<span data-ttu-id="ab351-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-129">Event ID</span></span>|<span data-ttu-id="ab351-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="ab351-131">1</span><span class="sxs-lookup"><span data-stu-id="ab351-131">1</span></span>|<span data-ttu-id="ab351-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="ab351-133">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-134">Field name</span></span>|<span data-ttu-id="ab351-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-135">Data type</span></span>|<span data-ttu-id="ab351-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-137">Recuento</span><span class="sxs-lookup"><span data-stu-id="ab351-137">Count</span></span>|<span data-ttu-id="ab351-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-138">win:UInt32</span></span>|<span data-ttu-id="ab351-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="ab351-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="ab351-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="ab351-140">Depth</span></span>|<span data-ttu-id="ab351-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-141">win:UInt32</span></span>|<span data-ttu-id="ab351-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="ab351-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="ab351-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="ab351-143">Reason</span></span>|<span data-ttu-id="ab351-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-144">win:UInt32</span></span>|<span data-ttu-id="ab351-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="ab351-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="ab351-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="ab351-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="ab351-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="ab351-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="ab351-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="ab351-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="ab351-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="ab351-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="ab351-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ab351-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="ab351-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="ab351-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="ab351-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="ab351-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="ab351-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ab351-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="ab351-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab351-154">Type</span></span>|<span data-ttu-id="ab351-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-155">win:UInt32</span></span>|<span data-ttu-id="ab351-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ab351-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="ab351-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ab351-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="ab351-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ab351-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="ab351-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-159">ClrInstanceID</span></span>|<span data-ttu-id="ab351-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-160">win:UInt16</span></span>|<span data-ttu-id="ab351-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="ab351-163">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="ab351-164">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-165">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-165">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-166">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-169">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-170">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-170">Event</span></span>|<span data-ttu-id="ab351-171">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-171">Event ID</span></span>|<span data-ttu-id="ab351-172">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="ab351-173">2</span><span class="sxs-lookup"><span data-stu-id="ab351-173">2</span></span>|<span data-ttu-id="ab351-174">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="ab351-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="ab351-175">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-176">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-176">Field name</span></span>|<span data-ttu-id="ab351-177">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-177">Data type</span></span>|<span data-ttu-id="ab351-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-179">Recuento</span><span class="sxs-lookup"><span data-stu-id="ab351-179">Count</span></span>|<span data-ttu-id="ab351-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-180">win:UInt32</span></span>|<span data-ttu-id="ab351-181">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="ab351-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="ab351-182">Profundidad</span><span class="sxs-lookup"><span data-stu-id="ab351-182">Depth</span></span>|<span data-ttu-id="ab351-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-183">win:UInt32</span></span>|<span data-ttu-id="ab351-184">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="ab351-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="ab351-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-185">ClrInstanceID</span></span>|<span data-ttu-id="ab351-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-186">win:UInt16</span></span>|<span data-ttu-id="ab351-187">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="ab351-189">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="ab351-190">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-191">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-191">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-192">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-195">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-196">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-196">Event</span></span>|<span data-ttu-id="ab351-197">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-197">Event ID</span></span>|<span data-ttu-id="ab351-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="ab351-199">4</span><span class="sxs-lookup"><span data-stu-id="ab351-199">4</span></span>|<span data-ttu-id="ab351-200">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="ab351-201">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-202">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-202">Field name</span></span>|<span data-ttu-id="ab351-203">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-203">Data type</span></span>|<span data-ttu-id="ab351-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="ab351-205">GenerationSize0</span></span>|<span data-ttu-id="ab351-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-206">win:UInt64</span></span>|<span data-ttu-id="ab351-207">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="ab351-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="ab351-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="ab351-208">TotalPromotedSize0</span></span>|<span data-ttu-id="ab351-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-209">win:UInt64</span></span>|<span data-ttu-id="ab351-210">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="ab351-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="ab351-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="ab351-211">GenerationSize1</span></span>|<span data-ttu-id="ab351-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-212">win:UInt64</span></span>|<span data-ttu-id="ab351-213">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="ab351-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="ab351-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="ab351-214">TotalPromotedSize1</span></span>|<span data-ttu-id="ab351-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-215">win:UInt64</span></span>|<span data-ttu-id="ab351-216">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="ab351-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="ab351-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="ab351-217">GenerationSize2</span></span>|<span data-ttu-id="ab351-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-218">win:UInt64</span></span>|<span data-ttu-id="ab351-219">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="ab351-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="ab351-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="ab351-220">TotalPromotedSize2</span></span>|<span data-ttu-id="ab351-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-221">win:UInt64</span></span>|<span data-ttu-id="ab351-222">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="ab351-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="ab351-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="ab351-223">GenerationSize3</span></span>|<span data-ttu-id="ab351-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-224">win:UInt64</span></span>|<span data-ttu-id="ab351-225">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ab351-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="ab351-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="ab351-226">TotalPromotedSize3</span></span>|<span data-ttu-id="ab351-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-227">win:UInt64</span></span>|<span data-ttu-id="ab351-228">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="ab351-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="ab351-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="ab351-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="ab351-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-230">win:UInt64</span></span>|<span data-ttu-id="ab351-231">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="ab351-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="ab351-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="ab351-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="ab351-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-233">win:UInt64</span></span>|<span data-ttu-id="ab351-234">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="ab351-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="ab351-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="ab351-235">PinnedObjectCount</span></span>|<span data-ttu-id="ab351-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-236">win:UInt32</span></span>|<span data-ttu-id="ab351-237">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="ab351-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="ab351-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="ab351-238">SinkBlockCount</span></span>|<span data-ttu-id="ab351-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-239">win:UInt32</span></span>|<span data-ttu-id="ab351-240">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="ab351-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="ab351-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="ab351-241">GCHandleCount</span></span>|<span data-ttu-id="ab351-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-242">win:UInt32</span></span>|<span data-ttu-id="ab351-243">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="ab351-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="ab351-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-244">ClrInstanceID</span></span>|<span data-ttu-id="ab351-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-245">win:UInt16</span></span>|<span data-ttu-id="ab351-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-247">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="ab351-248">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="ab351-249">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-250">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-250">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-251">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-254">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-255">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-255">Event</span></span>|<span data-ttu-id="ab351-256">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-256">Event ID</span></span>|<span data-ttu-id="ab351-257">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="ab351-258">5</span><span class="sxs-lookup"><span data-stu-id="ab351-258">5</span></span>|<span data-ttu-id="ab351-259">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="ab351-260">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="ab351-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="ab351-261">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-262">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-262">Field name</span></span>|<span data-ttu-id="ab351-263">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-263">Data type</span></span>|<span data-ttu-id="ab351-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-265">Dirección</span><span class="sxs-lookup"><span data-stu-id="ab351-265">Address</span></span>|<span data-ttu-id="ab351-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-266">win:UInt64</span></span>|<span data-ttu-id="ab351-267">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="ab351-267">The address of the segment.</span></span>|  
|<span data-ttu-id="ab351-268">Tamaño</span><span class="sxs-lookup"><span data-stu-id="ab351-268">Size</span></span>|<span data-ttu-id="ab351-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-269">win:UInt64</span></span>|<span data-ttu-id="ab351-270">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="ab351-270">The size of the segment.</span></span>|  
|<span data-ttu-id="ab351-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab351-271">Type</span></span>|<span data-ttu-id="ab351-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-272">win:UInt32</span></span>|<span data-ttu-id="ab351-273">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="ab351-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="ab351-274">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ab351-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="ab351-275">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ab351-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="ab351-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-276">ClrInstanceID</span></span>|<span data-ttu-id="ab351-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-277">win:UInt16</span></span>|<span data-ttu-id="ab351-278">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="ab351-279">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="ab351-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="ab351-280">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="ab351-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="ab351-281">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="ab351-282">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="ab351-283">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-284">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-284">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-285">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-288">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-289">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-289">Event</span></span>|<span data-ttu-id="ab351-290">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-290">Event ID</span></span>|<span data-ttu-id="ab351-291">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="ab351-292">6</span><span class="sxs-lookup"><span data-stu-id="ab351-292">6</span></span>|<span data-ttu-id="ab351-293">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="ab351-294">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-295">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-295">Field name</span></span>|<span data-ttu-id="ab351-296">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-296">Data type</span></span>|<span data-ttu-id="ab351-297">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-298">Dirección</span><span class="sxs-lookup"><span data-stu-id="ab351-298">Address</span></span>|<span data-ttu-id="ab351-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-299">win:UInt64</span></span>|<span data-ttu-id="ab351-300">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="ab351-300">The address of the segment.</span></span>|  
|<span data-ttu-id="ab351-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-301">ClrInstanceID</span></span>|<span data-ttu-id="ab351-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-302">win:UInt16</span></span>|<span data-ttu-id="ab351-303">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-304">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="ab351-305">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="ab351-306">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-307">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-307">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-308">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-311">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-312">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-312">Event</span></span>|<span data-ttu-id="ab351-313">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-313">Event ID</span></span>|<span data-ttu-id="ab351-314">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="ab351-315">7</span><span class="sxs-lookup"><span data-stu-id="ab351-315">7</span></span>|<span data-ttu-id="ab351-316">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ab351-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="ab351-317">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-317">No event data.</span></span>  
  
 [<span data-ttu-id="ab351-318">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="ab351-319">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="ab351-320">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-321">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-321">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-322">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-325">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-326">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-326">Event</span></span>|<span data-ttu-id="ab351-327">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-327">Event Id</span></span>|<span data-ttu-id="ab351-328">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="ab351-329">3</span><span class="sxs-lookup"><span data-stu-id="ab351-329">3</span></span>|<span data-ttu-id="ab351-330">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ab351-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="ab351-331">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-331">No event data.</span></span>  
  
 [<span data-ttu-id="ab351-332">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="ab351-333">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="ab351-334">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-335">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-335">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-336">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-339">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-340">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-340">Event</span></span>|<span data-ttu-id="ab351-341">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-341">Event ID</span></span>|<span data-ttu-id="ab351-342">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="ab351-343">9</span><span class="sxs-lookup"><span data-stu-id="ab351-343">9</span></span>|<span data-ttu-id="ab351-344">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="ab351-345">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-346">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-346">Field name</span></span>|<span data-ttu-id="ab351-347">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-347">Data type</span></span>|<span data-ttu-id="ab351-348">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="ab351-349">Reason</span></span>|<span data-ttu-id="ab351-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-350">win:UInt16</span></span>|<span data-ttu-id="ab351-351">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="ab351-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="ab351-352">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="ab351-353">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab351-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="ab351-354">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="ab351-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="ab351-355">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="ab351-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="ab351-356">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="ab351-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="ab351-357">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="ab351-358">Recuento</span><span class="sxs-lookup"><span data-stu-id="ab351-358">Count</span></span>|<span data-ttu-id="ab351-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-359">win:UInt32</span></span>|<span data-ttu-id="ab351-360">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="ab351-360">The GC count at the time.</span></span> <span data-ttu-id="ab351-361">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="ab351-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-362">ClrInstanceID</span></span>|<span data-ttu-id="ab351-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-363">win:UInt16</span></span>|<span data-ttu-id="ab351-364">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-365">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="ab351-366">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="ab351-367">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="ab351-368">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-368">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-369">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-372">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="ab351-373">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-373">Event</span></span>|<span data-ttu-id="ab351-374">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-374">Event ID</span></span>|<span data-ttu-id="ab351-375">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="ab351-376">8</span><span class="sxs-lookup"><span data-stu-id="ab351-376">8</span></span>|<span data-ttu-id="ab351-377">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab351-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="ab351-378">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-378">No event data.</span></span>  
  
 [<span data-ttu-id="ab351-379">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="ab351-380">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="ab351-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="ab351-381">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-382">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-382">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-383">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-386">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-387">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-387">Event</span></span>|<span data-ttu-id="ab351-388">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-388">Event ID</span></span>|<span data-ttu-id="ab351-389">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="ab351-390">10</span><span class="sxs-lookup"><span data-stu-id="ab351-390">10</span></span>|<span data-ttu-id="ab351-391">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="ab351-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="ab351-392">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-393">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-393">Field name</span></span>|<span data-ttu-id="ab351-394">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-394">Data type</span></span>|<span data-ttu-id="ab351-395">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="ab351-396">AllocationAmount</span></span>|<span data-ttu-id="ab351-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-397">win:UInt32</span></span>|<span data-ttu-id="ab351-398">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ab351-398">The allocation size, in bytes.</span></span> <span data-ttu-id="ab351-399">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="ab351-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="ab351-400">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="ab351-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="ab351-401">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="ab351-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="ab351-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="ab351-402">AllocationKind</span></span>|<span data-ttu-id="ab351-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-403">win:UInt32</span></span>|<span data-ttu-id="ab351-404">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="ab351-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="ab351-405">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="ab351-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="ab351-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-406">ClrInstanceID</span></span>|<span data-ttu-id="ab351-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-407">win:UInt16</span></span>|<span data-ttu-id="ab351-408">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="ab351-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="ab351-409">AllocationAmount64</span></span>|<span data-ttu-id="ab351-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ab351-410">win:UInt64</span></span>|<span data-ttu-id="ab351-411">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ab351-411">The allocation size, in bytes.</span></span> <span data-ttu-id="ab351-412">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="ab351-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="ab351-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="ab351-413">TypeId</span></span>|<span data-ttu-id="ab351-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="ab351-414">win:Pointer</span></span>|<span data-ttu-id="ab351-415">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="ab351-415">The address of the MethodTable.</span></span> <span data-ttu-id="ab351-416">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="ab351-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="ab351-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="ab351-417">TypeName</span></span>|<span data-ttu-id="ab351-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="ab351-418">win:UnicodeString</span></span>|<span data-ttu-id="ab351-419">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="ab351-419">The name of the type that was allocated.</span></span> <span data-ttu-id="ab351-420">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="ab351-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="ab351-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="ab351-421">HeapIndex</span></span>|<span data-ttu-id="ab351-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-422">win:UInt32</span></span>|<span data-ttu-id="ab351-423">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="ab351-423">The heap where the object was allocated.</span></span> <span data-ttu-id="ab351-424">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ab351-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="ab351-425">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="ab351-426">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="ab351-427">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-428">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-428">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-429">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-432">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-433">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-433">Event</span></span>|<span data-ttu-id="ab351-434">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-434">Event ID</span></span>|<span data-ttu-id="ab351-435">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="ab351-436">14</span><span class="sxs-lookup"><span data-stu-id="ab351-436">14</span></span>|<span data-ttu-id="ab351-437">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ab351-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="ab351-438">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-438">No event data.</span></span>  
  
 [<span data-ttu-id="ab351-439">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="ab351-440">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="ab351-441">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-442">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-442">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-443">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-446">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-447">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-447">Event</span></span>|<span data-ttu-id="ab351-448">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-448">Event ID</span></span>|<span data-ttu-id="ab351-449">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="ab351-450">13</span><span class="sxs-lookup"><span data-stu-id="ab351-450">13</span></span>|<span data-ttu-id="ab351-451">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ab351-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="ab351-452">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="ab351-453">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="ab351-453">Field name</span></span>|<span data-ttu-id="ab351-454">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab351-454">Data type</span></span>|<span data-ttu-id="ab351-455">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab351-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="ab351-456">Recuento</span><span class="sxs-lookup"><span data-stu-id="ab351-456">Count</span></span>|<span data-ttu-id="ab351-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ab351-457">win:UInt32</span></span>|<span data-ttu-id="ab351-458">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="ab351-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="ab351-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ab351-459">ClrInstanceID</span></span>|<span data-ttu-id="ab351-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ab351-460">win:UInt16</span></span>|<span data-ttu-id="ab351-461">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ab351-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="ab351-462">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="ab351-463">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="ab351-464">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-465">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-465">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-466">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-468">Informational (4)</span></span>|  
|<span data-ttu-id="ab351-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ab351-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ab351-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-471">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-472">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-472">Event</span></span>|<span data-ttu-id="ab351-473">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-473">Event ID</span></span>|<span data-ttu-id="ab351-474">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="ab351-475">11</span><span class="sxs-lookup"><span data-stu-id="ab351-475">11</span></span>|<span data-ttu-id="ab351-476">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="ab351-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="ab351-477">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-477">No event data.</span></span>  
  
 [<span data-ttu-id="ab351-478">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="ab351-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="ab351-479">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ab351-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="ab351-480">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ab351-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="ab351-481">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ab351-481">Keyword for raising the event</span></span>|<span data-ttu-id="ab351-482">Nivel</span><span class="sxs-lookup"><span data-stu-id="ab351-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="ab351-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ab351-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ab351-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-484">Informational (4)</span></span>|  
|<span data-ttu-id="ab351-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ab351-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ab351-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ab351-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="ab351-487">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="ab351-488">Evento</span><span class="sxs-lookup"><span data-stu-id="ab351-488">Event</span></span>|<span data-ttu-id="ab351-489">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ab351-489">Event ID</span></span>|<span data-ttu-id="ab351-490">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ab351-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="ab351-491">12</span><span class="sxs-lookup"><span data-stu-id="ab351-491">12</span></span>|<span data-ttu-id="ab351-492">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="ab351-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="ab351-493">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="ab351-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab351-494">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab351-494">See Also</span></span>  
 [<span data-ttu-id="ab351-495">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="ab351-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
