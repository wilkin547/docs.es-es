---
title: Eventos ETW de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715940"
---
# <a name="security-etw-events"></a><span data-ttu-id="21e07-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="21e07-102">Security ETW Events</span></span>

<span data-ttu-id="21e07-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="21e07-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="21e07-104">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="21e07-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="21e07-105">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="21e07-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="21e07-106">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="21e07-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="21e07-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="21e07-107">Keyword for raising the event</span></span>|<span data-ttu-id="21e07-108">Level</span><span class="sxs-lookup"><span data-stu-id="21e07-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="21e07-109">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="21e07-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="21e07-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="21e07-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="21e07-111">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="21e07-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="21e07-112">Event</span><span class="sxs-lookup"><span data-stu-id="21e07-112">Event</span></span>|<span data-ttu-id="21e07-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="21e07-113">Event ID</span></span>|<span data-ttu-id="21e07-114">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="21e07-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="21e07-115">181</span><span class="sxs-lookup"><span data-stu-id="21e07-115">181</span></span>|<span data-ttu-id="21e07-116">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="21e07-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="21e07-117">182</span><span class="sxs-lookup"><span data-stu-id="21e07-117">182</span></span>|<span data-ttu-id="21e07-118">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="21e07-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="21e07-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="21e07-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="21e07-120">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="21e07-120">Field name</span></span>|<span data-ttu-id="21e07-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="21e07-121">Data type</span></span>|<span data-ttu-id="21e07-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="21e07-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="21e07-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="21e07-123">VerificationFlags</span></span>|<span data-ttu-id="21e07-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="21e07-124">win:UInt32</span></span>|<span data-ttu-id="21e07-125">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="21e07-125">The verification flags.</span></span>|  
|<span data-ttu-id="21e07-126">errorCode</span><span class="sxs-lookup"><span data-stu-id="21e07-126">ErrorCode</span></span>|<span data-ttu-id="21e07-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="21e07-127">win:UInt32</span></span>|<span data-ttu-id="21e07-128">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="21e07-128">The HResult error code.</span></span>|  
|<span data-ttu-id="21e07-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="21e07-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="21e07-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="21e07-130">win:UnicodeString</span></span>|<span data-ttu-id="21e07-131">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="21e07-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="21e07-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="21e07-132">ClrInstanceID</span></span>|<span data-ttu-id="21e07-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="21e07-133">win:UInt16</span></span>|<span data-ttu-id="21e07-134">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="21e07-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="21e07-135">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="21e07-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="21e07-136">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="21e07-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="21e07-137">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="21e07-137">Keyword for raising the event</span></span>|<span data-ttu-id="21e07-138">Level</span><span class="sxs-lookup"><span data-stu-id="21e07-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="21e07-139">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="21e07-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="21e07-140">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="21e07-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="21e07-141">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="21e07-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="21e07-142">Event</span><span class="sxs-lookup"><span data-stu-id="21e07-142">Event</span></span>|<span data-ttu-id="21e07-143">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="21e07-143">Event ID</span></span>|<span data-ttu-id="21e07-144">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="21e07-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="21e07-145">183</span><span class="sxs-lookup"><span data-stu-id="21e07-145">183</span></span>|<span data-ttu-id="21e07-146">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="21e07-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="21e07-147">184</span><span class="sxs-lookup"><span data-stu-id="21e07-147">184</span></span>|<span data-ttu-id="21e07-148">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="21e07-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="21e07-149">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="21e07-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="21e07-150">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="21e07-150">Field name</span></span>|<span data-ttu-id="21e07-151">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="21e07-151">Data type</span></span>|<span data-ttu-id="21e07-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="21e07-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="21e07-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="21e07-153">VerificationFlags</span></span>|<span data-ttu-id="21e07-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="21e07-154">win:UInt32</span></span>|<span data-ttu-id="21e07-155">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="21e07-155">The verification flags.</span></span>|  
|<span data-ttu-id="21e07-156">errorCode</span><span class="sxs-lookup"><span data-stu-id="21e07-156">ErrorCode</span></span>|<span data-ttu-id="21e07-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="21e07-157">win:UInt32</span></span>|<span data-ttu-id="21e07-158">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="21e07-158">The HResult error code.</span></span>|  
|<span data-ttu-id="21e07-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="21e07-159">ModulePath</span></span>|<span data-ttu-id="21e07-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="21e07-160">win:UnicodeString</span></span>|<span data-ttu-id="21e07-161">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="21e07-161">The module path.</span></span>|  
|<span data-ttu-id="21e07-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="21e07-162">ClrInstanceID</span></span>|<span data-ttu-id="21e07-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="21e07-163">win:UInt16</span></span>|<span data-ttu-id="21e07-164">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="21e07-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21e07-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="21e07-165">See also</span></span>

- [<span data-ttu-id="21e07-166">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="21e07-166">CLR ETW Events</span></span>](clr-etw-events.md)
