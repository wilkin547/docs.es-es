---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659024"
---
# <a name="add-element-for-namedcaches"></a>\<Agregue > elemento para \<namedCaches >
Agrega una `namedCache` entrada a la `namedCaches` colección de una memoria caché.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|-|-|  
|`CacheMemoryLimitMegabytes`|Valor entero que especifica el tamaño máximo permitido (en megabytes) que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> . El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.|  
|`Name`|Nombre de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir. El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.|  
|`PollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se especifica en formato "HH: MM: SS".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 `None`  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.|  
  
## <a name="remarks"></a>Comentarios  
 El `add` elemento agrega una entrada a la `namedCaches` colección para una memoria caché. Puede usar el elemento [Clear](clear-element-for-namedcaches.md) antes de usar el `add` elemento para asegurarse de que no hay otras memorias caché con nombre en la colección. Este elemento se puede utilizar en el archivo Machine. config y en el archivo Web. config.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo definir la configuración de `namedCache` la entrada predeterminada `namedCaches` en la colección para una memoria caché.  
  
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
  
## <a name="see-also"></a>Vea también

- [\<namedCaches (elemento > (configuración de caché)](namedcaches-element-cache-settings.md)
