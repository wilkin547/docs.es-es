---
title: "&lt;audienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;audienceUris&gt;
Especifica el conjunto de identificadores URI que son aceptables identificadores de la parte que confía \(RP\).  Símbolos \(token\) no se aceptará, a menos que tengan el ámbito de uno de la audiencia permitida los identificadores URI.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|mode|Elemento  Descripción  El valor predeterminado es "Siempre".  Opcional.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`<add value=xs:string>`|Agrega el URI especificado por el `value` de atributo a la colección de audienceUris.  El atributo `value` es necesario.  El identificador URI distingue mayúsculas de minúsculas.|  
|`<clear>`|Borra la colección audienceUris.  Se quitan todos los identificadores de la colección.|  
|`<remove value=xs:string>`|Quita el identificador URI especificado por el `value` atributo de la colección audienceUris.  El atributo `value` es necesario.  El identificador URI distingue mayúsculas de minúsculas.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de una colección de seguridad de los controladores de símbolo \(token\).|  
  
## Comentarios  
 De forma predeterminada, la colección está vacía; Utilice `<add>`, `<clear>`, y `<remove>` elementos para modificar la colección.  <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>y <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objetos de uso permiten de los valores de la audiencia de la colección de URI para configurar cualquier audiencia restricciones de URI en <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objetos.  
  
 El `<audienceUris>` elemento está representado por el <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> clase.  Un URI individual agregado a la colección está representado por el <xref:System.IdentityModel.Configuration.AudienceUriElement> clase.  
  
> [!NOTE]
>  El uso de la `<audienceUris>` elemento como elemento secundario de la [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento se ha degradado, pero todavía se admite por compatibilidad con versiones anteriores.  Configuración de la `<securityTokenHandlerConfiguration>` elemento anulan a aquellos en los `<identityConfiguration>` elemento.  
  
## Ejemplo  
 El XML siguiente muestra cómo configurar la audiencia aceptable identificadores URI para una aplicación.  En este ejemplo configura un URI único.  Símbolos \(tokens\) el ámbito de este URI se aceptará, se rechazarán todos los demás.  
  
```  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```