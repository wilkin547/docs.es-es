---
title: "&lt;peer&gt; de &lt;clientCredentials&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;peer&gt; de &lt;clientCredentials&gt; (elemento)
Especifica las credenciales usadas al autenticar clientes punto a punto.  
  
## Sintaxis  
  
```  
  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.  .|  
|[\<peerAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Especifica las opciones de autenticación para clientes punto a punto.|  
|[\<messageSenderAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Especifica las opciones de autenticación para los remitentes del mensaje.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales usadas para autenticar un cliente a un servicio.|  
  
## Comentarios  
 Este elemento de configuración especifica las credenciales que un nodo entre pares utiliza para autenticarse en otros nodos de la malla, así como los valores de autenticación que un nodo entre pares utiliza para autenticar otros nodos entre pares.  Para obtener más información, vea [Peer Channel Message Authentication](http://msdn.microsoft.com/es-es/80e73386-514e-4c30-9e4a-b9ca8c173a95) y [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>   
 <xref:System.ServiceModel.Security.PeerCredential>   
 [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/es-es/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/es-es/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)