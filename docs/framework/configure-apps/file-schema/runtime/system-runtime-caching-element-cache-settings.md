---
title: Elemento <system.runtime.caching> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe9e81f0e8bef36b780878844512a36a5148fec
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489359"
---
# <a name="systemruntimecaching-element-cache-settings"></a>\<System.Runtime.Caching > elemento (configuración de caché)
Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.  
  
 \<configuration>  
\<system.runtime.caching>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 `None`  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración que usa el common language runtime y aplicaciones de .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  
 Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web` . Para obtener más información, consulta [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  La salida de almacenamiento en caché de funcionalidad y los tipos en el <xref:System.Runtime.Caching> espacio de nombres son nuevas en .NET Framework 4.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> . En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché. El nombre de la memoria caché se establece en el nombre predeterminado de la entrada de caché estableciendo el atributo `name` en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada. La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.  
  
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
