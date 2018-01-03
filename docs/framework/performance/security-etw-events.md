---
title: Eventos ETW de seguridad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abf6e6896267b6d1c8449b020230381923f38f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="d73f5-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="d73f5-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="d73f5-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d73f5-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="d73f5-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="d73f5-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="d73f5-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d73f5-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="d73f5-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d73f5-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="d73f5-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d73f5-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="d73f5-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d73f5-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="d73f5-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="d73f5-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d73f5-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-110">Keyword for raising the event</span></span>|<span data-ttu-id="d73f5-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="d73f5-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d73f5-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="d73f5-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="d73f5-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d73f5-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="d73f5-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d73f5-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d73f5-115">Evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-115">Event</span></span>|<span data-ttu-id="d73f5-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-116">Event ID</span></span>|<span data-ttu-id="d73f5-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d73f5-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="d73f5-118">181</span><span class="sxs-lookup"><span data-stu-id="d73f5-118">181</span></span>|<span data-ttu-id="d73f5-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d73f5-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="d73f5-120">182</span><span class="sxs-lookup"><span data-stu-id="d73f5-120">182</span></span>|<span data-ttu-id="d73f5-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d73f5-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="d73f5-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d73f5-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d73f5-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d73f5-123">Field name</span></span>|<span data-ttu-id="d73f5-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d73f5-124">Data type</span></span>|<span data-ttu-id="d73f5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d73f5-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d73f5-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="d73f5-126">VerificationFlags</span></span>|<span data-ttu-id="d73f5-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d73f5-127">win:UInt32</span></span>|<span data-ttu-id="d73f5-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="d73f5-128">The verification flags.</span></span>|  
|<span data-ttu-id="d73f5-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="d73f5-129">ErrorCode</span></span>|<span data-ttu-id="d73f5-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d73f5-130">win:UInt32</span></span>|<span data-ttu-id="d73f5-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="d73f5-131">The HResult error code.</span></span>|  
|<span data-ttu-id="d73f5-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="d73f5-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="d73f5-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d73f5-133">win:UnicodeString</span></span>|<span data-ttu-id="d73f5-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d73f5-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="d73f5-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d73f5-135">ClrInstanceID</span></span>|<span data-ttu-id="d73f5-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d73f5-136">win:UInt16</span></span>|<span data-ttu-id="d73f5-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d73f5-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d73f5-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="d73f5-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="d73f5-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d73f5-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="d73f5-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d73f5-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d73f5-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-141">Keyword for raising the event</span></span>|<span data-ttu-id="d73f5-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="d73f5-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d73f5-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="d73f5-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="d73f5-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d73f5-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="d73f5-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d73f5-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d73f5-146">Evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-146">Event</span></span>|<span data-ttu-id="d73f5-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d73f5-147">Event ID</span></span>|<span data-ttu-id="d73f5-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d73f5-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="d73f5-149">183</span><span class="sxs-lookup"><span data-stu-id="d73f5-149">183</span></span>|<span data-ttu-id="d73f5-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d73f5-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="d73f5-151">184</span><span class="sxs-lookup"><span data-stu-id="d73f5-151">184</span></span>|<span data-ttu-id="d73f5-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d73f5-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="d73f5-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d73f5-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d73f5-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d73f5-154">Field name</span></span>|<span data-ttu-id="d73f5-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d73f5-155">Data type</span></span>|<span data-ttu-id="d73f5-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="d73f5-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d73f5-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="d73f5-157">VerificationFlags</span></span>|<span data-ttu-id="d73f5-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d73f5-158">win:UInt32</span></span>|<span data-ttu-id="d73f5-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="d73f5-159">The verification flags.</span></span>|  
|<span data-ttu-id="d73f5-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="d73f5-160">ErrorCode</span></span>|<span data-ttu-id="d73f5-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d73f5-161">win:UInt32</span></span>|<span data-ttu-id="d73f5-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="d73f5-162">The HResult error code.</span></span>|  
|<span data-ttu-id="d73f5-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="d73f5-163">ModulePath</span></span>|<span data-ttu-id="d73f5-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d73f5-164">win:UnicodeString</span></span>|<span data-ttu-id="d73f5-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="d73f5-165">The module path.</span></span>|  
|<span data-ttu-id="d73f5-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d73f5-166">ClrInstanceID</span></span>|<span data-ttu-id="d73f5-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d73f5-167">win:UInt16</span></span>|<span data-ttu-id="d73f5-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d73f5-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d73f5-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="d73f5-169">See Also</span></span>  
 [<span data-ttu-id="d73f5-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="d73f5-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
