---
title: "&lt;nameClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;nameClaimType&gt;
Establece la petición tipo que especifica la propiedad de <xref:System.Security.Principal.IIdentity.Name%2A> .  Se utiliza el tipo de petición para buscar <xref:System.Security.Claims.Claim> en la colección de objetos <xref:System.Security.Claims.ClaimsIdentity> devueltos por el método de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> de este controlador de token.  El valor de petición correspondiente se establece en el nombre de <xref:System.Security.Principal.IIdentity> generado de este controlador de token.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|value|Una cadena que especifica el URI que representa el tipo de petición de petición a utilizar para la propiedad de <xref:System.Security.Principal.IIdentity.Name%2A> .  Obligatorio.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Proporciona la configuración para la clase de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , la clase de <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , o una clase derivada de cualquiera de estas clases.|  
  
## Comentarios  
 El elemento de `<nameClaimType>` la propiedad de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> cuando un objeto de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> inicializa de la configuración.  
  
## Ejemplo  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>