---
title: "&lt;add&gt; de &lt;issuerChannelBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; de &lt;issuerChannelBehaviors&gt;
Agrega un comportamiento del extremo que se va a usar al comunicar con STS.  
  
> [!NOTE]
>  Si un comportamiento del extremo contiene un elemento [\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md), se producirá una excepción.  
  
## Sintaxis  
  
```  
  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|issuerAddress|El URI del emisor del token seguridad con el que se va a comunicar.|  
|behaviorConfiguration|El nombre de un comportamiento del extremo definido en el mismo archivo de configuración.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Contiene una colección de comportamientos del extremo del cliente de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se van a usar al comunicar con los servicios de token de servidor especificados.|  
  
## Comentarios  
 `issuerAddress` contiene el URI del Servicio de token de seguridad con el que el cliente desea comunicarse.  `behaviorConfiguration` apunta a un comportamiento de extremo que la aplicación usa en los canales creados por [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] para obtener los tokens emitidos por los Servicios de token de seguridad.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Cómo crear un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Cómo: Configurar un emisor local](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)