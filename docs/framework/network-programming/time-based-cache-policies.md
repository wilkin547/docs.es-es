---
title: directivas de caché de duración definida
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
ms.openlocfilehash: 372621ce55891cb87594e6d059c7bbeeb99f6468
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239424"
---
# <a name="time-based-cache-policies"></a>directivas de caché de duración definida

Una directiva de caché de duración definida define la actualización de las entradas almacenadas en caché según la hora a la que se ha recuperado el recurso, los encabezados devueltos con este y la hora actual. Al establecer una directiva de caché de duración definida, puede usar la directiva de duración definida <xref:System.Net.Cache.HttpRequestCacheLevel.Default> o crear una directiva de duración definida personalizada. Al usar la directiva predeterminada de duración definida para los recursos obtenidos mediante el protocolo de transferencia de hipertexto (HTTP), el comportamiento de caché exacto viene determinado por los encabezados incluidos en la respuesta almacenada en caché y por los comportamientos especificados en las secciones 13 y 14 del RFC 2616, disponible en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/). Para obtener un ejemplo de código en el que se muestra cómo establecer la directiva predeterminada de duración definida para los recursos HTTP, vea [How to: Set the Default Time-Based Cache Policy for an Application](how-to-set-the-default-time-based-cache-policy-for-an-application.md) (Cómo establecer la directiva predeterminada de duración definida para una aplicación). Para obtener ejemplos de código que muestran cómo crear y usar directivas de caché, vea [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md).  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a>Criterios para determinar la actualización de las entradas en caché  

 Para personalizar una directiva de caché de duración definida, puede especificar que se apliquen uno o varios de los siguientes criterios para determinar la actualización de las entradas almacenadas en caché:  
  
- Antigüedad máxima  
  
- Obsolescencia máxima  
  
- Actualización mínima  
  
- Fecha de sincronización de caché  
  
> [!NOTE]
> No se debe confundir el uso de la directiva predeterminada de caché de duración definida con la configuración de una directiva de caché predeterminada para la aplicación. La directiva predeterminada de duración definida es una directiva específica que se puede usar a nivel de solicitud o de aplicación. La directiva de caché predeterminada para la aplicación es una directiva (de duración definida o basada en la ubicación) que surte efecto cuando no hay ninguna directiva establecida en una solicitud. Para obtener más información sobre cómo configurar una directiva de caché predeterminada para la aplicación, vea <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### <a name="maximum-age"></a>Antigüedad máxima  

 El criterio de directiva de antigüedad máxima especifica el tiempo durante el que se puede usar una copia en caché de un recurso. Si la copia en caché del recurso es anterior a la fecha especificada, el recurso se deberá volver a validar comprobándolo con el contenido del servidor. Si la antigüedad máxima permite que el recurso se use una vez expirado, no se respetará este criterio, a menos que también se especifique un valor de obsolescencia máxima.  
  
### <a name="maximum-staleness"></a>Obsolescencia máxima  

 El criterio de directiva de obsolescencia máxima especifica el período de tiempo posterior a la expiración del contenido en el que se puede usar la copia en caché del recurso. Este es el único criterio de directiva de caché que permite usar los recursos una vez expirados.  
  
### <a name="minimum-freshness"></a>Actualización mínima  

 El criterio de directiva de actualización mínima especifica el período de tiempo anterior a la expiración del contenido en el que se puede usar la copia en caché del recurso. Esta directiva hace que una entrada de caché expire antes de su fecha de expiración; por lo tanto, las opciones de actualización mínima y obsolescencia máxima son mutuamente excluyentes.  
  
## <a name="cache-synchronization-date"></a>Fecha de sincronización de caché  

 El criterio de la directiva de fecha de sincronización de caché determina cuándo se debe volver a validar una copia en caché de un recurso comprobándola con el contenido del servidor. Si el contenido ha cambiado desde que el elemento se almacenó en caché, se recuperará del servidor, se almacenará en la memoria caché y se devolverá a la aplicación. Si el contenido no ha cambiado, se actualizará su marca de tiempo y la aplicación recibirá el contenido almacenado en caché.  
  
 La fecha de sincronización de caché le permite especificar una fecha absoluta en la que se debe volver a validar el contenido en caché. Si una entrada de caché actualizada se revalidó por última vez antes de la fecha de sincronización de la memoria caché, la revalidación con el servidor sigue teniendo lugar. Si la entrada de caché se revalidó después de la fecha de sincronización de la memoria caché y no hay ninguna actualización más ni ningún requisito de revalidación del servidor que invalide la entrada en caché, se usará la entrada de la memoria caché. Si la fecha de sincronización de caché se establece en una fecha futura, la entrada se volverá a validar cada vez que se solicite, hasta que haya pasado la fecha de sincronización de caché.  
  
 Los temas siguientes proporcionan información sobre los efectos de combinar los criterios de directiva de caché de duración definida:  
  
- [Interacción de la directiva de caché: antigüedad máxima y obsolescencia máxima](cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
- [Interacción de la directiva de caché, antigüedad máxima y actualización mínima](cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Directiva de caché](cache-policy.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](location-based-cache-policies.md)
- [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md)
- [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
