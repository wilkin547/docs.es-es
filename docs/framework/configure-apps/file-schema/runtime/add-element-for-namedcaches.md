---
title: "&lt;add&gt; (Elemento para &lt;namedCaches&gt;) | Microsoft Docs"
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
  - "<add> (elemento para <namedCaches>)"
  - "add (elemento para <namedCaches>)"
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;add&gt; (Elemento para &lt;namedCaches&gt;)
Agrega una entrada `namedCache` a la colección `namedCaches` de una memoria caché en memoria.  
  
## Sintaxis  
  
```  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## Tipo  
 `None`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|||  
|-|-|  
|Atributo|Descripción|  
|`CacheMemoryLimitMegabytes`|Un valor entero que especifica el tamaño máximo de memoria permitido \(en megabytes\) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache>.  El valor predeterminado es 0, lo que indica que se utilizan las heurísticas del ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> de manera predeterminada.|  
|`Name`|Nombre de la memoria caché.|  
|`PhysicalMemoryLimitPercentage`|Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo físicamente instalada que puede consumir la caché.  El valor predeterminado es 0, lo que indica que se utilizan las heurísticas del ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> de manera predeterminada.|  
|`PollingInterval`|Un valor que indica el intervalo de tiempo después del cual la implementación de memoria caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje establecidos para la instancia de la memoria caché.  Este valor se especifica en formato "HH:MM:SS".|  
  
### Elementos secundarios  
 `None`  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de configuraciones de las instancias con nombre de <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Comentarios  
 El elemento `add` agrega una entrada a la colección `namedCaches` de una memoria caché en memoria.  Puede usar el elemento [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) antes de usar el elemento `add` para asegurarse de que no hay ninguna otra caché con nombre en la colección.  Este elemento se puede utilizar en el archivo machine.config y en el archivo Web.config.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo definir los valores para la entrada `namedCache` predeterminada en la colección `namedCaches`  para la memoria caché en memoria.  
  
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
 [\<namedCaches\> \(Elemento, Configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)