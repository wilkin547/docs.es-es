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
ms.openlocfilehash: 7f9bf0e309ec8c77d4b1d6afbf111e7eeae629ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149739"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="000b6-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="000b6-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="000b6-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="000b6-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="000b6-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="000b6-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="000b6-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="000b6-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="000b6-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="000b6-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="000b6-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="000b6-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="000b6-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="000b6-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="000b6-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="000b6-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="000b6-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="000b6-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="000b6-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="000b6-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="000b6-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="000b6-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="000b6-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="000b6-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="000b6-122">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="000b6-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="000b6-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-123">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-124">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-125">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-125">(0x1)</span></span>|<span data-ttu-id="000b6-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-128">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-128">Event</span></span>|<span data-ttu-id="000b6-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-129">Event ID</span></span>|<span data-ttu-id="000b6-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="000b6-131">1</span><span class="sxs-lookup"><span data-stu-id="000b6-131">1</span></span>|<span data-ttu-id="000b6-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="000b6-133">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-134">Field name</span></span>|<span data-ttu-id="000b6-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-135">Data type</span></span>|<span data-ttu-id="000b6-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-137">Recuento</span><span class="sxs-lookup"><span data-stu-id="000b6-137">Count</span></span>|<span data-ttu-id="000b6-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-138">win:UInt32</span></span>|<span data-ttu-id="000b6-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="000b6-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="000b6-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="000b6-140">Depth</span></span>|<span data-ttu-id="000b6-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-141">win:UInt32</span></span>|<span data-ttu-id="000b6-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="000b6-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="000b6-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="000b6-143">Reason</span></span>|<span data-ttu-id="000b6-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-144">win:UInt32</span></span>|<span data-ttu-id="000b6-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="000b6-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="000b6-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="000b6-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="000b6-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="000b6-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="000b6-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="000b6-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="000b6-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="000b6-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="000b6-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="000b6-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="000b6-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="000b6-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="000b6-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="000b6-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="000b6-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="000b6-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="000b6-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="000b6-154">Type</span></span>|<span data-ttu-id="000b6-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-155">win:UInt32</span></span>|<span data-ttu-id="000b6-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="000b6-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="000b6-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="000b6-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="000b6-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="000b6-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="000b6-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-159">ClrInstanceID</span></span>|<span data-ttu-id="000b6-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-160">win:UInt16</span></span>|<span data-ttu-id="000b6-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="000b6-163">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="000b6-164">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-165">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-165">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-166">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-166">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-167">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-167">(0x1)</span></span>|<span data-ttu-id="000b6-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-169">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-170">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-170">Event</span></span>|<span data-ttu-id="000b6-171">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-171">Event ID</span></span>|<span data-ttu-id="000b6-172">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="000b6-173">2</span><span class="sxs-lookup"><span data-stu-id="000b6-173">2</span></span>|<span data-ttu-id="000b6-174">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="000b6-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="000b6-175">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-176">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-176">Field name</span></span>|<span data-ttu-id="000b6-177">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-177">Data type</span></span>|<span data-ttu-id="000b6-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-179">Recuento</span><span class="sxs-lookup"><span data-stu-id="000b6-179">Count</span></span>|<span data-ttu-id="000b6-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-180">win:UInt32</span></span>|<span data-ttu-id="000b6-181">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="000b6-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="000b6-182">Profundidad</span><span class="sxs-lookup"><span data-stu-id="000b6-182">Depth</span></span>|<span data-ttu-id="000b6-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-183">win:UInt32</span></span>|<span data-ttu-id="000b6-184">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="000b6-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="000b6-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-185">ClrInstanceID</span></span>|<span data-ttu-id="000b6-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-186">win:UInt16</span></span>|<span data-ttu-id="000b6-187">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="000b6-189">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="000b6-190">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-191">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-191">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-192">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-192">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-193">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-193">(0x1)</span></span>|<span data-ttu-id="000b6-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-195">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-196">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-196">Event</span></span>|<span data-ttu-id="000b6-197">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-197">Event ID</span></span>|<span data-ttu-id="000b6-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="000b6-199">4</span><span class="sxs-lookup"><span data-stu-id="000b6-199">4</span></span>|<span data-ttu-id="000b6-200">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="000b6-201">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-202">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-202">Field name</span></span>|<span data-ttu-id="000b6-203">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-203">Data type</span></span>|<span data-ttu-id="000b6-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="000b6-205">GenerationSize0</span></span>|<span data-ttu-id="000b6-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-206">win:UInt64</span></span>|<span data-ttu-id="000b6-207">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="000b6-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="000b6-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="000b6-208">TotalPromotedSize0</span></span>|<span data-ttu-id="000b6-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-209">win:UInt64</span></span>|<span data-ttu-id="000b6-210">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="000b6-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="000b6-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="000b6-211">GenerationSize1</span></span>|<span data-ttu-id="000b6-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-212">win:UInt64</span></span>|<span data-ttu-id="000b6-213">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="000b6-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="000b6-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="000b6-214">TotalPromotedSize1</span></span>|<span data-ttu-id="000b6-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-215">win:UInt64</span></span>|<span data-ttu-id="000b6-216">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="000b6-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="000b6-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="000b6-217">GenerationSize2</span></span>|<span data-ttu-id="000b6-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-218">win:UInt64</span></span>|<span data-ttu-id="000b6-219">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="000b6-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="000b6-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="000b6-220">TotalPromotedSize2</span></span>|<span data-ttu-id="000b6-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-221">win:UInt64</span></span>|<span data-ttu-id="000b6-222">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="000b6-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="000b6-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="000b6-223">GenerationSize3</span></span>|<span data-ttu-id="000b6-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-224">win:UInt64</span></span>|<span data-ttu-id="000b6-225">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="000b6-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="000b6-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="000b6-226">TotalPromotedSize3</span></span>|<span data-ttu-id="000b6-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-227">win:UInt64</span></span>|<span data-ttu-id="000b6-228">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="000b6-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="000b6-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="000b6-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="000b6-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-230">win:UInt64</span></span>|<span data-ttu-id="000b6-231">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="000b6-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="000b6-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="000b6-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="000b6-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-233">win:UInt64</span></span>|<span data-ttu-id="000b6-234">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="000b6-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="000b6-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="000b6-235">PinnedObjectCount</span></span>|<span data-ttu-id="000b6-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-236">win:UInt32</span></span>|<span data-ttu-id="000b6-237">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="000b6-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="000b6-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="000b6-238">SinkBlockCount</span></span>|<span data-ttu-id="000b6-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-239">win:UInt32</span></span>|<span data-ttu-id="000b6-240">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="000b6-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="000b6-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="000b6-241">GCHandleCount</span></span>|<span data-ttu-id="000b6-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-242">win:UInt32</span></span>|<span data-ttu-id="000b6-243">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="000b6-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="000b6-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-244">ClrInstanceID</span></span>|<span data-ttu-id="000b6-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-245">win:UInt16</span></span>|<span data-ttu-id="000b6-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-247">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="000b6-248">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="000b6-249">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-250">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-250">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-251">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-251">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-252">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-252">(0x1)</span></span>|<span data-ttu-id="000b6-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-254">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-255">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-255">Event</span></span>|<span data-ttu-id="000b6-256">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-256">Event ID</span></span>|<span data-ttu-id="000b6-257">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="000b6-258">5</span><span class="sxs-lookup"><span data-stu-id="000b6-258">5</span></span>|<span data-ttu-id="000b6-259">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="000b6-260">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="000b6-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="000b6-261">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-262">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-262">Field name</span></span>|<span data-ttu-id="000b6-263">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-263">Data type</span></span>|<span data-ttu-id="000b6-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-265">Dirección</span><span class="sxs-lookup"><span data-stu-id="000b6-265">Address</span></span>|<span data-ttu-id="000b6-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-266">win:UInt64</span></span>|<span data-ttu-id="000b6-267">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="000b6-267">The address of the segment.</span></span>|  
|<span data-ttu-id="000b6-268">Tamaño</span><span class="sxs-lookup"><span data-stu-id="000b6-268">Size</span></span>|<span data-ttu-id="000b6-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-269">win:UInt64</span></span>|<span data-ttu-id="000b6-270">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="000b6-270">The size of the segment.</span></span>|  
|<span data-ttu-id="000b6-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="000b6-271">Type</span></span>|<span data-ttu-id="000b6-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-272">win:UInt32</span></span>|<span data-ttu-id="000b6-273">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="000b6-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="000b6-274">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="000b6-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="000b6-275">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="000b6-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="000b6-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-276">ClrInstanceID</span></span>|<span data-ttu-id="000b6-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-277">win:UInt16</span></span>|<span data-ttu-id="000b6-278">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="000b6-279">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="000b6-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="000b6-280">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="000b6-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="000b6-281">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="000b6-282">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="000b6-283">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-284">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-284">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-285">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-285">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-286">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-286">(0x1)</span></span>|<span data-ttu-id="000b6-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-288">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-289">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-289">Event</span></span>|<span data-ttu-id="000b6-290">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-290">Event ID</span></span>|<span data-ttu-id="000b6-291">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="000b6-292">6</span><span class="sxs-lookup"><span data-stu-id="000b6-292">6</span></span>|<span data-ttu-id="000b6-293">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="000b6-294">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-295">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-295">Field name</span></span>|<span data-ttu-id="000b6-296">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-296">Data type</span></span>|<span data-ttu-id="000b6-297">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-298">Dirección</span><span class="sxs-lookup"><span data-stu-id="000b6-298">Address</span></span>|<span data-ttu-id="000b6-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-299">win:UInt64</span></span>|<span data-ttu-id="000b6-300">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="000b6-300">The address of the segment.</span></span>|  
|<span data-ttu-id="000b6-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-301">ClrInstanceID</span></span>|<span data-ttu-id="000b6-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-302">win:UInt16</span></span>|<span data-ttu-id="000b6-303">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-304">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="000b6-305">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="000b6-306">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-307">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-307">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-308">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-308">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-309">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-309">(0x1)</span></span>|<span data-ttu-id="000b6-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-311">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-312">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-312">Event</span></span>|<span data-ttu-id="000b6-313">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-313">Event ID</span></span>|<span data-ttu-id="000b6-314">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="000b6-315">7</span><span class="sxs-lookup"><span data-stu-id="000b6-315">7</span></span>|<span data-ttu-id="000b6-316">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="000b6-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="000b6-317">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-317">No event data.</span></span>  
  
 [<span data-ttu-id="000b6-318">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="000b6-319">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="000b6-320">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-321">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-321">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-322">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-322">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-323">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-323">(0x1)</span></span>|<span data-ttu-id="000b6-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-325">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-326">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-326">Event</span></span>|<span data-ttu-id="000b6-327">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-327">Event Id</span></span>|<span data-ttu-id="000b6-328">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="000b6-329">3</span><span class="sxs-lookup"><span data-stu-id="000b6-329">3</span></span>|<span data-ttu-id="000b6-330">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="000b6-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="000b6-331">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-331">No event data.</span></span>  
  
 [<span data-ttu-id="000b6-332">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="000b6-333">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="000b6-334">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-335">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-335">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-336">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-336">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-337">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-337">(0x1)</span></span>|<span data-ttu-id="000b6-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-339">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-340">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-340">Event</span></span>|<span data-ttu-id="000b6-341">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-341">Event ID</span></span>|<span data-ttu-id="000b6-342">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="000b6-343">9</span><span class="sxs-lookup"><span data-stu-id="000b6-343">9</span></span>|<span data-ttu-id="000b6-344">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="000b6-345">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-346">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-346">Field name</span></span>|<span data-ttu-id="000b6-347">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-347">Data type</span></span>|<span data-ttu-id="000b6-348">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="000b6-349">Reason</span></span>|<span data-ttu-id="000b6-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-350">win:UInt16</span></span>|<span data-ttu-id="000b6-351">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="000b6-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="000b6-352">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="000b6-353">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="000b6-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="000b6-354">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="000b6-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="000b6-355">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="000b6-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="000b6-356">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="000b6-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="000b6-357">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="000b6-358">Recuento</span><span class="sxs-lookup"><span data-stu-id="000b6-358">Count</span></span>|<span data-ttu-id="000b6-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-359">win:UInt32</span></span>|<span data-ttu-id="000b6-360">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="000b6-360">The GC count at the time.</span></span> <span data-ttu-id="000b6-361">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="000b6-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-362">ClrInstanceID</span></span>|<span data-ttu-id="000b6-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-363">win:UInt16</span></span>|<span data-ttu-id="000b6-364">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-365">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="000b6-366">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="000b6-367">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="000b6-368">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-368">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-369">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-369">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-370">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-370">(0x1)</span></span>|<span data-ttu-id="000b6-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-372">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="000b6-373">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-373">Event</span></span>|<span data-ttu-id="000b6-374">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-374">Event ID</span></span>|<span data-ttu-id="000b6-375">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="000b6-376">8</span><span class="sxs-lookup"><span data-stu-id="000b6-376">8</span></span>|<span data-ttu-id="000b6-377">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="000b6-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="000b6-378">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-378">No event data.</span></span>  
  
 [<span data-ttu-id="000b6-379">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="000b6-380">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="000b6-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="000b6-381">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-382">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-382">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-383">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-383">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-384">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-384">(0x1)</span></span>|<span data-ttu-id="000b6-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-386">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-387">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-387">Event</span></span>|<span data-ttu-id="000b6-388">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-388">Event ID</span></span>|<span data-ttu-id="000b6-389">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="000b6-390">10</span><span class="sxs-lookup"><span data-stu-id="000b6-390">10</span></span>|<span data-ttu-id="000b6-391">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="000b6-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="000b6-392">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-393">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-393">Field name</span></span>|<span data-ttu-id="000b6-394">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-394">Data type</span></span>|<span data-ttu-id="000b6-395">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="000b6-396">AllocationAmount</span></span>|<span data-ttu-id="000b6-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-397">win:UInt32</span></span>|<span data-ttu-id="000b6-398">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="000b6-398">The allocation size, in bytes.</span></span> <span data-ttu-id="000b6-399">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="000b6-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="000b6-400">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="000b6-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="000b6-401">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="000b6-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="000b6-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="000b6-402">AllocationKind</span></span>|<span data-ttu-id="000b6-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-403">win:UInt32</span></span>|<span data-ttu-id="000b6-404">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="000b6-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="000b6-405">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="000b6-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="000b6-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-406">ClrInstanceID</span></span>|<span data-ttu-id="000b6-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-407">win:UInt16</span></span>|<span data-ttu-id="000b6-408">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="000b6-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="000b6-409">AllocationAmount64</span></span>|<span data-ttu-id="000b6-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="000b6-410">win:UInt64</span></span>|<span data-ttu-id="000b6-411">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="000b6-411">The allocation size, in bytes.</span></span> <span data-ttu-id="000b6-412">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="000b6-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="000b6-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="000b6-413">TypeId</span></span>|<span data-ttu-id="000b6-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="000b6-414">win:Pointer</span></span>|<span data-ttu-id="000b6-415">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="000b6-415">The address of the MethodTable.</span></span> <span data-ttu-id="000b6-416">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="000b6-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="000b6-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="000b6-417">TypeName</span></span>|<span data-ttu-id="000b6-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="000b6-418">win:UnicodeString</span></span>|<span data-ttu-id="000b6-419">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="000b6-419">The name of the type that was allocated.</span></span> <span data-ttu-id="000b6-420">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="000b6-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="000b6-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="000b6-421">HeapIndex</span></span>|<span data-ttu-id="000b6-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-422">win:UInt32</span></span>|<span data-ttu-id="000b6-423">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="000b6-423">The heap where the object was allocated.</span></span> <span data-ttu-id="000b6-424">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="000b6-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="000b6-425">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="000b6-426">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="000b6-427">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-428">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-428">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-429">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-429">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-430">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-430">(0x1)</span></span>|<span data-ttu-id="000b6-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-432">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-433">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-433">Event</span></span>|<span data-ttu-id="000b6-434">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-434">Event ID</span></span>|<span data-ttu-id="000b6-435">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="000b6-436">14</span><span class="sxs-lookup"><span data-stu-id="000b6-436">14</span></span>|<span data-ttu-id="000b6-437">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="000b6-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="000b6-438">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-438">No event data.</span></span>  
  
 [<span data-ttu-id="000b6-439">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="000b6-440">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="000b6-441">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-442">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-442">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-443">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-443">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-444">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-444">(0x1)</span></span>|<span data-ttu-id="000b6-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-446">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-447">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-447">Event</span></span>|<span data-ttu-id="000b6-448">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-448">Event ID</span></span>|<span data-ttu-id="000b6-449">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="000b6-450">13</span><span class="sxs-lookup"><span data-stu-id="000b6-450">13</span></span>|<span data-ttu-id="000b6-451">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="000b6-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="000b6-452">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="000b6-453">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="000b6-453">Field name</span></span>|<span data-ttu-id="000b6-454">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="000b6-454">Data type</span></span>|<span data-ttu-id="000b6-455">Descripción</span><span class="sxs-lookup"><span data-stu-id="000b6-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="000b6-456">Recuento</span><span class="sxs-lookup"><span data-stu-id="000b6-456">Count</span></span>|<span data-ttu-id="000b6-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="000b6-457">win:UInt32</span></span>|<span data-ttu-id="000b6-458">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="000b6-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="000b6-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="000b6-459">ClrInstanceID</span></span>|<span data-ttu-id="000b6-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="000b6-460">win:UInt16</span></span>|<span data-ttu-id="000b6-461">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="000b6-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="000b6-462">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="000b6-463">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="000b6-464">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-465">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-465">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-466">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-466">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-467">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-467">(0x1)</span></span>|<span data-ttu-id="000b6-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-468">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="000b6-469">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="000b6-469">(0x10000)</span></span>|<span data-ttu-id="000b6-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-471">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-472">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-472">Event</span></span>|<span data-ttu-id="000b6-473">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-473">Event ID</span></span>|<span data-ttu-id="000b6-474">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="000b6-475">11</span><span class="sxs-lookup"><span data-stu-id="000b6-475">11</span></span>|<span data-ttu-id="000b6-476">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="000b6-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="000b6-477">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-477">No event data.</span></span>  
  
 [<span data-ttu-id="000b6-478">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="000b6-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="000b6-479">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="000b6-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="000b6-480">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="000b6-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="000b6-481">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="000b6-481">Keyword for raising the event</span></span>|<span data-ttu-id="000b6-482">Nivel</span><span class="sxs-lookup"><span data-stu-id="000b6-482">Level</span></span>|  
|-----------------------------------|-----------|  
|`GCKeyword` <span data-ttu-id="000b6-483">(0x1)</span><span class="sxs-lookup"><span data-stu-id="000b6-483">(0x1)</span></span>|<span data-ttu-id="000b6-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-484">Informational (4)</span></span>|  
|`ThreadingKeyword` <span data-ttu-id="000b6-485">(0x10000)</span><span class="sxs-lookup"><span data-stu-id="000b6-485">(0x10000)</span></span>|<span data-ttu-id="000b6-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="000b6-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="000b6-487">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="000b6-488">evento</span><span class="sxs-lookup"><span data-stu-id="000b6-488">Event</span></span>|<span data-ttu-id="000b6-489">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="000b6-489">Event ID</span></span>|<span data-ttu-id="000b6-490">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="000b6-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="000b6-491">12</span><span class="sxs-lookup"><span data-stu-id="000b6-491">12</span></span>|<span data-ttu-id="000b6-492">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="000b6-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="000b6-493">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="000b6-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="000b6-494">Vea también</span><span class="sxs-lookup"><span data-stu-id="000b6-494">See also</span></span>

- [<span data-ttu-id="000b6-495">Eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="000b6-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
