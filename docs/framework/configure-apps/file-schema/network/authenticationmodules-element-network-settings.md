---
title: "&lt;authenticationModules&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<authenticationModules> (elemento)"
  - "authenticationModules (elemento)"
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;authenticationModules&gt; (Elemento, Configuraci&#243;n de red)
Especifica los módulos utilizados para autenticar solicitudes de red.  
  
## Sintaxis  
  
```  
  
      <authenticationModules>   
</authenticationModules>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[agregar](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|Agrega un módulo de autenticación a la aplicación.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|Quita todos los módulos de autenticación de la aplicación.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|Quita un módulo de autenticación de la aplicación.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Comentarios  
 El elemento `authenticationModule` especifica los módulos de autenticación que realizan el proceso de autenticación con un servidor.  Un módulo de autenticación debe implementar la interfaz <xref:System.Net.IAuthenticationModule>.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente habilita un módulo de autenticación.  Deberían reemplazarse los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)