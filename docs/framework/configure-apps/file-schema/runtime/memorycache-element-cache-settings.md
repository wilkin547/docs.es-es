---
description: 'Más información sobre: <memoryCache> elemento (configuración de caché)'
title: Elemento <memoryCache> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 1d46a156a222a0dc54e27cf56a5eb06cb1a908be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782343"
---
# <a name="memorycache-element-cache-settings"></a>Elemento \<memoryCache> (configuración de caché)

Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> . La clase <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> define un elemento [memoryCache](memorycache-element-cache-settings.md) que se puede usar para configurar la memoria caché. Se pueden usar varias instancias de la clase <xref:System.Runtime.Caching.MemoryCache> en una sola aplicación. Cada elemento `memoryCache` del archivo de configuración puede contener valores de configuración para una instancia de <xref:System.Runtime.Caching.MemoryCache> con nombre.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a>Tipo  

 Clase<xref:System.Runtime.Caching.MemoryCache> .  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|Tamaño máximo de memoria (en megabytes) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache> . El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .|  
|`Name`|Nombre de la configuración de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Porcentaje de memoria física que la memoria caché puede usar. El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .|  
|`PollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. El valor se especifica en formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia de `namedCache` .|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones integradas en el .NET Framework.|  
  
## <a name="remarks"></a>Observaciones  

 La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación concreta de la clase abstracta <xref:System.Runtime.Caching.ObjectCache> . Se puede proporcionar información de configuración a las instancias de la clase <xref:System.Runtime.Caching.MemoryCache> a partir de archivos de configuración de la aplicación. La sección de configuración [memoryCache](memorycache-element-cache-settings.md) contiene una colección de configuración `namedCaches` .  
  
 Cuando se inicializa un objeto de la caché basada en memoria, primero intenta encontrar una entrada `namedCaches` que coincida con el nombre del parámetro que se pasa al constructor de memoria caché. Si se encuentra una entrada `namedCaches` , se recupera la información de sondeo y administración de memoria del archivo de configuración.  
  
 Después, el proceso de inicialización determina si se ha reemplazado alguna entrada de configuración. Para ello, usa la colección opcional de pares nombre-valor de la información de configuración del constructor. Si pasa alguno de los valores siguientes en la colección de pares nombre-valor, estos valores reemplazarán la información obtenida del archivo de configuración:  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo establecer el nombre del <xref:System.Runtime.Caching.MemoryCache> objeto en el nombre del objeto de caché predeterminado estableciendo el `name` atributo en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryLimitPercentage` se establecen en cero. El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada. La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Caching.MemoryCache>
- [\<system.runtime.caching> (Elemento, configuración de caché)](system-runtime-caching-element-cache-settings.md)
- [\<namedCaches> (Elemento, configuración de caché)](namedcaches-element-cache-settings.md)
