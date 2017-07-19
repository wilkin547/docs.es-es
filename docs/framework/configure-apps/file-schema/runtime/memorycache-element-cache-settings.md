---
title: "Elemento &lt;memoryCache&gt; (configuraci&#243;n de cach&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "elemento <memoryCache>"
  - "almacenamiento en caché [.NET Framework], configuración"
  - "memoryCache (elemento)"
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Elemento &lt;memoryCache&gt; (configuraci&#243;n de cach&#233;)
Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache>. La clase <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> define un elemento [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) que se puede usar para configurar la memoria caché. Se pueden usar varias instancias de la clase <xref:System.Runtime.Caching.MemoryCache> en una sola aplicación. Cada elemento `memoryCache` del archivo de configuración puede contener valores de configuración para una instancia de <xref:System.Runtime.Caching.MemoryCache> con nombre.  
  
 \<configuration\>  
\<system.runtime.caching\>  
\<memoryCache\>  
  
## Sintaxis  
  
```  
<memoryCache   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
< memoryCache />  
```  
  
## Tipo  
 Clase <xref:System.Runtime.Caching.MemoryCache>.  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`CacheMemoryLimitMegabytes`|Tamaño máximo de memoria \(en megabytes\) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache>. El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache>.|  
|`Name`|Nombre de la configuración de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Porcentaje de memoria física que la memoria caché puede usar. El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache>.|  
|`PollingInterval`|Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché. El valor se especifica en formato "HH:MM:SS".|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de valores de configuración para la instancia de `namedCache`.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.runtime.caching\>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones que están integradas en [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
  
## Comentarios  
 La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación concreta de la clase abstracta <xref:System.Runtime.Caching.ObjectCache>. Se puede proporcionar información de configuración a las instancias de la clase <xref:System.Runtime.Caching.MemoryCache> a partir de archivos de configuración de la aplicación. La sección de configuración [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) contiene una colección de configuración `namedCaches`.  
  
 Cuando se inicializa un objeto de la caché basada en memoria, primero intenta encontrar una entrada `namedCaches` que coincida con el nombre del parámetro que se pasa al constructor de memoria caché. Si se encuentra una entrada `namedCaches`, se recupera la información de sondeo y administración de memoria del archivo de configuración.  
  
 Después, el proceso de inicialización determina si se ha reemplazado alguna entrada de configuración. Para ello, usa la colección opcional de pares nombre\-valor de la información de configuración del constructor. Si pasa alguno de los valores siguientes en la colección de pares nombre\-valor, estos valores reemplazarán la información obtenida del archivo de configuración:  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
-   <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
-   <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el nombre del objeto <xref:System.Runtime.Caching.MemoryCache> en el nombre del objeto de caché predeterminado estableciendo el atributo `name` en "default".  
  
 Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero. El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada. La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.  
  
```  
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
  
## Vea también  
 <xref:System.Runtime.Caching.MemoryCache>   
 [Elemento \<system.runtime.caching\> \(configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)   
 [\<namedCaches\> \(Elemento, Configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)