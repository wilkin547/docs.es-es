---
title: Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: 0e453b2bafffd9e07a1bdddd97282c5b97f5483d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716218"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="1eef6-102">Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)</span><span class="sxs-lookup"><span data-stu-id="1eef6-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="1eef6-103">Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="1eef6-104">Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.</span><span class="sxs-lookup"><span data-stu-id="1eef6-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="1eef6-105">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="1eef6-105">ThreadCreated Event</span></span>

<span data-ttu-id="1eef6-106">Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="1eef6-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="1eef6-107">Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="1eef6-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="1eef6-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1eef6-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="1eef6-109">Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1eef6-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="1eef6-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-110">Keyword for raising the event</span></span>|<span data-ttu-id="1eef6-111">Level</span><span class="sxs-lookup"><span data-stu-id="1eef6-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1eef6-112">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="1eef6-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1eef6-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-113">Informational(4)</span></span>|
|<span data-ttu-id="1eef6-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1eef6-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1eef6-115">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-115">Informational(4)</span></span>|

<span data-ttu-id="1eef6-116">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1eef6-116">The following table shows the event information:</span></span>

|<span data-ttu-id="1eef6-117">Event</span><span class="sxs-lookup"><span data-stu-id="1eef6-117">Event</span></span>|<span data-ttu-id="1eef6-118">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-118">Event ID</span></span>|<span data-ttu-id="1eef6-119">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1eef6-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="1eef6-120">85</span><span class="sxs-lookup"><span data-stu-id="1eef6-120">85</span></span>|<span data-ttu-id="1eef6-121">Se crea un subproceso para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="1eef6-122">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1eef6-122">The following table shows the event data:</span></span>

|<span data-ttu-id="1eef6-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1eef6-123">Field name</span></span>|<span data-ttu-id="1eef6-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1eef6-124">Data type</span></span>|<span data-ttu-id="1eef6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef6-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1eef6-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1eef6-126">ThreadID</span></span>|<span data-ttu-id="1eef6-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-127">win:UInt64</span></span>|<span data-ttu-id="1eef6-128">Se creó el identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="1eef6-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1eef6-129">AppDomainID</span></span>|<span data-ttu-id="1eef6-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-130">win:UInt64</span></span>|<span data-ttu-id="1eef6-131">Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="1eef6-132">Marcas</span><span class="sxs-lookup"><span data-stu-id="1eef6-132">Flags</span></span>|<span data-ttu-id="1eef6-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1eef6-133">win:UInt32</span></span>|<span data-ttu-id="1eef6-134">Marcas de creación de subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-134">Thread creation flags.</span></span>|
|<span data-ttu-id="1eef6-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="1eef6-135">ManagedThreadIndex</span></span>|<span data-ttu-id="1eef6-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1eef6-136">win:UInt32</span></span>|<span data-ttu-id="1eef6-137">Se creó el índice administrado del subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="1eef6-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="1eef6-138">OSThreadID</span></span>|<span data-ttu-id="1eef6-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1eef6-139">win:UInt32</span></span>|<span data-ttu-id="1eef6-140">Se creó el identificador del sistema operativo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="1eef6-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1eef6-141">ClrInstanceID</span></span>|<span data-ttu-id="1eef6-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1eef6-142">win:UInt16</span></span>|<span data-ttu-id="1eef6-143">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1eef6-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="1eef6-144">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="1eef6-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="1eef6-145">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1eef6-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1eef6-146">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-146">Keyword for raising the event</span></span>|<span data-ttu-id="1eef6-147">Level</span><span class="sxs-lookup"><span data-stu-id="1eef6-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1eef6-148">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="1eef6-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1eef6-149">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-149">Informational(4)</span></span>|

<span data-ttu-id="1eef6-150">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1eef6-150">The following table shows the event information:</span></span>

|<span data-ttu-id="1eef6-151">Event</span><span class="sxs-lookup"><span data-stu-id="1eef6-151">Event</span></span>|<span data-ttu-id="1eef6-152">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-152">Event ID</span></span>|<span data-ttu-id="1eef6-153">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1eef6-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="1eef6-154">83</span><span class="sxs-lookup"><span data-stu-id="1eef6-154">83</span></span>|<span data-ttu-id="1eef6-155">Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="1eef6-156">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1eef6-156">The following table shows the event data:</span></span>

|<span data-ttu-id="1eef6-157">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1eef6-157">Field name</span></span>|<span data-ttu-id="1eef6-158">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1eef6-158">Data type</span></span>|<span data-ttu-id="1eef6-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef6-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1eef6-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1eef6-160">AppDomainID</span></span>|<span data-ttu-id="1eef6-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-161">win:UInt64</span></span>|<span data-ttu-id="1eef6-162">Identificador del dominio de la aplicación para el que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="1eef6-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="1eef6-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="1eef6-163">Allocated</span></span>|<span data-ttu-id="1eef6-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-164">win:UInt64</span></span>|<span data-ttu-id="1eef6-165">Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).</span><span class="sxs-lookup"><span data-stu-id="1eef6-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="1eef6-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1eef6-166">ClrInstanceID</span></span>|<span data-ttu-id="1eef6-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1eef6-167">win:UInt16</span></span>|<span data-ttu-id="1eef6-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1eef6-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="1eef6-169">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="1eef6-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="1eef6-170">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1eef6-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1eef6-171">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-171">Keyword for raising the event</span></span>|<span data-ttu-id="1eef6-172">Level</span><span class="sxs-lookup"><span data-stu-id="1eef6-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1eef6-173">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="1eef6-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1eef6-174">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-174">Informational(4)</span></span>|

<span data-ttu-id="1eef6-175">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1eef6-175">The following table shows the event information:</span></span>

|<span data-ttu-id="1eef6-176">Event</span><span class="sxs-lookup"><span data-stu-id="1eef6-176">Event</span></span>|<span data-ttu-id="1eef6-177">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-177">Event ID</span></span>|<span data-ttu-id="1eef6-178">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1eef6-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="1eef6-179">84</span><span class="sxs-lookup"><span data-stu-id="1eef6-179">84</span></span>|<span data-ttu-id="1eef6-180">Fnalizadas todas las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1eef6-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="1eef6-181">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1eef6-181">The following table shows the event data:</span></span>

|<span data-ttu-id="1eef6-182">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1eef6-182">Field name</span></span>|<span data-ttu-id="1eef6-183">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1eef6-183">Data type</span></span>|<span data-ttu-id="1eef6-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef6-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1eef6-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1eef6-185">AppDomainID</span></span>|<span data-ttu-id="1eef6-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-186">win:UInt64</span></span>|<span data-ttu-id="1eef6-187">Identificador del dominio para el que recurso que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="1eef6-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="1eef6-188">Survived</span><span class="sxs-lookup"><span data-stu-id="1eef6-188">Survived</span></span>|<span data-ttu-id="1eef6-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-189">win:UInt64</span></span>|<span data-ttu-id="1eef6-190">Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="1eef6-191">Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.</span><span class="sxs-lookup"><span data-stu-id="1eef6-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="1eef6-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="1eef6-192">ProcessSurvived</span></span>|<span data-ttu-id="1eef6-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-193">win:UInt64</span></span>|<span data-ttu-id="1eef6-194">Bytes totales que sobrevivieron de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="1eef6-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="1eef6-195">Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="1eef6-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="1eef6-196">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="1eef6-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="1eef6-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1eef6-197">ClrInstanceID</span></span>|<span data-ttu-id="1eef6-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1eef6-198">win:UInt16</span></span>|<span data-ttu-id="1eef6-199">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1eef6-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="1eef6-200">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="1eef6-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="1eef6-201">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1eef6-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1eef6-202">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-202">Keyword for raising the event</span></span>|<span data-ttu-id="1eef6-203">Level</span><span class="sxs-lookup"><span data-stu-id="1eef6-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1eef6-204">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="1eef6-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1eef6-205">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-205">Informational(4)</span></span>|
|<span data-ttu-id="1eef6-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1eef6-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1eef6-207">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-207">Informational(4)</span></span>|

<span data-ttu-id="1eef6-208">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1eef6-208">The following table shows the event information:</span></span>

|<span data-ttu-id="1eef6-209">Event</span><span class="sxs-lookup"><span data-stu-id="1eef6-209">Event</span></span>|<span data-ttu-id="1eef6-210">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-210">Event ID</span></span>|<span data-ttu-id="1eef6-211">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1eef6-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="1eef6-212">87</span><span class="sxs-lookup"><span data-stu-id="1eef6-212">87</span></span>|<span data-ttu-id="1eef6-213">Un subproceso entra en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="1eef6-214">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1eef6-214">The following table shows the event data:</span></span>

|<span data-ttu-id="1eef6-215">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1eef6-215">Field name</span></span>|<span data-ttu-id="1eef6-216">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1eef6-216">Data type</span></span>|<span data-ttu-id="1eef6-217">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef6-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1eef6-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1eef6-218">ThreadID</span></span>|<span data-ttu-id="1eef6-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-219">win:UInt64</span></span>|<span data-ttu-id="1eef6-220">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-220">The thread identifier.</span></span>|
|<span data-ttu-id="1eef6-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1eef6-221">AppDomainID</span></span>|<span data-ttu-id="1eef6-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-222">win:UInt64</span></span>|<span data-ttu-id="1eef6-223">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-223">The application domain identifier.</span></span>|
|<span data-ttu-id="1eef6-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1eef6-224">ClrInstanceID</span></span>|<span data-ttu-id="1eef6-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1eef6-225">win:UInt16</span></span>|<span data-ttu-id="1eef6-226">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1eef6-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="1eef6-227">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="1eef6-227">ThreadTerminated Event</span></span>

<span data-ttu-id="1eef6-228">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="1eef6-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="1eef6-229">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-229">Keyword for raising the event</span></span>|<span data-ttu-id="1eef6-230">Level</span><span class="sxs-lookup"><span data-stu-id="1eef6-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="1eef6-231">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="1eef6-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="1eef6-232">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-232">Informational(4)</span></span>|
|<span data-ttu-id="1eef6-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1eef6-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1eef6-234">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1eef6-234">Informational(4)</span></span>|

<span data-ttu-id="1eef6-235">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="1eef6-235">The following table shows the event information:</span></span>

|<span data-ttu-id="1eef6-236">Event</span><span class="sxs-lookup"><span data-stu-id="1eef6-236">Event</span></span>|<span data-ttu-id="1eef6-237">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1eef6-237">Event ID</span></span>|<span data-ttu-id="1eef6-238">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="1eef6-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="1eef6-239">86</span><span class="sxs-lookup"><span data-stu-id="1eef6-239">86</span></span>|<span data-ttu-id="1eef6-240">Finaliza un subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-240">A thread terminates.</span></span>|

<span data-ttu-id="1eef6-241">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="1eef6-241">The following table shows the event data:</span></span>

|<span data-ttu-id="1eef6-242">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="1eef6-242">Field name</span></span>|<span data-ttu-id="1eef6-243">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1eef6-243">Data type</span></span>|<span data-ttu-id="1eef6-244">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef6-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="1eef6-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="1eef6-245">ThreadID</span></span>|<span data-ttu-id="1eef6-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-246">win:UInt64</span></span>|<span data-ttu-id="1eef6-247">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="1eef6-247">The thread identifier.</span></span>|
|<span data-ttu-id="1eef6-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="1eef6-248">AppDomainID</span></span>|<span data-ttu-id="1eef6-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1eef6-249">win:UInt64</span></span>|<span data-ttu-id="1eef6-250">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1eef6-250">The application domain identifier.</span></span>|
|<span data-ttu-id="1eef6-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1eef6-251">ClrInstanceID</span></span>|<span data-ttu-id="1eef6-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1eef6-252">win:UInt16</span></span>|<span data-ttu-id="1eef6-253">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1eef6-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1eef6-254">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eef6-254">See also</span></span>

- [<span data-ttu-id="1eef6-255">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="1eef6-255">CLR ETW Events</span></span>](clr-etw-events.md)
