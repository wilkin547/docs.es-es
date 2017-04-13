---
title: "&lt;settings&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#settings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<settings> (elemento)"
  - "settings (elemento)"
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;settings&gt; (Elemento, Configuraci&#243;n de red)
Configura las opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=fullName>.  
  
## Sintaxis  
  
```  
  
      <settings>  
..<httpListener> … </httpListener>  
..<httpWebRequest> … </httpWebRequest>  
..<ipv6> … </ipv6>  
..<performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
..<socket> … </socket>  
..<webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[httpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|Personaliza los parámetros utilizados por la clase <xref:System.Net.HttpListener>.|  
|[el más httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|Personaliza los parámetros de solicitud Web.|  
|[ipv6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|Permite la compatibilidad con la versión 6 del Protocolo de Internet \(IPv6\).|  
|[\<performanceCounter\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|Habilita contadores de rendimiento de red.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|Configura las conexiones a los recursos de red.|  
|[socket](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|Especifica si las operaciones del socket utilizan puertos de terminación.|  
|[Elemento \<webProxyScript\> \(configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|Configura las características del script que se utilizan para detectar los servidores proxy Web.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Comentarios  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Vea también  
 <xref:System.Net?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)