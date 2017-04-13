---
title: "&lt;add&gt; de &lt;allowedAudienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;add&gt; de &lt;allowedAudienceUris&gt;
Agrega un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.  
  
## Sintaxis  
  
```  
  
<allowedAudienceUris>   
   <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|allowedAudienceUri|Cadena que contiene un URI de destino para el que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<allowedAudienceUris\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|Representa una colección de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido.|  
  
## Comentarios  
 Debería utilizar esta colección en una aplicación federada que utilice un servicio de token seguro \(STS\) que emita tokens de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken>.  Cuando el STS emite el token de seguridad, puede especificar el URI de los servicios Web para el que está dirigido el token de seguridad mediante la agregación de una <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token de seguridad.  Eso le permite al <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servicio Web del destinatario comprobar que el token de seguridad emitido está dirigido a este servicio Web especificando que esta comprobación debería tener lugar haciendo lo siguiente:  
  
-   Establezca el atributo `audienceUriMode` de `<issuedTokenAuthentication>` en <xref:System.IdentityModel.Selectors.AudienceUriMode> o <xref:System.IdentityModel.Selectors.AudienceUriMode>.  
  
-   Especifique el conjunto de identificadores URI válidos, agregando los URI a esta colección.  
  
 Para obtener más información, consulta <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Para obtener más información sobre cómo utilizar este elemento de configuración, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## Vea también  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>   
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>   
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>   
 [\<allowedAudienceUris\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)   
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Cómo: Configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)