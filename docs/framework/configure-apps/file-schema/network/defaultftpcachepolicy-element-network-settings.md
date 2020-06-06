---
title: Elemento <defaultFtpCachePolicy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088430"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a>Elemento \<defaultFtpCachePolicy> (configuración de red)
Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`policyLevel`|Especifica la Directiva de almacenamiento en caché de FTP. El valor predeterminado es `Default`.|  
  
## <a name="policylevel-attribute"></a>Atributo policyLevel  
  
|Value|Descripción|  
|-----------|-----------------|  
|`Default`|Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.|  
|`BypassCache`|Devuelve el recurso del servidor.|  
|`CacheOnly`|Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.|  
|`CacheIfAvailable`|Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.|  
|`Revalidate`|Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.|  
|`Reload`|Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.|  
|`NoCacheNoStore`|Si existe un recurso almacenado en caché, se elimina. El recurso se descarga del servidor y se devuelve al autor de la llamada.|  
|`Revalidate`|Atiende una solicitud utilizando la copia almacenada en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la caché.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar una directiva de almacenamiento en caché de FTP de `NoCacheNoStore` .  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Esquema de la configuración de red](index.md)
