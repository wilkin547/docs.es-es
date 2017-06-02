---
title: "Elemento &lt;system.runtime.caching&gt; (configuraci&#243;n de cach&#233;) | Microsoft Docs"
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
  - "Elemento <system.runtime.caching>"
  - "almacenamiento en caché [.NET Framework], configuración"
  - "system.runtime.caching (elemento)"
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Elemento &lt;system.runtime.caching&gt; (configuraci&#243;n de cach&#233;)
Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.  
  
 \<configuration\>  
\<system.runtime.caching\>  
  
## Sintaxis  
  
```  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 `None`  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<memoryCache\>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz necesario en cada archivo de configuración usado por Common Language Runtime y por las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
  
## Comentarios  
 Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web`. Para obtener más información, consulta [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).  
  
> [!NOTE]
>  La funcionalidad y los tipos de almacenamiento en caché de salida del espacio de nombres <xref:System.Runtime.Caching> son nuevos en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache>. En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché. El nombre de la memoria caché se establece en el nombre predeterminado de la entrada de caché estableciendo el atributo `name` en "default".  
  
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
 [Elemento \<memoryCache\> \(configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)