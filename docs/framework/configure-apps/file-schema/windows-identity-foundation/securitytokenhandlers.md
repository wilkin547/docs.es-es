---
title: "&lt;securityTokenHandlers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;securityTokenHandlers&gt;
Especifica una colección de controladores de token de seguridad registrados con el extremo.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Especifica el nombre de una colección de controladores de símbolo \(token\).  Los únicos valores reconocidos por el marco de trabajo son "ActAs" y "OnBehalfOf".  Si se especifican las colecciones de símbolo \(token\) de controlador con cualquiera de estos nombres, la colección se utilizará al procesamiento de ActAs o OnBehalfOf símbolos \(token\) respectivamente.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega un controlador de token de seguridad a la colección de controladores de símbolo \(token\).|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Borra todos los controladores de token de seguridad de la colección de controladores de símbolo \(token\).|  
|[\<quitar\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Quita un controlador de token de seguridad de la colección de controladores de símbolo \(token\).|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de la colección de controladores de símbolo \(token\).|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica la configuración de la identidad de nivel de servicio.|  
  
## Comentarios  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción  name  
  
 De forma predeterminada, la colección se rellena con los siguientes tipos de controlador: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, y <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.  Puede modificar la colección mediante el uso de la `<add>`, `<remove>`, y `<clear>` elementos.  Debe asegurarse de que existe un solo controlador de ningún tipo concreto de la colección.  Elemento  
  
 Descripción  Configuración especificada a través de este elemento reemplaza las especificadas en el servicio a través de la [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.  Algunos controladores \(incluyendo varios de los tipos de controlador integrado\) pueden admitir una configuración adicional a través de un elemento secundario de la `<add>` elemento.  Configuración especificada en un controlador de reemplaza la configuración equivalente especificada en la colección o el servicio.