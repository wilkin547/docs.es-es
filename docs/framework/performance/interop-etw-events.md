---
title: Eventos ETW de interoperabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 787c6221b651a53dbb932a5a9d0edea123e1d97d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046436"
---
# <a name="interop-etw-events"></a><span data-ttu-id="2953c-102">Eventos ETW de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="2953c-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2953c-103">Los eventos de interoperabilidad capturan información sobre el almacenamiento en caché y la generación de código auxiliar del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2953c-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="2953c-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="2953c-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="2953c-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="2953c-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="2953c-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="2953c-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="2953c-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="2953c-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="2953c-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2953c-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="2953c-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="2953c-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2953c-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2953c-110">Keyword for raising the event</span></span>|<span data-ttu-id="2953c-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="2953c-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2953c-112">`InteropKeyword` (0 x 2000)</span><span class="sxs-lookup"><span data-stu-id="2953c-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="2953c-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2953c-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="2953c-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2953c-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2953c-115">Evento</span><span class="sxs-lookup"><span data-stu-id="2953c-115">Event</span></span>|<span data-ttu-id="2953c-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2953c-116">Event ID</span></span>|<span data-ttu-id="2953c-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2953c-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="2953c-118">88</span><span class="sxs-lookup"><span data-stu-id="2953c-118">88</span></span>|<span data-ttu-id="2953c-119">Se generó código auxiliar MSIL.</span><span class="sxs-lookup"><span data-stu-id="2953c-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="2953c-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2953c-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2953c-121">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="2953c-121">Field name</span></span>|<span data-ttu-id="2953c-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2953c-122">Data type</span></span>|<span data-ttu-id="2953c-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2953c-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2953c-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="2953c-124">ModuleID</span></span>|<span data-ttu-id="2953c-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2953c-125">win:UInt16</span></span>|<span data-ttu-id="2953c-126">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="2953c-126">The module identifier.</span></span>|  
|<span data-ttu-id="2953c-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="2953c-127">StubMethodID</span></span>|<span data-ttu-id="2953c-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2953c-128">win:UInt64</span></span>|<span data-ttu-id="2953c-129">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2953c-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="2953c-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="2953c-130">StubFlags</span></span>|<span data-ttu-id="2953c-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2953c-131">win:UInt64</span></span>|<span data-ttu-id="2953c-132">Marcas para el código auxiliar:</span><span class="sxs-lookup"><span data-stu-id="2953c-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="2953c-133">0x1 - Interoperabilidad inversa.</span><span class="sxs-lookup"><span data-stu-id="2953c-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="2953c-134">0x2 - Interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="2953c-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="2953c-135">0x4 - Código auxiliar generado por NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="2953c-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="2953c-136">0x8 - Delegado.</span><span class="sxs-lookup"><span data-stu-id="2953c-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="2953c-137">0x10-argumento variable.</span><span class="sxs-lookup"><span data-stu-id="2953c-137">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="2953c-138">0x20 - Destinatario no administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="2953c-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="2953c-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="2953c-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2953c-140">win:UInt32</span></span>|<span data-ttu-id="2953c-141">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="2953c-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="2953c-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-143">win:UnicodeString</span></span>|<span data-ttu-id="2953c-144">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="2953c-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="2953c-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-146">win:UnicodeString</span></span>|<span data-ttu-id="2953c-147">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="2953c-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="2953c-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-149">win:UnicodeString</span></span>|<span data-ttu-id="2953c-150">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="2953c-151">NativeMethodSignature</span></span>|<span data-ttu-id="2953c-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-152">win:UnicodeString</span></span>|<span data-ttu-id="2953c-153">Firma del método nativo.</span><span class="sxs-lookup"><span data-stu-id="2953c-153">The native method signature.</span></span>|  
|<span data-ttu-id="2953c-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="2953c-154">StubMethodSignature</span></span>|<span data-ttu-id="2953c-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-155">win:UnicodeString</span></span>|<span data-ttu-id="2953c-156">Firma del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2953c-156">The stub method signature.</span></span>|  
|<span data-ttu-id="2953c-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="2953c-157">StubMethodILCode</span></span>|<span data-ttu-id="2953c-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-158">win:UnicodeString</span></span>|<span data-ttu-id="2953c-159">Código MSIL para el método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2953c-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="2953c-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2953c-160">ClrInstanceID</span></span>|<span data-ttu-id="2953c-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2953c-161">win:UInt16</span></span>|<span data-ttu-id="2953c-162">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2953c-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2953c-163">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="2953c-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="2953c-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="2953c-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="2953c-165">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2953c-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2953c-166">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2953c-166">Keyword for raising the event</span></span>|<span data-ttu-id="2953c-167">Nivel</span><span class="sxs-lookup"><span data-stu-id="2953c-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2953c-168">`InteropKeyword` (0 x 2000)</span><span class="sxs-lookup"><span data-stu-id="2953c-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="2953c-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2953c-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="2953c-170">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2953c-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2953c-171">Evento</span><span class="sxs-lookup"><span data-stu-id="2953c-171">Event</span></span>|<span data-ttu-id="2953c-172">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2953c-172">Event ID</span></span>|<span data-ttu-id="2953c-173">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2953c-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="2953c-174">89</span><span class="sxs-lookup"><span data-stu-id="2953c-174">89</span></span>|<span data-ttu-id="2953c-175">Se tuvo acceso a la memoria caché MSIL.</span><span class="sxs-lookup"><span data-stu-id="2953c-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="2953c-176">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2953c-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2953c-177">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="2953c-177">Field name</span></span>|<span data-ttu-id="2953c-178">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2953c-178">Data type</span></span>|<span data-ttu-id="2953c-179">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2953c-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2953c-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="2953c-180">ModuleID</span></span>|<span data-ttu-id="2953c-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2953c-181">win:UInt16</span></span>|<span data-ttu-id="2953c-182">Identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="2953c-182">The module identifier.</span></span>|  
|<span data-ttu-id="2953c-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="2953c-183">StubMethodID</span></span>|<span data-ttu-id="2953c-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="2953c-184">win:UInt64</span></span>|<span data-ttu-id="2953c-185">Identificador del método de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="2953c-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="2953c-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="2953c-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="2953c-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2953c-187">win:UInt32</span></span>|<span data-ttu-id="2953c-188">Token del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="2953c-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="2953c-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-190">win:UnicodeString</span></span>|<span data-ttu-id="2953c-191">Espacio de nombres del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="2953c-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="2953c-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-193">win:UnicodeString</span></span>|<span data-ttu-id="2953c-194">Nombre del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="2953c-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="2953c-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2953c-196">win:UnicodeString</span></span>|<span data-ttu-id="2953c-197">Firma del método de interoperabilidad administrado.</span><span class="sxs-lookup"><span data-stu-id="2953c-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="2953c-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2953c-198">ClrInstanceID</span></span>|<span data-ttu-id="2953c-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2953c-199">win:UInt16</span></span>|<span data-ttu-id="2953c-200">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2953c-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2953c-201">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="2953c-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="2953c-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="2953c-202">See also</span></span>

- [<span data-ttu-id="2953c-203">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="2953c-203">CLR ETW Events</span></span>](clr-etw-events.md)
