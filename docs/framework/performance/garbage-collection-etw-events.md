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
ms.openlocfilehash: 13f7e935ab999ccc3cd3ea1e308e8d686bed4171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396940"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="b0f0d-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b0f0d-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="b0f0d-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="b0f0d-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="b0f0d-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="b0f0d-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="b0f0d-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="b0f0d-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="b0f0d-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="b0f0d-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="b0f0d-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="b0f0d-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="b0f0d-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="b0f0d-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="b0f0d-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="b0f0d-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="b0f0d-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="b0f0d-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="b0f0d-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="b0f0d-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="b0f0d-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="b0f0d-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="b0f0d-122">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b0f0d-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-123">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-128">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-128">Event</span></span>|<span data-ttu-id="b0f0d-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-129">Event ID</span></span>|<span data-ttu-id="b0f0d-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="b0f0d-131">1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-131">1</span></span>|<span data-ttu-id="b0f0d-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="b0f0d-133">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-134">Field name</span></span>|<span data-ttu-id="b0f0d-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-135">Data type</span></span>|<span data-ttu-id="b0f0d-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-137">Recuento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-137">Count</span></span>|<span data-ttu-id="b0f0d-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-138">win:UInt32</span></span>|<span data-ttu-id="b0f0d-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="b0f0d-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="b0f0d-140">Depth</span></span>|<span data-ttu-id="b0f0d-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-141">win:UInt32</span></span>|<span data-ttu-id="b0f0d-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="b0f0d-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-143">Reason</span></span>|<span data-ttu-id="b0f0d-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-144">win:UInt32</span></span>|<span data-ttu-id="b0f0d-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="b0f0d-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="b0f0d-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="b0f0d-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="b0f0d-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="b0f0d-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="b0f0d-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="b0f0d-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="b0f0d-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="b0f0d-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="b0f0d-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-154">Type</span></span>|<span data-ttu-id="b0f0d-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-155">win:UInt32</span></span>|<span data-ttu-id="b0f0d-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="b0f0d-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="b0f0d-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="b0f0d-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-159">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-160">win:UInt16</span></span>|<span data-ttu-id="b0f0d-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="b0f0d-163">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-164">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-165">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-165">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-166">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-169">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-170">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-170">Event</span></span>|<span data-ttu-id="b0f0d-171">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-171">Event ID</span></span>|<span data-ttu-id="b0f0d-172">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="b0f0d-173">2</span><span class="sxs-lookup"><span data-stu-id="b0f0d-173">2</span></span>|<span data-ttu-id="b0f0d-174">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="b0f0d-175">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-176">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-176">Field name</span></span>|<span data-ttu-id="b0f0d-177">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-177">Data type</span></span>|<span data-ttu-id="b0f0d-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-179">Recuento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-179">Count</span></span>|<span data-ttu-id="b0f0d-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-180">win:UInt32</span></span>|<span data-ttu-id="b0f0d-181">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="b0f0d-182">Profundidad</span><span class="sxs-lookup"><span data-stu-id="b0f0d-182">Depth</span></span>|<span data-ttu-id="b0f0d-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-183">win:UInt32</span></span>|<span data-ttu-id="b0f0d-184">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="b0f0d-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-185">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-186">win:UInt16</span></span>|<span data-ttu-id="b0f0d-187">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="b0f0d-189">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-190">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-191">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-191">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-192">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-195">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-196">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-196">Event</span></span>|<span data-ttu-id="b0f0d-197">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-197">Event ID</span></span>|<span data-ttu-id="b0f0d-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="b0f0d-199">4</span><span class="sxs-lookup"><span data-stu-id="b0f0d-199">4</span></span>|<span data-ttu-id="b0f0d-200">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="b0f0d-201">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-202">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-202">Field name</span></span>|<span data-ttu-id="b0f0d-203">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-203">Data type</span></span>|<span data-ttu-id="b0f0d-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="b0f0d-205">GenerationSize0</span></span>|<span data-ttu-id="b0f0d-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-206">win:UInt64</span></span>|<span data-ttu-id="b0f0d-207">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="b0f0d-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="b0f0d-208">TotalPromotedSize0</span></span>|<span data-ttu-id="b0f0d-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-209">win:UInt64</span></span>|<span data-ttu-id="b0f0d-210">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="b0f0d-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-211">GenerationSize1</span></span>|<span data-ttu-id="b0f0d-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-212">win:UInt64</span></span>|<span data-ttu-id="b0f0d-213">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="b0f0d-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-214">TotalPromotedSize1</span></span>|<span data-ttu-id="b0f0d-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-215">win:UInt64</span></span>|<span data-ttu-id="b0f0d-216">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="b0f0d-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="b0f0d-217">GenerationSize2</span></span>|<span data-ttu-id="b0f0d-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-218">win:UInt64</span></span>|<span data-ttu-id="b0f0d-219">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="b0f0d-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="b0f0d-220">TotalPromotedSize2</span></span>|<span data-ttu-id="b0f0d-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-221">win:UInt64</span></span>|<span data-ttu-id="b0f0d-222">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="b0f0d-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="b0f0d-223">GenerationSize3</span></span>|<span data-ttu-id="b0f0d-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-224">win:UInt64</span></span>|<span data-ttu-id="b0f0d-225">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="b0f0d-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="b0f0d-226">TotalPromotedSize3</span></span>|<span data-ttu-id="b0f0d-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-227">win:UInt64</span></span>|<span data-ttu-id="b0f0d-228">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="b0f0d-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="b0f0d-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="b0f0d-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-230">win:UInt64</span></span>|<span data-ttu-id="b0f0d-231">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="b0f0d-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="b0f0d-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="b0f0d-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-233">win:UInt64</span></span>|<span data-ttu-id="b0f0d-234">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="b0f0d-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="b0f0d-235">PinnedObjectCount</span></span>|<span data-ttu-id="b0f0d-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-236">win:UInt32</span></span>|<span data-ttu-id="b0f0d-237">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="b0f0d-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="b0f0d-238">SinkBlockCount</span></span>|<span data-ttu-id="b0f0d-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-239">win:UInt32</span></span>|<span data-ttu-id="b0f0d-240">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="b0f0d-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="b0f0d-241">GCHandleCount</span></span>|<span data-ttu-id="b0f0d-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-242">win:UInt32</span></span>|<span data-ttu-id="b0f0d-243">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="b0f0d-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-244">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-245">win:UInt16</span></span>|<span data-ttu-id="b0f0d-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-247">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="b0f0d-248">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-249">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-250">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-250">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-251">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-254">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-255">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-255">Event</span></span>|<span data-ttu-id="b0f0d-256">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-256">Event ID</span></span>|<span data-ttu-id="b0f0d-257">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="b0f0d-258">5</span><span class="sxs-lookup"><span data-stu-id="b0f0d-258">5</span></span>|<span data-ttu-id="b0f0d-259">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="b0f0d-260">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="b0f0d-261">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-262">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-262">Field name</span></span>|<span data-ttu-id="b0f0d-263">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-263">Data type</span></span>|<span data-ttu-id="b0f0d-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-265">Dirección</span><span class="sxs-lookup"><span data-stu-id="b0f0d-265">Address</span></span>|<span data-ttu-id="b0f0d-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-266">win:UInt64</span></span>|<span data-ttu-id="b0f0d-267">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-267">The address of the segment.</span></span>|  
|<span data-ttu-id="b0f0d-268">Tamaño</span><span class="sxs-lookup"><span data-stu-id="b0f0d-268">Size</span></span>|<span data-ttu-id="b0f0d-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-269">win:UInt64</span></span>|<span data-ttu-id="b0f0d-270">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-270">The size of the segment.</span></span>|  
|<span data-ttu-id="b0f0d-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-271">Type</span></span>|<span data-ttu-id="b0f0d-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-272">win:UInt32</span></span>|<span data-ttu-id="b0f0d-273">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="b0f0d-274">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="b0f0d-275">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="b0f0d-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-276">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-277">win:UInt16</span></span>|<span data-ttu-id="b0f0d-278">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="b0f0d-279">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="b0f0d-280">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="b0f0d-281">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="b0f0d-282">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-283">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-284">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-284">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-285">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-288">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-289">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-289">Event</span></span>|<span data-ttu-id="b0f0d-290">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-290">Event ID</span></span>|<span data-ttu-id="b0f0d-291">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="b0f0d-292">6</span><span class="sxs-lookup"><span data-stu-id="b0f0d-292">6</span></span>|<span data-ttu-id="b0f0d-293">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="b0f0d-294">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-295">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-295">Field name</span></span>|<span data-ttu-id="b0f0d-296">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-296">Data type</span></span>|<span data-ttu-id="b0f0d-297">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-298">Dirección</span><span class="sxs-lookup"><span data-stu-id="b0f0d-298">Address</span></span>|<span data-ttu-id="b0f0d-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-299">win:UInt64</span></span>|<span data-ttu-id="b0f0d-300">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-300">The address of the segment.</span></span>|  
|<span data-ttu-id="b0f0d-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-301">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-302">win:UInt16</span></span>|<span data-ttu-id="b0f0d-303">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-304">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="b0f0d-305">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-306">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-307">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-307">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-308">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-311">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-312">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-312">Event</span></span>|<span data-ttu-id="b0f0d-313">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-313">Event ID</span></span>|<span data-ttu-id="b0f0d-314">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="b0f0d-315">7</span><span class="sxs-lookup"><span data-stu-id="b0f0d-315">7</span></span>|<span data-ttu-id="b0f0d-316">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="b0f0d-317">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-317">No event data.</span></span>  
  
 [<span data-ttu-id="b0f0d-318">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="b0f0d-319">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-320">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-321">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-321">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-322">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-325">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-326">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-326">Event</span></span>|<span data-ttu-id="b0f0d-327">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-327">Event Id</span></span>|<span data-ttu-id="b0f0d-328">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="b0f0d-329">3</span><span class="sxs-lookup"><span data-stu-id="b0f0d-329">3</span></span>|<span data-ttu-id="b0f0d-330">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="b0f0d-331">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-331">No event data.</span></span>  
  
 [<span data-ttu-id="b0f0d-332">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="b0f0d-333">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-334">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-335">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-335">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-336">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-339">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-340">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-340">Event</span></span>|<span data-ttu-id="b0f0d-341">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-341">Event ID</span></span>|<span data-ttu-id="b0f0d-342">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="b0f0d-343">9</span><span class="sxs-lookup"><span data-stu-id="b0f0d-343">9</span></span>|<span data-ttu-id="b0f0d-344">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="b0f0d-345">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-346">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-346">Field name</span></span>|<span data-ttu-id="b0f0d-347">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-347">Data type</span></span>|<span data-ttu-id="b0f0d-348">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-349">Reason</span></span>|<span data-ttu-id="b0f0d-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-350">win:UInt16</span></span>|<span data-ttu-id="b0f0d-351">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="b0f0d-352">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="b0f0d-353">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="b0f0d-354">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="b0f0d-355">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="b0f0d-356">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="b0f0d-357">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="b0f0d-358">Recuento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-358">Count</span></span>|<span data-ttu-id="b0f0d-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-359">win:UInt32</span></span>|<span data-ttu-id="b0f0d-360">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-360">The GC count at the time.</span></span> <span data-ttu-id="b0f0d-361">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="b0f0d-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-362">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-363">win:UInt16</span></span>|<span data-ttu-id="b0f0d-364">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-365">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="b0f0d-366">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-367">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="b0f0d-368">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-368">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-369">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-372">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="b0f0d-373">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-373">Event</span></span>|<span data-ttu-id="b0f0d-374">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-374">Event ID</span></span>|<span data-ttu-id="b0f0d-375">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="b0f0d-376">8</span><span class="sxs-lookup"><span data-stu-id="b0f0d-376">8</span></span>|<span data-ttu-id="b0f0d-377">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="b0f0d-378">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-378">No event data.</span></span>  
  
 [<span data-ttu-id="b0f0d-379">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="b0f0d-380">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="b0f0d-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="b0f0d-381">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-382">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-382">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-383">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-386">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-387">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-387">Event</span></span>|<span data-ttu-id="b0f0d-388">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-388">Event ID</span></span>|<span data-ttu-id="b0f0d-389">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="b0f0d-390">10</span><span class="sxs-lookup"><span data-stu-id="b0f0d-390">10</span></span>|<span data-ttu-id="b0f0d-391">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="b0f0d-392">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-393">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-393">Field name</span></span>|<span data-ttu-id="b0f0d-394">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-394">Data type</span></span>|<span data-ttu-id="b0f0d-395">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="b0f0d-396">AllocationAmount</span></span>|<span data-ttu-id="b0f0d-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-397">win:UInt32</span></span>|<span data-ttu-id="b0f0d-398">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-398">The allocation size, in bytes.</span></span> <span data-ttu-id="b0f0d-399">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="b0f0d-400">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="b0f0d-401">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="b0f0d-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="b0f0d-402">AllocationKind</span></span>|<span data-ttu-id="b0f0d-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-403">win:UInt32</span></span>|<span data-ttu-id="b0f0d-404">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="b0f0d-405">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="b0f0d-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-406">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-407">win:UInt16</span></span>|<span data-ttu-id="b0f0d-408">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="b0f0d-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-409">AllocationAmount64</span></span>|<span data-ttu-id="b0f0d-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b0f0d-410">win:UInt64</span></span>|<span data-ttu-id="b0f0d-411">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-411">The allocation size, in bytes.</span></span> <span data-ttu-id="b0f0d-412">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="b0f0d-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="b0f0d-413">TypeId</span></span>|<span data-ttu-id="b0f0d-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="b0f0d-414">win:Pointer</span></span>|<span data-ttu-id="b0f0d-415">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-415">The address of the MethodTable.</span></span> <span data-ttu-id="b0f0d-416">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="b0f0d-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="b0f0d-417">TypeName</span></span>|<span data-ttu-id="b0f0d-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b0f0d-418">win:UnicodeString</span></span>|<span data-ttu-id="b0f0d-419">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-419">The name of the type that was allocated.</span></span> <span data-ttu-id="b0f0d-420">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="b0f0d-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="b0f0d-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="b0f0d-421">HeapIndex</span></span>|<span data-ttu-id="b0f0d-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-422">win:UInt32</span></span>|<span data-ttu-id="b0f0d-423">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-423">The heap where the object was allocated.</span></span> <span data-ttu-id="b0f0d-424">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="b0f0d-425">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="b0f0d-426">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-427">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-428">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-428">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-429">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-432">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-433">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-433">Event</span></span>|<span data-ttu-id="b0f0d-434">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-434">Event ID</span></span>|<span data-ttu-id="b0f0d-435">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="b0f0d-436">14</span><span class="sxs-lookup"><span data-stu-id="b0f0d-436">14</span></span>|<span data-ttu-id="b0f0d-437">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="b0f0d-438">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-438">No event data.</span></span>  
  
 [<span data-ttu-id="b0f0d-439">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="b0f0d-440">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-441">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-442">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-442">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-443">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-446">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-447">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-447">Event</span></span>|<span data-ttu-id="b0f0d-448">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-448">Event ID</span></span>|<span data-ttu-id="b0f0d-449">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="b0f0d-450">13</span><span class="sxs-lookup"><span data-stu-id="b0f0d-450">13</span></span>|<span data-ttu-id="b0f0d-451">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="b0f0d-452">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b0f0d-453">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b0f0d-453">Field name</span></span>|<span data-ttu-id="b0f0d-454">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b0f0d-454">Data type</span></span>|<span data-ttu-id="b0f0d-455">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f0d-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b0f0d-456">Recuento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-456">Count</span></span>|<span data-ttu-id="b0f0d-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b0f0d-457">win:UInt32</span></span>|<span data-ttu-id="b0f0d-458">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="b0f0d-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b0f0d-459">ClrInstanceID</span></span>|<span data-ttu-id="b0f0d-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b0f0d-460">win:UInt16</span></span>|<span data-ttu-id="b0f0d-461">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b0f0d-462">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="b0f0d-463">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-464">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-465">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-465">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-466">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-468">Informational (4)</span></span>|  
|<span data-ttu-id="b0f0d-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b0f0d-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-471">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-472">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-472">Event</span></span>|<span data-ttu-id="b0f0d-473">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-473">Event ID</span></span>|<span data-ttu-id="b0f0d-474">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="b0f0d-475">11</span><span class="sxs-lookup"><span data-stu-id="b0f0d-475">11</span></span>|<span data-ttu-id="b0f0d-476">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="b0f0d-477">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-477">No event data.</span></span>  
  
 [<span data-ttu-id="b0f0d-478">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b0f0d-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="b0f0d-479">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="b0f0d-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="b0f0d-480">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b0f0d-481">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-481">Keyword for raising the event</span></span>|<span data-ttu-id="b0f0d-482">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0f0d-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b0f0d-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="b0f0d-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-484">Informational (4)</span></span>|  
|<span data-ttu-id="b0f0d-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b0f0d-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="b0f0d-487">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b0f0d-488">Evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-488">Event</span></span>|<span data-ttu-id="b0f0d-489">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b0f0d-489">Event ID</span></span>|<span data-ttu-id="b0f0d-490">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b0f0d-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="b0f0d-491">12</span><span class="sxs-lookup"><span data-stu-id="b0f0d-491">12</span></span>|<span data-ttu-id="b0f0d-492">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="b0f0d-493">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b0f0d-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f0d-494">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0f0d-494">See Also</span></span>  
 [<span data-ttu-id="b0f0d-495">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="b0f0d-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
