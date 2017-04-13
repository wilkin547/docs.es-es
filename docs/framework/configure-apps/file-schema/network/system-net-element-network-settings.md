---
title: "&lt;system.Net&gt; (elemento) (configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.Net> (elemento)"
  - "system.Net (elemento)"
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;system.Net&gt; (elemento) (configuraci&#243;n de red)
Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.  
  
## Sintaxis  
  
```  
  
      <system.net>   
</system.net>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos utilizados para autenticar las solicitudes de Internet.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a un host de Internet.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto \(HTTP\).|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Configura opciones para el envío de correo del Protocolo simple de transferencia de correo \(SMTP\).|  
|[el requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Controla el mecanismo del almacenamiento en caché para las solicitudes de la red.|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para las clases de <xref:System.Net> y los espacios de nombres secundarios relacionados.|  
|[\<webRequestModules\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Especifica los módulos que se utilizan para solicitar información a hosts de Internet.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[configuration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Contiene los valores de configuración para todos los espacios de nombres.|  
  
## Comentarios  
 El elemento de [\<system.net\>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) contiene los valores de las clases en <xref:System.Net> y los espacios de nombres secundarios relacionados.  Los valores configuran los módulos de autenticación, la administración de conexiones, la configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de hosts de Internet.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra una configuración típica utilizada por clases <xref:System.Net>.  
  
```  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type = "System.Net.DigestClient" />  
      <add type = "System.Net.NegotiateClient" />  
      <add type = "System.Net.KerberosClient" />  
      <add type = "System.Net.NtlmClient" />  
      <add type = "System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault = "true"  
        bypassonlocal = "true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix = "http"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "https"  
        type = "System.Net.HttpRequestCreator"  
      />  
      <add prefix = "file"  
        type = "System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)