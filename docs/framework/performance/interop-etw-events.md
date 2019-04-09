---
title: Eventos ETW de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09b2848619256a255cc27f0268d46e5e6db8cbe4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083613"
---
# <a name="interop-etw-events"></a><span data-ttu-id="d3e09-102">Eventos ETW de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="d3e09-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="d3e09-103">Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3e09-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="d3e09-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="d3e09-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="d3e09-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d3e09-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="d3e09-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d3e09-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="d3e09-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d3e09-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="d3e09-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d3e09-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="d3e09-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="d3e09-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d3e09-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-110">Keyword for raising the event</span></span>|<span data-ttu-id="d3e09-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="d3e09-111">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="d3e09-112">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="d3e09-112">(0x2000)</span></span>|<span data-ttu-id="d3e09-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d3e09-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="d3e09-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d3e09-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d3e09-115">evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-115">Event</span></span>|<span data-ttu-id="d3e09-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-116">Event ID</span></span>|<span data-ttu-id="d3e09-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d3e09-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="d3e09-118">88</span><span class="sxs-lookup"><span data-stu-id="d3e09-118">88</span></span>|<span data-ttu-id="d3e09-119">Se generó código auxiliar MSIL.</span><span class="sxs-lookup"><span data-stu-id="d3e09-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="d3e09-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d3e09-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d3e09-121">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d3e09-121">Field name</span></span>|<span data-ttu-id="d3e09-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d3e09-122">Data type</span></span>|<span data-ttu-id="d3e09-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3e09-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d3e09-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d3e09-124">ModuleID</span></span>|<span data-ttu-id="d3e09-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3e09-125">win:UInt16</span></span>|<span data-ttu-id="d3e09-126">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="d3e09-126">The module identifier.</span></span>|  
|<span data-ttu-id="d3e09-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d3e09-127">StubMethodID</span></span>|<span data-ttu-id="d3e09-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3e09-128">win:UInt64</span></span>|<span data-ttu-id="d3e09-129">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d3e09-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="d3e09-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="d3e09-130">StubFlags</span></span>|<span data-ttu-id="d3e09-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3e09-131">win:UInt64</span></span>|<span data-ttu-id="d3e09-132">Marcas para el código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="d3e09-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="d3e09-133">0x1 - Interoperabilidad inversa.</span><span class="sxs-lookup"><span data-stu-id="d3e09-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="d3e09-134">0x2 - Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="d3e09-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="d3e09-135">0x4 - Código auxiliar generado por NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="d3e09-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="d3e09-136">0x8 - Delegado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="d3e09-137">0x10 - Argumento variable.</span><span class="sxs-lookup"><span data-stu-id="d3e09-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="d3e09-138">0x20 - Destinatario no administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="d3e09-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d3e09-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d3e09-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d3e09-140">win:UInt32</span></span>|<span data-ttu-id="d3e09-141">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d3e09-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d3e09-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-143">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-144">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d3e09-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="d3e09-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-146">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-147">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3e09-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d3e09-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-149">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-150">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3e09-151">NativeMethodSignature</span></span>|<span data-ttu-id="d3e09-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-152">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-153">Firma del método nativo.</span><span class="sxs-lookup"><span data-stu-id="d3e09-153">The native method signature.</span></span>|  
|<span data-ttu-id="d3e09-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3e09-154">StubMethodSignature</span></span>|<span data-ttu-id="d3e09-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-155">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-156">Firma del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d3e09-156">The stub method signature.</span></span>|  
|<span data-ttu-id="d3e09-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="d3e09-157">StubMethodILCode</span></span>|<span data-ttu-id="d3e09-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-158">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-159">Código MSIL para el método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d3e09-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="d3e09-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d3e09-160">ClrInstanceID</span></span>|<span data-ttu-id="d3e09-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3e09-161">win:UInt16</span></span>|<span data-ttu-id="d3e09-162">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d3e09-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d3e09-163">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="d3e09-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="d3e09-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d3e09-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="d3e09-165">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d3e09-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d3e09-166">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-166">Keyword for raising the event</span></span>|<span data-ttu-id="d3e09-167">Nivel</span><span class="sxs-lookup"><span data-stu-id="d3e09-167">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="d3e09-168">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="d3e09-168">(0x2000)</span></span>|<span data-ttu-id="d3e09-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d3e09-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="d3e09-170">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d3e09-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d3e09-171">evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-171">Event</span></span>|<span data-ttu-id="d3e09-172">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d3e09-172">Event ID</span></span>|<span data-ttu-id="d3e09-173">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d3e09-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="d3e09-174">89</span><span class="sxs-lookup"><span data-stu-id="d3e09-174">89</span></span>|<span data-ttu-id="d3e09-175">Se tuvo acceso a la memoria caché MSIL.</span><span class="sxs-lookup"><span data-stu-id="d3e09-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="d3e09-176">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d3e09-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d3e09-177">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d3e09-177">Field name</span></span>|<span data-ttu-id="d3e09-178">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d3e09-178">Data type</span></span>|<span data-ttu-id="d3e09-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3e09-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d3e09-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d3e09-180">ModuleID</span></span>|<span data-ttu-id="d3e09-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3e09-181">win:UInt16</span></span>|<span data-ttu-id="d3e09-182">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="d3e09-182">The module identifier.</span></span>|  
|<span data-ttu-id="d3e09-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d3e09-183">StubMethodID</span></span>|<span data-ttu-id="d3e09-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3e09-184">win:UInt64</span></span>|<span data-ttu-id="d3e09-185">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="d3e09-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="d3e09-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d3e09-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d3e09-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d3e09-187">win:UInt32</span></span>|<span data-ttu-id="d3e09-188">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d3e09-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d3e09-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-190">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-191">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d3e09-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="d3e09-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-193">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-194">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3e09-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d3e09-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3e09-196">win:UnicodeString</span></span>|<span data-ttu-id="d3e09-197">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="d3e09-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d3e09-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d3e09-198">ClrInstanceID</span></span>|<span data-ttu-id="d3e09-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3e09-199">win:UInt16</span></span>|<span data-ttu-id="d3e09-200">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d3e09-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d3e09-201">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="d3e09-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="d3e09-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3e09-202">See also</span></span>

- [<span data-ttu-id="d3e09-203">Eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="d3e09-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
