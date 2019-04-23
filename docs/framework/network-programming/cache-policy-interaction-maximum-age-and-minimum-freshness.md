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
ms.openlocfilehash: 93136d4c87463db7128a68957b243c1ef13a90eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174062"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a>Interacción de la directiva de caché, antigüedad máxima y actualización mínima
Para garantizar que se devuelva a la aplicación cliente el contenido más actualizado, la interacción de la directiva de caché de cliente y los requisitos de revalidación de servidor siempre da como resultado la directiva de caché más conservadora. Todos los ejemplos de este tema muestran la directiva de caché de un recurso que se ha almacenado en caché el 1 de enero y expira el 4 de enero.  
  
 Los ejemplos siguientes muestran la directiva de caché que resulta de la interacción de los valores de antigüedad máxima (`maxAge`) y actualización mínima (`minFresh`).  
  
-   Si la directiva de caché establece `maxAge` = 2 días y `minFresh` no está especificado, el contenido se vuelve a validar el 3 de enero.  
  
-   Si la directiva de caché establece `maxAge` = 2 días y `minFresh` = 1 día, según `maxAge`, el contenido está actualizado hasta el 3 de enero. Según `minFresh`, el contenido está actualizado hasta el 3 de enero. Por lo tanto, el contenido se debe volver a validar el 3 de enero.  
  
-   Si la directiva de caché establece `maxAge` = 2 días y `minFresh` = 2 días, según `maxAge`, el contenido está actualizado hasta el 3 de enero. Según `minFresh`, el contenido está actualizado hasta el 2 de enero. Por lo tanto, el contenido se debe volver a validar el 2 de enero.  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [Interacción de la directiva de caché: antigüedad máxima y obsolescencia máxima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
