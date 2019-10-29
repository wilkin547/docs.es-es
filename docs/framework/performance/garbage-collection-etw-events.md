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
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040581"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="1dc08-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="1dc08-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="1dc08-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="1dc08-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="1dc08-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="1dc08-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="1dc08-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="1dc08-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="1dc08-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="1dc08-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="1dc08-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="1dc08-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="1dc08-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="1dc08-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="1dc08-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="1dc08-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="1dc08-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="1dc08-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="1dc08-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="1dc08-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="1dc08-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="1dc08-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="1dc08-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="1dc08-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="1dc08-122">Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1dc08-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="1dc08-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-123">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-126">Informational (4)</span></span>|

<span data-ttu-id="1dc08-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-127">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-128">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-128">Event</span></span>|<span data-ttu-id="1dc08-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-129">Event ID</span></span>|<span data-ttu-id="1dc08-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="1dc08-131">1</span><span class="sxs-lookup"><span data-stu-id="1dc08-131">1</span></span>|<span data-ttu-id="1dc08-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-132">A garbage collection has started.</span></span>|

<span data-ttu-id="1dc08-133">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-133">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-134">Field name</span></span>|<span data-ttu-id="1dc08-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-135">Data type</span></span>|<span data-ttu-id="1dc08-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-137">Recuento</span><span class="sxs-lookup"><span data-stu-id="1dc08-137">Count</span></span>|<span data-ttu-id="1dc08-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-138">win:UInt32</span></span>|<span data-ttu-id="1dc08-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="1dc08-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="1dc08-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="1dc08-140">Depth</span></span>|<span data-ttu-id="1dc08-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-141">win:UInt32</span></span>|<span data-ttu-id="1dc08-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="1dc08-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="1dc08-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="1dc08-143">Reason</span></span>|<span data-ttu-id="1dc08-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-144">win:UInt32</span></span>|<span data-ttu-id="1dc08-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="1dc08-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="1dc08-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="1dc08-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="1dc08-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="1dc08-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="1dc08-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="1dc08-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="1dc08-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="1dc08-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="1dc08-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="1dc08-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="1dc08-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="1dc08-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="1dc08-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="1dc08-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1dc08-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="1dc08-154">Type</span><span class="sxs-lookup"><span data-stu-id="1dc08-154">Type</span></span>|<span data-ttu-id="1dc08-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-155">win:UInt32</span></span>|<span data-ttu-id="1dc08-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1dc08-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="1dc08-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1dc08-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="1dc08-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1dc08-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="1dc08-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-159">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-160">win:UInt16</span></span>|<span data-ttu-id="1dc08-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="1dc08-162">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="1dc08-163">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-164">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-164">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-165">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-167">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-167">Informational (4)</span></span>|

<span data-ttu-id="1dc08-168">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-168">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-169">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-169">Event</span></span>|<span data-ttu-id="1dc08-170">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-170">Event ID</span></span>|<span data-ttu-id="1dc08-171">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="1dc08-172">2</span><span class="sxs-lookup"><span data-stu-id="1dc08-172">2</span></span>|<span data-ttu-id="1dc08-173">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="1dc08-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="1dc08-174">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-174">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-175">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-175">Field name</span></span>|<span data-ttu-id="1dc08-176">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-176">Data type</span></span>|<span data-ttu-id="1dc08-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-178">Recuento</span><span class="sxs-lookup"><span data-stu-id="1dc08-178">Count</span></span>|<span data-ttu-id="1dc08-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-179">win:UInt32</span></span>|<span data-ttu-id="1dc08-180">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="1dc08-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="1dc08-181">Profundidad</span><span class="sxs-lookup"><span data-stu-id="1dc08-181">Depth</span></span>|<span data-ttu-id="1dc08-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-182">win:UInt32</span></span>|<span data-ttu-id="1dc08-183">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="1dc08-183">The generation that was collected.</span></span>|
|<span data-ttu-id="1dc08-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-184">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-185">win:UInt16</span></span>|<span data-ttu-id="1dc08-186">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="1dc08-187">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="1dc08-188">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-189">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-189">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-190">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-192">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-192">Informational (4)</span></span>|

<span data-ttu-id="1dc08-193">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-193">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-194">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-194">Event</span></span>|<span data-ttu-id="1dc08-195">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-195">Event ID</span></span>|<span data-ttu-id="1dc08-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="1dc08-197">4</span><span class="sxs-lookup"><span data-stu-id="1dc08-197">4</span></span>|<span data-ttu-id="1dc08-198">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="1dc08-199">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-199">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-200">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-200">Field name</span></span>|<span data-ttu-id="1dc08-201">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-201">Data type</span></span>|<span data-ttu-id="1dc08-202">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="1dc08-203">GenerationSize0</span></span>|<span data-ttu-id="1dc08-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-204">win:UInt64</span></span>|<span data-ttu-id="1dc08-205">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="1dc08-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="1dc08-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="1dc08-206">TotalPromotedSize0</span></span>|<span data-ttu-id="1dc08-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-207">win:UInt64</span></span>|<span data-ttu-id="1dc08-208">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="1dc08-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="1dc08-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="1dc08-209">GenerationSize1</span></span>|<span data-ttu-id="1dc08-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-210">win:UInt64</span></span>|<span data-ttu-id="1dc08-211">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="1dc08-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="1dc08-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="1dc08-212">TotalPromotedSize1</span></span>|<span data-ttu-id="1dc08-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-213">win:UInt64</span></span>|<span data-ttu-id="1dc08-214">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="1dc08-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="1dc08-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="1dc08-215">GenerationSize2</span></span>|<span data-ttu-id="1dc08-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-216">win:UInt64</span></span>|<span data-ttu-id="1dc08-217">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="1dc08-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="1dc08-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="1dc08-218">TotalPromotedSize2</span></span>|<span data-ttu-id="1dc08-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-219">win:UInt64</span></span>|<span data-ttu-id="1dc08-220">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="1dc08-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="1dc08-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="1dc08-221">GenerationSize3</span></span>|<span data-ttu-id="1dc08-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-222">win:UInt64</span></span>|<span data-ttu-id="1dc08-223">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="1dc08-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="1dc08-224">TotalPromotedSize3</span></span>|<span data-ttu-id="1dc08-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-225">win:UInt64</span></span>|<span data-ttu-id="1dc08-226">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="1dc08-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="1dc08-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="1dc08-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="1dc08-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-228">win:UInt64</span></span>|<span data-ttu-id="1dc08-229">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="1dc08-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="1dc08-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="1dc08-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="1dc08-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-231">win:UInt64</span></span>|<span data-ttu-id="1dc08-232">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="1dc08-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="1dc08-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="1dc08-233">PinnedObjectCount</span></span>|<span data-ttu-id="1dc08-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-234">win:UInt32</span></span>|<span data-ttu-id="1dc08-235">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="1dc08-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="1dc08-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="1dc08-236">SinkBlockCount</span></span>|<span data-ttu-id="1dc08-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-237">win:UInt32</span></span>|<span data-ttu-id="1dc08-238">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="1dc08-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="1dc08-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="1dc08-239">GCHandleCount</span></span>|<span data-ttu-id="1dc08-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-240">win:UInt32</span></span>|<span data-ttu-id="1dc08-241">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="1dc08-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="1dc08-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-242">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-243">win:UInt16</span></span>|<span data-ttu-id="1dc08-244">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="1dc08-245">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="1dc08-246">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-247">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-247">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-248">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-250">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-250">Informational (4)</span></span>|

<span data-ttu-id="1dc08-251">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-251">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-252">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-252">Event</span></span>|<span data-ttu-id="1dc08-253">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-253">Event ID</span></span>|<span data-ttu-id="1dc08-254">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="1dc08-255">5</span><span class="sxs-lookup"><span data-stu-id="1dc08-255">5</span></span>|<span data-ttu-id="1dc08-256">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="1dc08-257">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="1dc08-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="1dc08-258">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-258">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-259">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-259">Field name</span></span>|<span data-ttu-id="1dc08-260">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-260">Data type</span></span>|<span data-ttu-id="1dc08-261">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-262">Dirección</span><span class="sxs-lookup"><span data-stu-id="1dc08-262">Address</span></span>|<span data-ttu-id="1dc08-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-263">win:UInt64</span></span>|<span data-ttu-id="1dc08-264">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-264">The address of the segment.</span></span>|
|<span data-ttu-id="1dc08-265">Tamaño</span><span class="sxs-lookup"><span data-stu-id="1dc08-265">Size</span></span>|<span data-ttu-id="1dc08-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-266">win:UInt64</span></span>|<span data-ttu-id="1dc08-267">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-267">The size of the segment.</span></span>|
|<span data-ttu-id="1dc08-268">Type</span><span class="sxs-lookup"><span data-stu-id="1dc08-268">Type</span></span>|<span data-ttu-id="1dc08-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-269">win:UInt32</span></span>|<span data-ttu-id="1dc08-270">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="1dc08-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="1dc08-271">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="1dc08-272">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1dc08-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="1dc08-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-273">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-274">win:UInt16</span></span>|<span data-ttu-id="1dc08-275">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="1dc08-276">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="1dc08-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="1dc08-277">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="1dc08-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="1dc08-278">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="1dc08-279">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-280">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-280">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-281">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-283">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-283">Informational (4)</span></span>|

<span data-ttu-id="1dc08-284">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-284">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-285">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-285">Event</span></span>|<span data-ttu-id="1dc08-286">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-286">Event ID</span></span>|<span data-ttu-id="1dc08-287">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="1dc08-288">6</span><span class="sxs-lookup"><span data-stu-id="1dc08-288">6</span></span>|<span data-ttu-id="1dc08-289">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="1dc08-290">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-290">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-291">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-291">Field name</span></span>|<span data-ttu-id="1dc08-292">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-292">Data type</span></span>|<span data-ttu-id="1dc08-293">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-294">Dirección</span><span class="sxs-lookup"><span data-stu-id="1dc08-294">Address</span></span>|<span data-ttu-id="1dc08-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-295">win:UInt64</span></span>|<span data-ttu-id="1dc08-296">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-296">The address of the segment.</span></span>|
|<span data-ttu-id="1dc08-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-297">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-298">win:UInt16</span></span>|<span data-ttu-id="1dc08-299">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="1dc08-300">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="1dc08-301">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-302">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-302">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-303">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-305">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-305">Informational (4)</span></span>|

<span data-ttu-id="1dc08-306">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-306">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-307">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-307">Event</span></span>|<span data-ttu-id="1dc08-308">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-308">Event ID</span></span>|<span data-ttu-id="1dc08-309">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="1dc08-310">7</span><span class="sxs-lookup"><span data-stu-id="1dc08-310">7</span></span>|<span data-ttu-id="1dc08-311">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1dc08-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="1dc08-312">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="1dc08-313">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="1dc08-314">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-315">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-315">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-316">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-318">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-318">Informational (4)</span></span>|

<span data-ttu-id="1dc08-319">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-319">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-320">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-320">Event</span></span>|<span data-ttu-id="1dc08-321">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-321">Event Id</span></span>|<span data-ttu-id="1dc08-322">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="1dc08-323">3</span><span class="sxs-lookup"><span data-stu-id="1dc08-323">3</span></span>|<span data-ttu-id="1dc08-324">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1dc08-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="1dc08-325">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="1dc08-326">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="1dc08-327">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-328">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-328">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-329">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-331">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-331">Informational (4)</span></span>|

<span data-ttu-id="1dc08-332">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-332">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-333">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-333">Event</span></span>|<span data-ttu-id="1dc08-334">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-334">Event ID</span></span>|<span data-ttu-id="1dc08-335">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="1dc08-336">9</span><span class="sxs-lookup"><span data-stu-id="1dc08-336">9</span></span>|<span data-ttu-id="1dc08-337">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="1dc08-338">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-338">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-339">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-339">Field name</span></span>|<span data-ttu-id="1dc08-340">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-340">Data type</span></span>|<span data-ttu-id="1dc08-341">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-342">Motivo</span><span class="sxs-lookup"><span data-stu-id="1dc08-342">Reason</span></span>|<span data-ttu-id="1dc08-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-343">win:UInt16</span></span>|<span data-ttu-id="1dc08-344">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="1dc08-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="1dc08-345">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="1dc08-346">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1dc08-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="1dc08-347">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="1dc08-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="1dc08-348">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="1dc08-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="1dc08-349">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="1dc08-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="1dc08-350">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="1dc08-351">Recuento</span><span class="sxs-lookup"><span data-stu-id="1dc08-351">Count</span></span>|<span data-ttu-id="1dc08-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-352">win:UInt32</span></span>|<span data-ttu-id="1dc08-353">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-353">The GC count at the time.</span></span> <span data-ttu-id="1dc08-354">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="1dc08-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-355">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-356">win:UInt16</span></span>|<span data-ttu-id="1dc08-357">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="1dc08-358">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="1dc08-359">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-360">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-360">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-361">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-363">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-363">Informational (4)</span></span>|

<span data-ttu-id="1dc08-364">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-364">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-365">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-365">Event</span></span>|<span data-ttu-id="1dc08-366">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-366">Event ID</span></span>|<span data-ttu-id="1dc08-367">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="1dc08-368">8</span><span class="sxs-lookup"><span data-stu-id="1dc08-368">8</span></span>|<span data-ttu-id="1dc08-369">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1dc08-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="1dc08-370">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="1dc08-371">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="1dc08-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="1dc08-372">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-373">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-373">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-374">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-376">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-376">Informational (4)</span></span>|

<span data-ttu-id="1dc08-377">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-377">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-378">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-378">Event</span></span>|<span data-ttu-id="1dc08-379">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-379">Event ID</span></span>|<span data-ttu-id="1dc08-380">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="1dc08-381">10</span><span class="sxs-lookup"><span data-stu-id="1dc08-381">10</span></span>|<span data-ttu-id="1dc08-382">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="1dc08-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="1dc08-383">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-383">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-384">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-384">Field name</span></span>|<span data-ttu-id="1dc08-385">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-385">Data type</span></span>|<span data-ttu-id="1dc08-386">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="1dc08-387">AllocationAmount</span></span>|<span data-ttu-id="1dc08-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-388">win:UInt32</span></span>|<span data-ttu-id="1dc08-389">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-389">The allocation size, in bytes.</span></span> <span data-ttu-id="1dc08-390">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="1dc08-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="1dc08-391">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="1dc08-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="1dc08-392">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="1dc08-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="1dc08-393">AllocationKind</span></span>|<span data-ttu-id="1dc08-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-394">win:UInt32</span></span>|<span data-ttu-id="1dc08-395">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="1dc08-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="1dc08-396">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="1dc08-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="1dc08-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-397">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-398">win:UInt16</span></span>|<span data-ttu-id="1dc08-399">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="1dc08-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="1dc08-400">AllocationAmount64</span></span>|<span data-ttu-id="1dc08-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1dc08-401">win:UInt64</span></span>|<span data-ttu-id="1dc08-402">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-402">The allocation size, in bytes.</span></span> <span data-ttu-id="1dc08-403">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="1dc08-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="1dc08-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="1dc08-404">TypeId</span></span>|<span data-ttu-id="1dc08-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="1dc08-405">win:Pointer</span></span>|<span data-ttu-id="1dc08-406">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="1dc08-406">The address of the MethodTable.</span></span> <span data-ttu-id="1dc08-407">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="1dc08-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="1dc08-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="1dc08-408">TypeName</span></span>|<span data-ttu-id="1dc08-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="1dc08-409">win:UnicodeString</span></span>|<span data-ttu-id="1dc08-410">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="1dc08-410">The name of the type that was allocated.</span></span> <span data-ttu-id="1dc08-411">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="1dc08-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="1dc08-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="1dc08-412">HeapIndex</span></span>|<span data-ttu-id="1dc08-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-413">win:UInt32</span></span>|<span data-ttu-id="1dc08-414">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="1dc08-414">The heap where the object was allocated.</span></span> <span data-ttu-id="1dc08-415">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1dc08-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="1dc08-416">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="1dc08-417">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-418">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-418">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-419">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-421">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-421">Informational (4)</span></span>|

<span data-ttu-id="1dc08-422">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-422">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-423">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-423">Event</span></span>|<span data-ttu-id="1dc08-424">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-424">Event ID</span></span>|<span data-ttu-id="1dc08-425">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="1dc08-426">14</span><span class="sxs-lookup"><span data-stu-id="1dc08-426">14</span></span>|<span data-ttu-id="1dc08-427">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1dc08-427">The start of running finalizers.</span></span>|

<span data-ttu-id="1dc08-428">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="1dc08-429">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="1dc08-430">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-431">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-431">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-432">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-434">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-434">Informational (4)</span></span>|

<span data-ttu-id="1dc08-435">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-435">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-436">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-436">Event</span></span>|<span data-ttu-id="1dc08-437">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-437">Event ID</span></span>|<span data-ttu-id="1dc08-438">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="1dc08-439">13</span><span class="sxs-lookup"><span data-stu-id="1dc08-439">13</span></span>|<span data-ttu-id="1dc08-440">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1dc08-440">The end of running finalizers.</span></span>|

<span data-ttu-id="1dc08-441">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1dc08-441">The following table shows the event data:</span></span>

|<span data-ttu-id="1dc08-442">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1dc08-442">Field name</span></span>|<span data-ttu-id="1dc08-443">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1dc08-443">Data type</span></span>|<span data-ttu-id="1dc08-444">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dc08-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1dc08-445">Recuento</span><span class="sxs-lookup"><span data-stu-id="1dc08-445">Count</span></span>|<span data-ttu-id="1dc08-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1dc08-446">win:UInt32</span></span>|<span data-ttu-id="1dc08-447">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="1dc08-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="1dc08-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1dc08-448">ClrInstanceID</span></span>|<span data-ttu-id="1dc08-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1dc08-449">win:UInt16</span></span>|<span data-ttu-id="1dc08-450">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1dc08-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="1dc08-451">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="1dc08-452">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-453">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-453">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-454">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-456">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-456">Informational (4)</span></span>|
|<span data-ttu-id="1dc08-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1dc08-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1dc08-458">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-458">Informational (4)</span></span>|

<span data-ttu-id="1dc08-459">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-459">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-460">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-460">Event</span></span>|<span data-ttu-id="1dc08-461">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-461">Event ID</span></span>|<span data-ttu-id="1dc08-462">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="1dc08-463">11</span><span class="sxs-lookup"><span data-stu-id="1dc08-463">11</span></span>|<span data-ttu-id="1dc08-464">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="1dc08-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="1dc08-465">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="1dc08-466">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="1dc08-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="1dc08-467">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1dc08-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1dc08-468">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-468">Keyword for raising the event</span></span>|<span data-ttu-id="1dc08-469">Nivel</span><span class="sxs-lookup"><span data-stu-id="1dc08-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1dc08-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1dc08-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1dc08-471">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-471">Informational (4)</span></span>|
|<span data-ttu-id="1dc08-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1dc08-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1dc08-473">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1dc08-473">Informational (4)</span></span>|

<span data-ttu-id="1dc08-474">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-474">The following table shows the event information:</span></span>

|<span data-ttu-id="1dc08-475">evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-475">Event</span></span>|<span data-ttu-id="1dc08-476">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1dc08-476">Event ID</span></span>|<span data-ttu-id="1dc08-477">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1dc08-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="1dc08-478">12</span><span class="sxs-lookup"><span data-stu-id="1dc08-478">12</span></span>|<span data-ttu-id="1dc08-479">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="1dc08-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="1dc08-480">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="1dc08-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dc08-481">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dc08-481">See also</span></span>

- [<span data-ttu-id="1dc08-482">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="1dc08-482">CLR ETW Events</span></span>](clr-etw-events.md)
