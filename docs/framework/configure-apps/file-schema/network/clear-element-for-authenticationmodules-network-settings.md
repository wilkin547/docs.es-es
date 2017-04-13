---
title: "&lt;clear&gt; (Elemento para authenticationModules, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<authenticationModules>, clear (elemento)"
  - "<clear> (elemento), authenticationModules"
  - "authenticationModules, clear (elemento)"
  - "clear (elemento), authenticationModules"
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;clear&gt; (Elemento para authenticationModules, Configuraci&#243;n de red)
Quita todos los módulos de autenticación de la aplicación.  
  
## Sintaxis  
  
```  
  
<clear/>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos utilizados para autenticar solicitudes de red.|  
  
## Comentarios  
 El elemento `clear` quita todos los módulos de autenticación definidos anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente quita todos configuraron los módulos de autenticación configurados.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)