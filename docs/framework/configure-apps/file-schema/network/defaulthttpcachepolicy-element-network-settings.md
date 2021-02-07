---
description: 'Más información acerca de: <defaultHttpCachePolicy> elemento (configuración de red)'
title: Elemento <defaultHttpCachePolicy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: d2df27c9b140c9bdb4def49aef7de1a3d80f4a11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740332"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a>Elemento \<defaultHttpCachePolicy> (configuración de red)

Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`maximumAge`|Especifica el intervalo de tiempo máximo antes de que un objeto almacenado en memoria caché se marque como expirado.|  
|`maximumStale`|Especifica el tiempo máximo después del tiempo de actualización calculado antes de que un objeto almacenado en memoria caché se marque como expirado.|  
|`minimumFresh`|Especifica el tiempo mínimo que un objeto almacenado en memoria caché se debe considerar actualizado.|  
|`policyLevel`|Especifica si la Directiva de almacenamiento en caché es automática o si se omite la memoria caché. El valor predeterminado es `BypassCache`.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[requestCaching](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
  
## <a name="remarks"></a>Observaciones  

 El valor del `policyLevel` atributo es `BypassCache` o `Default` .  
  
 Los valores de `maximumAge` los `maximumStale` elementos, y `minimumFresh` son un intervalo de tiempo explícito con un formato de *d*.*HH*:*mm*:*SS* (días, horas, minutos y segundos), o las constantes `minValue` o `maxValue` , según corresponda.  
  
## <a name="configuration-files"></a>Archivos de configuración  

 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo especificar una hora de actualización mínima de seis horas, una duración máxima de dos días y un tiempo de expiración máximo de cuatro horas.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [Esquema de la configuración de red](index.md)
