---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512556"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="10f19-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="10f19-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="10f19-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="10f19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10f19-104">Id.</span><span class="sxs-lookup"><span data-stu-id="10f19-104">ID</span></span>|<span data-ttu-id="10f19-105">57398</span><span class="sxs-lookup"><span data-stu-id="10f19-105">57398</span></span>|  
|<span data-ttu-id="10f19-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="10f19-106">Keywords</span></span>|<span data-ttu-id="10f19-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="10f19-107">WFServices</span></span>|  
|<span data-ttu-id="10f19-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="10f19-108">Level</span></span>|<span data-ttu-id="10f19-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="10f19-109">Warning</span></span>|  
|<span data-ttu-id="10f19-110">Canal</span><span class="sxs-lookup"><span data-stu-id="10f19-110">Channel</span></span>|<span data-ttu-id="10f19-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="10f19-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10f19-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="10f19-112">Description</span></span>  
 <span data-ttu-id="10f19-113">Indica que el sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="10f19-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10f19-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="10f19-114">Message</span></span>  
 <span data-ttu-id="10f19-115">El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="10f19-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="10f19-116">El límite para este acelerador se estableció en %1.</span><span class="sxs-lookup"><span data-stu-id="10f19-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="10f19-117">El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="10f19-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10f19-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="10f19-118">Details</span></span>  
  
|<span data-ttu-id="10f19-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="10f19-119">Data Item Name</span></span>|<span data-ttu-id="10f19-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="10f19-120">Data Item Type</span></span>|<span data-ttu-id="10f19-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="10f19-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10f19-122">Name</span><span class="sxs-lookup"><span data-stu-id="10f19-122">Name</span></span>|<span data-ttu-id="10f19-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="10f19-123">xs:string</span></span>|<span data-ttu-id="10f19-124">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="10f19-124">The name of the item.</span></span>|  
|<span data-ttu-id="10f19-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10f19-125">AppDomain</span></span>|<span data-ttu-id="10f19-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="10f19-126">xs:string</span></span>|<span data-ttu-id="10f19-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="10f19-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
