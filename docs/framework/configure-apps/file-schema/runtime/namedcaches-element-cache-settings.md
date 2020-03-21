---
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153963"
---
# <a name="namedcaches-element-cache-settings"></a>\<NamedCaches> Element (Configuración de caché)
Especifica una colección de valores <xref:System.Runtime.Caching.MemoryCache> de configuración para las instancias con nombre. La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la `namedCaches` colección de valores de configuración de uno o varios elementos del archivo de configuración.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
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
|`cacheMemoryLimitMegabytes`|Un valor entero que especifica el tamaño máximo permitido, en <xref:System.Runtime.Caching.MemoryCache> megabytes, al que puede crecer una instancia de a. El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> la heurística de autodimensionamiento de la clase se utiliza de forma predeterminada.|  
|`name`|Nombre de la memoria caché.|  
|`physicalMemoryLimitPercentage`|Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalada físicamente que puede consumir la memoria caché. El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> la heurística de autodimensionamiento de la clase se utiliza de forma predeterminada.|  
|`pollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se introduce en formato "HH:MM:SS".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<añadir>](add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.|  
|[\<>claro](clear-element-for-namedcaches.md)|Borra la colección `namedCaches` de una caché en memoria.|  
|[\<eliminar>](remove-element-for-namedcaches.md)|Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuración>](../configuration-element.md)|Especifica el elemento raíz en cada archivo de configuración que usan las aplicaciones de Common Language Runtime y .NET Framework.|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|Contiene tipos que permiten implementar el almacenamiento en caché de resultados en aplicaciones integradas en .NET Framework.|  
  
## <a name="remarks"></a>Observaciones  
 La sección de configuración de memoria caché `add` `remove`del `clear` archivo Web.config puede contener , y atributos de la `namedCaches` colección. Cada `namedCaches` entrada se identifica `name` de forma única por el atributo.  
  
 Puede recuperar instancias de entradas de memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación. De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración. La instancia de caché predeterminada es <xref:System.Runtime.Caching.MemoryCache.Default%2A> la instancia que se devuelve desde la propiedad.  
  
 Si establece el atributo name en "default", el elemento utiliza la instancia de memoria caché predeterminada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el nombre de `name` la memoria caché en el nombre de entrada de caché predeterminado estableciendo el atributo en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. Establecer estos atributos en cero significa que se <xref:System.Runtime.Caching.MemoryCache> utilizan las heurísticas de autodimensionamiento de la clase. La implementación de la memoria caché compara la carga de memoria actual con los límites de memoria absolutos y basados en porcentajes cada dos minutos.  
  
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
  
## <a name="see-also"></a>Consulte también

- [\<MemoryCache> Element (Configuración de caché)](memorycache-element-cache-settings.md)
