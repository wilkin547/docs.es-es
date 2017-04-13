---
title: "&lt;issuerChannelBehaviors&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;issuerChannelBehaviors&gt; (elemento)
Contiene una colección de comportamientos de extremo de cliente de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] \(definidos en la configuración\) que se va a usar al comunicar con los servicios de tokens de servicio especificados.  Los comportamientos definidos no pueden incluir ningún elemento [\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).  
  
## Sintaxis  
  
```  
  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|Agrega un comportamiento a la colección.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<issuedToken\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Especifica un token personalizado usado para autenticar un cliente en un servicio.|  
  
## Comentarios  
 Use este elemento cuando se deba utilizar un comportamiento \(excepto los comportamientos que incluyen elementos `<clientCredentials>`\) para comunicar con un servicio.  Por ejemplo, si se debe incluir un elemento de comportamiento [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
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