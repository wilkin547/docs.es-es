---
title: Eventos ETW de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1dad042595608a805f978673858acaa5c01130f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974878"
---
# <a name="security-etw-events"></a><span data-ttu-id="d17be-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="d17be-102">Security ETW Events</span></span>

<span data-ttu-id="d17be-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d17be-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="d17be-104">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d17be-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="d17be-105">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d17be-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="d17be-106">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="d17be-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d17be-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d17be-107">Keyword for raising the event</span></span>|<span data-ttu-id="d17be-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d17be-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d17be-109">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="d17be-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="d17be-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d17be-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="d17be-111">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d17be-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d17be-112">evento</span><span class="sxs-lookup"><span data-stu-id="d17be-112">Event</span></span>|<span data-ttu-id="d17be-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d17be-113">Event ID</span></span>|<span data-ttu-id="d17be-114">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d17be-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="d17be-115">181</span><span class="sxs-lookup"><span data-stu-id="d17be-115">181</span></span>|<span data-ttu-id="d17be-116">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d17be-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="d17be-117">182</span><span class="sxs-lookup"><span data-stu-id="d17be-117">182</span></span>|<span data-ttu-id="d17be-118">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d17be-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="d17be-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d17be-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d17be-120">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d17be-120">Field name</span></span>|<span data-ttu-id="d17be-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d17be-121">Data type</span></span>|<span data-ttu-id="d17be-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17be-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d17be-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="d17be-123">VerificationFlags</span></span>|<span data-ttu-id="d17be-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d17be-124">win:UInt32</span></span>|<span data-ttu-id="d17be-125">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="d17be-125">The verification flags.</span></span>|  
|<span data-ttu-id="d17be-126">errorCode</span><span class="sxs-lookup"><span data-stu-id="d17be-126">ErrorCode</span></span>|<span data-ttu-id="d17be-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d17be-127">win:UInt32</span></span>|<span data-ttu-id="d17be-128">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="d17be-128">The HResult error code.</span></span>|  
|<span data-ttu-id="d17be-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="d17be-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="d17be-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d17be-130">win:UnicodeString</span></span>|<span data-ttu-id="d17be-131">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d17be-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="d17be-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d17be-132">ClrInstanceID</span></span>|<span data-ttu-id="d17be-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d17be-133">win:UInt16</span></span>|<span data-ttu-id="d17be-134">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d17be-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="d17be-135">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="d17be-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="d17be-136">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="d17be-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d17be-137">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="d17be-137">Keyword for raising the event</span></span>|<span data-ttu-id="d17be-138">Nivel</span><span class="sxs-lookup"><span data-stu-id="d17be-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d17be-139">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="d17be-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="d17be-140">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d17be-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="d17be-141">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="d17be-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d17be-142">evento</span><span class="sxs-lookup"><span data-stu-id="d17be-142">Event</span></span>|<span data-ttu-id="d17be-143">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d17be-143">Event ID</span></span>|<span data-ttu-id="d17be-144">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="d17be-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="d17be-145">183</span><span class="sxs-lookup"><span data-stu-id="d17be-145">183</span></span>|<span data-ttu-id="d17be-146">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d17be-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="d17be-147">184</span><span class="sxs-lookup"><span data-stu-id="d17be-147">184</span></span>|<span data-ttu-id="d17be-148">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="d17be-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="d17be-149">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="d17be-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d17be-150">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="d17be-150">Field name</span></span>|<span data-ttu-id="d17be-151">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d17be-151">Data type</span></span>|<span data-ttu-id="d17be-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="d17be-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d17be-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="d17be-153">VerificationFlags</span></span>|<span data-ttu-id="d17be-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d17be-154">win:UInt32</span></span>|<span data-ttu-id="d17be-155">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="d17be-155">The verification flags.</span></span>|  
|<span data-ttu-id="d17be-156">errorCode</span><span class="sxs-lookup"><span data-stu-id="d17be-156">ErrorCode</span></span>|<span data-ttu-id="d17be-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d17be-157">win:UInt32</span></span>|<span data-ttu-id="d17be-158">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="d17be-158">The HResult error code.</span></span>|  
|<span data-ttu-id="d17be-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="d17be-159">ModulePath</span></span>|<span data-ttu-id="d17be-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d17be-160">win:UnicodeString</span></span>|<span data-ttu-id="d17be-161">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="d17be-161">The module path.</span></span>|  
|<span data-ttu-id="d17be-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d17be-162">ClrInstanceID</span></span>|<span data-ttu-id="d17be-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d17be-163">win:UInt16</span></span>|<span data-ttu-id="d17be-164">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d17be-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d17be-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="d17be-165">See also</span></span>

- [<span data-ttu-id="d17be-166">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="d17be-166">CLR ETW Events</span></span>](clr-etw-events.md)
