---
title: "&lt;samlSecurityTokenRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;samlSecurityTokenRequirement&gt;
Proporciona la configuración para la clase de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , la clase de <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , o una clase derivada de cualquiera de estas clases.  Representado por la clase de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> .  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
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
|mapToWindows|Especifica si el controlador del token debe asignar el token que valida una cuenta de Windows mediante la petición de entrada de UPN.  El valor predeterminado es “false”.|  
|issuerCertificateRevocationMode|Un valor de <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de inversión para utilizar para el certificado X.509.  El valor predeterminado es “conectado”.|  
|issuerCertificateValidationMode|Un valor de <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación para utilizar para el certificado X.509.  El valor predeterminado es “PeerOrChainTrust”.|  
|issuerCertificateTrustedStoreLocation|Un valor de <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509.  El valor predeterminado es “LocalMachine”.|  
|issuerCertificateValidator|Un tipo personalizado que deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  Si el atributo de `issuerCertificateValidationMode` es “custom”, una instancia de este tipo se utiliza para la validación del certificado del emisor.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<nameClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|Establece la petición tipo que especifica la propiedad de <xref:System.Security.Principal.IIdentity.Name%2A> .|  
|[\<roleClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|Especifica la petición de tipos que define el rol de las peticiones de tipo en la colección de objetos <xref:System.Security.Claims.ClaimsIdentity> devueltos por el método de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> de controlador de token.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Agrega el controlador especificado de token de seguridad a la colección de controlador de token.|  
  
## Comentarios  
 El elemento de `<samlSecurityTokenRequirement>` se representa mediante la clase de <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos y se usa para configurar la propiedad de `SamlSecurityTokenRequirement` en <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.  
  
## Ejemplo  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```