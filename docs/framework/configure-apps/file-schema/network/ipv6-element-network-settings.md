---
title: "&lt;ipv6&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<ipv6> (elemento)"
  - "ipv6 (elemento)"
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;ipv6&gt; (Elemento, Configuraci&#243;n de red)
Habilita las respuestas IPv6 \(Protocolo de Internet versión 6\) de miembros obsoletos de la clase <xref:System.Net.Dns>.  
  
## Sintaxis  
  
```  
  
      <ipv6  
  enabled="true|false"  
/ipv6>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`enabled`|Especifica si los miembros de la clase <xref:System.Net.Dns> devuelven direcciones IPv6 \(Protocolo de Internet versión 6\).  El valor predeterminado es `false`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
 Esta opción habilita la compatibilidad con IPv6 para miembros obsoletos de la clase <xref:System.Net.Dns>: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A> y <xref:System.Net.Dns.Resolve%2A>.  Para otros miembros del espacio de nombres <xref:System.Net?displayProperty=fullName>, pueden devolverse direcciones IPv6 si la opción IPv6 está habilitada en el sistema operativo.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra la forma de habilitar la compatibilidad con IPv6 para la clase <xref:System.Net.Dns>.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Dns?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)