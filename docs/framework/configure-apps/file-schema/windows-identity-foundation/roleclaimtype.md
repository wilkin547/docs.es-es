---
title: "&lt;roleClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;roleClaimType&gt;
Especifica la petición de tipos que define el rol de las peticiones de tipo en la colección de objetos <xref:System.Security.Claims.ClaimsIdentity> devueltos por el método de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> de controlador de token.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
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
|value|Una cadena que especifica el URI que representa el tipo de petición de petición de utilizar para el rol del tipo de petición.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Proporciona la configuración para la clase de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , la clase de <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , o una clase derivada de cualquiera de estas clases.|  
  
## Comentarios  
 El elemento de `<roleClaimType>` la propiedad de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> cuando un objeto de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> inicializa de la configuración.  
  
## Ejemplo  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>