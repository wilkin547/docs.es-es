---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154510"
---
# <a name="add-element-for-namedcaches"></a>\<agregue> \<Element para namedCaches>
Agrega una `namedCache` entrada `namedCaches` a la colección para una memoria caché.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `None`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Un valor entero que especifica el tamaño máximo permitido (en <xref:System.Runtime.Caching.MemoryCache> megabytes) al que puede crecer una instancia de a. El valor predeterminado es 0, <xref:System.Runtime.Caching.MemoryCache> lo que significa que la heurística de autodimensionamiento de la clase se usa de forma predeterminada.|  
|`Name`|Nombre de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalada físicamente que puede consumir la memoria caché. El valor predeterminado es 0, <xref:System.Runtime.Caching.MemoryCache> lo que significa que la heurística de autodimensionamiento de la clase se usa de forma predeterminada.|  
|`PollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se introduce en formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 `None`  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una colección de <xref:System.Runtime.Caching.MemoryCache> valores de configuración para las instancias con nombre.|  
  
## <a name="remarks"></a>Observaciones  
 El `add` elemento agrega una `namedCaches` entrada a la colección para una memoria caché de memoria. Puede usar el elemento [clear](clear-element-for-namedcaches.md) `add` antes de usar el elemento para estar seguro de que no hay otras cachés con nombre en la colección. Este elemento se puede utilizar en el archivo machine.config y en el archivo Web.config.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra `namedCache` cómo `namedCaches` definir la configuración de la entrada predeterminada a la colección para una memoria caché.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [\<NamedCaches> Element (Configuración de caché)](namedcaches-element-cache-settings.md)
