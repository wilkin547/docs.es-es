---
title: "&lt;add&gt; (Elemento para authenticationModules, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento), authenticationModules"
  - "<authenticationModules>, add (elemento)"
  - "add (elemento), authenticationModules"
  - "authenticationModules, add (elemento)"
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;add&gt; (Elemento para authenticationModules, Configuraci&#243;n de red)
Agrega un módulo de autenticación a la aplicación.  
  
## Sintaxis  
  
```  
  
      <add   
   type = "client type", System, Version="version number", Culture="culture", PublicKeyToken="token"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`type`|Nombre de clase e información relacionada con el módulo que implementa la autenticación.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos utilizados para autenticar solicitudes de red.|  
  
## Comentarios  
 El elemento de `add` agrega un módulo de autenticación al final de la lista de módulos registrados de autenticación.  Se llama a los módulos de autenticación en el orden en que fueron agregados a la lista.  
  
 El valor para el atributo `type` debería ser un nombre de archivo DLL válido y el nombre de clase correspondiente, separados por una coma.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente habilita los módulos de autenticación predeterminados.  Deberían reemplazarse los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.  
  
```  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.IAuthenticationModule>   
 <xref:System.Net.AuthenticationManager>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)