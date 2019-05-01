---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945969"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="7ed6a-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="7ed6a-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="7ed6a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7ed6a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ed6a-104">ID</span><span class="sxs-lookup"><span data-stu-id="7ed6a-104">ID</span></span>|<span data-ttu-id="7ed6a-105">57398</span><span class="sxs-lookup"><span data-stu-id="7ed6a-105">57398</span></span>|  
|<span data-ttu-id="7ed6a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7ed6a-106">Keywords</span></span>|<span data-ttu-id="7ed6a-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="7ed6a-107">WFServices</span></span>|  
|<span data-ttu-id="7ed6a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7ed6a-108">Level</span></span>|<span data-ttu-id="7ed6a-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="7ed6a-109">Warning</span></span>|  
|<span data-ttu-id="7ed6a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7ed6a-110">Channel</span></span>|<span data-ttu-id="7ed6a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7ed6a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7ed6a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ed6a-112">Description</span></span>  
 <span data-ttu-id="7ed6a-113">Indica que el sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7ed6a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7ed6a-114">Message</span></span>  
 <span data-ttu-id="7ed6a-115">El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="7ed6a-116">El límite para este acelerador se estableció en %1.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="7ed6a-117">El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7ed6a-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="7ed6a-118">Details</span></span>  
  
|<span data-ttu-id="7ed6a-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7ed6a-119">Data Item Name</span></span>|<span data-ttu-id="7ed6a-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7ed6a-120">Data Item Type</span></span>|<span data-ttu-id="7ed6a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ed6a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7ed6a-122">Name</span><span class="sxs-lookup"><span data-stu-id="7ed6a-122">Name</span></span>|<span data-ttu-id="7ed6a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ed6a-123">xs:string</span></span>|<span data-ttu-id="7ed6a-124">Nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-124">The name of the item.</span></span>|  
|<span data-ttu-id="7ed6a-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7ed6a-125">AppDomain</span></span>|<span data-ttu-id="7ed6a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7ed6a-126">xs:string</span></span>|<span data-ttu-id="7ed6a-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
