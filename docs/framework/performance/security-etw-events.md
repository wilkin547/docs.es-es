---
title: Eventos ETW de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d09b5b76c39f33848d44beb43d9b09c5e6ed13b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046176"
---
# <a name="security-etw-events"></a><span data-ttu-id="6d1a6-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="6d1a6-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="6d1a6-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="6d1a6-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="6d1a6-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="6d1a6-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="6d1a6-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="6d1a6-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="6d1a6-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="6d1a6-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="6d1a6-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="6d1a6-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="6d1a6-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="6d1a6-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6d1a6-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-110">Keyword for raising the event</span></span>|<span data-ttu-id="6d1a6-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="6d1a6-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6d1a6-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="6d1a6-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="6d1a6-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6d1a6-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="6d1a6-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6d1a6-115">Evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-115">Event</span></span>|<span data-ttu-id="6d1a6-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-116">Event ID</span></span>|<span data-ttu-id="6d1a6-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="6d1a6-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="6d1a6-118">181</span><span class="sxs-lookup"><span data-stu-id="6d1a6-118">181</span></span>|<span data-ttu-id="6d1a6-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="6d1a6-120">182</span><span class="sxs-lookup"><span data-stu-id="6d1a6-120">182</span></span>|<span data-ttu-id="6d1a6-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="6d1a6-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6d1a6-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="6d1a6-123">Field name</span></span>|<span data-ttu-id="6d1a6-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6d1a6-124">Data type</span></span>|<span data-ttu-id="6d1a6-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6d1a6-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6d1a6-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="6d1a6-126">VerificationFlags</span></span>|<span data-ttu-id="6d1a6-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6d1a6-127">win:UInt32</span></span>|<span data-ttu-id="6d1a6-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-128">The verification flags.</span></span>|  
|<span data-ttu-id="6d1a6-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="6d1a6-129">ErrorCode</span></span>|<span data-ttu-id="6d1a6-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6d1a6-130">win:UInt32</span></span>|<span data-ttu-id="6d1a6-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-131">The HResult error code.</span></span>|  
|<span data-ttu-id="6d1a6-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6d1a6-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="6d1a6-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6d1a6-133">win:UnicodeString</span></span>|<span data-ttu-id="6d1a6-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="6d1a6-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6d1a6-135">ClrInstanceID</span></span>|<span data-ttu-id="6d1a6-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6d1a6-136">win:UInt16</span></span>|<span data-ttu-id="6d1a6-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6d1a6-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="6d1a6-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="6d1a6-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="6d1a6-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="6d1a6-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6d1a6-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-141">Keyword for raising the event</span></span>|<span data-ttu-id="6d1a6-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="6d1a6-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6d1a6-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="6d1a6-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="6d1a6-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6d1a6-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="6d1a6-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6d1a6-146">Evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-146">Event</span></span>|<span data-ttu-id="6d1a6-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6d1a6-147">Event ID</span></span>|<span data-ttu-id="6d1a6-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="6d1a6-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="6d1a6-149">183</span><span class="sxs-lookup"><span data-stu-id="6d1a6-149">183</span></span>|<span data-ttu-id="6d1a6-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="6d1a6-151">184</span><span class="sxs-lookup"><span data-stu-id="6d1a6-151">184</span></span>|<span data-ttu-id="6d1a6-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="6d1a6-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6d1a6-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="6d1a6-154">Field name</span></span>|<span data-ttu-id="6d1a6-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6d1a6-155">Data type</span></span>|<span data-ttu-id="6d1a6-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6d1a6-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6d1a6-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="6d1a6-157">VerificationFlags</span></span>|<span data-ttu-id="6d1a6-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6d1a6-158">win:UInt32</span></span>|<span data-ttu-id="6d1a6-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-159">The verification flags.</span></span>|  
|<span data-ttu-id="6d1a6-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="6d1a6-160">ErrorCode</span></span>|<span data-ttu-id="6d1a6-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6d1a6-161">win:UInt32</span></span>|<span data-ttu-id="6d1a6-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-162">The HResult error code.</span></span>|  
|<span data-ttu-id="6d1a6-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="6d1a6-163">ModulePath</span></span>|<span data-ttu-id="6d1a6-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="6d1a6-164">win:UnicodeString</span></span>|<span data-ttu-id="6d1a6-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-165">The module path.</span></span>|  
|<span data-ttu-id="6d1a6-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6d1a6-166">ClrInstanceID</span></span>|<span data-ttu-id="6d1a6-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6d1a6-167">win:UInt16</span></span>|<span data-ttu-id="6d1a6-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6d1a6-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d1a6-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d1a6-169">See also</span></span>

- [<span data-ttu-id="6d1a6-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="6d1a6-170">CLR ETW Events</span></span>](clr-etw-events.md)
