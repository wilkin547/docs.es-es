---
title: "&lt;namedCaches&gt; (Elemento, Configuraci&#243;n de cach&#233;) | Microsoft Docs"
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
  - "<namedCaches> (elemento)"
  - "almacenar en caché [.NET Framework], configuración"
  - "namedCaches (elemento)"
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;namedCaches&gt; (Elemento, Configuraci&#243;n de cach&#233;)
Especifica una colección de configuraciones de las instancias con nombre de <xref:System.Runtime.Caching.MemoryCache>.  La propiedad <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> hace referencia a la colección de valores de configuración de uno o más elementos `namedCaches` del archivo de configuración.  
  
## Sintaxis  
  
```  
<namedCaches>  
  <add name="default"   
</namedCaches>  
```  
  
## Tipo  
 `None`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`CacheMemoryLimitMegabytes`|Un valor entero que especifica el tamaño máximo de memoria permitido, en megabytes, que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache>.  El valor predeterminado es 0, lo que indica que se utilizan las heurísticas del ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> de manera predeterminada.|  
|`Name`|Nombre de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo físicamente instalada que puede consumir la caché.  El valor predeterminado es 0, lo que indica que se utilizan las heurísticas del ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> de manera predeterminada.|  
|`PollingInterval`|Un valor que indica el intervalo de tiempo después del cual la implementación de memoria caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje establecidos para la instancia de la memoria caché.  Este valor se especifica en formato "HH:MM:SS".|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|Agrega una caché con nombre a la colección `namedCaches` de una memoria caché en memoria.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|Borra la colección `namedCaches` para una memoria caché en memoria.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|Quita una entrada de la caché con nombre de la colección `namedCaches` de una memoria caché en memoria.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché que está basada en la clase <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Comentarios  
 La sección de configuración de la memoria caché en memoria del archivo Web.config puede contener los atributos `add`, `clear` y `remove` para la colección `namedCaches`.  El atributo `name` identifica singularmente cada entrada `namedCaches`.  
  
 Puede recuperar instancias de entradas de la memoria caché en memoria haciendo referencia a la información en los archivos de configuración de la aplicación.  De manera predeterminada, únicamente la instancia de la memoria caché predeterminada tiene una entrada en el archivo de configuración.  La instancia de caché predeterminada es la instancia que devuelve la propiedad <xref:System.Runtime.Caching.MemoryCache.Default%2A>.  
  
 Si se establece el atributo de nombre en"predeterminado, el elemento usa la instancia de la memoria caché en memoria predeterminada.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el nombre de la memoria caché en el nombre de entrada caché predeterminado estableciendo el atributo `name` en "predeterminado".  
  
 El atributo `cacheMemoryLimitMegabytes` y el atributo `physicalMemoryPercentage` se establecen en cero.  Establecer estos atributos en cero significa que se utilizan las heurísticas de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache>.  La implementación de la memoria caché compara la carga de la memoria actual con los límites absolutos y basada en el porcentaje de la memoria cada dos minutos.  
  
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
 [Elemento \<memoryCache\> \(configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)