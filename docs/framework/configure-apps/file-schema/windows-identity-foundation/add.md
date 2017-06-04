---
title: "&lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;add&gt;
Opcional.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
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
|type|El nombre de tipo CLR del controlador de símbolo \(token\) que se agregará.  Opcional.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> \(clase\), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.|  
|[\<sessionTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Opcional.|  
|[\<userNameSecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Elemento|  
|[\<x509SecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Descripción|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Especifica una colección de controladores de token de seguridad registrados con el extremo.|  
  
## Comentarios  
 El `<add>` elemento puede tener un elemento secundario que especifica la configuración para el controlador de símbolo \(token\).  Esto depende de si hace referencia la clase de controlador a través de la `type` atributo de la `<add>` elemento proporciona soporte para esta característica.  Las clases de controlador de símbolo \(token\) que proporcionan esta característica deben exponer un constructor que toma un <xref:System.Xml.XmlElement> objeto.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Algunas de las clases de controlador de token de seguridad integradas proporcionan esta funcionalidad.  These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  La colección de controladores de símbolo \(token\) sólo puede contener un solo controlador de cualquier tipo.  Los demás se omiten.  Puede utilizar el [\<quitar\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento para quitar un solo controlador de la colección o el uso del [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento para quitar todos los controladores de la colección.  
  
 Configuración especificada en un controlador de reemplaza la configuración equivalente especificada en la colección de controladores de símbolo \(token\) en el [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento y los que se especifican en el nivel de servicio en el [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.  
  
## Ejemplo  
 El XML siguiente muestra el uso de la `<add>` y `<remove>` elementos para reemplazar el controlador de token de sesión predeterminado con un controlador de token de sesión personalizado.  El código XML se toma de la `ClaimsAwareWebFarm` ejemplo.  
  
```  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```