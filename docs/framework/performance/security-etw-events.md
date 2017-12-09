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
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="b754c-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="b754c-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="b754c-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b754c-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="b754c-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="b754c-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="b754c-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b754c-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="b754c-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b754c-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="b754c-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b754c-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b754c-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b754c-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="b754c-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="b754c-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b754c-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b754c-110">Keyword for raising the event</span></span>|<span data-ttu-id="b754c-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="b754c-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b754c-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="b754c-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b754c-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b754c-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="b754c-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b754c-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b754c-115">Evento</span><span class="sxs-lookup"><span data-stu-id="b754c-115">Event</span></span>|<span data-ttu-id="b754c-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b754c-116">Event ID</span></span>|<span data-ttu-id="b754c-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b754c-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="b754c-118">181</span><span class="sxs-lookup"><span data-stu-id="b754c-118">181</span></span>|<span data-ttu-id="b754c-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="b754c-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="b754c-120">182</span><span class="sxs-lookup"><span data-stu-id="b754c-120">182</span></span>|<span data-ttu-id="b754c-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="b754c-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="b754c-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b754c-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b754c-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b754c-123">Field name</span></span>|<span data-ttu-id="b754c-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b754c-124">Data type</span></span>|<span data-ttu-id="b754c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b754c-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b754c-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b754c-126">VerificationFlags</span></span>|<span data-ttu-id="b754c-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b754c-127">win:UInt32</span></span>|<span data-ttu-id="b754c-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="b754c-128">The verification flags.</span></span>|  
|<span data-ttu-id="b754c-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="b754c-129">ErrorCode</span></span>|<span data-ttu-id="b754c-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b754c-130">win:UInt32</span></span>|<span data-ttu-id="b754c-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="b754c-131">The HResult error code.</span></span>|  
|<span data-ttu-id="b754c-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b754c-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="b754c-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b754c-133">win:UnicodeString</span></span>|<span data-ttu-id="b754c-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b754c-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="b754c-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b754c-135">ClrInstanceID</span></span>|<span data-ttu-id="b754c-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b754c-136">win:UInt16</span></span>|<span data-ttu-id="b754c-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b754c-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b754c-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="b754c-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="b754c-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b754c-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b754c-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="b754c-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b754c-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="b754c-141">Keyword for raising the event</span></span>|<span data-ttu-id="b754c-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="b754c-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b754c-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="b754c-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b754c-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b754c-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="b754c-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="b754c-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b754c-146">Evento</span><span class="sxs-lookup"><span data-stu-id="b754c-146">Event</span></span>|<span data-ttu-id="b754c-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b754c-147">Event ID</span></span>|<span data-ttu-id="b754c-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="b754c-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="b754c-149">183</span><span class="sxs-lookup"><span data-stu-id="b754c-149">183</span></span>|<span data-ttu-id="b754c-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b754c-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="b754c-151">184</span><span class="sxs-lookup"><span data-stu-id="b754c-151">184</span></span>|<span data-ttu-id="b754c-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b754c-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="b754c-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="b754c-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b754c-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="b754c-154">Field name</span></span>|<span data-ttu-id="b754c-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b754c-155">Data type</span></span>|<span data-ttu-id="b754c-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="b754c-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b754c-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b754c-157">VerificationFlags</span></span>|<span data-ttu-id="b754c-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b754c-158">win:UInt32</span></span>|<span data-ttu-id="b754c-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="b754c-159">The verification flags.</span></span>|  
|<span data-ttu-id="b754c-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="b754c-160">ErrorCode</span></span>|<span data-ttu-id="b754c-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b754c-161">win:UInt32</span></span>|<span data-ttu-id="b754c-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="b754c-162">The HResult error code.</span></span>|  
|<span data-ttu-id="b754c-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="b754c-163">ModulePath</span></span>|<span data-ttu-id="b754c-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b754c-164">win:UnicodeString</span></span>|<span data-ttu-id="b754c-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="b754c-165">The module path.</span></span>|  
|<span data-ttu-id="b754c-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b754c-166">ClrInstanceID</span></span>|<span data-ttu-id="b754c-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b754c-167">win:UInt16</span></span>|<span data-ttu-id="b754c-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b754c-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b754c-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="b754c-169">See Also</span></span>  
 [<span data-ttu-id="b754c-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="b754c-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
