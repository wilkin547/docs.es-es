---
title: Eventos de tiempo de ejecución ThreadPool
description: Vea eventos de grupo de subprocesos en tiempo de ejecución .NET que recopilan información de diagnóstico sobre el grupo de subprocesos en .NET Core Los eventos de grupo de subprocesos son eventos de grupo de subprocesos de trabajo o de subproceso de e/s.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594729"
---
# <a name="net-runtime-thread-pool-events"></a><span data-ttu-id="2a700-104">Eventos de grupo de subprocesos en tiempo de ejecución .NET</span><span class="sxs-lookup"><span data-stu-id="2a700-104">.NET runtime thread pool events</span></span>

<span data-ttu-id="2a700-105">Estos eventos recopilan información sobre el trabajo y los subprocesos de e/s en ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="2a700-105">These events collect information about worker and I/O threads in the threadpool.</span></span> <span data-ttu-id="2a700-106">Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="2a700-106">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="iothreadcreate_v1-event"></a><span data-ttu-id="2a700-107">Evento IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="2a700-107">IOThreadCreate_V1 event</span></span>

 <span data-ttu-id="2a700-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-108">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-109">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-109">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-110">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-110">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-111">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-111">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-112">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-112">Informational (4)</span></span>|

 <span data-ttu-id="2a700-113">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-113">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-114">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-114">Event</span></span>|<span data-ttu-id="2a700-115">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-115">Event ID</span></span>|<span data-ttu-id="2a700-116">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2a700-116">Raised when</span></span>|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|<span data-ttu-id="2a700-117">44</span><span class="sxs-lookup"><span data-stu-id="2a700-117">44</span></span>|<span data-ttu-id="2a700-118">Se crea un subproceso de E/S en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-118">An I/O thread is created in the thread pool.</span></span>|

 <span data-ttu-id="2a700-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-119">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-120">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-120">Field name</span></span>|<span data-ttu-id="2a700-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-121">Data type</span></span>|<span data-ttu-id="2a700-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-122">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="2a700-123">Número de subprocesos de E/S, incluido el subproceso recién creado.</span><span class="sxs-lookup"><span data-stu-id="2a700-123">Number of I/O threads, including the newly created thread.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="2a700-124">Número de subprocesos de trabajo retirados.</span><span class="sxs-lookup"><span data-stu-id="2a700-124">Number of retired worker threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-125">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-125">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadterminate_v1-event"></a><span data-ttu-id="2a700-126">Evento IOThreadTerminate_V1</span><span class="sxs-lookup"><span data-stu-id="2a700-126">IOThreadTerminate_V1 event</span></span>

 <span data-ttu-id="2a700-127">En la tabla siguiente se muestra la palabra clave y el nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-127">The following table shows the keyword and level</span></span>

|<span data-ttu-id="2a700-128">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-128">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-129">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-129">Level</span></span>
|-----------------------------------|-----------
|<span data-ttu-id="2a700-130">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-130">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-131">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-131">Informational (4)</span></span>

 <span data-ttu-id="2a700-132">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-132">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-133">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-133">Event</span></span>|<span data-ttu-id="2a700-134">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-134">Event ID</span></span>|<span data-ttu-id="2a700-135">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2a700-135">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|<span data-ttu-id="2a700-136">45</span><span class="sxs-lookup"><span data-stu-id="2a700-136">45</span></span>|<span data-ttu-id="2a700-137">Se termina un subproceso de e/s en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-137">An I/O thread is terminated in the thread pool.</span></span>|

 <span data-ttu-id="2a700-138">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-138">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-139">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-139">Field name</span></span>|<span data-ttu-id="2a700-140">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-140">Data type</span></span>|<span data-ttu-id="2a700-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-141">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="2a700-142">Número de subprocesos de E/S restantes en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-142">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="2a700-143">Número de subprocesos de E/S retirados.</span><span class="sxs-lookup"><span data-stu-id="2a700-143">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-144">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadretire_v1-event"></a><span data-ttu-id="2a700-145">Evento IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="2a700-145">IOThreadRetire_V1 event</span></span>

 <span data-ttu-id="2a700-146">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-146">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-147">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-147">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-148">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-149">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-149">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-150">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-150">Informational (4)</span></span>|

 <span data-ttu-id="2a700-151">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-151">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-152">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-152">Event</span></span>|<span data-ttu-id="2a700-153">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-153">Event ID</span></span>|<span data-ttu-id="2a700-154">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2a700-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|<span data-ttu-id="2a700-155">46</span><span class="sxs-lookup"><span data-stu-id="2a700-155">46</span></span>|<span data-ttu-id="2a700-156">Un subproceso de E/S se convierte en un candidato para la retirada.</span><span class="sxs-lookup"><span data-stu-id="2a700-156">An I/O thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="2a700-157">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-157">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-158">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-158">Field name</span></span>|<span data-ttu-id="2a700-159">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-159">Data type</span></span>|<span data-ttu-id="2a700-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-160">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="2a700-161">Número de subprocesos de E/S restantes en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-161">Number of I/O threads remaining in the thread pool.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="2a700-162">Número de subprocesos de E/S retirados.</span><span class="sxs-lookup"><span data-stu-id="2a700-162">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-163">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="iothreadunretire_v1-event"></a><span data-ttu-id="2a700-164">Evento IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="2a700-164">IOThreadUnretire_V1 event</span></span>

 <span data-ttu-id="2a700-165">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-165">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-166">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-166">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-167">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-168">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-168">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-169">Informational (4)</span></span>|

 <span data-ttu-id="2a700-170">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-170">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-171">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-171">Event</span></span>|<span data-ttu-id="2a700-172">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-172">Event ID</span></span>|<span data-ttu-id="2a700-173">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2a700-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|<span data-ttu-id="2a700-174">47</span><span class="sxs-lookup"><span data-stu-id="2a700-174">47</span></span>|<span data-ttu-id="2a700-175">La retirada de un subproceso de E/S se anula debido a que llega una E/S dentro de un período de espera y después de que el subproceso se convierte en un candidato para la retirada.</span><span class="sxs-lookup"><span data-stu-id="2a700-175">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|

 <span data-ttu-id="2a700-176">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-176">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-177">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-177">Field name</span></span>|<span data-ttu-id="2a700-178">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-178">Data type</span></span>|<span data-ttu-id="2a700-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-179">Description</span></span>|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|<span data-ttu-id="2a700-180">Número de subprocesos de E/S en el grupo de subprocesos, incluido este.</span><span class="sxs-lookup"><span data-stu-id="2a700-180">Number of I/O threads in the thread pool, including this one.</span></span>|
|`NumRetired`|`win:UInt64`|<span data-ttu-id="2a700-181">Número de subprocesos de E/S retirados.</span><span class="sxs-lookup"><span data-stu-id="2a700-181">Number of retired I/O threads.</span></span>|
|`ClrInstanceID`|`Win:UInt16`|<span data-ttu-id="2a700-182">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-182">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstart-event"></a><span data-ttu-id="2a700-183">Evento ThreadPoolWorkerThreadStart</span><span class="sxs-lookup"><span data-stu-id="2a700-183">ThreadPoolWorkerThreadStart event</span></span>

|<span data-ttu-id="2a700-184">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-184">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-185">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-185">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="2a700-186">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-186">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-187">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-187">Informational (4)</span></span>|

|<span data-ttu-id="2a700-188">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-188">Event</span></span>|<span data-ttu-id="2a700-189">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-189">Event ID</span></span>|<span data-ttu-id="2a700-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-190">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="2a700-191">50</span><span class="sxs-lookup"><span data-stu-id="2a700-191">50</span></span>|<span data-ttu-id="2a700-192">Se crea un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-192">A worker thread is created.</span></span>|

|<span data-ttu-id="2a700-193">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-193">Field name</span></span>|<span data-ttu-id="2a700-194">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-194">Data type</span></span>|<span data-ttu-id="2a700-195">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-195">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-196">Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-196">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-197">Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-197">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-198">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-198">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadstop-event"></a><span data-ttu-id="2a700-199">Evento ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="2a700-199">ThreadPoolWorkerThreadStop event</span></span>

|<span data-ttu-id="2a700-200">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-200">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-201">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-201">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="2a700-202">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-202">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-203">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-203">Informational (4)</span></span>|

|<span data-ttu-id="2a700-204">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-204">Event</span></span>|<span data-ttu-id="2a700-205">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-205">Event ID</span></span>|<span data-ttu-id="2a700-206">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-206">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="2a700-207">51</span><span class="sxs-lookup"><span data-stu-id="2a700-207">51</span></span>|<span data-ttu-id="2a700-208">Se detiene un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-208">A worker thread is stopped.</span></span>|

|<span data-ttu-id="2a700-209">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-209">Field name</span></span>|<span data-ttu-id="2a700-210">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-210">Data type</span></span>|<span data-ttu-id="2a700-211">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-211">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-212">Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-212">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-213">Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-213">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-214">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-214">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadwait-event"></a><span data-ttu-id="2a700-215">Evento ThreadPoolWorkerThreadWait</span><span class="sxs-lookup"><span data-stu-id="2a700-215">ThreadPoolWorkerThreadWait event</span></span>

|<span data-ttu-id="2a700-216">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-216">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-217">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-217">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="2a700-218">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-218">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-219">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-219">Informational (4)</span></span>|

|<span data-ttu-id="2a700-220">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-220">Event</span></span>|<span data-ttu-id="2a700-221">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-221">Event ID</span></span>|<span data-ttu-id="2a700-222">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-222">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|<span data-ttu-id="2a700-223">57</span><span class="sxs-lookup"><span data-stu-id="2a700-223">57</span></span>|<span data-ttu-id="2a700-224">Un subproceso de trabajo inicia la espera de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-224">A worker thread starts waiting for work.</span></span>|

|<span data-ttu-id="2a700-225">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-225">Field name</span></span>|<span data-ttu-id="2a700-226">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-226">Data type</span></span>|<span data-ttu-id="2a700-227">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-227">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-228">Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-228">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-229">Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-229">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-230">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-230">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstart-event"></a><span data-ttu-id="2a700-231">Evento ThreadPoolWorkerThreadRetirementStart</span><span class="sxs-lookup"><span data-stu-id="2a700-231">ThreadPoolWorkerThreadRetirementStart event</span></span>

|<span data-ttu-id="2a700-232">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-232">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-233">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-233">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="2a700-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-235">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-235">Informational (4)</span></span>|

|<span data-ttu-id="2a700-236">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-236">Event</span></span>|<span data-ttu-id="2a700-237">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-237">Event ID</span></span>|<span data-ttu-id="2a700-238">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-238">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="2a700-239">52</span><span class="sxs-lookup"><span data-stu-id="2a700-239">52</span></span>|<span data-ttu-id="2a700-240">Se retira un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-240">A worker thread retires.</span></span>|

|<span data-ttu-id="2a700-241">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-241">Field name</span></span>|<span data-ttu-id="2a700-242">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-242">Data type</span></span>|<span data-ttu-id="2a700-243">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-243">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-244">Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-244">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-245">Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-245">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadretirementstop-event"></a><span data-ttu-id="2a700-247">Evento ThreadPoolWorkerThreadRetirementStop</span><span class="sxs-lookup"><span data-stu-id="2a700-247">ThreadPoolWorkerThreadRetirementStop event</span></span>

|<span data-ttu-id="2a700-248">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-248">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-249">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-249">Level</span></span>|
|-----------------------------------|-----------|-----------|
|<span data-ttu-id="2a700-250">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-250">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-251">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-251">Informational (4)</span></span>|

|<span data-ttu-id="2a700-252">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-252">Event</span></span>|<span data-ttu-id="2a700-253">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-253">Event ID</span></span>|<span data-ttu-id="2a700-254">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-254">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="2a700-255">53</span><span class="sxs-lookup"><span data-stu-id="2a700-255">53</span></span>|<span data-ttu-id="2a700-256">Un subproceso de trabajo retirado se vuelve activo.</span><span class="sxs-lookup"><span data-stu-id="2a700-256">A retired worker thread becomes active again.</span></span>|

|<span data-ttu-id="2a700-257">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-257">Field name</span></span>|<span data-ttu-id="2a700-258">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-258">Data type</span></span>|<span data-ttu-id="2a700-259">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-259">Description</span></span>|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-260">Número de subprocesos de trabajo disponibles para procesar trabajo, incluidos los que ya están procesando trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-260">Number of worker threads available to process work, including those that are already processing work.</span></span>|
|`RetiredWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-261">Número de subprocesos de trabajo que no están disponibles para procesar trabajo, pero que se mantienen en reserva en caso de que posteriormente se necesiten más subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-261">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-262">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-262">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a><span data-ttu-id="2a700-263">Evento ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="2a700-263">ThreadPoolWorkerThreadAdjustmentSample event</span></span>

 <span data-ttu-id="2a700-264">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-264">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-265">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-265">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-266">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-266">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-267">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-267">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-268">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-268">Informational (4)</span></span>|

 <span data-ttu-id="2a700-269">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-269">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-270">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-270">Event</span></span>|<span data-ttu-id="2a700-271">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-271">Event ID</span></span>|<span data-ttu-id="2a700-272">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-272">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="2a700-273">54</span><span class="sxs-lookup"><span data-stu-id="2a700-273">54</span></span>|<span data-ttu-id="2a700-274">Se refiere a la recopilación de información para un ejemplo; es decir, una medición del rendimiento con un determinado nivel de simultaneidad en un instante de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2a700-274">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|

 <span data-ttu-id="2a700-275">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-275">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-276">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-276">Field name</span></span>|<span data-ttu-id="2a700-277">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-277">Data type</span></span>|<span data-ttu-id="2a700-278">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-278">Description</span></span>|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|<span data-ttu-id="2a700-279">Número de finalizaciones por unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2a700-279">Number of completions per unit of time.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-280">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a><span data-ttu-id="2a700-281">Evento ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="2a700-281">ThreadPoolWorkerThreadAdjustmentAdjustment event</span></span>

 <span data-ttu-id="2a700-282">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-282">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-283">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-283">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-284">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-284">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-286">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-286">Informational (4)</span></span>|

 <span data-ttu-id="2a700-287">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-287">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-288">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-288">Event</span></span>|<span data-ttu-id="2a700-289">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-289">Event ID</span></span>|<span data-ttu-id="2a700-290">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-290">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="2a700-291">55</span><span class="sxs-lookup"><span data-stu-id="2a700-291">55</span></span>|<span data-ttu-id="2a700-292">Registra un cambio en el control, cuando el algoritmo de inserción de subproceso (hill-climbing) determina que tiene lugar un cambio en el nivel de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="2a700-292">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|

 <span data-ttu-id="2a700-293">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-293">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-294">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-294">Field name</span></span>|<span data-ttu-id="2a700-295">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-295">Data type</span></span>|<span data-ttu-id="2a700-296">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-296">Description</span></span>|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|<span data-ttu-id="2a700-297">Rendimiento medio de un ejemplo de mediciones.</span><span class="sxs-lookup"><span data-stu-id="2a700-297">Average throughput of a sample of measurements.</span></span>|
|`NewWorkerThreadCount`|`win:UInt32`|<span data-ttu-id="2a700-298">Nuevo número de subprocesos de trabajo activos.</span><span class="sxs-lookup"><span data-stu-id="2a700-298">New number of active worker threads.</span></span>|
|`Reason`|`win:UInt32`|<span data-ttu-id="2a700-299">Razón para el ajuste.</span><span class="sxs-lookup"><span data-stu-id="2a700-299">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="2a700-300">`0x0` Preparación.</span><span class="sxs-lookup"><span data-stu-id="2a700-300">`0x0` - Warmup.</span></span><br /><br /> <span data-ttu-id="2a700-301">`0x1` Inicial.</span><span class="sxs-lookup"><span data-stu-id="2a700-301">`0x1` - Initializing.</span></span><br /><br /> <span data-ttu-id="2a700-302">`0x2` -Movimiento aleatorio.</span><span class="sxs-lookup"><span data-stu-id="2a700-302">`0x2` - Random move.</span></span><br /><br /> <span data-ttu-id="2a700-303">`0x3` -Movimiento de subida.</span><span class="sxs-lookup"><span data-stu-id="2a700-303">`0x3` - Climbing move.</span></span><br /><br /> <span data-ttu-id="2a700-304">`0x4` -Cambiar punto.</span><span class="sxs-lookup"><span data-stu-id="2a700-304">`0x4` - Change point.</span></span><br /><br /> <span data-ttu-id="2a700-305">`0x5` Estabilización.</span><span class="sxs-lookup"><span data-stu-id="2a700-305">`0x5` - Stabilizing.</span></span><br /><br /> <span data-ttu-id="2a700-306">`0x6` Colapso.</span><span class="sxs-lookup"><span data-stu-id="2a700-306">`0x6` - Starvation.</span></span><br /><br /> <span data-ttu-id="2a700-307">`0x7` -El subproceso agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2a700-307">`0x7` - Thread timed out.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-308">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-308">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a><span data-ttu-id="2a700-309">Evento ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="2a700-309">ThreadPoolWorkerThreadAdjustmentStats event</span></span>

 <span data-ttu-id="2a700-310">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-310">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-311">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-311">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-312">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-312">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-313">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-313">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-314">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-314">Verbose (5)</span></span>

 <span data-ttu-id="2a700-315">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-315">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-316">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-316">Event</span></span>|<span data-ttu-id="2a700-317">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-317">Event ID</span></span>|<span data-ttu-id="2a700-318">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-318">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="2a700-319">56</span><span class="sxs-lookup"><span data-stu-id="2a700-319">56</span></span>|<span data-ttu-id="2a700-320">Recopila datos en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-320">Gathers data on the thread pool.</span></span>|

 <span data-ttu-id="2a700-321">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-321">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-322">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-322">Field name</span></span>|<span data-ttu-id="2a700-323">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-323">Data type</span></span>|<span data-ttu-id="2a700-324">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-324">Description</span></span>|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|<span data-ttu-id="2a700-325">Cantidad de tiempo, en segundos, durante el que se recopilaron estas estadísticas.</span><span class="sxs-lookup"><span data-stu-id="2a700-325">Amount of time, in seconds, during which these statistics were collected.</span></span>|
|`Throughput`|`win:Double`|<span data-ttu-id="2a700-326">Promedio de finalizaciones por segundo durante este intervalo.</span><span class="sxs-lookup"><span data-stu-id="2a700-326">Average number of completions per second during this interval.</span></span>|
|`ThreadWave`|`win:Double`|<span data-ttu-id="2a700-327">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-327">Reserved for internal use.</span></span>|
|`ThroughputWave`|`win:Double`|<span data-ttu-id="2a700-328">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-328">Reserved for internal use.</span></span>|
|`ThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="2a700-329">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-329">Reserved for internal use.</span></span>|
|`AverageThroughputErrorEstimate`|`win:Double`|<span data-ttu-id="2a700-330">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-330">Reserved for internal use.</span></span>|
|`ThroughputRatio`|`win:Double`|<span data-ttu-id="2a700-331">Mejora relativa en el rendimiento producida por variaciones en el número de subprocesos de trabajo activos durante este intervalo.</span><span class="sxs-lookup"><span data-stu-id="2a700-331">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|
|`Confidence`|`win:Double`|<span data-ttu-id="2a700-332">Medida de la validez del campo ThroughputRatio.</span><span class="sxs-lookup"><span data-stu-id="2a700-332">A measure of the validity of the ThroughputRatio field.</span></span>|
|`NewcontrolSetting`|`win:Double`|<span data-ttu-id="2a700-333">El número de subprocesos de trabajo activos que servirá de línea de base para las variaciones futuras en el recuento de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="2a700-333">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|
|`NewThreadWaveMagnitude`|`win:UInt16`|<span data-ttu-id="2a700-334">La magnitud de variaciones futuras en el recuento de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="2a700-334">The magnitude of future variations in active thread count.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-335">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-335">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadpoolenqueue-event"></a><span data-ttu-id="2a700-336">Evento ThreadPoolEnqueue</span><span class="sxs-lookup"><span data-stu-id="2a700-336">ThreadPoolEnqueue event</span></span>

 <span data-ttu-id="2a700-337">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-337">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-338">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-338">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-339">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-339">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-340">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-340">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-341">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-341">Verbose (5)</span></span>

 <span data-ttu-id="2a700-342">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-342">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-343">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-343">Event</span></span>|<span data-ttu-id="2a700-344">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-344">Event ID</span></span>|<span data-ttu-id="2a700-345">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-345">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|<span data-ttu-id="2a700-346">61</span><span class="sxs-lookup"><span data-stu-id="2a700-346">61</span></span>|<span data-ttu-id="2a700-347">Se puso en cola un elemento de trabajo en la cola del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-347">A work item was enqueued in the thread pool queue.</span></span>|

 <span data-ttu-id="2a700-348">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-348">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-349">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-349">Field name</span></span>|<span data-ttu-id="2a700-350">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-350">Data type</span></span>|<span data-ttu-id="2a700-351">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-351">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="2a700-352">Puntero a la solicitud de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-352">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-353">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-353">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooldequeue-event"></a><span data-ttu-id="2a700-354">Evento ThreadPoolDequeue</span><span class="sxs-lookup"><span data-stu-id="2a700-354">ThreadPoolDequeue event</span></span>

 <span data-ttu-id="2a700-355">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-355">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-356">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-356">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-357">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-357">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-358">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-358">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-359">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-359">Verbose (5)</span></span>

 <span data-ttu-id="2a700-360">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-360">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-361">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-361">Event</span></span>|<span data-ttu-id="2a700-362">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-362">Event ID</span></span>|<span data-ttu-id="2a700-363">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-363">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|<span data-ttu-id="2a700-364">62</span><span class="sxs-lookup"><span data-stu-id="2a700-364">62</span></span>|<span data-ttu-id="2a700-365">Se quitó la cola de un elemento de trabajo de la cola del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2a700-365">A work item was dequeued from the thread pool queue.</span></span>|

 <span data-ttu-id="2a700-366">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-366">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-367">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-367">Field name</span></span>|<span data-ttu-id="2a700-368">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-368">Data type</span></span>|<span data-ttu-id="2a700-369">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-369">Description</span></span>|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|<span data-ttu-id="2a700-370">Puntero a la solicitud de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a700-370">Pointer to the work request.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-371">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-371">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpoolioenqueue-event"></a><span data-ttu-id="2a700-372">Evento ThreadPoolIOEnqueue</span><span class="sxs-lookup"><span data-stu-id="2a700-372">ThreadPoolIOEnqueue event</span></span>

 <span data-ttu-id="2a700-373">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-373">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-374">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-374">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-375">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-375">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-376">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-376">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-377">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-377">Verbose (5)</span></span>

 <span data-ttu-id="2a700-378">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-378">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-379">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-379">Event</span></span>|<span data-ttu-id="2a700-380">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-380">Event ID</span></span>|<span data-ttu-id="2a700-381">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-381">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|<span data-ttu-id="2a700-382">63</span><span class="sxs-lookup"><span data-stu-id="2a700-382">63</span></span>|<span data-ttu-id="2a700-383">Un subproceso pone en cola una notificación de finalización de e/s cuando se produce una finalización de e/s asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2a700-383">A thread enqueues an IO completion notification after an async IO completion occurs.</span></span>|

 <span data-ttu-id="2a700-384">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-384">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-385">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-385">Field name</span></span>|<span data-ttu-id="2a700-386">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-386">Data type</span></span>|<span data-ttu-id="2a700-387">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-387">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="2a700-388">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-388">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="2a700-389">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-389">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="2a700-390">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-390">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-391">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-391">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliodequeue-event"></a><span data-ttu-id="2a700-392">Evento ThreadPoolIODequeue</span><span class="sxs-lookup"><span data-stu-id="2a700-392">ThreadPoolIODequeue event</span></span>

 <span data-ttu-id="2a700-393">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-393">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-394">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-394">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-395">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-395">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-396">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-396">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-397">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-397">Verbose (5)</span></span>

 <span data-ttu-id="2a700-398">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-398">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-399">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-399">Event</span></span>|<span data-ttu-id="2a700-400">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-400">Event ID</span></span>|<span data-ttu-id="2a700-401">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-401">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|<span data-ttu-id="2a700-402">64</span><span class="sxs-lookup"><span data-stu-id="2a700-402">64</span></span>|<span data-ttu-id="2a700-403">Un subproceso quita la cola de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="2a700-403">A thread dequeues the IO completion notification.</span></span>|

 <span data-ttu-id="2a700-404">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-404">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-405">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-405">Field name</span></span>|<span data-ttu-id="2a700-406">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-406">Data type</span></span>|<span data-ttu-id="2a700-407">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-407">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="2a700-408">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-408">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="2a700-409">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-409">Reserved for internal use.</span></span>|
|`MultiDequeues`|`win:Boolean`|<span data-ttu-id="2a700-410">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-410">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-411">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-411">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadpooliopack-event"></a><span data-ttu-id="2a700-412">Evento ThreadPoolIOPack</span><span class="sxs-lookup"><span data-stu-id="2a700-412">ThreadPoolIOPack event</span></span>

 <span data-ttu-id="2a700-413">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-413">The following table shows the keyword and level.</span></span>

|<span data-ttu-id="2a700-414">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-414">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-415">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-415">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-416">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-416">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-417">Detallado (5)</span><span class="sxs-lookup"><span data-stu-id="2a700-417">Verbose (5)</span></span>|

 <span data-ttu-id="2a700-418">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-418">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-419">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-419">Event</span></span>|<span data-ttu-id="2a700-420">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-420">Event ID</span></span>|<span data-ttu-id="2a700-421">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-421">Description</span></span>|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|<span data-ttu-id="2a700-422">65</span><span class="sxs-lookup"><span data-stu-id="2a700-422">65</span></span>|<span data-ttu-id="2a700-423">Se llama al módulo de e/s superpuesta de ThreadPool.</span><span class="sxs-lookup"><span data-stu-id="2a700-423">ThreadPool overlapped IO pack is called.</span></span>|

 <span data-ttu-id="2a700-424">En la tabla siguiente se muestran los datos del evento</span><span class="sxs-lookup"><span data-stu-id="2a700-424">The following table shows the event data</span></span>

|<span data-ttu-id="2a700-425">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-425">Field name</span></span>|<span data-ttu-id="2a700-426">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-426">Data type</span></span>|<span data-ttu-id="2a700-427">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-427">Description</span></span>|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|<span data-ttu-id="2a700-428">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-428">Reserved for internal use.</span></span>|
|`Overlapped`|`win:Pointer`|<span data-ttu-id="2a700-429">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2a700-429">Reserved for internal use.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-430">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-430">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadcreating-event"></a><span data-ttu-id="2a700-431">Evento ThreadCreating</span><span class="sxs-lookup"><span data-stu-id="2a700-431">ThreadCreating event</span></span>

 <span data-ttu-id="2a700-432">En la tabla siguiente se muestran las palabras clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-432">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="2a700-433">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-433">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-434">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-435">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-435">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-436">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-436">Informational (4)</span></span>|

 <span data-ttu-id="2a700-437">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-437">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-438">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-438">Event</span></span>|<span data-ttu-id="2a700-439">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-439">Event ID</span></span>|<span data-ttu-id="2a700-440">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-440">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadCreating`|<span data-ttu-id="2a700-441">70</span><span class="sxs-lookup"><span data-stu-id="2a700-441">70</span></span>|<span data-ttu-id="2a700-442">Se ha creado el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2a700-442">Thread has been created.</span></span>|

 <span data-ttu-id="2a700-443">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-443">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-444">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-444">Field name</span></span>|<span data-ttu-id="2a700-445">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-445">Data type</span></span>|<span data-ttu-id="2a700-446">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-446">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="2a700-447">Id. de subproceso</span><span class="sxs-lookup"><span data-stu-id="2a700-447">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-448">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-448">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="threadrunning-event"></a><span data-ttu-id="2a700-449">Evento ThreadRunning</span><span class="sxs-lookup"><span data-stu-id="2a700-449">ThreadRunning event</span></span>

 <span data-ttu-id="2a700-450">En la tabla siguiente se muestran las palabras clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2a700-450">The following table shows the keywords and level.</span></span>

|<span data-ttu-id="2a700-451">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2a700-451">Keyword for raising the event</span></span>|<span data-ttu-id="2a700-452">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a700-452">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="2a700-453">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="2a700-453">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="2a700-454">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2a700-454">Informational (4)</span></span>|

 <span data-ttu-id="2a700-455">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-455">The following table shows the event information.</span></span>

|<span data-ttu-id="2a700-456">Evento</span><span class="sxs-lookup"><span data-stu-id="2a700-456">Event</span></span>|<span data-ttu-id="2a700-457">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2a700-457">Event ID</span></span>|<span data-ttu-id="2a700-458">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-458">Description</span></span>|
|----------------|---------------|-----------------|
|`ThreadRunning`|<span data-ttu-id="2a700-459">71</span><span class="sxs-lookup"><span data-stu-id="2a700-459">71</span></span>|<span data-ttu-id="2a700-460">El subproceso ha empezado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2a700-460">Thread has started running.</span></span>|

 <span data-ttu-id="2a700-461">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2a700-461">The following table shows the event data.</span></span>

|<span data-ttu-id="2a700-462">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2a700-462">Field name</span></span>|<span data-ttu-id="2a700-463">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2a700-463">Data type</span></span>|<span data-ttu-id="2a700-464">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a700-464">Description</span></span>|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|<span data-ttu-id="2a700-465">Id. de subproceso</span><span class="sxs-lookup"><span data-stu-id="2a700-465">Thread ID</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="2a700-466">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2a700-466">Unique ID for the instance of CoreCLR.</span></span>|
