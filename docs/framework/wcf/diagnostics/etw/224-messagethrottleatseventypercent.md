---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e7d35407fe22dc913f7122163006035717d60d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="88cf9-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="88cf9-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="88cf9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="88cf9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88cf9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="88cf9-104">ID</span></span>|<span data-ttu-id="88cf9-105">224</span><span class="sxs-lookup"><span data-stu-id="88cf9-105">224</span></span>|  
|<span data-ttu-id="88cf9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="88cf9-106">Keywords</span></span>|<span data-ttu-id="88cf9-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="88cf9-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="88cf9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="88cf9-108">Level</span></span>|<span data-ttu-id="88cf9-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="88cf9-109">Warning</span></span>|  
|<span data-ttu-id="88cf9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="88cf9-110">Channel</span></span>|<span data-ttu-id="88cf9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="88cf9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="88cf9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="88cf9-112">Description</span></span>  
 <span data-ttu-id="88cf9-113">Cuando se ha superado uno de los aceleradores del servicio principal, se emite el evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="88cf9-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="88cf9-114">Cuando la punta de actividad se retrasa y el valor actual del acelerador está al 70 por ciento del límite actual, entonces se emite este evento.</span><span class="sxs-lookup"><span data-stu-id="88cf9-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="88cf9-115">Tenga en cuenta que este evento solo se emite una vez cuando la actividad se retrasa.</span><span class="sxs-lookup"><span data-stu-id="88cf9-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="88cf9-116">Si el valor actual oscila alrededor del valor del 70 por ciento (por ejemplo, 70, 69, 70, 71, 70, 69), solo la primera aparición del 70 por ciento producirá un evento.</span><span class="sxs-lookup"><span data-stu-id="88cf9-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="88cf9-117">Una vez emitido este evento, las situaciones futuras de superación del límite del acelerador resultarán en un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="88cf9-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="88cf9-118">Mensaje</span><span class="sxs-lookup"><span data-stu-id="88cf9-118">Message</span></span>  
 <span data-ttu-id="88cf9-119">La limitación '%1' de '%2' se encuentra al 70%.</span><span class="sxs-lookup"><span data-stu-id="88cf9-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="88cf9-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="88cf9-120">Details</span></span>  
  
|<span data-ttu-id="88cf9-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="88cf9-121">Data Item Name</span></span>|<span data-ttu-id="88cf9-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="88cf9-122">Data Item Type</span></span>|<span data-ttu-id="88cf9-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="88cf9-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="88cf9-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="88cf9-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="88cf9-125">El nombre del acelerador que se ha superado.</span><span class="sxs-lookup"><span data-stu-id="88cf9-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="88cf9-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="88cf9-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="88cf9-127">Limit</span><span class="sxs-lookup"><span data-stu-id="88cf9-127">Limit</span></span>|`xs:long`|<span data-ttu-id="88cf9-128">El límite configurado actual del acelerador.</span><span class="sxs-lookup"><span data-stu-id="88cf9-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="88cf9-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="88cf9-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="88cf9-130">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="88cf9-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="88cf9-131">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="88cf9-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="88cf9-132">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="88cf9-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="88cf9-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="88cf9-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="88cf9-134">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="88cf9-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
