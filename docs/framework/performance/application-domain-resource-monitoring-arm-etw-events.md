---
title: Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040562"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="8d4ee-102">Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="8d4ee-103">Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="8d4ee-104">Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="8d4ee-105">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="8d4ee-105">ThreadCreated Event</span></span>

<span data-ttu-id="8d4ee-106">Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="8d4ee-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="8d4ee-107">Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="8d4ee-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="8d4ee-109">Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8d4ee-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="8d4ee-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-110">Keyword for raising the event</span></span>|<span data-ttu-id="8d4ee-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d4ee-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8d4ee-112">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8d4ee-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-113">Informational(4)</span></span>|
|<span data-ttu-id="8d4ee-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8d4ee-115">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-115">Informational(4)</span></span>|

<span data-ttu-id="8d4ee-116">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-116">The following table shows the event information:</span></span>

|<span data-ttu-id="8d4ee-117">evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-117">Event</span></span>|<span data-ttu-id="8d4ee-118">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-118">Event ID</span></span>|<span data-ttu-id="8d4ee-119">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8d4ee-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="8d4ee-120">85</span><span class="sxs-lookup"><span data-stu-id="8d4ee-120">85</span></span>|<span data-ttu-id="8d4ee-121">Se crea un subproceso para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="8d4ee-122">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8d4ee-122">The following table shows the event data:</span></span>

|<span data-ttu-id="8d4ee-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="8d4ee-123">Field name</span></span>|<span data-ttu-id="8d4ee-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d4ee-124">Data type</span></span>|<span data-ttu-id="8d4ee-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d4ee-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8d4ee-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-126">ThreadID</span></span>|<span data-ttu-id="8d4ee-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-127">win:UInt64</span></span>|<span data-ttu-id="8d4ee-128">Se creó el identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="8d4ee-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-129">AppDomainID</span></span>|<span data-ttu-id="8d4ee-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-130">win:UInt64</span></span>|<span data-ttu-id="8d4ee-131">Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="8d4ee-132">Marcas</span><span class="sxs-lookup"><span data-stu-id="8d4ee-132">Flags</span></span>|<span data-ttu-id="8d4ee-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8d4ee-133">win:UInt32</span></span>|<span data-ttu-id="8d4ee-134">Marcas de creación de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-134">Thread creation flags.</span></span>|
|<span data-ttu-id="8d4ee-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="8d4ee-135">ManagedThreadIndex</span></span>|<span data-ttu-id="8d4ee-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8d4ee-136">win:UInt32</span></span>|<span data-ttu-id="8d4ee-137">Se creó el índice administrado del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="8d4ee-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-138">OSThreadID</span></span>|<span data-ttu-id="8d4ee-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="8d4ee-139">win:UInt32</span></span>|<span data-ttu-id="8d4ee-140">Se creó el identificador del sistema operativo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="8d4ee-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-141">ClrInstanceID</span></span>|<span data-ttu-id="8d4ee-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8d4ee-142">win:UInt16</span></span>|<span data-ttu-id="8d4ee-143">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="8d4ee-144">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="8d4ee-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="8d4ee-145">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8d4ee-146">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-146">Keyword for raising the event</span></span>|<span data-ttu-id="8d4ee-147">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d4ee-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8d4ee-148">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8d4ee-149">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-149">Informational(4)</span></span>|

<span data-ttu-id="8d4ee-150">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-150">The following table shows the event information:</span></span>

|<span data-ttu-id="8d4ee-151">evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-151">Event</span></span>|<span data-ttu-id="8d4ee-152">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-152">Event ID</span></span>|<span data-ttu-id="8d4ee-153">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8d4ee-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="8d4ee-154">83</span><span class="sxs-lookup"><span data-stu-id="8d4ee-154">83</span></span>|<span data-ttu-id="8d4ee-155">Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="8d4ee-156">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8d4ee-156">The following table shows the event data:</span></span>

|<span data-ttu-id="8d4ee-157">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="8d4ee-157">Field name</span></span>|<span data-ttu-id="8d4ee-158">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d4ee-158">Data type</span></span>|<span data-ttu-id="8d4ee-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d4ee-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8d4ee-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-160">AppDomainID</span></span>|<span data-ttu-id="8d4ee-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-161">win:UInt64</span></span>|<span data-ttu-id="8d4ee-162">Identificador del dominio de la aplicación para el que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="8d4ee-163">Allocated</span><span class="sxs-lookup"><span data-stu-id="8d4ee-163">Allocated</span></span>|<span data-ttu-id="8d4ee-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-164">win:UInt64</span></span>|<span data-ttu-id="8d4ee-165">Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).</span><span class="sxs-lookup"><span data-stu-id="8d4ee-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="8d4ee-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-166">ClrInstanceID</span></span>|<span data-ttu-id="8d4ee-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8d4ee-167">win:UInt16</span></span>|<span data-ttu-id="8d4ee-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="8d4ee-169">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="8d4ee-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="8d4ee-170">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8d4ee-171">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-171">Keyword for raising the event</span></span>|<span data-ttu-id="8d4ee-172">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d4ee-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8d4ee-173">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8d4ee-174">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-174">Informational(4)</span></span>|

<span data-ttu-id="8d4ee-175">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-175">The following table shows the event information:</span></span>

|<span data-ttu-id="8d4ee-176">evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-176">Event</span></span>|<span data-ttu-id="8d4ee-177">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-177">Event ID</span></span>|<span data-ttu-id="8d4ee-178">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8d4ee-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="8d4ee-179">84</span><span class="sxs-lookup"><span data-stu-id="8d4ee-179">84</span></span>|<span data-ttu-id="8d4ee-180">Fnalizadas todas las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="8d4ee-181">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8d4ee-181">The following table shows the event data:</span></span>

|<span data-ttu-id="8d4ee-182">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="8d4ee-182">Field name</span></span>|<span data-ttu-id="8d4ee-183">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d4ee-183">Data type</span></span>|<span data-ttu-id="8d4ee-184">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d4ee-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8d4ee-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-185">AppDomainID</span></span>|<span data-ttu-id="8d4ee-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-186">win:UInt64</span></span>|<span data-ttu-id="8d4ee-187">Identificador del dominio para el que recurso que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="8d4ee-188">Survived</span><span class="sxs-lookup"><span data-stu-id="8d4ee-188">Survived</span></span>|<span data-ttu-id="8d4ee-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-189">win:UInt64</span></span>|<span data-ttu-id="8d4ee-190">Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="8d4ee-191">Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="8d4ee-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="8d4ee-192">ProcessSurvived</span></span>|<span data-ttu-id="8d4ee-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-193">win:UInt64</span></span>|<span data-ttu-id="8d4ee-194">Bytes totales que sobrevivieron de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="8d4ee-195">Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="8d4ee-196">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="8d4ee-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-197">ClrInstanceID</span></span>|<span data-ttu-id="8d4ee-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8d4ee-198">win:UInt16</span></span>|<span data-ttu-id="8d4ee-199">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="8d4ee-200">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="8d4ee-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="8d4ee-201">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8d4ee-202">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-202">Keyword for raising the event</span></span>|<span data-ttu-id="8d4ee-203">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d4ee-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8d4ee-204">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8d4ee-205">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-205">Informational(4)</span></span>|
|<span data-ttu-id="8d4ee-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8d4ee-207">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-207">Informational(4)</span></span>|

<span data-ttu-id="8d4ee-208">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-208">The following table shows the event information:</span></span>

|<span data-ttu-id="8d4ee-209">evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-209">Event</span></span>|<span data-ttu-id="8d4ee-210">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-210">Event ID</span></span>|<span data-ttu-id="8d4ee-211">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8d4ee-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="8d4ee-212">87</span><span class="sxs-lookup"><span data-stu-id="8d4ee-212">87</span></span>|<span data-ttu-id="8d4ee-213">Un subproceso entra en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="8d4ee-214">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8d4ee-214">The following table shows the event data:</span></span>

|<span data-ttu-id="8d4ee-215">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="8d4ee-215">Field name</span></span>|<span data-ttu-id="8d4ee-216">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d4ee-216">Data type</span></span>|<span data-ttu-id="8d4ee-217">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d4ee-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8d4ee-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-218">ThreadID</span></span>|<span data-ttu-id="8d4ee-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-219">win:UInt64</span></span>|<span data-ttu-id="8d4ee-220">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-220">The thread identifier.</span></span>|
|<span data-ttu-id="8d4ee-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-221">AppDomainID</span></span>|<span data-ttu-id="8d4ee-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-222">win:UInt64</span></span>|<span data-ttu-id="8d4ee-223">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-223">The application domain identifier.</span></span>|
|<span data-ttu-id="8d4ee-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-224">ClrInstanceID</span></span>|<span data-ttu-id="8d4ee-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8d4ee-225">win:UInt16</span></span>|<span data-ttu-id="8d4ee-226">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="8d4ee-227">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="8d4ee-227">ThreadTerminated Event</span></span>

<span data-ttu-id="8d4ee-228">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="8d4ee-229">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-229">Keyword for raising the event</span></span>|<span data-ttu-id="8d4ee-230">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d4ee-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="8d4ee-231">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="8d4ee-232">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-232">Informational(4)</span></span>|
|<span data-ttu-id="8d4ee-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="8d4ee-234">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-234">Informational(4)</span></span>|

<span data-ttu-id="8d4ee-235">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-235">The following table shows the event information:</span></span>

|<span data-ttu-id="8d4ee-236">evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-236">Event</span></span>|<span data-ttu-id="8d4ee-237">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d4ee-237">Event ID</span></span>|<span data-ttu-id="8d4ee-238">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="8d4ee-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="8d4ee-239">86</span><span class="sxs-lookup"><span data-stu-id="8d4ee-239">86</span></span>|<span data-ttu-id="8d4ee-240">Finaliza un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-240">A thread terminates.</span></span>|

<span data-ttu-id="8d4ee-241">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="8d4ee-241">The following table shows the event data:</span></span>

|<span data-ttu-id="8d4ee-242">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="8d4ee-242">Field name</span></span>|<span data-ttu-id="8d4ee-243">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8d4ee-243">Data type</span></span>|<span data-ttu-id="8d4ee-244">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d4ee-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="8d4ee-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-245">ThreadID</span></span>|<span data-ttu-id="8d4ee-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-246">win:UInt64</span></span>|<span data-ttu-id="8d4ee-247">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-247">The thread identifier.</span></span>|
|<span data-ttu-id="8d4ee-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-248">AppDomainID</span></span>|<span data-ttu-id="8d4ee-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="8d4ee-249">win:UInt64</span></span>|<span data-ttu-id="8d4ee-250">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-250">The application domain identifier.</span></span>|
|<span data-ttu-id="8d4ee-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="8d4ee-251">ClrInstanceID</span></span>|<span data-ttu-id="8d4ee-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="8d4ee-252">win:UInt16</span></span>|<span data-ttu-id="8d4ee-253">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="8d4ee-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="8d4ee-254">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d4ee-254">See also</span></span>

- [<span data-ttu-id="8d4ee-255">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="8d4ee-255">CLR ETW Events</span></span>](clr-etw-events.md)
