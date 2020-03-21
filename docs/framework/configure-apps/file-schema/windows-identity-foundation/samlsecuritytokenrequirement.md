---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152637"
---
# <a name="samlsecuritytokenrequirement"></a>\<> samlSecurityTokenRequirement
Proporciona configuración <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> para la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase, la clase o una clase derivada de cualquiera de estas clases. Representado por <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> la clase.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>samlSecurityTokenRequirement**  
  
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
|mapToWindows|Especifica si el controlador de tokens debe asignar el token de validación a una cuenta de Windows mediante la notificación UPN entrante. El valor predeterminado es "false".|  
|issuerCertificateRevocationMode|Valor <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> que especifica el modo de revocación que se usará para el certificado X.509. El valor predeterminado es "Online".|  
|issuerCertificateValidationMode|Valor <xref:System.ServiceModel.Security.X509CertificateValidationMode> que especifica el modo de validación que se usará para el certificado X.509. El valor predeterminado es "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|Valor <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica el almacén de certificados X.509. El valor predeterminado es "LocalMachine".|  
|issuerCertificateValidator|Un tipo personalizado que <xref:System.IdentityModel.Selectors.X509CertificateValidator>deriva de . Si `issuerCertificateValidationMode` el atributo es "Custom", se utiliza una instancia de este tipo para la validación del certificado de emisor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Establece el tipo de <xref:System.Security.Principal.IIdentity.Name%2A> notificación que especifica la propiedad.|  
|[\<roleClaimType>](roleclaimtype.md)|Especifica el tipo de notificación que define <xref:System.Security.Claims.ClaimsIdentity> las notificaciones <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> de tipo de rol en la colección de objetos devueltos por el método del controlador de tokens.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<añadir>](add.md)|Agrega el controlador de token de seguridad especificado a la colección de controladores de tokens.|  
  
## <a name="remarks"></a>Observaciones  
 El `<samlSecurityTokenRequirement>` elemento se representa <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> mediante la clase en el `SamlSecurityTokenRequirement` modelo de <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> objetos y se utiliza para configurar la propiedad en un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>archivo .  
  
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
