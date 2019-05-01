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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949206"
---
# <a name="security-etw-events"></a><span data-ttu-id="fe6a3-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="fe6a3-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="fe6a3-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="fe6a3-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="fe6a3-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="fe6a3-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fe6a3-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="fe6a3-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fe6a3-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="fe6a3-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fe6a3-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="fe6a3-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="fe6a3-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="fe6a3-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="fe6a3-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-110">Keyword for raising the event</span></span>|<span data-ttu-id="fe6a3-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="fe6a3-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fe6a3-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="fe6a3-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="fe6a3-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fe6a3-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="fe6a3-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="fe6a3-115">evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-115">Event</span></span>|<span data-ttu-id="fe6a3-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-116">Event ID</span></span>|<span data-ttu-id="fe6a3-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="fe6a3-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="fe6a3-118">181</span><span class="sxs-lookup"><span data-stu-id="fe6a3-118">181</span></span>|<span data-ttu-id="fe6a3-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="fe6a3-120">182</span><span class="sxs-lookup"><span data-stu-id="fe6a3-120">182</span></span>|<span data-ttu-id="fe6a3-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="fe6a3-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="fe6a3-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="fe6a3-123">Field name</span></span>|<span data-ttu-id="fe6a3-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fe6a3-124">Data type</span></span>|<span data-ttu-id="fe6a3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe6a3-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fe6a3-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="fe6a3-126">VerificationFlags</span></span>|<span data-ttu-id="fe6a3-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fe6a3-127">win:UInt32</span></span>|<span data-ttu-id="fe6a3-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-128">The verification flags.</span></span>|  
|<span data-ttu-id="fe6a3-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="fe6a3-129">ErrorCode</span></span>|<span data-ttu-id="fe6a3-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fe6a3-130">win:UInt32</span></span>|<span data-ttu-id="fe6a3-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-131">The HResult error code.</span></span>|  
|<span data-ttu-id="fe6a3-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="fe6a3-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="fe6a3-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fe6a3-133">win:UnicodeString</span></span>|<span data-ttu-id="fe6a3-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="fe6a3-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fe6a3-135">ClrInstanceID</span></span>|<span data-ttu-id="fe6a3-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fe6a3-136">win:UInt16</span></span>|<span data-ttu-id="fe6a3-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="fe6a3-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="fe6a3-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="fe6a3-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fe6a3-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="fe6a3-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="fe6a3-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-141">Keyword for raising the event</span></span>|<span data-ttu-id="fe6a3-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="fe6a3-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fe6a3-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="fe6a3-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="fe6a3-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fe6a3-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="fe6a3-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="fe6a3-146">evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-146">Event</span></span>|<span data-ttu-id="fe6a3-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fe6a3-147">Event ID</span></span>|<span data-ttu-id="fe6a3-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="fe6a3-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="fe6a3-149">183</span><span class="sxs-lookup"><span data-stu-id="fe6a3-149">183</span></span>|<span data-ttu-id="fe6a3-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="fe6a3-151">184</span><span class="sxs-lookup"><span data-stu-id="fe6a3-151">184</span></span>|<span data-ttu-id="fe6a3-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="fe6a3-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="fe6a3-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="fe6a3-154">Field name</span></span>|<span data-ttu-id="fe6a3-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fe6a3-155">Data type</span></span>|<span data-ttu-id="fe6a3-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe6a3-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fe6a3-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="fe6a3-157">VerificationFlags</span></span>|<span data-ttu-id="fe6a3-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fe6a3-158">win:UInt32</span></span>|<span data-ttu-id="fe6a3-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-159">The verification flags.</span></span>|  
|<span data-ttu-id="fe6a3-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="fe6a3-160">ErrorCode</span></span>|<span data-ttu-id="fe6a3-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fe6a3-161">win:UInt32</span></span>|<span data-ttu-id="fe6a3-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-162">The HResult error code.</span></span>|  
|<span data-ttu-id="fe6a3-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="fe6a3-163">ModulePath</span></span>|<span data-ttu-id="fe6a3-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fe6a3-164">win:UnicodeString</span></span>|<span data-ttu-id="fe6a3-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-165">The module path.</span></span>|  
|<span data-ttu-id="fe6a3-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fe6a3-166">ClrInstanceID</span></span>|<span data-ttu-id="fe6a3-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fe6a3-167">win:UInt16</span></span>|<span data-ttu-id="fe6a3-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fe6a3-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe6a3-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6a3-169">See also</span></span>

- [<span data-ttu-id="fe6a3-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="fe6a3-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
