---
title: "Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6384700c7039cb705f2db759ebd3d733bf8954ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="f3038-102">Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)</span><span class="sxs-lookup"><span data-stu-id="f3038-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="f3038-103">Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="f3038-104">Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.</span><span class="sxs-lookup"><span data-stu-id="f3038-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="f3038-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="f3038-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="f3038-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f3038-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="f3038-107">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="f3038-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="f3038-108">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="f3038-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="f3038-109">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="f3038-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="f3038-110">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="f3038-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="f3038-111">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f3038-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="f3038-112">Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="f3038-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="f3038-113">Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="f3038-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="f3038-114">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f3038-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="f3038-115">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="f3038-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f3038-116">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f3038-116">Keyword for raising the event</span></span>|<span data-ttu-id="f3038-117">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3038-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f3038-118">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f3038-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f3038-119">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-119">Informational(4)</span></span>|  
|<span data-ttu-id="f3038-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f3038-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f3038-121">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="f3038-122">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f3038-123">Evento</span><span class="sxs-lookup"><span data-stu-id="f3038-123">Event</span></span>|<span data-ttu-id="f3038-124">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f3038-124">Event ID</span></span>|<span data-ttu-id="f3038-125">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f3038-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="f3038-126">85</span><span class="sxs-lookup"><span data-stu-id="f3038-126">85</span></span>|<span data-ttu-id="f3038-127">Se crea un subproceso para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="f3038-128">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f3038-129">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f3038-129">Field name</span></span>|<span data-ttu-id="f3038-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3038-130">Data type</span></span>|<span data-ttu-id="f3038-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3038-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f3038-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f3038-132">ThreadID</span></span>|<span data-ttu-id="f3038-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-133">win:UInt64</span></span>|<span data-ttu-id="f3038-134">Se creó el identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f3038-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f3038-135">AppDomainID</span></span>|<span data-ttu-id="f3038-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-136">win:UInt64</span></span>|<span data-ttu-id="f3038-137">Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="f3038-138">Marcas</span><span class="sxs-lookup"><span data-stu-id="f3038-138">Flags</span></span>|<span data-ttu-id="f3038-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f3038-139">win:UInt32</span></span>|<span data-ttu-id="f3038-140">Marcas de creación de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="f3038-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="f3038-141">ManagedThreadIndex</span></span>|<span data-ttu-id="f3038-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f3038-142">win:UInt32</span></span>|<span data-ttu-id="f3038-143">Se creó el índice administrado del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="f3038-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="f3038-144">OSThreadID</span></span>|<span data-ttu-id="f3038-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f3038-145">win:UInt32</span></span>|<span data-ttu-id="f3038-146">Se creó el identificador del sistema operativo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f3038-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f3038-147">ClrInstanceID</span></span>|<span data-ttu-id="f3038-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f3038-148">win:UInt16</span></span>|<span data-ttu-id="f3038-149">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f3038-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f3038-150">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f3038-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="f3038-151">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="f3038-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="f3038-152">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f3038-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f3038-153">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f3038-153">Keyword for raising the event</span></span>|<span data-ttu-id="f3038-154">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3038-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f3038-155">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f3038-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f3038-156">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="f3038-157">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f3038-158">Evento</span><span class="sxs-lookup"><span data-stu-id="f3038-158">Event</span></span>|<span data-ttu-id="f3038-159">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f3038-159">Event ID</span></span>|<span data-ttu-id="f3038-160">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f3038-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="f3038-161">83</span><span class="sxs-lookup"><span data-stu-id="f3038-161">83</span></span>|<span data-ttu-id="f3038-162">Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="f3038-163">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f3038-164">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f3038-164">Field name</span></span>|<span data-ttu-id="f3038-165">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3038-165">Data type</span></span>|<span data-ttu-id="f3038-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3038-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f3038-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f3038-167">AppDomainID</span></span>|<span data-ttu-id="f3038-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-168">win:UInt64</span></span>|<span data-ttu-id="f3038-169">Identificador del dominio de la aplicación para el que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3038-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f3038-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="f3038-170">Allocated</span></span>|<span data-ttu-id="f3038-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-171">win:UInt64</span></span>|<span data-ttu-id="f3038-172">Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).</span><span class="sxs-lookup"><span data-stu-id="f3038-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="f3038-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f3038-173">ClrInstanceID</span></span>|<span data-ttu-id="f3038-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f3038-174">win:UInt16</span></span>|<span data-ttu-id="f3038-175">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f3038-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f3038-176">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f3038-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="f3038-177">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="f3038-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="f3038-178">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f3038-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f3038-179">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f3038-179">Keyword for raising the event</span></span>|<span data-ttu-id="f3038-180">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3038-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f3038-181">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f3038-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f3038-182">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="f3038-183">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f3038-184">Evento</span><span class="sxs-lookup"><span data-stu-id="f3038-184">Event</span></span>|<span data-ttu-id="f3038-185">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f3038-185">Event ID</span></span>|<span data-ttu-id="f3038-186">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f3038-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="f3038-187">84</span><span class="sxs-lookup"><span data-stu-id="f3038-187">84</span></span>|<span data-ttu-id="f3038-188">Fnalizadas todas las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f3038-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="f3038-189">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f3038-190">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f3038-190">Field name</span></span>|<span data-ttu-id="f3038-191">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3038-191">Data type</span></span>|<span data-ttu-id="f3038-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3038-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f3038-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f3038-193">AppDomainID</span></span>|<span data-ttu-id="f3038-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-194">win:UInt64</span></span>|<span data-ttu-id="f3038-195">Identificador del dominio para el que recurso que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="f3038-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f3038-196">Survived</span><span class="sxs-lookup"><span data-stu-id="f3038-196">Survived</span></span>|<span data-ttu-id="f3038-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-197">win:UInt64</span></span>|<span data-ttu-id="f3038-198">Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="f3038-199">Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.</span><span class="sxs-lookup"><span data-stu-id="f3038-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="f3038-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="f3038-200">ProcessSurvived</span></span>|<span data-ttu-id="f3038-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-201">win:UInt64</span></span>|<span data-ttu-id="f3038-202">Bytes totales que sobrevivieron de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="f3038-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="f3038-203">Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="f3038-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="f3038-204">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="f3038-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="f3038-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f3038-205">ClrInstanceID</span></span>|<span data-ttu-id="f3038-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f3038-206">win:UInt16</span></span>|<span data-ttu-id="f3038-207">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f3038-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f3038-208">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f3038-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="f3038-209">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="f3038-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="f3038-210">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f3038-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f3038-211">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f3038-211">Keyword for raising the event</span></span>|<span data-ttu-id="f3038-212">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3038-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f3038-213">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f3038-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f3038-214">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-214">Informational(4)</span></span>|  
|<span data-ttu-id="f3038-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f3038-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f3038-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="f3038-217">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f3038-218">Evento</span><span class="sxs-lookup"><span data-stu-id="f3038-218">Event</span></span>|<span data-ttu-id="f3038-219">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f3038-219">Event ID</span></span>|<span data-ttu-id="f3038-220">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f3038-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="f3038-221">87</span><span class="sxs-lookup"><span data-stu-id="f3038-221">87</span></span>|<span data-ttu-id="f3038-222">Un subproceso entra en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="f3038-223">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f3038-224">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f3038-224">Field name</span></span>|<span data-ttu-id="f3038-225">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3038-225">Data type</span></span>|<span data-ttu-id="f3038-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3038-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f3038-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f3038-227">ThreadID</span></span>|<span data-ttu-id="f3038-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-228">win:UInt64</span></span>|<span data-ttu-id="f3038-229">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-229">The thread identifier.</span></span>|  
|<span data-ttu-id="f3038-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f3038-230">AppDomainID</span></span>|<span data-ttu-id="f3038-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-231">win:UInt64</span></span>|<span data-ttu-id="f3038-232">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="f3038-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f3038-233">ClrInstanceID</span></span>|<span data-ttu-id="f3038-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f3038-234">win:UInt16</span></span>|<span data-ttu-id="f3038-235">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f3038-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f3038-236">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f3038-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="f3038-237">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="f3038-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="f3038-238">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f3038-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f3038-239">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f3038-239">Keyword for raising the event</span></span>|<span data-ttu-id="f3038-240">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3038-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f3038-241">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f3038-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f3038-242">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-242">Informational(4)</span></span>|  
|<span data-ttu-id="f3038-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f3038-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f3038-244">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f3038-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="f3038-245">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f3038-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f3038-246">Evento</span><span class="sxs-lookup"><span data-stu-id="f3038-246">Event</span></span>|<span data-ttu-id="f3038-247">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f3038-247">Event ID</span></span>|<span data-ttu-id="f3038-248">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f3038-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="f3038-249">86</span><span class="sxs-lookup"><span data-stu-id="f3038-249">86</span></span>|<span data-ttu-id="f3038-250">Finaliza un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="f3038-251">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="f3038-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="f3038-252">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f3038-252">Field name</span></span>|<span data-ttu-id="f3038-253">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f3038-253">Data type</span></span>|<span data-ttu-id="f3038-254">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3038-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f3038-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f3038-255">ThreadID</span></span>|<span data-ttu-id="f3038-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-256">win:UInt64</span></span>|<span data-ttu-id="f3038-257">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f3038-257">The thread identifier.</span></span>|  
|<span data-ttu-id="f3038-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f3038-258">AppDomainID</span></span>|<span data-ttu-id="f3038-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f3038-259">win:UInt64</span></span>|<span data-ttu-id="f3038-260">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3038-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="f3038-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f3038-261">ClrInstanceID</span></span>|<span data-ttu-id="f3038-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f3038-262">win:UInt16</span></span>|<span data-ttu-id="f3038-263">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f3038-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3038-264">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3038-264">See Also</span></span>  
 [<span data-ttu-id="f3038-265">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="f3038-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
