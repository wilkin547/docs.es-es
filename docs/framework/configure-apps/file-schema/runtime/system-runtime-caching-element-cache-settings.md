---
title: Elemento <system.runtime.caching> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153859"
---
# <a name="systemruntimecaching-element-cache-settings"></a>Elemento \<system.runtime.caching> (configuración de caché)

Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
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
|[\<memoryCache>](memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Comentarios

Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web` . Para obtener más información, consulta [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
> La funcionalidad de almacenamiento en caché de resultados y los tipos del <xref:System.Runtime.Caching> espacio de nombres son nuevos en .NET Framework 4.  
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> . En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché. El nombre de la memoria caché se establece en el nombre de la entrada de caché predeterminado estableciendo el `name` atributo en "default".  
  
Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada. La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.  
  
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
  
## <a name="see-also"></a>Consulte también

- [\<memoryCache>(Elemento, configuración de caché)](memorycache-element-cache-settings.md)
