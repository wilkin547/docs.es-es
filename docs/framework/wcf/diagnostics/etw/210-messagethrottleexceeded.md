---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 299cc11dc4f6794b65761ad7da71bcf062c318db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="210---messagethrottleexceeded"></a><span data-ttu-id="a13b2-102">210 - MessageThrottleExceeded</span><span class="sxs-lookup"><span data-stu-id="a13b2-102">210 - MessageThrottleExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="a13b2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a13b2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a13b2-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a13b2-104">ID</span></span>|<span data-ttu-id="a13b2-105">210</span><span class="sxs-lookup"><span data-stu-id="a13b2-105">210</span></span>|  
|<span data-ttu-id="a13b2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a13b2-106">Keywords</span></span>|<span data-ttu-id="a13b2-107">EndToEndMonitoring, HealthMonitoring, Solución de problemas, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a13b2-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a13b2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a13b2-108">Level</span></span>|<span data-ttu-id="a13b2-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="a13b2-109">Warning</span></span>|  
|<span data-ttu-id="a13b2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a13b2-110">Channel</span></span>|<span data-ttu-id="a13b2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a13b2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a13b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a13b2-112">Description</span></span>  
 <span data-ttu-id="a13b2-113">Este evento se emite cuando se ha superado uno de los tres aceleradores del servicio principales.</span><span class="sxs-lookup"><span data-stu-id="a13b2-113">This event is emitted when one of the three main service throttles have been exceeded.</span></span> <span data-ttu-id="a13b2-114">Tenga en cuenta que este evento solo se emite cuando se supera inicialmente el límite del acelerador.</span><span class="sxs-lookup"><span data-stu-id="a13b2-114">Note that this event is only emitted when the throttle limit is initially exceeded.</span></span> <span data-ttu-id="a13b2-115">Por ejemplo, si el límite del acelerador para las llamadas simultáneas es 10, la llamada simultánea n.º 11 da como resultado un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="a13b2-115">For example, if the throttle limit for concurrent calls is 10, the 11th concurrent call results in a `MessageThrottleExceeded` event.</span></span> <span data-ttu-id="a13b2-116">La llamada n.º 12 no produce otro evento.</span><span class="sxs-lookup"><span data-stu-id="a13b2-116">The 12th call does not result in another event.</span></span> <span data-ttu-id="a13b2-117">Además, para evitar una secuencia de eventos con ruido, la actividad que se sitúa cerca del límite no produce otro evento.</span><span class="sxs-lookup"><span data-stu-id="a13b2-117">Additionally, to avoid a noisy event stream, activity that hovers around the limit does not result in another event.</span></span> <span data-ttu-id="a13b2-118">En este ejemplo, si un par de llamadas finalizan, hay 9 llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="a13b2-118">In this example, if a couple of calls complete then there are 9 concurrent calls.</span></span> <span data-ttu-id="a13b2-119">Si, posteriormente, entran dos llamadas más, el valor actual será de nuevo 11.</span><span class="sxs-lookup"><span data-stu-id="a13b2-119">If subsequently two more calls come in, the current value is again 11.</span></span> <span data-ttu-id="a13b2-120">Esto no produce otro evento.</span><span class="sxs-lookup"><span data-stu-id="a13b2-120">This does not result in another event.</span></span> <span data-ttu-id="a13b2-121">Cuando el valor actual desciende al 70 por ciento del límite del acelerador, se emite un evento diferente que indica que la actividad es más lenta.</span><span class="sxs-lookup"><span data-stu-id="a13b2-121">When the current value falls to 70 percent of the throttle limit a different event is emitted that indicates that the activity has slowed.</span></span> <span data-ttu-id="a13b2-122">Actividad futura que supera los resultados límite en otro evento `MessageThrottleExceeded` que se emite.</span><span class="sxs-lookup"><span data-stu-id="a13b2-122">Future activity that exceeds the limit results in another `MessageThrottleExceeded` event being emitted.</span></span> <span data-ttu-id="a13b2-123">En este ejemplo, si la cantidad de llamadas simultáneas desciende a 7 y, a continuación, vuelve a alcanzar 11, se emite otro evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="a13b2-123">In this example, if the amount of concurrent calls falls to 7 and then again reaches 11 and another `MessageThrottleExceeded` event is emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a13b2-124">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a13b2-124">Message</span></span>  
 <span data-ttu-id="a13b2-125">Se alcanzó el límite '%1' de '%2'.</span><span class="sxs-lookup"><span data-stu-id="a13b2-125">The '%1' throttle limit of '%2' was hit.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a13b2-126">Detalles</span><span class="sxs-lookup"><span data-stu-id="a13b2-126">Details</span></span>  
  
|<span data-ttu-id="a13b2-127">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a13b2-127">Data Item Name</span></span>|<span data-ttu-id="a13b2-128">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a13b2-128">Data Item Type</span></span>|<span data-ttu-id="a13b2-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a13b2-129">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a13b2-130">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="a13b2-130">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="a13b2-131">El nombre del acelerador que se ha superado.</span><span class="sxs-lookup"><span data-stu-id="a13b2-131">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="a13b2-132">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="a13b2-132">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="a13b2-133">Limit</span><span class="sxs-lookup"><span data-stu-id="a13b2-133">Limit</span></span>|`xs:long`|<span data-ttu-id="a13b2-134">El límite configurado actual del acelerador.</span><span class="sxs-lookup"><span data-stu-id="a13b2-134">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="a13b2-135">HostReference</span><span class="sxs-lookup"><span data-stu-id="a13b2-135">HostReference</span></span>|`xs:string`|<span data-ttu-id="a13b2-136">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="a13b2-136">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a13b2-137">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a13b2-137">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a13b2-138">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a13b2-138">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a13b2-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a13b2-139">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a13b2-140">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a13b2-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
