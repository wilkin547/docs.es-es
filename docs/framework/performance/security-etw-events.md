---
title: Eventos ETW de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2ea19c88ff8b854b09ed372b35bf8c45d994585
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583652"
---
# <a name="security-etw-events"></a><span data-ttu-id="dcbbd-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="dcbbd-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="dcbbd-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="dcbbd-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="dcbbd-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="dcbbd-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dcbbd-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="dcbbd-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dcbbd-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="dcbbd-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dcbbd-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="dcbbd-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="dcbbd-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="dcbbd-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="dcbbd-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-110">Keyword for raising the event</span></span>|<span data-ttu-id="dcbbd-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="dcbbd-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="dcbbd-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="dcbbd-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="dcbbd-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="dcbbd-115">evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-115">Event</span></span>|<span data-ttu-id="dcbbd-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-116">Event ID</span></span>|<span data-ttu-id="dcbbd-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="dcbbd-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="dcbbd-118">181</span><span class="sxs-lookup"><span data-stu-id="dcbbd-118">181</span></span>|<span data-ttu-id="dcbbd-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="dcbbd-120">182</span><span class="sxs-lookup"><span data-stu-id="dcbbd-120">182</span></span>|<span data-ttu-id="dcbbd-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="dcbbd-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="dcbbd-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="dcbbd-123">Field name</span></span>|<span data-ttu-id="dcbbd-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dcbbd-124">Data type</span></span>|<span data-ttu-id="dcbbd-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcbbd-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="dcbbd-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="dcbbd-126">VerificationFlags</span></span>|<span data-ttu-id="dcbbd-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dcbbd-127">win:UInt32</span></span>|<span data-ttu-id="dcbbd-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-128">The verification flags.</span></span>|  
|<span data-ttu-id="dcbbd-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="dcbbd-129">ErrorCode</span></span>|<span data-ttu-id="dcbbd-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dcbbd-130">win:UInt32</span></span>|<span data-ttu-id="dcbbd-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-131">The HResult error code.</span></span>|  
|<span data-ttu-id="dcbbd-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="dcbbd-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="dcbbd-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="dcbbd-133">win:UnicodeString</span></span>|<span data-ttu-id="dcbbd-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="dcbbd-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="dcbbd-135">ClrInstanceID</span></span>|<span data-ttu-id="dcbbd-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="dcbbd-136">win:UInt16</span></span>|<span data-ttu-id="dcbbd-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="dcbbd-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="dcbbd-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="dcbbd-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dcbbd-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="dcbbd-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="dcbbd-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-141">Keyword for raising the event</span></span>|<span data-ttu-id="dcbbd-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="dcbbd-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="dcbbd-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="dcbbd-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="dcbbd-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="dcbbd-146">evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-146">Event</span></span>|<span data-ttu-id="dcbbd-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dcbbd-147">Event ID</span></span>|<span data-ttu-id="dcbbd-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="dcbbd-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="dcbbd-149">183</span><span class="sxs-lookup"><span data-stu-id="dcbbd-149">183</span></span>|<span data-ttu-id="dcbbd-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="dcbbd-151">184</span><span class="sxs-lookup"><span data-stu-id="dcbbd-151">184</span></span>|<span data-ttu-id="dcbbd-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="dcbbd-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="dcbbd-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="dcbbd-154">Field name</span></span>|<span data-ttu-id="dcbbd-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dcbbd-155">Data type</span></span>|<span data-ttu-id="dcbbd-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcbbd-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="dcbbd-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="dcbbd-157">VerificationFlags</span></span>|<span data-ttu-id="dcbbd-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dcbbd-158">win:UInt32</span></span>|<span data-ttu-id="dcbbd-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-159">The verification flags.</span></span>|  
|<span data-ttu-id="dcbbd-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="dcbbd-160">ErrorCode</span></span>|<span data-ttu-id="dcbbd-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dcbbd-161">win:UInt32</span></span>|<span data-ttu-id="dcbbd-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-162">The HResult error code.</span></span>|  
|<span data-ttu-id="dcbbd-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="dcbbd-163">ModulePath</span></span>|<span data-ttu-id="dcbbd-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="dcbbd-164">win:UnicodeString</span></span>|<span data-ttu-id="dcbbd-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-165">The module path.</span></span>|  
|<span data-ttu-id="dcbbd-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="dcbbd-166">ClrInstanceID</span></span>|<span data-ttu-id="dcbbd-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="dcbbd-167">win:UInt16</span></span>|<span data-ttu-id="dcbbd-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="dcbbd-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcbbd-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcbbd-169">See also</span></span>

- [<span data-ttu-id="dcbbd-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="dcbbd-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
