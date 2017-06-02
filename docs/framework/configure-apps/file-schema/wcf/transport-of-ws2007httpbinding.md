---
title: "&lt;transport&gt; de &lt;ws2007HttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;transport&gt; de &lt;ws2007HttpBinding&gt;
Define la configuración de autenticación del transporte HTTP.  
  
## Sintaxis  
  
```  
  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## Tipo  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`clientCredentialType`|Especifica la credencial utilizada para autenticar el cliente al servicio.  Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Especifica la credencial usada para autenticar al cliente en un proxy del dominio.  Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|El dominio de autenticación para autenticación implícita o básica.  El valor predeterminado es una cadena vacía.<br /><br /> Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.  También puede especificar una colección de usuarios que tiene acceso.  Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|La seguridad está deshabilitada.|  
|Básico|Usa la autenticación básica.|  
|Implícita|Usa la autenticación implícita.|  
|Ntlm|Utiliza la autenticación NTLM como reserva con un dominio de Windows.|  
|Windows|Utiliza la autenticación de Windows integrada.|  
|Certificado|Utiliza los certificados X.509 para autenticar al cliente.|  
  
## Atributo proxyCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|La seguridad está deshabilitada.|  
|Básico|Usa la autenticación básica.|  
|Implícita|Usa la autenticación implícita.|  
|Ntlm|Utiliza NTLM como reserva con un dominio de Windows.|  
|Windows|Utiliza la autenticación de Windows integrada.|  
|Certificado|Utiliza los certificados X.509 para autenticar al cliente.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Representa las funciones de seguridad del elemento [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.HttpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)