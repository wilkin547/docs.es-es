---
title: "&lt;transport&gt; de &lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;transport&gt; de &lt;peerTransport&gt;
Especifica el tipo de transporte para mensajes seguros enviados por pares configurados con este enlace.  
  
## Sintaxis  
  
```  
  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|credentialType|Opcional.  Especifica el tipo de credenciales utilizado para comprobar mensajes enviados con el transporte del mismo nivel.  Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## Atributo credentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Certificado|La autenticación del transporte de canal del mismo nivel requiere un certificado X509.|  
|Contraseña|La autenticación del transporte de canal del mismo nivel requiere una contraseña correcta.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Define la configuración de seguridad de un transporte del mismo nivel.|  
  
## Comentarios  
 Este elemento se establece sólo si el atributo de modo de [\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) se establece en `Transport` o `TransportWithMessageCredential`.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)