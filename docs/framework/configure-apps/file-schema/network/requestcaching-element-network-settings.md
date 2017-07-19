---
title: "&lt;requestCaching&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requestCaching> (elemento)"
  - "requestCaching (elemento)"
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;requestCaching&gt; (Elemento, Configuraci&#243;n de red)
Controla el mecanismo del almacenamiento en caché para las solicitudes de la red.  
  
## Sintaxis  
  
```  
  
      <requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss""  
  <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
  <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`isPrivateCache`|Especifica si la caché proporciona aislamiento entre la información de distintos usuarios.  El valor predeterminado es `true`.  Este valor debería ser `false` para las aplicaciones de nivel medio.|  
|`disableAllCaching`|Especifica que se deshabilite el almacenamiento en caché para todas las respuestas de Web, y no se puede reemplazar mediante programación.|  
|`defaultPolicyLevel`|Uno de los valores de la enumeración <xref:System.Net.Cache.RequestCacheLevel>.  El valor predeterminado es `BypassCache`.|  
|`unspecifiedMaximumAge`|Especifica el tiempo predeterminado después del cual el contenido se marca como expirado.|  
  
## Atributo policyLevel  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`Default`|Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud de su contenido es exacta y los atributos de expiración, modificación y longitud de contenido están presentes.|  
|`BypassCache`|Devuelve el recurso del servidor.|  
|`CacheOnly`|Devuelve el recurso almacenado en caché si está presente la longitud del contenido y coincide con el tamaño de la entrada.|  
|`CacheIfAvailable`|Devuelve el recurso almacenado en memoria caché si se proporciona la longitud del contenido y coincide con el tamaño de la entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al llamador.|  
|`Revalidate`|Devuelve el recurso almacenado en memoria caché si la marca de tiempo del recurso almacenado en caché coincide con la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la caché y se devuelve al llamador.|  
|`Reload`|Descarga el recurso del servidor, lo almacena en caché y devuelve el recurso al llamador.|  
|`NoCacheNoStore`|Si existe un recurso almacenado en memoria caché, se elimina.  El recurso se descarga del servidor y se devuelve al llamador.|  
|`Revalidate`|Satisface una solicitud mediante la copia en caché del recurso si la marca de tiempo del recurso almacenado en caché coincide con la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la memoria caché.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Elemento opcional.<br /><br /> Describe si el almacenamiento en caché de HTTP está activo y describe la directiva predeterminada de almacenamiento en caché.|  
|[\<defaultFtpCachePolicy\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Elemento opcional.<br /><br /> Describe si el almacenamiento en caché de FTP está activo y describe la directiva predeterminada de almacenamiento en caché.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo deshabilitar el almacenamiento en caché.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Cache?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)