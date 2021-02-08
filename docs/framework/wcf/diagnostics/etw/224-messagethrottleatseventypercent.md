---
description: 'Más información acerca de: 224-MessageThrottleAtSeventyPercent'
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 14c08371c5db7e6f7deb0a5851a1d24dfc94475e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794278"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="fa0ea-103">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="fa0ea-103">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="fa0ea-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fa0ea-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa0ea-105">Id.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-105">ID</span></span>|<span data-ttu-id="fa0ea-106">224</span><span class="sxs-lookup"><span data-stu-id="fa0ea-106">224</span></span>|  
|<span data-ttu-id="fa0ea-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fa0ea-107">Keywords</span></span>|<span data-ttu-id="fa0ea-108">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fa0ea-108">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fa0ea-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="fa0ea-109">Level</span></span>|<span data-ttu-id="fa0ea-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="fa0ea-110">Warning</span></span>|  
|<span data-ttu-id="fa0ea-111">Canal</span><span class="sxs-lookup"><span data-stu-id="fa0ea-111">Channel</span></span>|<span data-ttu-id="fa0ea-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fa0ea-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa0ea-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa0ea-113">Description</span></span>  

 <span data-ttu-id="fa0ea-114">Cuando se ha superado uno de los aceleradores del servicio principal, se emite el evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-114">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="fa0ea-115">Cuando la punta de actividad se retrasa y el valor actual del acelerador está al 70 por ciento del límite actual, entonces se emite este evento.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-115">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="fa0ea-116">Tenga en cuenta que este evento solo se emite una vez cuando la actividad se retrasa.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-116">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="fa0ea-117">Si el valor actual oscila alrededor del valor del 70 por ciento (por ejemplo, 70, 69, 70, 71, 70, 69), solo la primera aparición del 70 por ciento producirá un evento.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-117">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="fa0ea-118">Una vez emitido este evento, las situaciones futuras de superación del límite del acelerador resultarán en un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-118">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa0ea-119">Message</span><span class="sxs-lookup"><span data-stu-id="fa0ea-119">Message</span></span>  

 <span data-ttu-id="fa0ea-120">La limitación '%1' de '%2' se encuentra al 70%.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-120">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa0ea-121">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa0ea-121">Details</span></span>  
  
|<span data-ttu-id="fa0ea-122">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fa0ea-122">Data Item Name</span></span>|<span data-ttu-id="fa0ea-123">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fa0ea-123">Data Item Type</span></span>|<span data-ttu-id="fa0ea-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa0ea-124">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa0ea-125">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="fa0ea-125">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="fa0ea-126">El nombre del acelerador que se ha superado.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-126">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="fa0ea-127">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="fa0ea-127">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="fa0ea-128">Límite</span><span class="sxs-lookup"><span data-stu-id="fa0ea-128">Limit</span></span>|`xs:long`|<span data-ttu-id="fa0ea-129">El límite configurado actual del acelerador.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-129">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="fa0ea-130">HostReference</span><span class="sxs-lookup"><span data-stu-id="fa0ea-130">HostReference</span></span>|`xs:string`|<span data-ttu-id="fa0ea-131">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-131">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fa0ea-132">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-132">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fa0ea-133">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-133">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fa0ea-134">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa0ea-134">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fa0ea-135">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fa0ea-135">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
