---
title: Eventos ETW de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134035"
---
# <a name="security-etw-events"></a><span data-ttu-id="a6dd0-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="a6dd0-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a6dd0-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="a6dd0-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="a6dd0-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a6dd0-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6dd0-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="a6dd0-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6dd0-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="a6dd0-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6dd0-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a6dd0-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="a6dd0-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="a6dd0-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a6dd0-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-110">Keyword for raising the event</span></span>|<span data-ttu-id="a6dd0-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="a6dd0-111">Level</span></span>|  
|-----------------------------------|-----------|  
|`SecurityKeyword` <span data-ttu-id="a6dd0-112">(0x400)</span><span class="sxs-lookup"><span data-stu-id="a6dd0-112">(0x400)</span></span>|<span data-ttu-id="a6dd0-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a6dd0-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="a6dd0-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a6dd0-115">evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-115">Event</span></span>|<span data-ttu-id="a6dd0-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-116">Event ID</span></span>|<span data-ttu-id="a6dd0-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="a6dd0-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a6dd0-118">181</span><span class="sxs-lookup"><span data-stu-id="a6dd0-118">181</span></span>|<span data-ttu-id="a6dd0-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a6dd0-120">182</span><span class="sxs-lookup"><span data-stu-id="a6dd0-120">182</span></span>|<span data-ttu-id="a6dd0-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a6dd0-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a6dd0-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="a6dd0-123">Field name</span></span>|<span data-ttu-id="a6dd0-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a6dd0-124">Data type</span></span>|<span data-ttu-id="a6dd0-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dd0-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a6dd0-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a6dd0-126">VerificationFlags</span></span>|<span data-ttu-id="a6dd0-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6dd0-127">win:UInt32</span></span>|<span data-ttu-id="a6dd0-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-128">The verification flags.</span></span>|  
|<span data-ttu-id="a6dd0-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="a6dd0-129">ErrorCode</span></span>|<span data-ttu-id="a6dd0-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6dd0-130">win:UInt32</span></span>|<span data-ttu-id="a6dd0-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-131">The HResult error code.</span></span>|  
|<span data-ttu-id="a6dd0-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a6dd0-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a6dd0-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a6dd0-133">win:UnicodeString</span></span>|<span data-ttu-id="a6dd0-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a6dd0-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6dd0-135">ClrInstanceID</span></span>|<span data-ttu-id="a6dd0-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6dd0-136">win:UInt16</span></span>|<span data-ttu-id="a6dd0-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a6dd0-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="a6dd0-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="a6dd0-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6dd0-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a6dd0-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a6dd0-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-141">Keyword for raising the event</span></span>|<span data-ttu-id="a6dd0-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="a6dd0-142">Level</span></span>|  
|-----------------------------------|-----------|  
|`SecurityKeyword` <span data-ttu-id="a6dd0-143">(0x400)</span><span class="sxs-lookup"><span data-stu-id="a6dd0-143">(0x400)</span></span>|<span data-ttu-id="a6dd0-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a6dd0-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="a6dd0-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a6dd0-146">evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-146">Event</span></span>|<span data-ttu-id="a6dd0-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a6dd0-147">Event ID</span></span>|<span data-ttu-id="a6dd0-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="a6dd0-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a6dd0-149">183</span><span class="sxs-lookup"><span data-stu-id="a6dd0-149">183</span></span>|<span data-ttu-id="a6dd0-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a6dd0-151">184</span><span class="sxs-lookup"><span data-stu-id="a6dd0-151">184</span></span>|<span data-ttu-id="a6dd0-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a6dd0-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a6dd0-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="a6dd0-154">Field name</span></span>|<span data-ttu-id="a6dd0-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="a6dd0-155">Data type</span></span>|<span data-ttu-id="a6dd0-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6dd0-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a6dd0-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a6dd0-157">VerificationFlags</span></span>|<span data-ttu-id="a6dd0-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6dd0-158">win:UInt32</span></span>|<span data-ttu-id="a6dd0-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-159">The verification flags.</span></span>|  
|<span data-ttu-id="a6dd0-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="a6dd0-160">ErrorCode</span></span>|<span data-ttu-id="a6dd0-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6dd0-161">win:UInt32</span></span>|<span data-ttu-id="a6dd0-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-162">The HResult error code.</span></span>|  
|<span data-ttu-id="a6dd0-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a6dd0-163">ModulePath</span></span>|<span data-ttu-id="a6dd0-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a6dd0-164">win:UnicodeString</span></span>|<span data-ttu-id="a6dd0-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-165">The module path.</span></span>|  
|<span data-ttu-id="a6dd0-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6dd0-166">ClrInstanceID</span></span>|<span data-ttu-id="a6dd0-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6dd0-167">win:UInt16</span></span>|<span data-ttu-id="a6dd0-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a6dd0-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6dd0-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6dd0-169">See also</span></span>

- [<span data-ttu-id="a6dd0-170">Eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="a6dd0-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
