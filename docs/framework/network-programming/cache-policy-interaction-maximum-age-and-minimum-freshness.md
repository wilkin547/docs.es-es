---
title: Interacción de la directiva de caché, antigüedad máxima y actualización mínima
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
ms.openlocfilehash: 2ec958cc035ac62086cdd3e2844811accc181d47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048809"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="2a9fd-102">Interacción de la directiva de caché, antigüedad máxima y actualización mínima</span><span class="sxs-lookup"><span data-stu-id="2a9fd-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>
<span data-ttu-id="2a9fd-103">Para garantizar que se devuelva a la aplicación cliente el contenido más actualizado, la interacción de la directiva de caché de cliente y los requisitos de revalidación de servidor siempre da como resultado la directiva de caché más conservadora.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="2a9fd-104">Todos los ejemplos de este tema muestran la directiva de caché de un recurso que se ha almacenado en caché el 1 de enero y expira el 4 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="2a9fd-105">Los ejemplos siguientes muestran la directiva de caché que resulta de la interacción de los valores de antigüedad máxima (`maxAge`) y actualización mínima (`minFresh`).</span><span class="sxs-lookup"><span data-stu-id="2a9fd-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
- <span data-ttu-id="2a9fd-106">Si la directiva de caché establece `maxAge` = 2 días y `minFresh` no está especificado, el contenido se vuelve a validar el 3 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
- <span data-ttu-id="2a9fd-107">Si la directiva de caché establece `maxAge` = 2 días y `minFresh` = 1 día, según `maxAge`, el contenido está actualizado hasta el 3 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="2a9fd-108">Según `minFresh`, el contenido está actualizado hasta el 3 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="2a9fd-109">Por lo tanto, el contenido se debe volver a validar el 3 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
- <span data-ttu-id="2a9fd-110">Si la directiva de caché establece `maxAge` = 2 días y `minFresh` = 2 días, según `maxAge`, el contenido está actualizado hasta el 3 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="2a9fd-111">Según `minFresh`, el contenido está actualizado hasta el 2 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="2a9fd-112">Por lo tanto, el contenido se debe volver a validar el 2 de enero.</span><span class="sxs-lookup"><span data-stu-id="2a9fd-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9fd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a9fd-113">See also</span></span>

- [<span data-ttu-id="2a9fd-114">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="2a9fd-114">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="2a9fd-115">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="2a9fd-115">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="2a9fd-116">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="2a9fd-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- <span data-ttu-id="2a9fd-117">[Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="2a9fd-117">[Time-Based Cache Policies](time-based-cache-policies.md)</span></span>
- [<span data-ttu-id="2a9fd-118">Configurar el almacenamiento en caché de las aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="2a9fd-118">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="2a9fd-119">Interacción de la directiva de caché: antigüedad máxima y obsolescencia máxima</span><span class="sxs-lookup"><span data-stu-id="2a9fd-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](cache-policy-interaction-maximum-age-and-maximum-staleness.md)
