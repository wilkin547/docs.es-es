---
title: '&lt;requestCaching&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 3e014c7a47a53a424bbaef51c9acb28e59b43078
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401308"
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;requestCaching&gt; elemento (configuración de red)
Controla el mecanismo de almacenamiento en caché para las solicitudes de red.  
  
 \<configuration>  
\<System.NET >  
\<requestCaching >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`isPrivateCache`|Especifica si la memoria caché proporciona aislamiento entre la información de usuarios diferentes. El valor predeterminado es `true`. Este valor debe ser `false` para aplicaciones de nivel intermedio.|  
|`disableAllCaching`|Especifica que la opción de almacenamiento en caché está deshabilitada para todas las respuestas de Web y no se puede invalidar mediante programación.|  
|`defaultPolicyLevel`|Uno de los valores de la enumeración <xref:System.Net.Cache.RequestCacheLevel>. El valor predeterminado es `BypassCache`.|  
|`unspecifiedMaximumAge`|Especifica el tiempo predeterminado después del cual el contenido se marca como caducada.|  
  
## <a name="policylevel-attribute"></a>Atributo policyLevel  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`Default`|Devuelve el recurso almacenado en caché si el recurso está actualizado, la longitud del contenido es precisa y están presentes los atributos de la longitud del contenido, modificación y caducidad.|  
|`BypassCache`|Devuelve el recurso desde el servidor.|  
|`CacheOnly`|Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.|  
|`CacheIfAvailable`|Devuelve el recurso almacenado en caché si la longitud del contenido se proporciona y coincide con el tamaño de la entrada; en caso contrario, el recurso se descarga desde el servidor y se devuelve al llamador.|  
|`Revalidate`|Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, almacenado en la memoria caché y se devuelve al llamador.|  
|`Reload`|Descarga el recurso desde el servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.|  
|`NoCacheNoStore`|Si existe un recurso almacenado en caché, se elimina. El recurso se descarga desde el servidor y se devuelve al llamador.|  
|`Revalidate`|Atiende una solicitud mediante el uso de la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, se presenta al llamador y se almacena en la memoria caché,|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Elemento opcional.<br /><br /> Describe si el almacenamiento en caché de HTTP está activo y describe la directiva de caché de predeterminada.|  
|[\<defaultFtpCachePolicy > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Elemento opcional.<br /><br /> Describe si el almacenamiento en caché de FTP está activo y describe la directiva de caché de predeterminada.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene valores que especifican cómo se conecta .NET Framework a la red.|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo deshabilitar todo almacenamiento en caché.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
