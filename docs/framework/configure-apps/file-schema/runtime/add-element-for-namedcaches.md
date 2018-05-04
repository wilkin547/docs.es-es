---
title: '&lt;agregar&gt; (elemento) para &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d65dfd9a1560f2657f48b327277b64ab77014b47
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a>&lt;agregar&gt; (elemento) para &lt;namedCaches&gt;
Agrega un `namedCache` entrada para el `namedCaches` colección de una memoria caché.  
  
 \<System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
    <add name="default" />  
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
|`CacheMemoryLimitMegabytes`|Un valor entero que especifica el tamaño máximo permitido (en megabytes) que una instancia de un <xref:System.Runtime.Caching.MemoryCache> pueden crecer hasta. El valor predeterminado es 0, lo que significa que el <xref:System.Runtime.Caching.MemoryCache> heurísticas de ajuste automático de la clase se utilizan de forma predeterminada.|  
|`Name`|Nombre de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Un valor de número entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo físicamente instalada que puede ser utilizado por la memoria caché. El valor predeterminado es 0, lo que significa que el <xref:System.Runtime.Caching.MemoryCache> heurísticas de ajuste automático de la clase se utilizan de forma predeterminada.|  
|`PollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se introduce en formato "Hh".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 `None`  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.|  
  
## <a name="remarks"></a>Comentarios  
 El `add` elemento agrega una entrada para el `namedCaches` colección de una memoria caché. Puede usar el [borrar](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) elemento antes de usar el `add` elemento para estar seguro de que no hay ninguna otra nombrar cachés en la colección. Este elemento se puede usar en el archivo machine.config y en el archivo Web.config.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo definir la configuración para el valor predeterminado `namedCache` entrada para el `namedCaches` colección de una memoria caché.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [\<namedCaches > Element (Cache Settings)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
