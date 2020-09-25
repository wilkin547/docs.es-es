---
title: <issuedTokenAuthentication> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
ms.openlocfilehash: 88657b6982108596c8d9030161390f76fcff6609
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202479"
---
# <a name="issuedtokenauthentication-of-servicecredentials"></a>\<issuedTokenAuthentication> de \<serviceCredentials>

Especifica un token personalizado emitido como una credencial de servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenAuthentication>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<issuedTokenAuthentication allowUntrustedRsaIssuers="Boolean"
                           audienceUriMode="Always/BearerKeyOnly/Never"
                           customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                           certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                           revocationMode="NoCheck/Online/Offline"
                           samlSerializer="String"
                           trustedStoreLocation="CurrentUser/LocalMachine">
  <allowedAudienceUris>
    <add allowedAudienceUri="String" />
  </allowedAudienceUris>
  <knownCertificates>
    <add findValue="String"
         storeLocation="CurrentUser/LocalMachine"
         storeName=" CurrentUser/LocalMachine"
         x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`allowedAudienceUris`|Obtiene el conjunto de los URI de destino para los que el token de seguridad <xref:System.IdentityModel.Tokens.SamlSecurityToken> se puede destinar con el fin de que una instancia de <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> lo considere válido. Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.|  
|`allowUntrustedRsaIssuers`|Un valor booleano que especifica si se permiten emisores de certificados de RSA que no son de confianza.<br /><br /> Las entidades emisoras de certificados (CA) firman los certificados para comprobar la autenticidad. Un emisor que no es de confianza es una CA de la cual no se especifica que sea de confianza para firmar certificados.|  
|`audienceUriMode`|Obtiene un valor que especifica si se debería validar <xref:System.IdentityModel.Tokens.SamlSecurityToken> del token de seguridad <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>. Este valor es del tipo <xref:System.IdentityModel.Selectors.AudienceUriMode>. Para obtener más información sobre cómo usar este atributo, vea <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.|  
|`certificateValidationMode`|Especifica el modo de validación del certificado. Uno de los valores válidos de <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`. De manera predeterminada, es `ChainTrust`.|  
|`customCertificateValidatorType`|Cadena opcional. Tipo y ensamblado utilizados para validar un tipo personalizado. Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.|  
|`revocationMode`|Establece el modo de revocación que especifica si se produce una comprobación de revocación, y si se realiza en línea o sin conexión. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.|  
|`samlSerializer`|Un atributo de cadena opcional que especifica el tipo de SamlSerializer que se usa para la credencial del servicio. El valor predeterminado es una cadena vacía.|  
|`trustedStoreLocation`|Enumeración opcional. Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`knownCertificates`|Especifica una colección de elementos <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> que indican emisores de confianza para la credencial del servicio.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Observaciones  

 El escenario del token emitido tiene tres etapas. En la primera fase, un cliente que intenta tener acceso a un servicio se conoce como *servicio de token seguro*. El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML). El cliente vuelve a continuación al servicio con el token. El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente. Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.  
  
 Este elemento es el repositorio para todos los certificados de servicio de token seguro. Para agregar certificados, use [\<knownCertificates>](knowncertificates.md) . Inserte un [\<add>](add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.  
  
```xml  
<issuedTokenAuthentication>
  <knownCertificates>
    <add findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="My"
         X509FindType="FindBySubjectName" />
  </knownCertificates>
</issuedTokenAuthentication>
```  
  
 De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad. Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.  
  
 Para obtener más información sobre el uso de este elemento de configuración, consulte [Cómo: configurar credenciales en un servicio de Federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Procedimiento para configurar las credenciales en un servicio de federación](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
