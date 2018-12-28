---
title: '&lt;namedCaches&gt; elemento (configuración de caché)'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d6f741f4ecd3ea52dacc9f981024690a0031a533
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611092"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt; elemento (configuración de caché)
Especifica una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias. El <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la colección de valores de configuración de uno o varios `namedCaches` elementos del archivo de configuración.  
  
 \<configuration>  
\< System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a>Tipo  
 `None`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Valor entero que especifica el tamaño máximo permitido, en megabytes, que una instancia de un <xref:System.Runtime.Caching.MemoryCache> pueden crecer hasta. El valor predeterminado es 0, lo que significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan de forma predeterminada.|  
|`name`|Nombre de la memoria caché.|  
|`physicalMemoryLimitPercentage`|Un valor de número entero entre 0 y 100 que especifica el porcentaje máximo de memoria instalada físicamente del equipo que puede consumir la memoria caché. El valor predeterminado es 0, lo que significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan de forma predeterminada.|  
|`pollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se escribe en formato "Hh".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Borra la colección `namedCaches` de una caché en memoria.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Comentarios  
 La sección de configuración de memoria caché del archivo Web.config puede contener `add`, `remove`, y `clear` atributos para el `namedCaches` colección. Cada `namedCaches` entrada se identifica mediante el `name` atributo.  
  
 Puede recuperar las instancias de entradas de la memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación. De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración. La instancia de caché predeterminada es la instancia que se devuelve desde el <xref:System.Runtime.Caching.MemoryCache.Default%2A> propiedad.  
  
 Si establece el atributo name en "default", el elemento utiliza la instancia predeterminada de la memoria caché de memoria.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo establecer el nombre de la memoria caché en el nombre de entrada de caché predeterminado estableciendo la `name` atributo en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. Establecer estos atributos en cero significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan. La implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje de cada dos minutos.  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
- [\<memoryCache > elemento (configuración de caché)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
