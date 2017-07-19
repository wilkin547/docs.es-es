---
title: "Elemento &lt;secureConversationAuthentication&gt; de &lt;serviceCredential&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Elemento &lt;secureConversationAuthentication&gt; de &lt;serviceCredential&gt;
Especifica los valores para un servicio de conversación seguro.  
  
## Sintaxis  
  
```  
  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`securityStateEncoderType`|Una cadena que especifica el tipo de <xref:System.ServiceModel.Security.SecurityStateEncoder> que se debe utilizar.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## Comentarios  
 Utilice este elemento de configuración para especificar una lista de tipos de demanda conocidos para la serialización de cookies de token de contexto de seguridad \(SCT\), así como un codificador para codificar y proteger la información de las cookies.  Para obtener más información acerca de SCT, vea <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>