---
title: Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8442b8723476984b90f740beac912688719f1791
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689840"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="f13ae-102">Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)</span><span class="sxs-lookup"><span data-stu-id="f13ae-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="f13ae-103">Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="f13ae-104">Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.</span><span class="sxs-lookup"><span data-stu-id="f13ae-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="f13ae-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="f13ae-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="f13ae-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f13ae-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="f13ae-107">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="f13ae-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="f13ae-108">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="f13ae-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="f13ae-109">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="f13ae-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="f13ae-110">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="f13ae-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="f13ae-111">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="f13ae-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="f13ae-112">Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="f13ae-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="f13ae-113">Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="f13ae-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="f13ae-114">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f13ae-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="f13ae-115">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="f13ae-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f13ae-116">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-116">Keyword for raising the event</span></span>|<span data-ttu-id="f13ae-117">Nivel</span><span class="sxs-lookup"><span data-stu-id="f13ae-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f13ae-118">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f13ae-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f13ae-119">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-119">Informational(4)</span></span>|  
|<span data-ttu-id="f13ae-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f13ae-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f13ae-121">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="f13ae-122">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f13ae-123">Evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-123">Event</span></span>|<span data-ttu-id="f13ae-124">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-124">Event ID</span></span>|<span data-ttu-id="f13ae-125">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f13ae-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="f13ae-126">85</span><span class="sxs-lookup"><span data-stu-id="f13ae-126">85</span></span>|<span data-ttu-id="f13ae-127">Se crea un subproceso para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="f13ae-128">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f13ae-129">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f13ae-129">Field name</span></span>|<span data-ttu-id="f13ae-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f13ae-130">Data type</span></span>|<span data-ttu-id="f13ae-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13ae-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f13ae-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f13ae-132">ThreadID</span></span>|<span data-ttu-id="f13ae-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-133">win:UInt64</span></span>|<span data-ttu-id="f13ae-134">Se creó el identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f13ae-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f13ae-135">AppDomainID</span></span>|<span data-ttu-id="f13ae-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-136">win:UInt64</span></span>|<span data-ttu-id="f13ae-137">Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="f13ae-138">Marcas</span><span class="sxs-lookup"><span data-stu-id="f13ae-138">Flags</span></span>|<span data-ttu-id="f13ae-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f13ae-139">win:UInt32</span></span>|<span data-ttu-id="f13ae-140">Marcas de creación de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="f13ae-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="f13ae-141">ManagedThreadIndex</span></span>|<span data-ttu-id="f13ae-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f13ae-142">win:UInt32</span></span>|<span data-ttu-id="f13ae-143">Se creó el índice administrado del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="f13ae-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="f13ae-144">OSThreadID</span></span>|<span data-ttu-id="f13ae-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f13ae-145">win:UInt32</span></span>|<span data-ttu-id="f13ae-146">Se creó el identificador del sistema operativo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="f13ae-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f13ae-147">ClrInstanceID</span></span>|<span data-ttu-id="f13ae-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f13ae-148">win:UInt16</span></span>|<span data-ttu-id="f13ae-149">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f13ae-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f13ae-150">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f13ae-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="f13ae-151">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="f13ae-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="f13ae-152">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f13ae-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f13ae-153">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-153">Keyword for raising the event</span></span>|<span data-ttu-id="f13ae-154">Nivel</span><span class="sxs-lookup"><span data-stu-id="f13ae-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f13ae-155">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f13ae-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f13ae-156">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="f13ae-157">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f13ae-158">Evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-158">Event</span></span>|<span data-ttu-id="f13ae-159">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-159">Event ID</span></span>|<span data-ttu-id="f13ae-160">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f13ae-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="f13ae-161">83</span><span class="sxs-lookup"><span data-stu-id="f13ae-161">83</span></span>|<span data-ttu-id="f13ae-162">Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="f13ae-163">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f13ae-164">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f13ae-164">Field name</span></span>|<span data-ttu-id="f13ae-165">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f13ae-165">Data type</span></span>|<span data-ttu-id="f13ae-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13ae-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f13ae-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f13ae-167">AppDomainID</span></span>|<span data-ttu-id="f13ae-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-168">win:UInt64</span></span>|<span data-ttu-id="f13ae-169">Identificador del dominio de la aplicación para el que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="f13ae-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f13ae-170">Allocated</span><span class="sxs-lookup"><span data-stu-id="f13ae-170">Allocated</span></span>|<span data-ttu-id="f13ae-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-171">win:UInt64</span></span>|<span data-ttu-id="f13ae-172">Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).</span><span class="sxs-lookup"><span data-stu-id="f13ae-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="f13ae-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f13ae-173">ClrInstanceID</span></span>|<span data-ttu-id="f13ae-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f13ae-174">win:UInt16</span></span>|<span data-ttu-id="f13ae-175">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f13ae-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f13ae-176">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f13ae-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="f13ae-177">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="f13ae-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="f13ae-178">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f13ae-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f13ae-179">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-179">Keyword for raising the event</span></span>|<span data-ttu-id="f13ae-180">Nivel</span><span class="sxs-lookup"><span data-stu-id="f13ae-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f13ae-181">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f13ae-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f13ae-182">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="f13ae-183">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f13ae-184">Evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-184">Event</span></span>|<span data-ttu-id="f13ae-185">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-185">Event ID</span></span>|<span data-ttu-id="f13ae-186">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f13ae-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="f13ae-187">84</span><span class="sxs-lookup"><span data-stu-id="f13ae-187">84</span></span>|<span data-ttu-id="f13ae-188">Fnalizadas todas las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f13ae-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="f13ae-189">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f13ae-190">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f13ae-190">Field name</span></span>|<span data-ttu-id="f13ae-191">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f13ae-191">Data type</span></span>|<span data-ttu-id="f13ae-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13ae-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f13ae-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f13ae-193">AppDomainID</span></span>|<span data-ttu-id="f13ae-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-194">win:UInt64</span></span>|<span data-ttu-id="f13ae-195">Identificador del dominio para el que recurso que se notifica el uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="f13ae-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="f13ae-196">Survived</span><span class="sxs-lookup"><span data-stu-id="f13ae-196">Survived</span></span>|<span data-ttu-id="f13ae-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-197">win:UInt64</span></span>|<span data-ttu-id="f13ae-198">Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="f13ae-199">Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.</span><span class="sxs-lookup"><span data-stu-id="f13ae-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="f13ae-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="f13ae-200">ProcessSurvived</span></span>|<span data-ttu-id="f13ae-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-201">win:UInt64</span></span>|<span data-ttu-id="f13ae-202">Bytes totales que sobrevivieron de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="f13ae-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="f13ae-203">Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados.</span><span class="sxs-lookup"><span data-stu-id="f13ae-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="f13ae-204">Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.</span><span class="sxs-lookup"><span data-stu-id="f13ae-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="f13ae-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f13ae-205">ClrInstanceID</span></span>|<span data-ttu-id="f13ae-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f13ae-206">win:UInt16</span></span>|<span data-ttu-id="f13ae-207">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f13ae-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f13ae-208">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f13ae-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="f13ae-209">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="f13ae-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="f13ae-210">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f13ae-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f13ae-211">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-211">Keyword for raising the event</span></span>|<span data-ttu-id="f13ae-212">Nivel</span><span class="sxs-lookup"><span data-stu-id="f13ae-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f13ae-213">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f13ae-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f13ae-214">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-214">Informational(4)</span></span>|  
|<span data-ttu-id="f13ae-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f13ae-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f13ae-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="f13ae-217">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f13ae-218">Evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-218">Event</span></span>|<span data-ttu-id="f13ae-219">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-219">Event ID</span></span>|<span data-ttu-id="f13ae-220">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f13ae-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="f13ae-221">87</span><span class="sxs-lookup"><span data-stu-id="f13ae-221">87</span></span>|<span data-ttu-id="f13ae-222">Un subproceso entra en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="f13ae-223">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f13ae-224">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f13ae-224">Field name</span></span>|<span data-ttu-id="f13ae-225">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f13ae-225">Data type</span></span>|<span data-ttu-id="f13ae-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13ae-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f13ae-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f13ae-227">ThreadID</span></span>|<span data-ttu-id="f13ae-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-228">win:UInt64</span></span>|<span data-ttu-id="f13ae-229">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-229">The thread identifier.</span></span>|  
|<span data-ttu-id="f13ae-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f13ae-230">AppDomainID</span></span>|<span data-ttu-id="f13ae-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-231">win:UInt64</span></span>|<span data-ttu-id="f13ae-232">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="f13ae-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f13ae-233">ClrInstanceID</span></span>|<span data-ttu-id="f13ae-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f13ae-234">win:UInt16</span></span>|<span data-ttu-id="f13ae-235">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f13ae-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f13ae-236">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="f13ae-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="f13ae-237">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="f13ae-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="f13ae-238">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="f13ae-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f13ae-239">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-239">Keyword for raising the event</span></span>|<span data-ttu-id="f13ae-240">Nivel</span><span class="sxs-lookup"><span data-stu-id="f13ae-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f13ae-241">`AppDomainResourceManagementKeyword` (0 x 800)</span><span class="sxs-lookup"><span data-stu-id="f13ae-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="f13ae-242">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-242">Informational(4)</span></span>|  
|<span data-ttu-id="f13ae-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="f13ae-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="f13ae-244">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f13ae-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="f13ae-245">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f13ae-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f13ae-246">Evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-246">Event</span></span>|<span data-ttu-id="f13ae-247">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f13ae-247">Event ID</span></span>|<span data-ttu-id="f13ae-248">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f13ae-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="f13ae-249">86</span><span class="sxs-lookup"><span data-stu-id="f13ae-249">86</span></span>|<span data-ttu-id="f13ae-250">Finaliza un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="f13ae-251">En la siguiente tabla, se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="f13ae-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="f13ae-252">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="f13ae-252">Field name</span></span>|<span data-ttu-id="f13ae-253">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f13ae-253">Data type</span></span>|<span data-ttu-id="f13ae-254">Descripción</span><span class="sxs-lookup"><span data-stu-id="f13ae-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f13ae-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="f13ae-255">ThreadID</span></span>|<span data-ttu-id="f13ae-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-256">win:UInt64</span></span>|<span data-ttu-id="f13ae-257">Identifiador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f13ae-257">The thread identifier.</span></span>|  
|<span data-ttu-id="f13ae-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="f13ae-258">AppDomainID</span></span>|<span data-ttu-id="f13ae-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f13ae-259">win:UInt64</span></span>|<span data-ttu-id="f13ae-260">Identificador del dominio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f13ae-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="f13ae-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f13ae-261">ClrInstanceID</span></span>|<span data-ttu-id="f13ae-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f13ae-262">win:UInt16</span></span>|<span data-ttu-id="f13ae-263">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f13ae-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f13ae-264">Vea también</span><span class="sxs-lookup"><span data-stu-id="f13ae-264">See also</span></span>
- [<span data-ttu-id="f13ae-265">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="f13ae-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
