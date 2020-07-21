---
title: Eventos ETW de seguridad
description: Comprender los eventos ETW de seguridad, que se generan durante la comprobación de nombre seguro y la comprobación de Authenticode en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474220"
---
# <a name="security-etw-events"></a><span data-ttu-id="eb6fa-103">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="eb6fa-103">Security ETW Events</span></span>

<span data-ttu-id="eb6fa-104">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="eb6fa-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="eb6fa-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="eb6fa-106">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="eb6fa-107">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="eb6fa-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="eb6fa-108">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-108">Keyword for raising the event</span></span>|<span data-ttu-id="eb6fa-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="eb6fa-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb6fa-110">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="eb6fa-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="eb6fa-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="eb6fa-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="eb6fa-112">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb6fa-113">Evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-113">Event</span></span>|<span data-ttu-id="eb6fa-114">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-114">Event ID</span></span>|<span data-ttu-id="eb6fa-115">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="eb6fa-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="eb6fa-116">181</span><span class="sxs-lookup"><span data-stu-id="eb6fa-116">181</span></span>|<span data-ttu-id="eb6fa-117">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="eb6fa-118">182</span><span class="sxs-lookup"><span data-stu-id="eb6fa-118">182</span></span>|<span data-ttu-id="eb6fa-119">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="eb6fa-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb6fa-121">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="eb6fa-121">Field name</span></span>|<span data-ttu-id="eb6fa-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="eb6fa-122">Data type</span></span>|<span data-ttu-id="eb6fa-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb6fa-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb6fa-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="eb6fa-124">VerificationFlags</span></span>|<span data-ttu-id="eb6fa-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb6fa-125">win:UInt32</span></span>|<span data-ttu-id="eb6fa-126">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-126">The verification flags.</span></span>|  
|<span data-ttu-id="eb6fa-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="eb6fa-127">ErrorCode</span></span>|<span data-ttu-id="eb6fa-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb6fa-128">win:UInt32</span></span>|<span data-ttu-id="eb6fa-129">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-129">The HResult error code.</span></span>|  
|<span data-ttu-id="eb6fa-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="eb6fa-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="eb6fa-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="eb6fa-131">win:UnicodeString</span></span>|<span data-ttu-id="eb6fa-132">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="eb6fa-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb6fa-133">ClrInstanceID</span></span>|<span data-ttu-id="eb6fa-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb6fa-134">win:UInt16</span></span>|<span data-ttu-id="eb6fa-135">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="eb6fa-136">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="eb6fa-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="eb6fa-137">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="eb6fa-138">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-138">Keyword for raising the event</span></span>|<span data-ttu-id="eb6fa-139">Nivel</span><span class="sxs-lookup"><span data-stu-id="eb6fa-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="eb6fa-140">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="eb6fa-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="eb6fa-141">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="eb6fa-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="eb6fa-142">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="eb6fa-143">Evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-143">Event</span></span>|<span data-ttu-id="eb6fa-144">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="eb6fa-144">Event ID</span></span>|<span data-ttu-id="eb6fa-145">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="eb6fa-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="eb6fa-146">183</span><span class="sxs-lookup"><span data-stu-id="eb6fa-146">183</span></span>|<span data-ttu-id="eb6fa-147">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="eb6fa-148">184</span><span class="sxs-lookup"><span data-stu-id="eb6fa-148">184</span></span>|<span data-ttu-id="eb6fa-149">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="eb6fa-150">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="eb6fa-151">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="eb6fa-151">Field name</span></span>|<span data-ttu-id="eb6fa-152">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="eb6fa-152">Data type</span></span>|<span data-ttu-id="eb6fa-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb6fa-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="eb6fa-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="eb6fa-154">VerificationFlags</span></span>|<span data-ttu-id="eb6fa-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb6fa-155">win:UInt32</span></span>|<span data-ttu-id="eb6fa-156">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-156">The verification flags.</span></span>|  
|<span data-ttu-id="eb6fa-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="eb6fa-157">ErrorCode</span></span>|<span data-ttu-id="eb6fa-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="eb6fa-158">win:UInt32</span></span>|<span data-ttu-id="eb6fa-159">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-159">The HResult error code.</span></span>|  
|<span data-ttu-id="eb6fa-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="eb6fa-160">ModulePath</span></span>|<span data-ttu-id="eb6fa-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="eb6fa-161">win:UnicodeString</span></span>|<span data-ttu-id="eb6fa-162">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-162">The module path.</span></span>|  
|<span data-ttu-id="eb6fa-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="eb6fa-163">ClrInstanceID</span></span>|<span data-ttu-id="eb6fa-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="eb6fa-164">win:UInt16</span></span>|<span data-ttu-id="eb6fa-165">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="eb6fa-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb6fa-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb6fa-166">See also</span></span>

- [<span data-ttu-id="eb6fa-167">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="eb6fa-167">CLR ETW Events</span></span>](clr-etw-events.md)
