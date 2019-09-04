---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251905"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases. Se representa mediante <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> la clase.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> samlSecurityTokenRequirement**  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|mapToWindows|Especifica si el controlador de token debe asignar el token de validación a una cuenta de Windows mediante la notificaciones de UPN entrantes. El valor predeterminado es "false".|  
|issuerCertificateRevocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valor que especifica el modo de revocación que se va a usar para el certificado X. 509. El valor predeterminado es "online".|  
|issuerCertificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Valor que especifica el modo de validación que se va a usar para el certificado X. 509. El valor predeterminado es "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|<xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica el almacén de certificados X. 509. El valor predeterminado es "LocalMachine".|  
|issuerCertificateValidator|Un tipo personalizado que se deriva de <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Si el `issuerCertificateValidationMode` atributo es "Custom", se usa una instancia de este tipo para la validación del certificado del emisor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Establece el tipo de demanda que especifica <xref:System.Security.Principal.IIdentity.Name%2A> la propiedad.|  
|[\<roleClaimType>](roleclaimtype.md)|Especifica el tipo de notificación que define las notificaciones de tipo de rol <xref:System.Security.Claims.ClaimsIdentity> en la colección de <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> objetos devuelta por el método del controlador de token.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<add>](add.md)|Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 La `<samlSecurityTokenRequirement>` <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> clase representa el elemento en el modelo de objetos y se usa para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> configurar la `SamlSecurityTokenRequirement` propiedad en o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.  
  
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
