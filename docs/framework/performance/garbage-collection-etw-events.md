---
title: Eventos ETW de recolección de elementos no utilizados
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5e10a1dc1ad3230213a20b850741a6ec0468294
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616423"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="cc616-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="cc616-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="cc616-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="cc616-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="cc616-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="cc616-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="cc616-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="cc616-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="cc616-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="cc616-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="cc616-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="cc616-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="cc616-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="cc616-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="cc616-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="cc616-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="cc616-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="cc616-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="cc616-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="cc616-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="cc616-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="cc616-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="cc616-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="cc616-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="cc616-122">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="cc616-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="cc616-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-123">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-128">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-128">Event</span></span>|<span data-ttu-id="cc616-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-129">Event ID</span></span>|<span data-ttu-id="cc616-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="cc616-131">1</span><span class="sxs-lookup"><span data-stu-id="cc616-131">1</span></span>|<span data-ttu-id="cc616-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="cc616-133">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-134">Field name</span></span>|<span data-ttu-id="cc616-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-135">Data type</span></span>|<span data-ttu-id="cc616-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-137">Recuento</span><span class="sxs-lookup"><span data-stu-id="cc616-137">Count</span></span>|<span data-ttu-id="cc616-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-138">win:UInt32</span></span>|<span data-ttu-id="cc616-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="cc616-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="cc616-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="cc616-140">Depth</span></span>|<span data-ttu-id="cc616-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-141">win:UInt32</span></span>|<span data-ttu-id="cc616-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="cc616-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="cc616-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="cc616-143">Reason</span></span>|<span data-ttu-id="cc616-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-144">win:UInt32</span></span>|<span data-ttu-id="cc616-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="cc616-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="cc616-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="cc616-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="cc616-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="cc616-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="cc616-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="cc616-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="cc616-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="cc616-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="cc616-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="cc616-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="cc616-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="cc616-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="cc616-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="cc616-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="cc616-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cc616-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="cc616-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="cc616-154">Type</span></span>|<span data-ttu-id="cc616-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-155">win:UInt32</span></span>|<span data-ttu-id="cc616-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="cc616-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="cc616-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="cc616-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="cc616-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="cc616-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="cc616-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-159">ClrInstanceID</span></span>|<span data-ttu-id="cc616-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-160">win:UInt16</span></span>|<span data-ttu-id="cc616-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="cc616-163">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="cc616-164">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-165">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-165">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-166">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-169">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-170">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-170">Event</span></span>|<span data-ttu-id="cc616-171">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-171">Event ID</span></span>|<span data-ttu-id="cc616-172">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="cc616-173">2</span><span class="sxs-lookup"><span data-stu-id="cc616-173">2</span></span>|<span data-ttu-id="cc616-174">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="cc616-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="cc616-175">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-176">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-176">Field name</span></span>|<span data-ttu-id="cc616-177">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-177">Data type</span></span>|<span data-ttu-id="cc616-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-179">Recuento</span><span class="sxs-lookup"><span data-stu-id="cc616-179">Count</span></span>|<span data-ttu-id="cc616-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-180">win:UInt32</span></span>|<span data-ttu-id="cc616-181">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="cc616-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="cc616-182">Profundidad</span><span class="sxs-lookup"><span data-stu-id="cc616-182">Depth</span></span>|<span data-ttu-id="cc616-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-183">win:UInt32</span></span>|<span data-ttu-id="cc616-184">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="cc616-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="cc616-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-185">ClrInstanceID</span></span>|<span data-ttu-id="cc616-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-186">win:UInt16</span></span>|<span data-ttu-id="cc616-187">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="cc616-189">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="cc616-190">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-191">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-191">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-192">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-195">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-196">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-196">Event</span></span>|<span data-ttu-id="cc616-197">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-197">Event ID</span></span>|<span data-ttu-id="cc616-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="cc616-199">4</span><span class="sxs-lookup"><span data-stu-id="cc616-199">4</span></span>|<span data-ttu-id="cc616-200">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="cc616-201">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-202">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-202">Field name</span></span>|<span data-ttu-id="cc616-203">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-203">Data type</span></span>|<span data-ttu-id="cc616-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="cc616-205">GenerationSize0</span></span>|<span data-ttu-id="cc616-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-206">win:UInt64</span></span>|<span data-ttu-id="cc616-207">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="cc616-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="cc616-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="cc616-208">TotalPromotedSize0</span></span>|<span data-ttu-id="cc616-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-209">win:UInt64</span></span>|<span data-ttu-id="cc616-210">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="cc616-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="cc616-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="cc616-211">GenerationSize1</span></span>|<span data-ttu-id="cc616-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-212">win:UInt64</span></span>|<span data-ttu-id="cc616-213">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="cc616-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="cc616-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="cc616-214">TotalPromotedSize1</span></span>|<span data-ttu-id="cc616-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-215">win:UInt64</span></span>|<span data-ttu-id="cc616-216">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="cc616-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="cc616-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="cc616-217">GenerationSize2</span></span>|<span data-ttu-id="cc616-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-218">win:UInt64</span></span>|<span data-ttu-id="cc616-219">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="cc616-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="cc616-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="cc616-220">TotalPromotedSize2</span></span>|<span data-ttu-id="cc616-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-221">win:UInt64</span></span>|<span data-ttu-id="cc616-222">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="cc616-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="cc616-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="cc616-223">GenerationSize3</span></span>|<span data-ttu-id="cc616-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-224">win:UInt64</span></span>|<span data-ttu-id="cc616-225">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="cc616-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="cc616-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="cc616-226">TotalPromotedSize3</span></span>|<span data-ttu-id="cc616-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-227">win:UInt64</span></span>|<span data-ttu-id="cc616-228">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="cc616-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="cc616-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="cc616-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="cc616-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-230">win:UInt64</span></span>|<span data-ttu-id="cc616-231">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="cc616-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="cc616-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="cc616-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="cc616-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-233">win:UInt64</span></span>|<span data-ttu-id="cc616-234">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="cc616-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="cc616-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="cc616-235">PinnedObjectCount</span></span>|<span data-ttu-id="cc616-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-236">win:UInt32</span></span>|<span data-ttu-id="cc616-237">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="cc616-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="cc616-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="cc616-238">SinkBlockCount</span></span>|<span data-ttu-id="cc616-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-239">win:UInt32</span></span>|<span data-ttu-id="cc616-240">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="cc616-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="cc616-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="cc616-241">GCHandleCount</span></span>|<span data-ttu-id="cc616-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-242">win:UInt32</span></span>|<span data-ttu-id="cc616-243">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="cc616-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="cc616-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-244">ClrInstanceID</span></span>|<span data-ttu-id="cc616-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-245">win:UInt16</span></span>|<span data-ttu-id="cc616-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-247">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="cc616-248">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="cc616-249">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-250">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-250">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-251">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-254">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-255">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-255">Event</span></span>|<span data-ttu-id="cc616-256">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-256">Event ID</span></span>|<span data-ttu-id="cc616-257">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="cc616-258">5</span><span class="sxs-lookup"><span data-stu-id="cc616-258">5</span></span>|<span data-ttu-id="cc616-259">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="cc616-260">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="cc616-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="cc616-261">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-262">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-262">Field name</span></span>|<span data-ttu-id="cc616-263">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-263">Data type</span></span>|<span data-ttu-id="cc616-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-265">Dirección</span><span class="sxs-lookup"><span data-stu-id="cc616-265">Address</span></span>|<span data-ttu-id="cc616-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-266">win:UInt64</span></span>|<span data-ttu-id="cc616-267">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="cc616-267">The address of the segment.</span></span>|  
|<span data-ttu-id="cc616-268">Tamaño</span><span class="sxs-lookup"><span data-stu-id="cc616-268">Size</span></span>|<span data-ttu-id="cc616-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-269">win:UInt64</span></span>|<span data-ttu-id="cc616-270">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="cc616-270">The size of the segment.</span></span>|  
|<span data-ttu-id="cc616-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="cc616-271">Type</span></span>|<span data-ttu-id="cc616-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-272">win:UInt32</span></span>|<span data-ttu-id="cc616-273">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="cc616-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="cc616-274">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="cc616-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="cc616-275">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="cc616-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="cc616-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-276">ClrInstanceID</span></span>|<span data-ttu-id="cc616-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-277">win:UInt16</span></span>|<span data-ttu-id="cc616-278">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="cc616-279">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="cc616-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="cc616-280">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="cc616-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="cc616-281">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="cc616-282">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="cc616-283">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-284">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-284">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-285">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-288">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-289">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-289">Event</span></span>|<span data-ttu-id="cc616-290">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-290">Event ID</span></span>|<span data-ttu-id="cc616-291">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="cc616-292">6</span><span class="sxs-lookup"><span data-stu-id="cc616-292">6</span></span>|<span data-ttu-id="cc616-293">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="cc616-294">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-295">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-295">Field name</span></span>|<span data-ttu-id="cc616-296">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-296">Data type</span></span>|<span data-ttu-id="cc616-297">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-298">Dirección</span><span class="sxs-lookup"><span data-stu-id="cc616-298">Address</span></span>|<span data-ttu-id="cc616-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-299">win:UInt64</span></span>|<span data-ttu-id="cc616-300">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="cc616-300">The address of the segment.</span></span>|  
|<span data-ttu-id="cc616-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-301">ClrInstanceID</span></span>|<span data-ttu-id="cc616-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-302">win:UInt16</span></span>|<span data-ttu-id="cc616-303">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-304">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="cc616-305">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="cc616-306">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-307">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-307">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-308">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-311">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-312">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-312">Event</span></span>|<span data-ttu-id="cc616-313">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-313">Event ID</span></span>|<span data-ttu-id="cc616-314">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="cc616-315">7</span><span class="sxs-lookup"><span data-stu-id="cc616-315">7</span></span>|<span data-ttu-id="cc616-316">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cc616-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="cc616-317">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-317">No event data.</span></span>  
  
 [<span data-ttu-id="cc616-318">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="cc616-319">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="cc616-320">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-321">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-321">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-322">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-325">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-326">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-326">Event</span></span>|<span data-ttu-id="cc616-327">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-327">Event Id</span></span>|<span data-ttu-id="cc616-328">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="cc616-329">3</span><span class="sxs-lookup"><span data-stu-id="cc616-329">3</span></span>|<span data-ttu-id="cc616-330">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cc616-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="cc616-331">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-331">No event data.</span></span>  
  
 [<span data-ttu-id="cc616-332">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="cc616-333">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="cc616-334">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-335">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-335">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-336">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-339">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-340">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-340">Event</span></span>|<span data-ttu-id="cc616-341">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-341">Event ID</span></span>|<span data-ttu-id="cc616-342">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="cc616-343">9</span><span class="sxs-lookup"><span data-stu-id="cc616-343">9</span></span>|<span data-ttu-id="cc616-344">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="cc616-345">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-346">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-346">Field name</span></span>|<span data-ttu-id="cc616-347">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-347">Data type</span></span>|<span data-ttu-id="cc616-348">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="cc616-349">Reason</span></span>|<span data-ttu-id="cc616-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-350">win:UInt16</span></span>|<span data-ttu-id="cc616-351">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="cc616-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="cc616-352">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="cc616-353">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc616-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="cc616-354">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="cc616-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="cc616-355">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="cc616-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="cc616-356">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="cc616-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="cc616-357">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="cc616-358">Recuento</span><span class="sxs-lookup"><span data-stu-id="cc616-358">Count</span></span>|<span data-ttu-id="cc616-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-359">win:UInt32</span></span>|<span data-ttu-id="cc616-360">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="cc616-360">The GC count at the time.</span></span> <span data-ttu-id="cc616-361">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="cc616-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-362">ClrInstanceID</span></span>|<span data-ttu-id="cc616-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-363">win:UInt16</span></span>|<span data-ttu-id="cc616-364">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-365">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="cc616-366">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="cc616-367">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="cc616-368">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-368">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-369">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-372">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="cc616-373">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-373">Event</span></span>|<span data-ttu-id="cc616-374">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-374">Event ID</span></span>|<span data-ttu-id="cc616-375">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="cc616-376">8</span><span class="sxs-lookup"><span data-stu-id="cc616-376">8</span></span>|<span data-ttu-id="cc616-377">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cc616-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="cc616-378">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-378">No event data.</span></span>  
  
 [<span data-ttu-id="cc616-379">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="cc616-380">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="cc616-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="cc616-381">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-382">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-382">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-383">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-386">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-387">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-387">Event</span></span>|<span data-ttu-id="cc616-388">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-388">Event ID</span></span>|<span data-ttu-id="cc616-389">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="cc616-390">10</span><span class="sxs-lookup"><span data-stu-id="cc616-390">10</span></span>|<span data-ttu-id="cc616-391">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="cc616-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="cc616-392">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-393">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-393">Field name</span></span>|<span data-ttu-id="cc616-394">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-394">Data type</span></span>|<span data-ttu-id="cc616-395">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="cc616-396">AllocationAmount</span></span>|<span data-ttu-id="cc616-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-397">win:UInt32</span></span>|<span data-ttu-id="cc616-398">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="cc616-398">The allocation size, in bytes.</span></span> <span data-ttu-id="cc616-399">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="cc616-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="cc616-400">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="cc616-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="cc616-401">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="cc616-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="cc616-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="cc616-402">AllocationKind</span></span>|<span data-ttu-id="cc616-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-403">win:UInt32</span></span>|<span data-ttu-id="cc616-404">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="cc616-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="cc616-405">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="cc616-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="cc616-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-406">ClrInstanceID</span></span>|<span data-ttu-id="cc616-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-407">win:UInt16</span></span>|<span data-ttu-id="cc616-408">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="cc616-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="cc616-409">AllocationAmount64</span></span>|<span data-ttu-id="cc616-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="cc616-410">win:UInt64</span></span>|<span data-ttu-id="cc616-411">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="cc616-411">The allocation size, in bytes.</span></span> <span data-ttu-id="cc616-412">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="cc616-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="cc616-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="cc616-413">TypeId</span></span>|<span data-ttu-id="cc616-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="cc616-414">win:Pointer</span></span>|<span data-ttu-id="cc616-415">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="cc616-415">The address of the MethodTable.</span></span> <span data-ttu-id="cc616-416">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="cc616-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="cc616-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="cc616-417">TypeName</span></span>|<span data-ttu-id="cc616-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cc616-418">win:UnicodeString</span></span>|<span data-ttu-id="cc616-419">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="cc616-419">The name of the type that was allocated.</span></span> <span data-ttu-id="cc616-420">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="cc616-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="cc616-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="cc616-421">HeapIndex</span></span>|<span data-ttu-id="cc616-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-422">win:UInt32</span></span>|<span data-ttu-id="cc616-423">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="cc616-423">The heap where the object was allocated.</span></span> <span data-ttu-id="cc616-424">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cc616-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="cc616-425">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="cc616-426">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="cc616-427">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-428">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-428">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-429">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-432">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-433">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-433">Event</span></span>|<span data-ttu-id="cc616-434">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-434">Event ID</span></span>|<span data-ttu-id="cc616-435">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="cc616-436">14</span><span class="sxs-lookup"><span data-stu-id="cc616-436">14</span></span>|<span data-ttu-id="cc616-437">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="cc616-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="cc616-438">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-438">No event data.</span></span>  
  
 [<span data-ttu-id="cc616-439">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="cc616-440">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="cc616-441">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-442">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-442">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-443">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-446">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-447">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-447">Event</span></span>|<span data-ttu-id="cc616-448">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-448">Event ID</span></span>|<span data-ttu-id="cc616-449">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="cc616-450">13</span><span class="sxs-lookup"><span data-stu-id="cc616-450">13</span></span>|<span data-ttu-id="cc616-451">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="cc616-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="cc616-452">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="cc616-453">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="cc616-453">Field name</span></span>|<span data-ttu-id="cc616-454">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc616-454">Data type</span></span>|<span data-ttu-id="cc616-455">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc616-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc616-456">Recuento</span><span class="sxs-lookup"><span data-stu-id="cc616-456">Count</span></span>|<span data-ttu-id="cc616-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc616-457">win:UInt32</span></span>|<span data-ttu-id="cc616-458">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="cc616-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="cc616-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc616-459">ClrInstanceID</span></span>|<span data-ttu-id="cc616-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc616-460">win:UInt16</span></span>|<span data-ttu-id="cc616-461">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc616-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="cc616-462">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="cc616-463">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="cc616-464">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-465">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-465">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-466">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-468">Informational (4)</span></span>|  
|<span data-ttu-id="cc616-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="cc616-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="cc616-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-471">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-472">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-472">Event</span></span>|<span data-ttu-id="cc616-473">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-473">Event ID</span></span>|<span data-ttu-id="cc616-474">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="cc616-475">11</span><span class="sxs-lookup"><span data-stu-id="cc616-475">11</span></span>|<span data-ttu-id="cc616-476">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="cc616-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="cc616-477">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-477">No event data.</span></span>  
  
 [<span data-ttu-id="cc616-478">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="cc616-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="cc616-479">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="cc616-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="cc616-480">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="cc616-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="cc616-481">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc616-481">Keyword for raising the event</span></span>|<span data-ttu-id="cc616-482">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc616-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc616-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="cc616-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="cc616-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-484">Informational (4)</span></span>|  
|<span data-ttu-id="cc616-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="cc616-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="cc616-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="cc616-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="cc616-487">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="cc616-488">evento</span><span class="sxs-lookup"><span data-stu-id="cc616-488">Event</span></span>|<span data-ttu-id="cc616-489">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc616-489">Event ID</span></span>|<span data-ttu-id="cc616-490">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc616-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="cc616-491">12</span><span class="sxs-lookup"><span data-stu-id="cc616-491">12</span></span>|<span data-ttu-id="cc616-492">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="cc616-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="cc616-493">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc616-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc616-494">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc616-494">See also</span></span>

- [<span data-ttu-id="cc616-495">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="cc616-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
