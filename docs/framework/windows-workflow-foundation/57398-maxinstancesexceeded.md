---
description: 'Más información acerca de: 57398-MaxInstancesExceeded'
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: 104c466cb2e0ee8156e2b268caf5e757353dfb09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720233"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="4a44d-103">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="4a44d-103">57398 - MaxInstancesExceeded</span></span>

## <a name="properties"></a><span data-ttu-id="4a44d-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4a44d-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a44d-105">Id.</span><span class="sxs-lookup"><span data-stu-id="4a44d-105">ID</span></span>|<span data-ttu-id="4a44d-106">57398</span><span class="sxs-lookup"><span data-stu-id="4a44d-106">57398</span></span>|  
|<span data-ttu-id="4a44d-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4a44d-107">Keywords</span></span>|<span data-ttu-id="4a44d-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="4a44d-108">WFServices</span></span>|  
|<span data-ttu-id="4a44d-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="4a44d-109">Level</span></span>|<span data-ttu-id="4a44d-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="4a44d-110">Warning</span></span>|  
|<span data-ttu-id="4a44d-111">Canal</span><span class="sxs-lookup"><span data-stu-id="4a44d-111">Channel</span></span>|<span data-ttu-id="4a44d-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4a44d-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4a44d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a44d-113">Description</span></span>  

 <span data-ttu-id="4a44d-114">Indica que el sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="4a44d-114">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4a44d-115">Message</span><span class="sxs-lookup"><span data-stu-id="4a44d-115">Message</span></span>  

 <span data-ttu-id="4a44d-116">El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="4a44d-116">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="4a44d-117">El límite para este acelerador se estableció en %1.</span><span class="sxs-lookup"><span data-stu-id="4a44d-117">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="4a44d-118">El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="4a44d-118">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4a44d-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="4a44d-119">Details</span></span>  
  
|<span data-ttu-id="4a44d-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4a44d-120">Data Item Name</span></span>|<span data-ttu-id="4a44d-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4a44d-121">Data Item Type</span></span>|<span data-ttu-id="4a44d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a44d-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4a44d-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="4a44d-123">Name</span></span>|<span data-ttu-id="4a44d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4a44d-124">xs:string</span></span>|<span data-ttu-id="4a44d-125">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="4a44d-125">The name of the item.</span></span>|  
|<span data-ttu-id="4a44d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4a44d-126">AppDomain</span></span>|<span data-ttu-id="4a44d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4a44d-127">xs:string</span></span>|<span data-ttu-id="4a44d-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4a44d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
