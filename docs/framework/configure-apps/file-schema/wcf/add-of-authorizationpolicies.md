---
title: "&lt;add&gt; de &lt;authorizationPolicies&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;add&gt; de &lt;authorizationPolicies&gt;
Especifica una directiva de autorización para la transformación de notificaciones.  
  
## Sintaxis  
  
```  
  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`policyType`|Atributo de cadena requerido.<br /><br /> El modelo de control de acceso de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] admite el aprovisionamiento de un conjunto de directivas de autorización como tipos.  Este atributo especifica una directiva de autorización que permite la transformación de un conjunto de notificaciones de entrada en otro conjunto de notificaciones.  Se puede permitir o denegar el acceso en base a eso.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<authorizationPolicies\>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|Especifica una colección de tipos de directiva de autorización.|  
  
## Comentarios  
 Cada directiva de autorización contiene un atributo `policyType` necesario único que es una cadena.  El atributo especifica una directiva de autorización que permite la transformación de un conjunto de demandas de entrada en otro conjunto de demandas.  Se puede permitir o denegar el acceso en base a eso.  Para obtener más información sobre cómo funciona una directiva de autorización, vea <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>   
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>   
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>   
 [Autorización de acceso a operaciones de servicio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)   
 [Cómo crear un administrador de autorización personalizado para un servicio](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)   
 [Directiva de autorización](../../../../../docs/framework/wcf/samples/authorization-policy.md)