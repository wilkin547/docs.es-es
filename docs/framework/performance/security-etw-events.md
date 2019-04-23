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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134035"
---
# <a name="security-etw-events"></a><span data-ttu-id="98715-102">Eventos ETW de seguridad</span><span class="sxs-lookup"><span data-stu-id="98715-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="98715-103">Los eventos de seguridad se generan durante la comprobación de nombre seguro y la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="98715-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="98715-104">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="98715-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="98715-105">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="98715-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="98715-106">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="98715-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="98715-107">Eventos StrongNameVerificationStart_V1 y StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="98715-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="98715-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="98715-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="98715-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="98715-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="98715-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="98715-110">Keyword for raising the event</span></span>|<span data-ttu-id="98715-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="98715-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="98715-112">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="98715-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="98715-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="98715-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="98715-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="98715-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="98715-115">evento</span><span class="sxs-lookup"><span data-stu-id="98715-115">Event</span></span>|<span data-ttu-id="98715-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="98715-116">Event ID</span></span>|<span data-ttu-id="98715-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="98715-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="98715-118">181</span><span class="sxs-lookup"><span data-stu-id="98715-118">181</span></span>|<span data-ttu-id="98715-119">Inicio de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="98715-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="98715-120">182</span><span class="sxs-lookup"><span data-stu-id="98715-120">182</span></span>|<span data-ttu-id="98715-121">Fin de comprobación de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="98715-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="98715-122">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="98715-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="98715-123">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="98715-123">Field name</span></span>|<span data-ttu-id="98715-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="98715-124">Data type</span></span>|<span data-ttu-id="98715-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="98715-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="98715-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="98715-126">VerificationFlags</span></span>|<span data-ttu-id="98715-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="98715-127">win:UInt32</span></span>|<span data-ttu-id="98715-128">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="98715-128">The verification flags.</span></span>|  
|<span data-ttu-id="98715-129">errorCode</span><span class="sxs-lookup"><span data-stu-id="98715-129">ErrorCode</span></span>|<span data-ttu-id="98715-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="98715-130">win:UInt32</span></span>|<span data-ttu-id="98715-131">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="98715-131">The HResult error code.</span></span>|  
|<span data-ttu-id="98715-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="98715-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="98715-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="98715-133">win:UnicodeString</span></span>|<span data-ttu-id="98715-134">Nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98715-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="98715-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="98715-135">ClrInstanceID</span></span>|<span data-ttu-id="98715-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="98715-136">win:UInt16</span></span>|<span data-ttu-id="98715-137">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="98715-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="98715-138">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="98715-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="98715-139">Eventos AuthenticodeVerificationStart_V1 y AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="98715-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="98715-140">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="98715-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="98715-141">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="98715-141">Keyword for raising the event</span></span>|<span data-ttu-id="98715-142">Nivel</span><span class="sxs-lookup"><span data-stu-id="98715-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="98715-143">`SecurityKeyword` (0 x 400)</span><span class="sxs-lookup"><span data-stu-id="98715-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="98715-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="98715-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="98715-145">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="98715-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="98715-146">evento</span><span class="sxs-lookup"><span data-stu-id="98715-146">Event</span></span>|<span data-ttu-id="98715-147">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="98715-147">Event ID</span></span>|<span data-ttu-id="98715-148">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="98715-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="98715-149">183</span><span class="sxs-lookup"><span data-stu-id="98715-149">183</span></span>|<span data-ttu-id="98715-150">Inicio de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="98715-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="98715-151">184</span><span class="sxs-lookup"><span data-stu-id="98715-151">184</span></span>|<span data-ttu-id="98715-152">Fin de la comprobación de Authenticode.</span><span class="sxs-lookup"><span data-stu-id="98715-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="98715-153">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="98715-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="98715-154">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="98715-154">Field name</span></span>|<span data-ttu-id="98715-155">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="98715-155">Data type</span></span>|<span data-ttu-id="98715-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="98715-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="98715-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="98715-157">VerificationFlags</span></span>|<span data-ttu-id="98715-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="98715-158">win:UInt32</span></span>|<span data-ttu-id="98715-159">Marcas de verificación.</span><span class="sxs-lookup"><span data-stu-id="98715-159">The verification flags.</span></span>|  
|<span data-ttu-id="98715-160">errorCode</span><span class="sxs-lookup"><span data-stu-id="98715-160">ErrorCode</span></span>|<span data-ttu-id="98715-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="98715-161">win:UInt32</span></span>|<span data-ttu-id="98715-162">Código de error HResult.</span><span class="sxs-lookup"><span data-stu-id="98715-162">The HResult error code.</span></span>|  
|<span data-ttu-id="98715-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="98715-163">ModulePath</span></span>|<span data-ttu-id="98715-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="98715-164">win:UnicodeString</span></span>|<span data-ttu-id="98715-165">Ruta de acceso del módulo.</span><span class="sxs-lookup"><span data-stu-id="98715-165">The module path.</span></span>|  
|<span data-ttu-id="98715-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="98715-166">ClrInstanceID</span></span>|<span data-ttu-id="98715-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="98715-167">win:UInt16</span></span>|<span data-ttu-id="98715-168">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="98715-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98715-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="98715-169">See also</span></span>

- [<span data-ttu-id="98715-170">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="98715-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
