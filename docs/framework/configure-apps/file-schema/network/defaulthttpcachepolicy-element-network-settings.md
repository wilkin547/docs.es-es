---
title: "&lt;defaultHttpCachePolicy&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<defaultHttpCachePolicy> (elemento)"
  - "<defaultHttpCachePolicy> (elemento)"
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;defaultHttpCachePolicy&gt; (Elemento, Configuraci&#243;n de red)
Describe si el almacenamiento en caché de HTTP está activo y describe la directiva predeterminada de almacenamiento en caché.  
  
## Sintaxis  
  
```  
< defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss"|"minValue"  
  maximumAge  ="d.hh:mm:ss"|"maxValue"  
  maximumStale="d.hh:mm:ss"|"maxValue"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`maximumAge`|Especifica el intervalo de tiempo máximo que tiene que transcurrir antes de que un objeto almacenado en caché se marque como expirado.|  
|`maximumStale`|Especifica el intervalo de tiempo máximo tras la hora de actualización calculada que tiene que transcurrir antes de que un objeto almacenado en caché se marque como expirado.|  
|`minimumFresh`|Especifica el intervalo de tiempo mínimo durante el que un objeto almacenado en caché se considerará actualizado.|  
|`policyLevel`|Especifica si la directiva de almacenamiento en caché es automática o si se omite la caché.  El valor predeterminado es `BypassCache`.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[el requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controla el mecanismo del almacenamiento en caché para las solicitudes de la red.|  
  
## Comentarios  
 El valor del atributo `policyLevel` es `BypassCache` o `Default`.  
  
 Los valores para `maximumAge`, `maximumStale`, y los elementos de `minimumFresh` están en el intervalo de tiempo explícito con un formato de *d*.*hh*:*mm*:*ss* \(días, horas, minutos, segundos y\), o las constantes `minValue` o `maxValue`, según corresponda.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra la forma de especificar un intervalo mínimo de actualización de seis horas, un intervalo máximo de antigüedad de dos días y un plazo máximo de expiración de cuatro horas.  
  
```  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy>  
        <set minimumFresh="0.06:00:00" />  
        <set maximumAge  ="2.00:00:00" />  
        <set maximumStale="0.04:00:00" />  
      </defaultHttpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Cache>   
 <xref:System.Net.WebRequest>   
 <xref:System.Net.Cache.RequestCacheLevel>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)