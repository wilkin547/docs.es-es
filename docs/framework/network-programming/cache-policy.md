---
title: Directiva de caché
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
ms.openlocfilehash: 2d3d85ebd80f417ebd0fa0e619097e15f2a6a39b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048770"
---
# <a name="cache-policy"></a>Directiva de caché
Una directiva de caché define reglas que se usan para determinar si se puede satisfacer una solicitud mediante una copia almacenada en caché del recurso solicitado. Las aplicaciones especifican requisitos de caché de cliente de actualización, pero la directiva de caché en vigor viene determinada por los requisitos de caché de cliente, los requisitos de expiración del contenido del servidor y los requisitos de revalidación del servidor. La interacción de la directiva de caché de cliente y los requisitos de servidor siempre da como resultado la directiva de caché más conservadora para ayudar a garantizar que el contenido actualizado se devuelva a la aplicación cliente.  
  
 Las directivas de caché están basadas en la ubicación o en el tiempo. Una directiva de caché basada en la ubicación define la actualización de las entradas almacenadas en caché en función de dónde se puede obtener el recurso solicitado. Una directiva de caché basada en el tiempo define la actualización de las entradas almacenadas en caché según la hora a la que se ha recuperado el recurso, los encabezados devueltos con este y la hora actual. La mayoría de las aplicaciones puede usar la directiva de caché basada en el tiempo predeterminada, que implementa la directiva de caché que se especifica en RFC 2616, disponible en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/).  
  
 Las clases descritas en la siguiente tabla se usan para especificar directivas de caché.  
  
|Nombre de la clase|Description|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|Representa directivas de caché basadas en la ubicación y en el tiempo para los recursos solicitados mediante objetos <xref:System.Net.HttpWebRequest>.|  
|<xref:System.Net.Cache.RequestCachePolicy>|Representa directivas de caché basadas en la ubicación o la directiva de caché basada en el tiempo <xref:System.Net.Cache.RequestCacheLevel.Default> para los recursos solicitados mediante objetos <xref:System.Net.WebRequest>.|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|Especifica valores usados para crear objetos <xref:System.Net.Cache.HttpRequestCachePolicy> basados en el tiempo.|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|Especifica valores usados para crear objetos <xref:System.Net.Cache.HttpRequestCachePolicy> basados en el tiempo y en la ubicación.|  
|<xref:System.Net.Cache.RequestCacheLevel>|Especifica valores usados para crear objetos <xref:System.Net.Cache.RequestCacheLevel.Default> basados en la ubicación o el objeto basado en el tiempo <xref:System.Net.Cache.RequestCachePolicy>.|  
  
 Puede definir una directiva de caché para todas las solicitudes realizadas por la aplicación o para solicitudes individuales. Cuando se especifican una directiva de caché de nivel de aplicación y una directiva de caché de nivel de solicitud, se usa la directiva de nivel de solicitud. Puede especificar una directiva de caché de nivel de aplicación mediante programación o mediante archivos de configuración de aplicación o equipo. Para más información, vea [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
 Para crear una directiva de caché, debe crear un objeto de directiva mediante la creación de una instancia de la clase <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>. Para especificar la directiva en una solicitud, establezca la propiedad <xref:System.Net.WebRequest.CachePolicy%2A> de la solicitud en el objeto de directiva. Al establecer una directiva de nivel de aplicación mediante programación, establezca la propiedad <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> en el objeto de directiva.  
  
 Para obtener ejemplos de código que muestran cómo crear y usar directivas de caché, vea [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md).  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](location-based-cache-policies.md)
- [Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md)
