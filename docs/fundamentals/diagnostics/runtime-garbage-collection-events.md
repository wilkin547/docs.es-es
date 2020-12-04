---
title: Eventos de Runtime de recolección de elementos no utilizados
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica del recolector de elementos no utilizados de .NET.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- GC events
- garbage collection events (CoreCLR)
- ETW, EventPipe, LTTng garbage collection events (CoreCLR)
ms.openlocfilehash: 2799a93f351baf23ec7a359b0b4b2be5c216dc4d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594707"
---
# <a name="net-runtime-garbage-collection-events"></a><span data-ttu-id="ec960-103">Eventos de recolección de elementos no utilizados de .NET Runtime</span><span class="sxs-lookup"><span data-stu-id="ec960-103">.NET runtime garbage collection events</span></span>

<span data-ttu-id="ec960-104">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-104">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="ec960-105">Ayudan en el diagnóstico y la depuración, incluida la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="ec960-105">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, etc. For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="gcstart_v2-event"></a><span data-ttu-id="ec960-106">Evento GCStart_V2</span><span class="sxs-lookup"><span data-stu-id="ec960-106">GCStart_V2 Event</span></span>

<span data-ttu-id="ec960-107">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-107">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-108">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-108">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-110">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-110">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-111">Informational (4)</span></span>|

<span data-ttu-id="ec960-112">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-112">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-113">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-113">Event</span></span>|<span data-ttu-id="ec960-114">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-114">Event ID</span></span>|<span data-ttu-id="ec960-115">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="ec960-116">1</span><span class="sxs-lookup"><span data-stu-id="ec960-116">1</span></span>|<span data-ttu-id="ec960-117">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-117">A garbage collection has started.</span></span>|

<span data-ttu-id="ec960-118">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-118">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-119">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-119">Field name</span></span>|<span data-ttu-id="ec960-120">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-120">Data type</span></span>|<span data-ttu-id="ec960-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-121">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="ec960-122">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="ec960-122">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="ec960-123">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="ec960-123">The generation that is being collected.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="ec960-124">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="ec960-124">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="ec960-125">`0x0` -Asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="ec960-125">`0x0` - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="ec960-126">`0x1` Inducida.</span><span class="sxs-lookup"><span data-stu-id="ec960-126">`0x1` - Induced.</span></span><br /><br /> <span data-ttu-id="ec960-127">`0x2` -Memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="ec960-127">`0x2` - Low memory.</span></span><br /><br /> <span data-ttu-id="ec960-128">`0x3` Vacía.</span><span class="sxs-lookup"><span data-stu-id="ec960-128">`0x3` - Empty.</span></span><br /><br /> <span data-ttu-id="ec960-129">`0x4` -Asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ec960-129">`0x4` - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="ec960-130">`0x5` -Espacio insuficiente (para el montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="ec960-130">`0x5` - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="ec960-131">`0x6` -Espacio insuficiente (para el montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="ec960-131">`0x6` - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="ec960-132">`0x7` -Inducido pero no forzado como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ec960-132">`0x7` - Induced but not forced as blocking.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="ec960-133">`0x0` -La recolección de elementos no utilizados bloqueada fuera de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-133">`0x0` - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="ec960-134">`0x1` -Recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="ec960-134">`0x1` - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="ec960-135">`0x2` -La recolección de elementos no utilizados bloqueada durante la recolección de elementos no utilizados en segundo plano</span><span class="sxs-lookup"><span data-stu-id="ec960-135">`0x2` - Blocking garbage collection occurred during background garbage collection.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="ec960-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-136">win:UInt16</span></span>|<span data-ttu-id="ec960-137">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-137">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="ec960-138">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-138">GCEnd_V1 Event</span></span>

<span data-ttu-id="ec960-139">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-139">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-140">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-140">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-141">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-141">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-142">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-142">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-143">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-143">Informational (4)</span></span>|

<span data-ttu-id="ec960-144">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-144">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-145">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-145">Event</span></span>|<span data-ttu-id="ec960-146">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-146">Event ID</span></span>|<span data-ttu-id="ec960-147">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-147">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="ec960-148">2</span><span class="sxs-lookup"><span data-stu-id="ec960-148">2</span></span>|<span data-ttu-id="ec960-149">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="ec960-149">The garbage collection has ended.</span></span>|

<span data-ttu-id="ec960-150">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-150">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-151">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-151">Field name</span></span>|<span data-ttu-id="ec960-152">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-152">Data type</span></span>|<span data-ttu-id="ec960-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-153">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="ec960-154">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="ec960-154">The *n* th garbage collection.</span></span>|
|`Depth`|`win:UInt32`|<span data-ttu-id="ec960-155">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="ec960-155">The generation that was collected.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="ec960-156">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-156">win:UInt16</span></span>|<span data-ttu-id="ec960-157">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-157">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcheapstats_v2-event"></a><span data-ttu-id="ec960-158">Evento GCHeapStats_V2</span><span class="sxs-lookup"><span data-stu-id="ec960-158">GCHeapStats_V2 Event</span></span>

<span data-ttu-id="ec960-159">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-159">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-160">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-160">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-161">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-161">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-162">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-162">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-163">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-163">Informational (4)</span></span>|

<span data-ttu-id="ec960-164">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-164">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-165">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-165">Event</span></span>|<span data-ttu-id="ec960-166">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-166">Event ID</span></span>|<span data-ttu-id="ec960-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-167">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V2`|<span data-ttu-id="ec960-168">4</span><span class="sxs-lookup"><span data-stu-id="ec960-168">4</span></span>|<span data-ttu-id="ec960-169">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-169">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="ec960-170">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-170">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-171">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-171">Field name</span></span>|<span data-ttu-id="ec960-172">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-172">Data type</span></span>|<span data-ttu-id="ec960-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-173">Description</span></span>|
|----------------|---------------|-----------------|
|`GenerationSize0`|`win:UInt64`|<span data-ttu-id="ec960-174">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="ec960-174">The size, in bytes, of generation 0 memory.</span></span>|
|`TotalPromotedSize0`|`win:UInt64`|<span data-ttu-id="ec960-175">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="ec960-175">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|`GenerationSize1`|`win:UInt64`|<span data-ttu-id="ec960-176">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="ec960-176">The size, in bytes, of generation 1 memory.</span></span>|
|`TotalPromotedSize1`|`win:UInt64`|<span data-ttu-id="ec960-177">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="ec960-177">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|`GenerationSize2`|`win:UInt64`|<span data-ttu-id="ec960-178">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="ec960-178">The size, in bytes, of generation 2 memory.</span></span>|
|`TotalPromotedSize2`|`win:UInt64`|<span data-ttu-id="ec960-179">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="ec960-179">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|`GenerationSize3`|`win:UInt64`|<span data-ttu-id="ec960-180">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ec960-180">The size, in bytes, of the large object heap.</span></span>|
|`TotalPromotedSize3`|`win:UInt64`|<span data-ttu-id="ec960-181">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="ec960-181">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|`FinalizationPromotedSize`|`win:UInt64`|<span data-ttu-id="ec960-182">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="ec960-182">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|`FinalizationPromotedCount`|`win:UInt64`|<span data-ttu-id="ec960-183">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="ec960-183">The number of objects that are ready for finalization.</span></span>|
|`PinnedObjectCount`|`win:UInt32`|<span data-ttu-id="ec960-184">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="ec960-184">The number of pinned (unmovable) objects.</span></span>|
|`SinkBlockCount`|`win:UInt32`|<span data-ttu-id="ec960-185">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="ec960-185">The number of synchronization blocks in use.</span></span>|
|`GCHandleCount`|`win:UInt32`|<span data-ttu-id="ec960-186">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="ec960-186">The number of garbage collection handles in use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-187">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-187">Unique ID for the instance of CoreCLR.</span></span>|
|`GenerationSize4`|`win:UInt64`|<span data-ttu-id="ec960-188">Tamaño, en bytes, del montón de objetos anclados.</span><span class="sxs-lookup"><span data-stu-id="ec960-188">The size, in bytes, of the pinned object heap.</span></span>|
|`TotalPromotedSize4`|`win:UInt64`|<span data-ttu-id="ec960-189">Número de bytes que sobrevivieron en el montón de objetos anclados después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="ec960-189">The number of bytes that survived in the pinned object heap after the last collection.</span></span>|

## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="ec960-190">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-190">GCCreateSegment_V1 event</span></span>

<span data-ttu-id="ec960-191">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-191">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-192">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-192">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-193">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-193">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-194">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-194">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-195">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-195">Informational (4)</span></span>|

<span data-ttu-id="ec960-196">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-196">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-197">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-197">Event</span></span>|<span data-ttu-id="ec960-198">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-198">Event ID</span></span>|<span data-ttu-id="ec960-199">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-199">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="ec960-200">5</span><span class="sxs-lookup"><span data-stu-id="ec960-200">5</span></span>|<span data-ttu-id="ec960-201">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-201">A new garbage collection segment has been created.</span></span> <span data-ttu-id="ec960-202">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="ec960-202">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="ec960-203">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-203">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-204">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-204">Field name</span></span>|<span data-ttu-id="ec960-205">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-205">Data type</span></span>|<span data-ttu-id="ec960-206">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-206">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="ec960-207">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="ec960-207">The address of the segment.</span></span>|
|`Size`|`win:UInt64`|<span data-ttu-id="ec960-208">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="ec960-208">The size of the segment.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="ec960-209">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="ec960-209">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="ec960-210">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="ec960-210">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="ec960-211">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="ec960-211">0x2 - Read-only heap.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-212">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-212">Unique ID for the instance of CoreCLR.</span></span>|

<span data-ttu-id="ec960-213">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="ec960-213">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="ec960-214">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="ec960-214">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="ec960-215">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-215">GCFreeSegment_V1 event</span></span>

<span data-ttu-id="ec960-216">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-216">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-217">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-217">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-218">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-218">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-219">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-219">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-220">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-220">Informational (4)</span></span>|

<span data-ttu-id="ec960-221">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-221">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-222">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-222">Event</span></span>|<span data-ttu-id="ec960-223">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-223">Event ID</span></span>|<span data-ttu-id="ec960-224">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-224">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="ec960-225">6</span><span class="sxs-lookup"><span data-stu-id="ec960-225">6</span></span>|<span data-ttu-id="ec960-226">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-226">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="ec960-227">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-227">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-228">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-228">Field name</span></span>|<span data-ttu-id="ec960-229">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-229">Data type</span></span>|<span data-ttu-id="ec960-230">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-230">Description</span></span>|
|----------------|---------------|-----------------|
|`Address`|`win:UInt64`|<span data-ttu-id="ec960-231">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="ec960-231">The address of the segment.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-232">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-232">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="ec960-233">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-233">GCRestartEEBegin_V1 event</span></span>

<span data-ttu-id="ec960-234">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-234">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-235">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-235">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-236">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-236">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-237">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-237">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-238">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-238">Informational (4)</span></span>|

<span data-ttu-id="ec960-239">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-239">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-240">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-240">Event</span></span>|<span data-ttu-id="ec960-241">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-241">Event ID</span></span>|<span data-ttu-id="ec960-242">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-242">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="ec960-243">7</span><span class="sxs-lookup"><span data-stu-id="ec960-243">7</span></span>|<span data-ttu-id="ec960-244">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ec960-244">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="ec960-245">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-245">This event does not have any event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="ec960-246">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-246">GCRestartEEEnd_V1 event</span></span>

<span data-ttu-id="ec960-247">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-247">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-248">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-248">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-249">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-249">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-250">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-250">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-251">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-251">Informational (4)</span></span>|

<span data-ttu-id="ec960-252">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-252">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-253">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-253">Event</span></span>|<span data-ttu-id="ec960-254">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-254">Event Id</span></span>|<span data-ttu-id="ec960-255">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-255">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="ec960-256">3</span><span class="sxs-lookup"><span data-stu-id="ec960-256">3</span></span>|<span data-ttu-id="ec960-257">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ec960-257">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="ec960-258">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-258">This event does not have any event data.</span></span>

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="ec960-259">Evento GCSuspendEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-259">GCSuspendEEEnd_V1 event</span></span>

<span data-ttu-id="ec960-260">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-260">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-261">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-261">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-262">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-262">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-263">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-263">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-264">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-264">Informational (4)</span></span>|

<span data-ttu-id="ec960-265">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-265">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-266">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-266">Event</span></span>|<span data-ttu-id="ec960-267">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-267">Event ID</span></span>|<span data-ttu-id="ec960-268">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-268">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="ec960-269">8</span><span class="sxs-lookup"><span data-stu-id="ec960-269">8</span></span>|<span data-ttu-id="ec960-270">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-270">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="ec960-271">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-271">This event does not have any event data.</span></span>

## <a name="gcsuspendeebegin_v1-event"></a><span data-ttu-id="ec960-272">Evento GCSuspendEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-272">GCSuspendEEBegin_V1 event</span></span>

<span data-ttu-id="ec960-273">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-273">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-274">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-274">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-275">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-275">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-276">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-276">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-277">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-277">Informational (4)</span></span>|

<span data-ttu-id="ec960-278">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-278">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-279">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-279">Event</span></span>|<span data-ttu-id="ec960-280">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-280">Event ID</span></span>|<span data-ttu-id="ec960-281">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-281">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEBegin_V1`|<span data-ttu-id="ec960-282">8</span><span class="sxs-lookup"><span data-stu-id="ec960-282">8</span></span>|<span data-ttu-id="ec960-283">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ec960-283">Start of suspension of the execution engine for garbage collection.</span></span>|

|<span data-ttu-id="ec960-284">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-284">Field name</span></span>|<span data-ttu-id="ec960-285">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-285">Data type</span></span>|<span data-ttu-id="ec960-286">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-286">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="ec960-287">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="ec960-287">The *n* th garbage collection.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="ec960-288">Motivo de la suspensión de EE.</span><span class="sxs-lookup"><span data-stu-id="ec960-288">Reason for EE suspension.</span></span><br/><br/><span data-ttu-id="ec960-289">`0x0`: Suspender para otros</span><span class="sxs-lookup"><span data-stu-id="ec960-289">`0x0`: Suspend for Other</span></span><br/><br/><span data-ttu-id="ec960-290">`0x1`: Suspender para GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-290">`0x1`: Suspend for GC.</span></span><br/><br/><span data-ttu-id="ec960-291">`0x2`: Suspender para el cierre de AppDomain.</span><span class="sxs-lookup"><span data-stu-id="ec960-291">`0x2`: Suspend for AppDomain shutdown.</span></span><br/><br/><span data-ttu-id="ec960-292">`0x3`: Suspender para el paso del código.</span><span class="sxs-lookup"><span data-stu-id="ec960-292">`0x3`: Suspend for code pitching.</span></span><br/><br/><span data-ttu-id="ec960-293">`0x4`: Suspender para apagar.</span><span class="sxs-lookup"><span data-stu-id="ec960-293">`0x4`: Suspend for shutdown.</span></span><br/><br/><span data-ttu-id="ec960-294">`0x5`: Suspender para el depurador.</span><span class="sxs-lookup"><span data-stu-id="ec960-294">`0x5`: Suspend for debugger.</span></span><br/><br/><span data-ttu-id="ec960-295">`0x6`: Suspend para la preparación de GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-295">`0x6`: Suspend for GC Prep.</span></span><br/><br/><span data-ttu-id="ec960-296">`0x7`: Suspender el barrido del depurador</span><span class="sxs-lookup"><span data-stu-id="ec960-296">`0x7`: Suspend for debugger sweep</span></span>|

## <a name="gcallocationtick_v3-event"></a><span data-ttu-id="ec960-297">Evento GCAllocationTick_V3</span><span class="sxs-lookup"><span data-stu-id="ec960-297">GCAllocationTick_V3 event</span></span>

<span data-ttu-id="ec960-298">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-298">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-299">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-299">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-300">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-300">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-301">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-301">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-302">Verbose (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-302">Verbose (4)</span></span>|

<span data-ttu-id="ec960-303">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-303">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-304">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-304">Event</span></span>|<span data-ttu-id="ec960-305">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-305">Event ID</span></span>|<span data-ttu-id="ec960-306">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-306">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V3`|<span data-ttu-id="ec960-307">10</span><span class="sxs-lookup"><span data-stu-id="ec960-307">10</span></span>|<span data-ttu-id="ec960-308">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="ec960-308">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="ec960-309">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-309">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-310">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-310">Field name</span></span>|<span data-ttu-id="ec960-311">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-311">Data type</span></span>|<span data-ttu-id="ec960-312">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-312">Description</span></span>|
|----------------|---------------|-----------------|
|`AllocationAmount`|`win:UInt32`|<span data-ttu-id="ec960-313">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ec960-313">The allocation size, in bytes.</span></span> <span data-ttu-id="ec960-314">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="ec960-314">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="ec960-315">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="ec960-315">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="ec960-316">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="ec960-316">Use `AllocationAmount64` for very large allocations.</span></span>|
|`AllocationKind`|`win:UInt32`|<span data-ttu-id="ec960-317">`0x0` -Asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="ec960-317">`0x0` - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="ec960-318">`0x1` -Asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="ec960-318">`0x1` - Large object allocation (allocation is in large object heap).</span></span>|
|`AllocationAmount64`|`win:UInt64`|<span data-ttu-id="ec960-319">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ec960-319">The allocation size, in bytes.</span></span> <span data-ttu-id="ec960-320">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="ec960-320">This value is accurate for very large allocations.</span></span>|
|`TypeId`|`win:Pointer`|<span data-ttu-id="ec960-321">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="ec960-321">The address of the MethodTable.</span></span> <span data-ttu-id="ec960-322">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="ec960-322">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="ec960-323">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="ec960-323">The name of the type that was allocated.</span></span> <span data-ttu-id="ec960-324">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="ec960-324">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|`HeapIndex`|`win:UInt32`|<span data-ttu-id="ec960-325">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="ec960-325">The heap where the object was allocated.</span></span> <span data-ttu-id="ec960-326">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec960-326">This value is 0 (zero) when running with workstation garbage collection.</span></span>|
|`Address`|`win:Pointer`|<span data-ttu-id="ec960-327">Dirección del último objeto asignado.</span><span class="sxs-lookup"><span data-stu-id="ec960-327">The address of the last allocated object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-328">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-328">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="ec960-329">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-329">GCCreateConcurrentThread_V1 event</span></span>

<span data-ttu-id="ec960-330">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-330">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-331">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-331">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-332">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-332">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-333">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-333">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-334">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-334">Informational (4)</span></span>|
|<span data-ttu-id="ec960-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ec960-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ec960-336">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-336">Informational (4)</span></span>|

<span data-ttu-id="ec960-337">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-337">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-338">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-338">Event</span></span>|<span data-ttu-id="ec960-339">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-339">Event ID</span></span>|<span data-ttu-id="ec960-340">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-340">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="ec960-341">11</span><span class="sxs-lookup"><span data-stu-id="ec960-341">11</span></span>|<span data-ttu-id="ec960-342">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="ec960-342">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="ec960-343">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-343">This event does not have any event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="ec960-344">Evento GCTerminateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-344">GCTerminateConcurrentThread_V1 event</span></span>

<span data-ttu-id="ec960-345">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-345">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-346">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-346">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-347">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-347">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-348">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-348">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-349">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-349">Informational (4)</span></span>|
|<span data-ttu-id="ec960-350">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ec960-350">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ec960-351">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-351">Informational (4)</span></span>|

<span data-ttu-id="ec960-352">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-352">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-353">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-353">Event</span></span>|<span data-ttu-id="ec960-354">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-354">Event ID</span></span>|<span data-ttu-id="ec960-355">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-355">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="ec960-356">12</span><span class="sxs-lookup"><span data-stu-id="ec960-356">12</span></span>|<span data-ttu-id="ec960-357">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="ec960-357">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="ec960-358">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-358">This event does not have any event data.</span></span>

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="ec960-359">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-359">GCFinalizersBegin_V1 event</span></span>

<span data-ttu-id="ec960-360">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-360">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-361">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-361">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-362">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-362">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-363">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-363">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-364">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-364">Informational (4)</span></span>|

<span data-ttu-id="ec960-365">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-365">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-366">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-366">Event</span></span>|<span data-ttu-id="ec960-367">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-367">Event ID</span></span>|<span data-ttu-id="ec960-368">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-368">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="ec960-369">14</span><span class="sxs-lookup"><span data-stu-id="ec960-369">14</span></span>|<span data-ttu-id="ec960-370">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec960-370">The start of running finalizers.</span></span>|

<span data-ttu-id="ec960-371">Este evento no tiene datos de evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-371">This event does not have any event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="ec960-372">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="ec960-372">GCFinalizersEnd_V1 event</span></span>

<span data-ttu-id="ec960-373">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-373">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-374">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-374">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-375">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-376">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-376">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-377">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-377">Informational (4)</span></span>|

<span data-ttu-id="ec960-378">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-378">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-379">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-379">Event</span></span>|<span data-ttu-id="ec960-380">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-380">Event ID</span></span>|<span data-ttu-id="ec960-381">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-381">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="ec960-382">13</span><span class="sxs-lookup"><span data-stu-id="ec960-382">13</span></span>|<span data-ttu-id="ec960-383">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec960-383">The end of running finalizers.</span></span>|

<span data-ttu-id="ec960-384">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-384">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-385">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-385">Field name</span></span>|<span data-ttu-id="ec960-386">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-386">Data type</span></span>|<span data-ttu-id="ec960-387">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-387">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt32`|<span data-ttu-id="ec960-388">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="ec960-388">The number of finalizers that were run.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="ec960-389">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-389">win:UInt16</span></span>|<span data-ttu-id="ec960-390">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-390">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="setgchandle-event"></a><span data-ttu-id="ec960-391">Evento SetGCHandle</span><span class="sxs-lookup"><span data-stu-id="ec960-391">SetGCHandle event</span></span>

<span data-ttu-id="ec960-392">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-392">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-393">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-393">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-394">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-394">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-395">`GCHandleKeyword` 0X2</span><span class="sxs-lookup"><span data-stu-id="ec960-395">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="ec960-396">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-396">Informational (4)</span></span>|

<span data-ttu-id="ec960-397">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-397">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-398">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-398">Event</span></span>|<span data-ttu-id="ec960-399">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-399">Event ID</span></span>|<span data-ttu-id="ec960-400">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-400">Raised when</span></span>|
|-----------|--------------|-----------------|
|`SetGCHandle`|<span data-ttu-id="ec960-401">30</span><span class="sxs-lookup"><span data-stu-id="ec960-401">30</span></span>|<span data-ttu-id="ec960-402">Se ha establecido un identificador de GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-402">A GC Handle has been set.</span></span>|

<span data-ttu-id="ec960-403">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-403">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-404">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-404">Field name</span></span>|<span data-ttu-id="ec960-405">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-405">Data type</span></span>|<span data-ttu-id="ec960-406">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-406">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="ec960-407">Dirección del identificador asignado.</span><span class="sxs-lookup"><span data-stu-id="ec960-407">The address of the allocated handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="ec960-408">Dirección del objeto cuyo identificador se creó.</span><span class="sxs-lookup"><span data-stu-id="ec960-408">The address of the object whose handle was created.</span></span>|
|`Kind`|`win:UInt32`|<span data-ttu-id="ec960-409">El tipo de identificador de GC que se estableció.</span><span class="sxs-lookup"><span data-stu-id="ec960-409">The type of GC handle that was set.</span></span> <br /><br /><span data-ttu-id="ec960-410">`0x0`: WeakShort</span><span class="sxs-lookup"><span data-stu-id="ec960-410">`0x0`: WeakShort</span></span> <br/><br/><span data-ttu-id="ec960-411">`0x1`: WeakLong</span><span class="sxs-lookup"><span data-stu-id="ec960-411">`0x1`: WeakLong</span></span> <br /><br /><span data-ttu-id="ec960-412">`0x2`: Strong</span><span class="sxs-lookup"><span data-stu-id="ec960-412">`0x2`: Strong</span></span> <br /><br /><span data-ttu-id="ec960-413">`0x3`: Anclado</span><span class="sxs-lookup"><span data-stu-id="ec960-413">`0x3`: Pinned</span></span> <br /><br /><span data-ttu-id="ec960-414">`0x4`: Variable</span><span class="sxs-lookup"><span data-stu-id="ec960-414">`0x4`: Variable</span></span><br /><br /><span data-ttu-id="ec960-415">`0x5`: RefCounted</span><span class="sxs-lookup"><span data-stu-id="ec960-415">`0x5`: RefCounted</span></span> <br /><br /><span data-ttu-id="ec960-416">`0x6`: Dependiente</span><span class="sxs-lookup"><span data-stu-id="ec960-416">`0x6`: Dependent</span></span><br /><br /><span data-ttu-id="ec960-417">`0x7`: AsyncPinned</span><span class="sxs-lookup"><span data-stu-id="ec960-417">`0x7`: AsyncPinned</span></span><br /><br /><span data-ttu-id="ec960-418">`0x8`: Identificador sizedref</span><span class="sxs-lookup"><span data-stu-id="ec960-418">`0x8`: SizedRef</span></span>|
|`Generation`|`win:UInt32`|<span data-ttu-id="ec960-419">La generación del objeto cuyo identificador se creó.</span><span class="sxs-lookup"><span data-stu-id="ec960-419">The generation of the object whose handle was created.</span></span>|
|`AppDomainID`|`win:UInt64`|<span data-ttu-id="ec960-420">IDENTIFICADOR de AppDomain.</span><span class="sxs-lookup"><span data-stu-id="ec960-420">The AppDomain ID.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-421">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-421">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="destroygchandle-event"></a><span data-ttu-id="ec960-422">Evento DestroyGCHandle</span><span class="sxs-lookup"><span data-stu-id="ec960-422">DestroyGCHandle event</span></span>

<span data-ttu-id="ec960-423">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-423">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-424">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-424">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-425">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-425">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-426">`GCHandleKeyword` 0X2</span><span class="sxs-lookup"><span data-stu-id="ec960-426">`GCHandleKeyword` (0x2)</span></span>|<span data-ttu-id="ec960-427">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-427">Informational (4)</span></span>|

<span data-ttu-id="ec960-428">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-428">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-429">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-429">Event</span></span>|<span data-ttu-id="ec960-430">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-430">Event ID</span></span>|<span data-ttu-id="ec960-431">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-431">Raised when</span></span>|
|-----------|--------------|-----------------|
|`DestroyGCHandle`|<span data-ttu-id="ec960-432">31</span><span class="sxs-lookup"><span data-stu-id="ec960-432">31</span></span>|<span data-ttu-id="ec960-433">Se destruye un identificador de GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-433">A GC Handle is destroyed.</span></span>|

<span data-ttu-id="ec960-434">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-434">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-435">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-435">Field name</span></span>|<span data-ttu-id="ec960-436">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-436">Data type</span></span>|<span data-ttu-id="ec960-437">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-437">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="ec960-438">Dirección del identificador destruido.</span><span class="sxs-lookup"><span data-stu-id="ec960-438">The address of the destroyed handle.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="ec960-439">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-439">win:UInt16</span></span>|<span data-ttu-id="ec960-440">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-440">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="pinobjectatgctime-event"></a><span data-ttu-id="ec960-441">Evento PinObjectAtGCTime</span><span class="sxs-lookup"><span data-stu-id="ec960-441">PinObjectAtGCTime event</span></span>

<span data-ttu-id="ec960-442">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-442">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-443">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-443">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-444">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-444">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-445">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-445">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-446">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="ec960-446">Verbose (5)</span></span>|

<span data-ttu-id="ec960-447">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-447">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-448">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-448">Event</span></span>|<span data-ttu-id="ec960-449">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-449">Event ID</span></span>|<span data-ttu-id="ec960-450">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-450">Raised when</span></span>|
|-----------|--------------|-----------------|
|`PinObjectAtGCTime`|<span data-ttu-id="ec960-451">33</span><span class="sxs-lookup"><span data-stu-id="ec960-451">33</span></span>|<span data-ttu-id="ec960-452">Se ancló un objeto durante un GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-452">An object was pinned during a GC.</span></span>|

<span data-ttu-id="ec960-453">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-453">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-454">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-454">Field name</span></span>|<span data-ttu-id="ec960-455">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-455">Data type</span></span>|<span data-ttu-id="ec960-456">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-456">Description</span></span>|
|----------------|---------------|-----------------|
|`HandleID`|`win:Pointer`|<span data-ttu-id="ec960-457">Dirección del identificador.</span><span class="sxs-lookup"><span data-stu-id="ec960-457">The address of the handle.</span></span>|
|`ObjectID`|`win:Pointer`|<span data-ttu-id="ec960-458">Dirección del objeto anclado.</span><span class="sxs-lookup"><span data-stu-id="ec960-458">The address of the pinned object.</span></span>|
|`ObjectSize`|`win:UInt64`|<span data-ttu-id="ec960-459">Tamaño del objeto anclado.</span><span class="sxs-lookup"><span data-stu-id="ec960-459">The size of the pinned object.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="ec960-460">Nombre del tipo del objeto anclado.</span><span class="sxs-lookup"><span data-stu-id="ec960-460">The name of the type of the pinned object.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-461">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-461">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gctriggered-event"></a><span data-ttu-id="ec960-462">Evento GCTriggered</span><span class="sxs-lookup"><span data-stu-id="ec960-462">GCTriggered event</span></span>

<span data-ttu-id="ec960-463">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-463">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-464">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-464">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-465">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-465">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-466">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-466">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-467">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="ec960-467">Verbose (5)</span></span>|

<span data-ttu-id="ec960-468">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-468">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-469">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-469">Event</span></span>|<span data-ttu-id="ec960-470">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-470">Event ID</span></span>|<span data-ttu-id="ec960-471">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-471">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTriggered`|<span data-ttu-id="ec960-472">33</span><span class="sxs-lookup"><span data-stu-id="ec960-472">33</span></span>|<span data-ttu-id="ec960-473">Se ha desencadenado un GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-473">A GC has been triggered.</span></span>|

<span data-ttu-id="ec960-474">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-474">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-475">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-475">Field name</span></span>|<span data-ttu-id="ec960-476">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-476">Data type</span></span>|<span data-ttu-id="ec960-477">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-477">Description</span></span>|
|----------------|---------------|-----------------|
|`Reason`|`win:UInt32`|<span data-ttu-id="ec960-478">Motivo por el que se desencadenó un GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-478">The reason a GC was triggered.</span></span><br/><br/><span data-ttu-id="ec960-479">`0x0`: AllocSmall</span><span class="sxs-lookup"><span data-stu-id="ec960-479">`0x0`: AllocSmall</span></span><br/><br/><span data-ttu-id="ec960-480">`0x1`: Inducido</span><span class="sxs-lookup"><span data-stu-id="ec960-480">`0x1`: Induced</span></span> <br/><br/><span data-ttu-id="ec960-481">`0x2`: LowMemory</span><span class="sxs-lookup"><span data-stu-id="ec960-481">`0x2`: LowMemory</span></span> <br/><br/><span data-ttu-id="ec960-482">`0x3`: Vacío</span><span class="sxs-lookup"><span data-stu-id="ec960-482">`0x3`: Empty</span></span> <br/><br/><span data-ttu-id="ec960-483">`0x4`: AllocLarge</span><span class="sxs-lookup"><span data-stu-id="ec960-483">`0x4`: AllocLarge</span></span> <br/><br/><span data-ttu-id="ec960-484">`0x5`: OutOfSpaceSmallObjectHeap</span><span class="sxs-lookup"><span data-stu-id="ec960-484">`0x5`: OutOfSpaceSmallObjectHeap</span></span> <br/><br/><span data-ttu-id="ec960-485">`0x6`: OutOfSpaceLargeObjectHeap</span><span class="sxs-lookup"><span data-stu-id="ec960-485">`0x6`: OutOfSpaceLargeObjectHeap</span></span> <br/><br/><span data-ttu-id="ec960-486">`0x7`:InducedNoForce</span><span class="sxs-lookup"><span data-stu-id="ec960-486">`0x7`:InducedNoForce</span></span> <br/><br/><span data-ttu-id="ec960-487">`0x8`: Stress</span><span class="sxs-lookup"><span data-stu-id="ec960-487">`0x8`: Stress</span></span> <br/><br/><span data-ttu-id="ec960-488">`0x9`: InducedLowMemory</span><span class="sxs-lookup"><span data-stu-id="ec960-488">`0x9`: InducedLowMemory</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-489">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-489">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="increasememorypressure-event"></a><span data-ttu-id="ec960-490">Evento IncreaseMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="ec960-490">IncreaseMemoryPressure event</span></span>

<span data-ttu-id="ec960-491">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-491">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-492">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-492">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-493">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-493">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-494">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-494">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-495">Información (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-495">Information (4)</span></span>|

<span data-ttu-id="ec960-496">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-496">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-497">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-497">Event</span></span>|<span data-ttu-id="ec960-498">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-498">Event ID</span></span>|<span data-ttu-id="ec960-499">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-499">Raised when</span></span>|
|----------------|---------------|-----------------|
|`IncreaseMemoryPressure`|<span data-ttu-id="ec960-500">200</span><span class="sxs-lookup"><span data-stu-id="ec960-500">200</span></span>|<span data-ttu-id="ec960-501">Se aumentó la presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="ec960-501">Memory pressure was increased.</span></span>|

<span data-ttu-id="ec960-502">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-502">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-503">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-503">Field Name</span></span>|<span data-ttu-id="ec960-504">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-504">Data type</span></span>|<span data-ttu-id="ec960-505">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-505">Description</span></span>|
|----------------|---------------|-----------------|
|`ClrInstanceID`|<span data-ttu-id="ec960-506">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-506">win:UInt16</span></span>|<span data-ttu-id="ec960-507">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-507">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="decreasememorypressure-event"></a><span data-ttu-id="ec960-508">Evento DecreaseMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="ec960-508">DecreaseMemoryPressure event</span></span>

<span data-ttu-id="ec960-509">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-509">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-510">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-510">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-511">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-511">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-512">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-512">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-513">Información (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-513">Information (4)</span></span>|

<span data-ttu-id="ec960-514">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-514">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-515">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-515">Event</span></span>|<span data-ttu-id="ec960-516">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-516">Event ID</span></span>|<span data-ttu-id="ec960-517">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-517">Raised when</span></span>|
|----------------|---------------|-----------------|
|`DecreaseMemoryPressure`|<span data-ttu-id="ec960-518">201</span><span class="sxs-lookup"><span data-stu-id="ec960-518">201</span></span>|<span data-ttu-id="ec960-519">Se disminuyó la presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="ec960-519">Memory pressure was decreased.</span></span>|

<span data-ttu-id="ec960-520">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-520">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-521">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-521">Field Name</span></span>|<span data-ttu-id="ec960-522">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-522">Data type</span></span>|<span data-ttu-id="ec960-523">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-523">Description</span></span>|
|----------------|---------------|-----------------|
|`BytesFreed`|`win:UInt32`|<span data-ttu-id="ec960-524">Bytes liberados.</span><span class="sxs-lookup"><span data-stu-id="ec960-524">Bytes freed.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-525">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-525">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="gcmarkwithtype-event"></a><span data-ttu-id="ec960-526">Evento GCMarkWithType</span><span class="sxs-lookup"><span data-stu-id="ec960-526">GCMarkWithType event</span></span>

<span data-ttu-id="ec960-527">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-527">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-528">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-528">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-529">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-529">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-530">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-530">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-531">Información (4)</span><span class="sxs-lookup"><span data-stu-id="ec960-531">Information (4)</span></span>|

<span data-ttu-id="ec960-532">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-532">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-533">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-533">Event</span></span>|<span data-ttu-id="ec960-534">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-534">Event ID</span></span>|<span data-ttu-id="ec960-535">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-535">Raised when</span></span>|
|----------------|---------------|-----------------|
|`GCMarkWithType`|<span data-ttu-id="ec960-536">202</span><span class="sxs-lookup"><span data-stu-id="ec960-536">202</span></span>|<span data-ttu-id="ec960-537">Se ha marcado una raíz de GC durante la fase de marca de GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-537">A GC root has been marked during GC mark phase.</span></span>|

<span data-ttu-id="ec960-538">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-538">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-539">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-539">Field Name</span></span>|<span data-ttu-id="ec960-540">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-540">Data type</span></span>|<span data-ttu-id="ec960-541">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-541">Description</span></span>|
|----------------|---------------|-----------------|
|`HeapNum`|`win:UInt32`|<span data-ttu-id="ec960-542">El número de montón.</span><span class="sxs-lookup"><span data-stu-id="ec960-542">The heap number.</span></span>|
|`ClrInstanceID`|<span data-ttu-id="ec960-543">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ec960-543">win:UInt16</span></span>|<span data-ttu-id="ec960-544">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-544">Unique ID for the instance of CoreCLR.</span></span>|
|`Type`|`win:UInt32`|<span data-ttu-id="ec960-545">Tipo raíz del GC.</span><span class="sxs-lookup"><span data-stu-id="ec960-545">The GC root type.</span></span><br/><br/><span data-ttu-id="ec960-546">`0x0`: Stack</span><span class="sxs-lookup"><span data-stu-id="ec960-546">`0x0`: Stack</span></span><br/><br/><span data-ttu-id="ec960-547">`0x1`: Finalizador</span><span class="sxs-lookup"><span data-stu-id="ec960-547">`0x1`: Finalizer</span></span><br/><br/><span data-ttu-id="ec960-548">`0x2`: Handle</span><span class="sxs-lookup"><span data-stu-id="ec960-548">`0x2`: Handle</span></span><br/><br/><span data-ttu-id="ec960-549">`0x3`: Anterior</span><span class="sxs-lookup"><span data-stu-id="ec960-549">`0x3`: Older</span></span><br/><br/><span data-ttu-id="ec960-550">`0x4`: Identificador sizedref</span><span class="sxs-lookup"><span data-stu-id="ec960-550">`0x4`: SizedRef</span></span><br/><br/><span data-ttu-id="ec960-551">`0x5`: Desbordamiento</span><span class="sxs-lookup"><span data-stu-id="ec960-551">`0x5`: Overflow</span></span><br/><br/>|
|`Bytes`|`win:UInt64`|<span data-ttu-id="ec960-552">Número de bytes marcados como.</span><span class="sxs-lookup"><span data-stu-id="ec960-552">The number of bytes marked.</span></span>|

## <a name="gcjoin_v2-event"></a><span data-ttu-id="ec960-553">Evento GCJoin_V2</span><span class="sxs-lookup"><span data-stu-id="ec960-553">GCJoin_V2 event</span></span>

<span data-ttu-id="ec960-554">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="ec960-554">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ec960-555">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ec960-555">Keyword for raising the event</span></span>|<span data-ttu-id="ec960-556">Nivel</span><span class="sxs-lookup"><span data-stu-id="ec960-556">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ec960-557">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="ec960-557">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="ec960-558">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="ec960-558">Verbose (5)</span></span>|

<span data-ttu-id="ec960-559">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="ec960-559">The following table shows the event information:</span></span>

|<span data-ttu-id="ec960-560">Evento</span><span class="sxs-lookup"><span data-stu-id="ec960-560">Event</span></span>|<span data-ttu-id="ec960-561">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec960-561">Event ID</span></span>|<span data-ttu-id="ec960-562">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="ec960-562">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCJoin_V2`|<span data-ttu-id="ec960-563">203</span><span class="sxs-lookup"><span data-stu-id="ec960-563">203</span></span>|<span data-ttu-id="ec960-564">Un subproceso GC combinado.</span><span class="sxs-lookup"><span data-stu-id="ec960-564">A GC thread joined.</span></span>|

<span data-ttu-id="ec960-565">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="ec960-565">The following table shows the event data:</span></span>

|<span data-ttu-id="ec960-566">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ec960-566">Field name</span></span>|<span data-ttu-id="ec960-567">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ec960-567">Data type</span></span>|<span data-ttu-id="ec960-568">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec960-568">Description</span></span>|
|----------------|---------------|-----------------|
|`Heap`|`win:UInt32`|<span data-ttu-id="ec960-569">El número de montón</span><span class="sxs-lookup"><span data-stu-id="ec960-569">The heap number</span></span>|
|`JoinTime`|`win:UInt32`|<span data-ttu-id="ec960-570">Indica si este evento se desencadena al principio de una combinación o el final de una combinación (para el inicio de la combinación `0x0` , para el extremo de la `0x1` combinación)</span><span class="sxs-lookup"><span data-stu-id="ec960-570">Indicates whether this event is fired at the start of a join or end of a join (`0x0` for join start, `0x1` for join end)</span></span>|
|`JoinType`|`win:UInt32`|<span data-ttu-id="ec960-571">Tipo de combinación.</span><span class="sxs-lookup"><span data-stu-id="ec960-571">The join type.</span></span> <br/><br/><span data-ttu-id="ec960-572">`0x0`: Última combinación</span><span class="sxs-lookup"><span data-stu-id="ec960-572">`0x0`: Last Join</span></span><br/><br/><span data-ttu-id="ec960-573">`0x1`: Join</span><span class="sxs-lookup"><span data-stu-id="ec960-573">`0x1`: Join</span></span> <br/><br/><span data-ttu-id="ec960-574">`0x2`: Reiniciar</span><span class="sxs-lookup"><span data-stu-id="ec960-574">`0x2`: Restart</span></span> <br/><br/><span data-ttu-id="ec960-575">`0x3`: Primera combinación inversa</span><span class="sxs-lookup"><span data-stu-id="ec960-575">`0x3`: First Reverse Join</span></span><br/><br/><span data-ttu-id="ec960-576">`0x4`: Combinación inversa</span><span class="sxs-lookup"><span data-stu-id="ec960-576">`0x4`: Reverse Join</span></span><br/><br/>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ec960-577">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ec960-577">Unique ID for the instance of CoreCLR.</span></span>|
