---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152637"
---
# \<samlSecurityTokenRequirement>
Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases. Se representa mediante la <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|mapToWindows|Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes. El valor predeterminado es "false".|  
|issuerCertificateRevocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valor que especifica el modo de revocación que se va a usar para el certificado X. 509. El valor predeterminado es "online".|  
|issuerCertificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode>Valor que especifica el modo de validación que se va a usar para el certificado X. 509. El valor predeterminado es "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica el almacén de certificados X. 509. El valor predeterminado es "LocalMachine".|  
|issuerCertificateValidator|Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator> . Si el `issuerCertificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Establece el tipo de demanda que especifica la <xref:System.Security.Principal.IIdentity.Name%2A> propiedad.|  
|[\<roleClaimType>](roleclaimtype.md)|Especifica el tipo de notificación que define las notificaciones de tipo de rol en la colección de <xref:System.Security.Claims.ClaimsIdentity> objetos devuelta por el <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> método del controlador de token.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](add.md)|Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 La `<samlSecurityTokenRequirement>` clase representa el elemento <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> en el modelo de objetos y se usa para configurar la `SamlSecurityTokenRequirement` propiedad en <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .  
  
## <a name="example"></a>Ejemplo  
  
```xml  
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
