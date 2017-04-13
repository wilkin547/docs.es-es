---
title: "&lt;remove&gt; (Elemento para authenticationModules, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<authenticationModules>, remove (elemento)"
  - "<remove> (elemento), authenticationModules"
  - "authenticationModules, remove (elemento)"
  - "remove (elemento), authenticationModules"
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;remove&gt; (Elemento para authenticationModules, Configuraci&#243;n de red)
Quita un módulo de autenticación de la aplicación.  
  
## Sintaxis  
  
```  
  
      <remove   
   name = "authentication module name"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|**nombre**|Nombre del módulo de autenticación que se va a quitar.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos utilizados para autenticar solicitudes de red.|  
  
## Comentarios  
 El elemento de `remove` quita los módulos de autenticación que anteriormente definido en el archivo de configuración o de alto nivel en la jerarquía de configuración.  
  
 El valor para el atributo `name` debería ser un nombre de clase válido.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente quita un módulo de autenticación.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove name = "System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)