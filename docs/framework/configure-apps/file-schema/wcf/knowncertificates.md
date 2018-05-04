---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 394ae246ad29a0747f3814b36fae2557b04c235a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowncertificatesgt"></a>&lt;knownCertificates&gt;
Representa una colección de certificados X.509 que se proporcionan para autenticar las credenciales de seguridad emitidas desde un Servicio de token de seguridad (STS).  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<issuedTokenAuthentication >  
\<knownCertificates >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|Agrega un certificado X.509 a la colección.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|Especifica un token emitido como una credencial del servicio.|  
  
## <a name="remarks"></a>Comentarios  
 El escenario del token emitido tiene tres etapas. En la primera fase, un cliente intenta tener acceso a un servicio se remite a un *del servicio de token seguro*. El servicio de token seguro autentica, a continuación, al cliente y como consecuencia el cliente emite un token, normalmente un token del lenguaje de marcado de aserción de seguridad (SAML). El cliente vuelve a continuación al servicio con el token. El servicio examina el token para los datos que permite al servicio autenticar el token y, por consiguiente, al cliente. Para autenticar el token, el servicio debe conocer el certificado que usa el servicio de token seguro.  
  
 El [ \<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) elemento es el repositorio para cualquier tales certificados de servicio de token seguro. Para agregar certificados, use el [ \<knownCertificates > elemento](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md). Insertar un [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) para cada certificado, tal como se muestra en el ejemplo siguiente.  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 De forma predeterminada, los certificados se deben obtener a partir de un servicio de token de seguridad. Estos certificados "conocidos" garantizan que solo los clientes legítimos pueden obtener acceso a un servicio.  
  
 Para revisar las condiciones requeridas para que un cliente que va a autenticar un servicio federado, así como para obtener más información sobre el uso de este elemento de configuración, vea [Cómo: configurar las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md). Para obtener más información acerca de escenarios federados, consulte [federación y Tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
 Para obtener un ejemplo que muestra cómo rellenar la colección en la configuración, consulte [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [\<issuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Configuración de las credenciales en un servicio de federación](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Federación y tokens emitidos](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
