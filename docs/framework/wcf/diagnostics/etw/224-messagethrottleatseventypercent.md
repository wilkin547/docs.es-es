---
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 26b860b88313a971960a65b599562ef1ccb4e7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243526"
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="4bd70-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="4bd70-102">224 - MessageThrottleAtSeventyPercent</span></span>

## <a name="properties"></a><span data-ttu-id="4bd70-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4bd70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bd70-104">ID</span><span class="sxs-lookup"><span data-stu-id="4bd70-104">ID</span></span>|<span data-ttu-id="4bd70-105">224</span><span class="sxs-lookup"><span data-stu-id="4bd70-105">224</span></span>|  
|<span data-ttu-id="4bd70-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4bd70-106">Keywords</span></span>|<span data-ttu-id="4bd70-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4bd70-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4bd70-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4bd70-108">Level</span></span>|<span data-ttu-id="4bd70-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="4bd70-109">Warning</span></span>|  
|<span data-ttu-id="4bd70-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4bd70-110">Channel</span></span>|<span data-ttu-id="4bd70-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4bd70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4bd70-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bd70-112">Description</span></span>  

 <span data-ttu-id="4bd70-113">Cuando se ha superado uno de los aceleradores del servicio principal, se emite el evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="4bd70-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="4bd70-114">Cuando la punta de actividad se retrasa y el valor actual del acelerador está al 70 por ciento del límite actual, entonces se emite este evento.</span><span class="sxs-lookup"><span data-stu-id="4bd70-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="4bd70-115">Tenga en cuenta que este evento solo se emite una vez cuando la actividad se retrasa.</span><span class="sxs-lookup"><span data-stu-id="4bd70-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="4bd70-116">Si el valor actual oscila alrededor del valor del 70 por ciento (por ejemplo, 70, 69, 70, 71, 70, 69), solo la primera aparición del 70 por ciento producirá un evento.</span><span class="sxs-lookup"><span data-stu-id="4bd70-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="4bd70-117">Una vez emitido este evento, las situaciones futuras de superación del límite del acelerador resultarán en un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="4bd70-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4bd70-118">Message</span><span class="sxs-lookup"><span data-stu-id="4bd70-118">Message</span></span>  

 <span data-ttu-id="4bd70-119">La limitación '%1' de '%2' se encuentra al 70%.</span><span class="sxs-lookup"><span data-stu-id="4bd70-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4bd70-120">Detalles</span><span class="sxs-lookup"><span data-stu-id="4bd70-120">Details</span></span>  
  
|<span data-ttu-id="4bd70-121">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4bd70-121">Data Item Name</span></span>|<span data-ttu-id="4bd70-122">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4bd70-122">Data Item Type</span></span>|<span data-ttu-id="4bd70-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bd70-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4bd70-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="4bd70-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="4bd70-125">El nombre del acelerador que se ha superado.</span><span class="sxs-lookup"><span data-stu-id="4bd70-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="4bd70-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="4bd70-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="4bd70-127">Límite</span><span class="sxs-lookup"><span data-stu-id="4bd70-127">Limit</span></span>|`xs:long`|<span data-ttu-id="4bd70-128">El límite configurado actual del acelerador.</span><span class="sxs-lookup"><span data-stu-id="4bd70-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="4bd70-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="4bd70-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="4bd70-130">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="4bd70-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4bd70-131">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="4bd70-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4bd70-132">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="4bd70-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4bd70-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4bd70-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4bd70-134">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4bd70-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
