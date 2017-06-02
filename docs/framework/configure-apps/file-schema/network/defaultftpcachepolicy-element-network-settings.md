---
title: "&lt;defaultFtpCachePolicy&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultFtpCachePolicy> (elemento)"
  - "defaultFtpCachePolicy (elemento)"
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;defaultFtpCachePolicy&gt; (Elemento, Configuraci&#243;n de red)
Describe si el almacenamiento en caché de FTP está activo y describe la directiva predeterminada de almacenamiento en caché.  
  
## Sintaxis  
  
```  
< defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`policyLevel`|Especifica la directiva de almacenamiento en caché FTP.  El valor predeterminado es `Default`.|  
  
## Atributo policyLevel  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`Default`|Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud de su contenido es exacta y los atributos de expiración, modificación y longitud de contenido están presentes.|  
|`BypassCache`|Devuelve el recurso del servidor.|  
|`CacheOnly`|Devuelve el recurso almacenado en caché si está presente la longitud del contenido y coincide con el tamaño de la entrada.|  
|`CacheIfAvailable`|Devuelve el recurso almacenado en memoria caché si se proporciona la longitud del contenido y coincide con el tamaño de la entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al llamador.|  
|`Revalidate`|Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es la misma que la marca de tiempo del recurso del servidor; en caso contrario, el recurso se descarga del servidor, se almacena en la caché y se devuelve al llamador.|  
|`Reload`|Descarga el recurso del servidor, lo almacena en caché y devuelve el recurso al llamador.|  
|`NoCacheNoStore`|Si existe un recurso almacenado en memoria caché, se elimina.  El recurso se descarga del servidor y se devuelve al llamador.|  
|`Revalidate`|Atiende una solicitud utilizando la copia almacenada en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la caché.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[el requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controla el mecanismo del almacenamiento en caché para las solicitudes de la red.|  
  
## Comentarios  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo especificar una directiva de almacenamiento en caché FTP de `NoCacheNoStore`.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        Level="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)