---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="42c52-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="42c52-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="42c52-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="42c52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42c52-104">Id.</span><span class="sxs-lookup"><span data-stu-id="42c52-104">ID</span></span>|<span data-ttu-id="42c52-105">57398</span><span class="sxs-lookup"><span data-stu-id="42c52-105">57398</span></span>|  
|<span data-ttu-id="42c52-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="42c52-106">Keywords</span></span>|<span data-ttu-id="42c52-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="42c52-107">WFServices</span></span>|  
|<span data-ttu-id="42c52-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="42c52-108">Level</span></span>|<span data-ttu-id="42c52-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="42c52-109">Warning</span></span>|  
|<span data-ttu-id="42c52-110">Canal</span><span class="sxs-lookup"><span data-stu-id="42c52-110">Channel</span></span>|<span data-ttu-id="42c52-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="42c52-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42c52-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="42c52-112">Description</span></span>  
 <span data-ttu-id="42c52-113">Indica que el sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="42c52-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42c52-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="42c52-114">Message</span></span>  
 <span data-ttu-id="42c52-115">El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="42c52-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="42c52-116">El límite para este acelerador se estableció en %1.</span><span class="sxs-lookup"><span data-stu-id="42c52-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="42c52-117">El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="42c52-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42c52-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="42c52-118">Details</span></span>  
  
|<span data-ttu-id="42c52-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="42c52-119">Data Item Name</span></span>|<span data-ttu-id="42c52-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="42c52-120">Data Item Type</span></span>|<span data-ttu-id="42c52-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="42c52-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42c52-122">Name</span><span class="sxs-lookup"><span data-stu-id="42c52-122">Name</span></span>|<span data-ttu-id="42c52-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="42c52-123">xs:string</span></span>|<span data-ttu-id="42c52-124">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="42c52-124">The name of the item.</span></span>|  
|<span data-ttu-id="42c52-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42c52-125">AppDomain</span></span>|<span data-ttu-id="42c52-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="42c52-126">xs:string</span></span>|<span data-ttu-id="42c52-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="42c52-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
