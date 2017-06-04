---
title: "&lt;security&gt; de &lt;peerTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;security&gt; de &lt;peerTransport&gt;
Contiene la configuración de seguridad asociada con un canal del mismo nivel, incluido el tipo de autenticación utilizado y la seguridad utilizada para el transporte del mensaje.  
  
## Sintaxis  
  
```  
  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`mode`|Especifica el tipo de seguridad que se va a aplicar.  El valor predeterminado es Mensaje.  Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Transport`|La seguridad se proporciona utilizando HTTPS.|  
|`Message`|La seguridad SOAP proporciona autenticación, integridad y confidencialidad.|  
|`TransportWithMessageCredential`|HTTPS proporciona autenticación y confidencialidad.  Los mensajes SOAP proporcionan tipos de credencial enriquecidos.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado.  Este elemento tiene un atributo `clientCredentialType` que especifica las credenciales que se van a usar al interactuar con un servicio.  Este atributo es del tipo <xref:System.ServiceModel.PeerTransportCredentialType>.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<peerTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|Define un transporte del mismo nivel para un enlace personalizado.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)