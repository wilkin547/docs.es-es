---
title: "&lt;userNameSecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;userNameSecurityTokenHandlerRequirement&gt;
Proporciona la configuración para la clase o clases derivadas de <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> .  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
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
|membershipProviderName|Especifica <xref:System.Web.Security.MembershipProvider> que se debe utilizar el controlador de token de seguridad.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega el controlador especificado de token de seguridad a la colección de controlador de token.|  
  
## Comentarios  
 El elemento de `<userNameSecurityTokenHandlerRequirement>` la propiedad de <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> cuando un objeto de <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> inicializa de la configuración.  
  
## Ejemplo  
  
```  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```