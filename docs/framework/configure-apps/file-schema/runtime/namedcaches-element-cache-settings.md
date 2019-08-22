---
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 9cedd462aa539745ddab844dff158912914cb024
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663579"
---
# <a name="namedcaches-element-cache-settings"></a>\<namedCaches (elemento > (configuración de caché)
Especifica una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre. La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la colección de valores de configuración de `namedCaches` uno o más elementos del archivo de configuración.  
  
 \<configuration>  
\<System. Runtime. Caching >  
\<memoryCache>  
\<namedCaches>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a>Type  
 `None`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|Valor entero que especifica el tamaño máximo permitido, en megabytes, que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> . El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase.|  
|`name`|Nombre de la memoria caché.|  
|`physicalMemoryLimitPercentage`|Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir. El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase.|  
|`pollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. Este valor se especifica en formato "HH: MM: SS".|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.|  
|[\<clear>](clear-element-for-namedcaches.md)|Borra la colección `namedCaches` de una caché en memoria.|  
|[\<remove>](remove-element-for-namedcaches.md)|Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|  
  
## <a name="remarks"></a>Comentarios  
 La sección de configuración de la memoria caché del archivo Web. config `add`puede `remove`contener los `clear` atributos, y `namedCaches` para la colección. Cada `namedCaches` entrada se identifica de forma única mediante `name` el atributo.  
  
 Puede recuperar instancias de entradas de la memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación. De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración. La instancia de caché predeterminada es la instancia de que se devuelve <xref:System.Runtime.Caching.MemoryCache.Default%2A> desde la propiedad.  
  
 Si establece el atributo name en "default", el elemento utiliza la instancia de la memoria caché predeterminada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el nombre de la memoria caché en el nombre de la entrada de `name` caché predeterminado estableciendo el atributo en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. Establecer estos atributos en cero significa que se utiliza la heurística de ajuste automático <xref:System.Runtime.Caching.MemoryCache> de tamaño de la clase. La implementación de caché compara la carga de memoria actual con los límites de memoria absoluta y basada en porcentajes cada dos minutos.  
  
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

- [\<memoryCache > elemento (configuración de caché)](memorycache-element-cache-settings.md)
