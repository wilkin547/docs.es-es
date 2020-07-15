---
title: Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
description: Lea acerca de los eventos ETW de supervisión de recursos del dominio de aplicación (ARM) en .NET, como ThreadCreated (, AppDomainMemAllocated, AppDomainMemSurvived, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309786"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="8dfc2-103">Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="8dfc2-104">Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="8dfc2-105">Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="8dfc2-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="8dfc2-106">ThreadCreated Event</span></span>

<span data-ttu-id="8dfc2-107">Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="8dfc2-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="8dfc2-108">Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="8dfc2-109">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="8dfc2-110">Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8dfc2-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="8dfc2-111">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-111">Keyword for raising the event</span></span>|<span data-ttu-id="8dfc2-112">Nivel</span><span class="sxs-lookup"><span data-stu-id="8dfc2-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8dfc2-113">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8dfc2-114">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-114">Informational(4)</span></span>|
|<span data-ttu-id="8dfc2-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8dfc2-116">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-116">Informational(4)</span></span>|

<span data-ttu-id="8dfc2-117">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-117">The following table shows the event information:</span></span>

|<span data-ttu-id="8dfc2-118">Evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-118">Event</span></span>|<span data-ttu-id="8dfc2-119">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-119">Event ID</span></span>|<span data-ttu-id="8dfc2-120">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8dfc2-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="8dfc2-121">85</span><span class="sxs-lookup"><span data-stu-id="8dfc2-121">85</span></span>|<span data-ttu-id="8dfc2-122">Se crea un subproceso para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="8dfc2-123">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8dfc2-123">The following table shows the event data:</span></span>

|<span data-ttu-id="8dfc2-124">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="8dfc2-124">Field name</span></span>|<span data-ttu-id="8dfc2-125">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8dfc2-125">Data type</span></span>|<span data-ttu-id="8dfc2-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfc2-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8dfc2-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-127">ThreadID</span></span>|<span data-ttu-id="8dfc2-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-128">win:UInt64</span></span>|<span data-ttu-id="8dfc2-129">Se creó el identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="8dfc2-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-130">AppDomainID</span></span>|<span data-ttu-id="8dfc2-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-131">win:UInt64</span></span>|<span data-ttu-id="8dfc2-132">Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="8dfc2-133">Marcas</span><span class="sxs-lookup"><span data-stu-id="8dfc2-133">Flags</span></span>|<span data-ttu-id="8dfc2-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8dfc2-134">win:UInt32</span></span>|<span data-ttu-id="8dfc2-135">Marcas de creación de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-135">Thread creation flags.</span></span>|
|<span data-ttu-id="8dfc2-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="8dfc2-136">ManagedThreadIndex</span></span>|<span data-ttu-id="8dfc2-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8dfc2-137">win:UInt32</span></span>|<span data-ttu-id="8dfc2-138">Se creó el índice administrado del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="8dfc2-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-139">OSThreadID</span></span>|<span data-ttu-id="8dfc2-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8dfc2-140">win:UInt32</span></span>|<span data-ttu-id="8dfc2-141">Se creó el identificador del sistema operativo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="8dfc2-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-142">ClrInstanceID</span></span>|<span data-ttu-id="8dfc2-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8dfc2-143">win:UInt16</span></span>|<span data-ttu-id="8dfc2-144">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="8dfc2-145">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="8dfc2-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="8dfc2-146">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8dfc2-147">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-147">Keyword for raising the event</span></span>|<span data-ttu-id="8dfc2-148">Nivel</span><span class="sxs-lookup"><span data-stu-id="8dfc2-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8dfc2-149">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8dfc2-150">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-150">Informational(4)</span></span>|

<span data-ttu-id="8dfc2-151">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-151">The following table shows the event information:</span></span>

|<span data-ttu-id="8dfc2-152">Evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-152">Event</span></span>|<span data-ttu-id="8dfc2-153">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-153">Event ID</span></span>|<span data-ttu-id="8dfc2-154">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8dfc2-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="8dfc2-155">83</span><span class="sxs-lookup"><span data-stu-id="8dfc2-155">83</span></span>|<span data-ttu-id="8dfc2-156">Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="8dfc2-157">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8dfc2-157">The following table shows the event data:</span></span>

|<span data-ttu-id="8dfc2-158">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="8dfc2-158">Field name</span></span>|<span data-ttu-id="8dfc2-159">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8dfc2-159">Data type</span></span>|<span data-ttu-id="8dfc2-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfc2-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8dfc2-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-161">AppDomainID</span></span>|<span data-ttu-id="8dfc2-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-162">win:UInt64</span></span>|<span data-ttu-id="8dfc2-163">Identificador del dominio de la aplicación para el que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="8dfc2-164">Allocated</span><span class="sxs-lookup"><span data-stu-id="8dfc2-164">Allocated</span></span>|<span data-ttu-id="8dfc2-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-165">win:UInt64</span></span>|<span data-ttu-id="8dfc2-166">Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).</span><span class="sxs-lookup"><span data-stu-id="8dfc2-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="8dfc2-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-167">ClrInstanceID</span></span>|<span data-ttu-id="8dfc2-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8dfc2-168">win:UInt16</span></span>|<span data-ttu-id="8dfc2-169">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="8dfc2-170">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="8dfc2-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="8dfc2-171">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8dfc2-172">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-172">Keyword for raising the event</span></span>|<span data-ttu-id="8dfc2-173">Nivel</span><span class="sxs-lookup"><span data-stu-id="8dfc2-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8dfc2-174">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8dfc2-175">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-175">Informational(4)</span></span>|

<span data-ttu-id="8dfc2-176">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-176">The following table shows the event information:</span></span>

|<span data-ttu-id="8dfc2-177">Evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-177">Event</span></span>|<span data-ttu-id="8dfc2-178">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-178">Event ID</span></span>|<span data-ttu-id="8dfc2-179">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8dfc2-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="8dfc2-180">84</span><span class="sxs-lookup"><span data-stu-id="8dfc2-180">84</span></span>|<span data-ttu-id="8dfc2-181">Fnalizadas todas las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="8dfc2-182">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8dfc2-182">The following table shows the event data:</span></span>

|<span data-ttu-id="8dfc2-183">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="8dfc2-183">Field name</span></span>|<span data-ttu-id="8dfc2-184">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8dfc2-184">Data type</span></span>|<span data-ttu-id="8dfc2-185">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfc2-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8dfc2-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-186">AppDomainID</span></span>|<span data-ttu-id="8dfc2-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-187">win:UInt64</span></span>|<span data-ttu-id="8dfc2-188">Identificador del dominio para el que recurso que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="8dfc2-189">Survived</span><span class="sxs-lookup"><span data-stu-id="8dfc2-189">Survived</span></span>|<span data-ttu-id="8dfc2-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-190">win:UInt64</span></span>|<span data-ttu-id="8dfc2-191">Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="8dfc2-192">Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="8dfc2-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="8dfc2-193">ProcessSurvived</span></span>|<span data-ttu-id="8dfc2-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-194">win:UInt64</span></span>|<span data-ttu-id="8dfc2-195">Bytes totales que sobrevivieron de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="8dfc2-196">Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="8dfc2-197">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="8dfc2-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-198">ClrInstanceID</span></span>|<span data-ttu-id="8dfc2-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8dfc2-199">win:UInt16</span></span>|<span data-ttu-id="8dfc2-200">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="8dfc2-201">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="8dfc2-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="8dfc2-202">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8dfc2-203">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-203">Keyword for raising the event</span></span>|<span data-ttu-id="8dfc2-204">Nivel</span><span class="sxs-lookup"><span data-stu-id="8dfc2-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8dfc2-205">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8dfc2-206">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-206">Informational(4)</span></span>|
|<span data-ttu-id="8dfc2-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8dfc2-208">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-208">Informational(4)</span></span>|

<span data-ttu-id="8dfc2-209">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-209">The following table shows the event information:</span></span>

|<span data-ttu-id="8dfc2-210">Evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-210">Event</span></span>|<span data-ttu-id="8dfc2-211">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-211">Event ID</span></span>|<span data-ttu-id="8dfc2-212">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8dfc2-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="8dfc2-213">87</span><span class="sxs-lookup"><span data-stu-id="8dfc2-213">87</span></span>|<span data-ttu-id="8dfc2-214">Un subproceso entra en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="8dfc2-215">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8dfc2-215">The following table shows the event data:</span></span>

|<span data-ttu-id="8dfc2-216">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="8dfc2-216">Field name</span></span>|<span data-ttu-id="8dfc2-217">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8dfc2-217">Data type</span></span>|<span data-ttu-id="8dfc2-218">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfc2-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8dfc2-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-219">ThreadID</span></span>|<span data-ttu-id="8dfc2-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-220">win:UInt64</span></span>|<span data-ttu-id="8dfc2-221">Identificador de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-221">The thread identifier.</span></span>|
|<span data-ttu-id="8dfc2-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-222">AppDomainID</span></span>|<span data-ttu-id="8dfc2-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-223">win:UInt64</span></span>|<span data-ttu-id="8dfc2-224">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-224">The application domain identifier.</span></span>|
|<span data-ttu-id="8dfc2-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-225">ClrInstanceID</span></span>|<span data-ttu-id="8dfc2-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8dfc2-226">win:UInt16</span></span>|<span data-ttu-id="8dfc2-227">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="8dfc2-228">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="8dfc2-228">ThreadTerminated Event</span></span>

<span data-ttu-id="8dfc2-229">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8dfc2-230">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-230">Keyword for raising the event</span></span>|<span data-ttu-id="8dfc2-231">Nivel</span><span class="sxs-lookup"><span data-stu-id="8dfc2-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8dfc2-232">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8dfc2-233">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-233">Informational(4)</span></span>|
|<span data-ttu-id="8dfc2-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8dfc2-235">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-235">Informational(4)</span></span>|

<span data-ttu-id="8dfc2-236">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-236">The following table shows the event information:</span></span>

|<span data-ttu-id="8dfc2-237">Evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-237">Event</span></span>|<span data-ttu-id="8dfc2-238">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8dfc2-238">Event ID</span></span>|<span data-ttu-id="8dfc2-239">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8dfc2-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="8dfc2-240">86</span><span class="sxs-lookup"><span data-stu-id="8dfc2-240">86</span></span>|<span data-ttu-id="8dfc2-241">Finaliza un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-241">A thread terminates.</span></span>|

<span data-ttu-id="8dfc2-242">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8dfc2-242">The following table shows the event data:</span></span>

|<span data-ttu-id="8dfc2-243">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="8dfc2-243">Field name</span></span>|<span data-ttu-id="8dfc2-244">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8dfc2-244">Data type</span></span>|<span data-ttu-id="8dfc2-245">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dfc2-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8dfc2-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-246">ThreadID</span></span>|<span data-ttu-id="8dfc2-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-247">win:UInt64</span></span>|<span data-ttu-id="8dfc2-248">Identificador de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-248">The thread identifier.</span></span>|
|<span data-ttu-id="8dfc2-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-249">AppDomainID</span></span>|<span data-ttu-id="8dfc2-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8dfc2-250">win:UInt64</span></span>|<span data-ttu-id="8dfc2-251">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-251">The application domain identifier.</span></span>|
|<span data-ttu-id="8dfc2-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8dfc2-252">ClrInstanceID</span></span>|<span data-ttu-id="8dfc2-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8dfc2-253">win:UInt16</span></span>|<span data-ttu-id="8dfc2-254">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8dfc2-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8dfc2-255">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8dfc2-255">See also</span></span>

- [<span data-ttu-id="8dfc2-256">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="8dfc2-256">CLR ETW Events</span></span>](clr-etw-events.md)
