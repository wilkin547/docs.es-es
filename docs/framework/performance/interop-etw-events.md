---
title: Eventos ETW de interoperabilidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="59fdd-102">Eventos ETW de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="59fdd-102">Interop ETW Events</span></span>
<span data-ttu-id="59fdd-103"><a name="top"></a> Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59fdd-103"><a name="top"></a> Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="59fdd-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="59fdd-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="59fdd-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="59fdd-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="59fdd-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="59fdd-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="59fdd-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="59fdd-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="59fdd-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="59fdd-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="59fdd-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="59fdd-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="59fdd-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-110">Keyword for raising the event</span></span>|<span data-ttu-id="59fdd-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="59fdd-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="59fdd-112">`InteropKeyword` (0 x 2000)</span><span class="sxs-lookup"><span data-stu-id="59fdd-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="59fdd-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="59fdd-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="59fdd-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="59fdd-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="59fdd-115">Evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-115">Event</span></span>|<span data-ttu-id="59fdd-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-116">Event ID</span></span>|<span data-ttu-id="59fdd-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="59fdd-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="59fdd-118">88</span><span class="sxs-lookup"><span data-stu-id="59fdd-118">88</span></span>|<span data-ttu-id="59fdd-119">Se generó código auxiliar MSIL.</span><span class="sxs-lookup"><span data-stu-id="59fdd-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="59fdd-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="59fdd-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="59fdd-121">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="59fdd-121">Field name</span></span>|<span data-ttu-id="59fdd-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="59fdd-122">Data type</span></span>|<span data-ttu-id="59fdd-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="59fdd-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="59fdd-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="59fdd-124">ModuleID</span></span>|<span data-ttu-id="59fdd-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="59fdd-125">win:UInt16</span></span>|<span data-ttu-id="59fdd-126">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="59fdd-126">The module identifier.</span></span>|  
|<span data-ttu-id="59fdd-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="59fdd-127">StubMethodID</span></span>|<span data-ttu-id="59fdd-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="59fdd-128">win:UInt64</span></span>|<span data-ttu-id="59fdd-129">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="59fdd-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="59fdd-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="59fdd-130">StubFlags</span></span>|<span data-ttu-id="59fdd-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="59fdd-131">win:UInt64</span></span>|<span data-ttu-id="59fdd-132">Marcas para el código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="59fdd-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="59fdd-133">0x1 - Interoperabilidad inversa.</span><span class="sxs-lookup"><span data-stu-id="59fdd-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="59fdd-134">0x2 - Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="59fdd-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="59fdd-135">0x4 - Código auxiliar generado por NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="59fdd-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="59fdd-136">0x8 - Delegado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="59fdd-137">0x10 - Argumento variable.</span><span class="sxs-lookup"><span data-stu-id="59fdd-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="59fdd-138">0x20 - Destinatario no administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="59fdd-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="59fdd-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="59fdd-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="59fdd-140">win:UInt32</span></span>|<span data-ttu-id="59fdd-141">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="59fdd-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="59fdd-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-143">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-144">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="59fdd-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="59fdd-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-146">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-147">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="59fdd-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="59fdd-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-149">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-150">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="59fdd-151">NativeMethodSignature</span></span>|<span data-ttu-id="59fdd-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-152">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-153">Firma del método nativo.</span><span class="sxs-lookup"><span data-stu-id="59fdd-153">The native method signature.</span></span>|  
|<span data-ttu-id="59fdd-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="59fdd-154">StubMethodSignature</span></span>|<span data-ttu-id="59fdd-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-155">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-156">Firma del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="59fdd-156">The stub method signature.</span></span>|  
|<span data-ttu-id="59fdd-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="59fdd-157">StubMethodILCode</span></span>|<span data-ttu-id="59fdd-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-158">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-159">Código MSIL para el método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="59fdd-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="59fdd-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="59fdd-160">ClrInstanceID</span></span>|<span data-ttu-id="59fdd-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="59fdd-161">win:UInt16</span></span>|<span data-ttu-id="59fdd-162">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="59fdd-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="59fdd-163">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="59fdd-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="59fdd-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="59fdd-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="59fdd-165">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="59fdd-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="59fdd-166">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-166">Keyword for raising the event</span></span>|<span data-ttu-id="59fdd-167">Nivel</span><span class="sxs-lookup"><span data-stu-id="59fdd-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="59fdd-168">`InteropKeyword` (0 x 2000)</span><span class="sxs-lookup"><span data-stu-id="59fdd-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="59fdd-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="59fdd-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="59fdd-170">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="59fdd-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="59fdd-171">Evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-171">Event</span></span>|<span data-ttu-id="59fdd-172">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="59fdd-172">Event ID</span></span>|<span data-ttu-id="59fdd-173">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="59fdd-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="59fdd-174">89</span><span class="sxs-lookup"><span data-stu-id="59fdd-174">89</span></span>|<span data-ttu-id="59fdd-175">Se tuvo acceso a la memoria caché MSIL.</span><span class="sxs-lookup"><span data-stu-id="59fdd-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="59fdd-176">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="59fdd-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="59fdd-177">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="59fdd-177">Field name</span></span>|<span data-ttu-id="59fdd-178">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="59fdd-178">Data type</span></span>|<span data-ttu-id="59fdd-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="59fdd-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="59fdd-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="59fdd-180">ModuleID</span></span>|<span data-ttu-id="59fdd-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="59fdd-181">win:UInt16</span></span>|<span data-ttu-id="59fdd-182">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="59fdd-182">The module identifier.</span></span>|  
|<span data-ttu-id="59fdd-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="59fdd-183">StubMethodID</span></span>|<span data-ttu-id="59fdd-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="59fdd-184">win:UInt64</span></span>|<span data-ttu-id="59fdd-185">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="59fdd-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="59fdd-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="59fdd-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="59fdd-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="59fdd-187">win:UInt32</span></span>|<span data-ttu-id="59fdd-188">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="59fdd-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="59fdd-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-190">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-191">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="59fdd-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="59fdd-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-193">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-194">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="59fdd-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="59fdd-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="59fdd-196">win:UnicodeString</span></span>|<span data-ttu-id="59fdd-197">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="59fdd-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="59fdd-198">ClrInstanceID</span></span>|<span data-ttu-id="59fdd-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="59fdd-199">win:UInt16</span></span>|<span data-ttu-id="59fdd-200">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="59fdd-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="59fdd-201">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="59fdd-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="59fdd-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="59fdd-202">See Also</span></span>  
 [<span data-ttu-id="59fdd-203">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="59fdd-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
