---
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
ms.openlocfilehash: 18a73a46bc4b463d0a5f5690afe6d1109e06171c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207141"
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a>Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima
Para garantizar que se devuelva a la aplicación cliente el contenido más actualizado, la interacción de la directiva de caché de cliente y los requisitos de revalidación de servidor siempre da como resultado la directiva de caché más conservadora. Todos los ejemplos de este tema muestran la directiva de caché de un recurso que se ha almacenado en caché el 1 de enero y expira el 4 de enero.  
  
 En los ejemplos siguientes se usa el valor de obsolescencia máximo (`maxStale`) junto con una antigüedad máxima (`maxAge`):  
  
-   Si la directiva de caché establece `maxAge` = 5 días y no especifica un valor `maxStale`, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero. Pero según los requisitos de revalidación de servidor, el contenido expira el 4 de enero. Dado que la fecha de expiración del contenido es más conservadora (anterior), tiene prioridad sobre la directiva `maxAge`. Por lo tanto, el contenido expira el 4 de enero y se debe volver a validar aunque no se haya alcanzado su antigüedad máxima.  
  
-   Si la directiva de caché establece `maxAge` = 5 días y `maxStale` = 3 días, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero. Según el valor `maxStale`, el contenido se puede usar hasta el 7 de enero. Por lo tanto, el contenido se vuelve a validar el 6 de enero.  
  
-   Si la directiva de caché establece `maxAge` = 5 días y `maxStale` = 1 día, según el valor `maxAge`, el contenido se puede usar hasta el 6 de enero. Según el valor `maxStale`, el contenido se puede usar hasta el 5 de enero. Por lo tanto, el contenido se vuelve a validar el 5 de enero.  
  
 Cuando la antigüedad máxima es menor que la fecha de expiración del contenido, el comportamiento de almacenamiento en caché más conservador siempre prevalece y el valor de obsolescencia máximo no tiene ningún efecto. Los ejemplos siguientes muestran el efecto de establecer un valor de obsolescencia máximo (`maxStale`) cuando se alcanza la antigüedad máxima (`maxAge`) antes de que expire el contenido:  
  
-   Si la directiva de caché establece `maxAge` = 1 día y no especifica un valor para `maxStale`, el contenido se vuelve a validar el 2 de enero aunque no haya expirado.  
  
-   Si la directiva de caché establece `maxAge` = 1 día y `maxStale` = 3 días, el contenido se vuelve a validar el 2 de enero para aplicar el valor de directiva más conservador.  
  
-   Si la directiva de caché establece `maxAge` = 1 día y `maxStale` = 1 día, el contenido se vuelve a validar el 2 de enero.  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)
- [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [Interacción de la directiva de caché, antigüedad máxima y actualización mínima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
