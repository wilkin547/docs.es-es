---
description: 'Más información acerca de: Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima'
title: Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima
ms.date: 03/30/2017
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
ms.openlocfilehash: 909a7203d4c9813c90dc0dea9bae7f8a1f7336cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791665"
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="77f4f-103">Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima</span><span class="sxs-lookup"><span data-stu-id="77f4f-103">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>

<span data-ttu-id="77f4f-104">Para garantizar que se devuelva a la aplicación cliente el contenido más actualizado, la interacción de la directiva de caché de cliente y los requisitos de revalidación de servidor siempre da como resultado la directiva de caché más conservadora.</span><span class="sxs-lookup"><span data-stu-id="77f4f-104">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="77f4f-105">Todos los ejemplos de este tema muestran la directiva de caché de un recurso que se ha almacenado en caché el 1 de enero y expira el 4 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-105">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="77f4f-106">En los ejemplos siguientes se usa el valor de obsolescencia máximo (`maxStale`) junto con una antigüedad máxima (`maxAge`):</span><span class="sxs-lookup"><span data-stu-id="77f4f-106">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
- <span data-ttu-id="77f4f-107">Si la directiva de caché establece `maxAge` = 5 días y no especifica un valor `maxStale`, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-107">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="77f4f-108">Pero según los requisitos de revalidación de servidor, el contenido expira el 4 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-108">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="77f4f-109">Dado que la fecha de expiración del contenido es más conservadora (anterior), tiene prioridad sobre la directiva `maxAge`.</span><span class="sxs-lookup"><span data-stu-id="77f4f-109">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="77f4f-110">Por lo tanto, el contenido expira el 4 de enero y se debe volver a validar aunque no se haya alcanzado su antigüedad máxima.</span><span class="sxs-lookup"><span data-stu-id="77f4f-110">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
- <span data-ttu-id="77f4f-111">Si la directiva de caché establece `maxAge` = 5 días y `maxStale` = 3 días, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-111">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="77f4f-112">Según el valor `maxStale`, el contenido se puede usar hasta el 7 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-112">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="77f4f-113">Por lo tanto, el contenido se vuelve a validar el 6 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-113">Therefore, the content gets revalidated on January 6.</span></span>  
  
- <span data-ttu-id="77f4f-114">Si la directiva de caché establece `maxAge` = 5 días y `maxStale` = 1 día, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-114">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="77f4f-115">Según el valor `maxStale`, el contenido se puede usar hasta el 5 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-115">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="77f4f-116">Por lo tanto, el contenido se vuelve a validar el 5 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-116">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="77f4f-117">Cuando la antigüedad máxima es menor que la fecha de expiración del contenido, el comportamiento de almacenamiento en caché más conservador siempre prevalece y el valor de obsolescencia máximo no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="77f4f-117">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="77f4f-118">Los ejemplos siguientes muestran el efecto de establecer un valor de obsolescencia máximo (`maxStale`) cuando se alcanza la antigüedad máxima (`maxAge`) antes de que expire el contenido:</span><span class="sxs-lookup"><span data-stu-id="77f4f-118">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
- <span data-ttu-id="77f4f-119">Si la directiva de caché establece `maxAge` = 1 día y no especifica un valor para `maxStale`, el contenido se vuelve a validar el 2 de enero aunque no haya expirado.</span><span class="sxs-lookup"><span data-stu-id="77f4f-119">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
- <span data-ttu-id="77f4f-120">Si la directiva de caché establece `maxAge` = 1 día y `maxStale` = 3 días, el contenido se vuelve a validar el 2 de enero para aplicar el valor de directiva más conservador.</span><span class="sxs-lookup"><span data-stu-id="77f4f-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
- <span data-ttu-id="77f4f-121">Si la directiva de caché establece `maxAge` = 1 día y `maxStale` = 1 día, el contenido se vuelve a validar el 2 de enero.</span><span class="sxs-lookup"><span data-stu-id="77f4f-121">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f4f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="77f4f-122">See also</span></span>

- [<span data-ttu-id="77f4f-123">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="77f4f-123">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="77f4f-124">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="77f4f-124">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="77f4f-125">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="77f4f-125">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="77f4f-126">Directivas de caché de duración definida</span><span class="sxs-lookup"><span data-stu-id="77f4f-126">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="77f4f-127">Configurar el almacenamiento en caché de las aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="77f4f-127">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="77f4f-128">Interacción de la directiva de caché, antigüedad máxima y actualización mínima</span><span class="sxs-lookup"><span data-stu-id="77f4f-128">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](cache-policy-interaction-maximum-age-and-minimum-freshness.md)
