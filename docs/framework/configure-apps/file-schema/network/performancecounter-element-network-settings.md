---
title: "&lt;performanceCounter&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<performanceCounter> (elemento)"
  - "performanceCounter (elemento)"
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;performanceCounter&gt; (Elemento, Configuraci&#243;n de red)
Habilita o deshabilita los contadores de rendimiento de red.  
  
## Sintaxis  
  
```  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Especifica si los contadores de rendimiento de red están habilitados.  El valor predeterminado es `false`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
 Los contadores de rendimiento de red necesitan estar habilitados en el archivo de configuración que se va a utilizar.  Todos los contadores de rendimiento de red se habilitan o deshabilitan con un único valor del archivo de configuración.  Los contadores de rendimiento de red individuales no se pueden habilitar o deshabilitar.  Para obtener más información sobre contadores de rendimiento de red concretos, vea [Networking Performance Counters](http://msdn.microsoft.com/es-es/d1860235-f643-46ae-846c-ff0ed8b0e3cd).  
  
 El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.  
  
 La propiedad <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo **enabled** de los archivos de configuración aplicables.  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo configurar <xref:System.Net> y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [Networking Performance Counters](http://msdn.microsoft.com/es-es/d1860235-f643-46ae-846c-ff0ed8b0e3cd)