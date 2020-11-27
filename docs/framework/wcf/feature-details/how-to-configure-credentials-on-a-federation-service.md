---
title: Procedimiento para configurar las credenciales en un servicio de federación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 149ab165-0ef3-490a-83a9-4322a07bd98a
ms.openlocfilehash: 692ccc0c39ca7ed40601551ea6bbcdd840fa03af
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257592"
---
# <a name="how-to-configure-credentials-on-a-federation-service"></a>Procedimiento para configurar las credenciales en un servicio de federación

En Windows Communication Foundation (WCF), la creación de un servicio federado consta de los siguientes procedimientos principales:  
  
1. Configurar un <xref:System.ServiceModel.WSFederationHttpBinding> o un enlace personalizado similar. Para obtener más información sobre cómo crear un enlace adecuado, vea [Cómo: crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md).  
  
2. Configurar el <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> que controla cómo se autentican los tokens emitidos que se presentan al servicio.  
  
 Este tema proporciona detalles sobre el segundo paso. Para obtener más información sobre cómo funciona un servicio federado, vea [Federación](federation.md).  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-code"></a>Para establecer las propiedades de IssuedTokenServiceCredential en el código  
  
1. Utilice la propiedad <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A> de la clase <xref:System.ServiceModel.Description.ServiceCredentials> para devolver una referencia a una instancia <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. Se obtiene acceso a la propiedad desde la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> de la clase <xref:System.ServiceModel.ServiceHostBase>.  
  
2. Establezca la <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> propiedad en `true` si se van a autenticar los tokens emitidos automáticamente, como las tarjetas de CardSpace. De manera predeterminada, es `false`.  
  
3. Rellene la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> con instancias de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>. Cada instancia representa un emisor desde el que el servicio autenticará los tokens.  
  
    > [!NOTE]
    > A diferencia de la colección del lado del cliente devuelta por la propiedad <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>, la colección de certificados conocida no es una colección con clave. El servicio acepta los tokens que los certificados especificados emiten sin tener en cuenta la dirección del cliente que envió el mensaje con el token emitido (sujeto a las restricciones siguientes, que se describirán más adelante).  
  
4. Establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> en uno de los valores de enumeración <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Esto solo se puede hacer en código. De manera predeterminada, es <xref:System.IdentityModel.Selectors.X509CertificateValidator.ChainTrust%2A>.  
  
5. Si la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> está establecida en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>, asigne a continuación una instancia de la clase personalizada <xref:System.IdentityModel.Selectors.X509CertificateValidator> a la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.  
  
6. Si <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> está definido en `ChainTrust` o `PeerOrChainTrust`, defina la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.RevocationMode%2A> en un valor apropiado de la enumeración <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. Tenga en cuenta que el modo de revocación no se utiliza en `PeerTrust` ni en los modos de validación `Custom`.  
  
7. Si es necesario, asigne una instancia de una clase <xref:System.IdentityModel.Tokens.SamlSerializer> personalizada a la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.SamlSerializer%2A>. Se necesita un serializador del Lenguaje de marcado de aserción de seguridad (SAML) personalizado, por ejemplo, para analizar las aserciones de SAML personalizadas.  
  
### <a name="to-set-the-properties-of-issuedtokenservicecredential-in-configuration"></a>Para establecer las propiedades de IssuedTokenServiceCredential en la configuración  
  
1. Cree un `<issuedTokenAuthentication>` elemento como elemento secundario de un `serviceCredentials` elemento <>.  
  
2. Establezca el `allowUntrustedRsaIssuers` atributo del `<issuedTokenAuthentication>` elemento en `true` si se autentica un token emitido automáticamente, como una tarjeta de CardSpace.  
  
3. Cree un elemento `<knownCertificates>` como elemento secundario del elemento de `<issuedTokenAuthentication>`.  
  
4. Cree cero o más elementos `<add>``<knownCertificates>``storeLocation``storeName` y .  
  
5. Si es necesario, establezca el `samlSerializer` atributo del `issuedTokenAuthentication` elemento <> en el nombre de tipo de la <xref:System.IdentityModel.Tokens.SamlSerializer> clase personalizada.  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo define las propiedades de un <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> en el código.  
  
 [!code-csharp[C_FederatedService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedservice/cs/source.cs#2)]
 [!code-vb[C_FederatedService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedservice/vb/source.vb#2)]  
  
 Para que un servicio federado autentique un cliente, debe cumplirse lo siguiente sobre el token emitido:  
  
- Cuando la firma digital del token emitido utiliza un identificador de clave de seguridad de RSA, la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowUntrustedRsaIssuers%2A> debe ser `true`.  
  
- Cuando la firma del token emitido utiliza un número de serie de emisor de X.509, un identificador de clave de sujeto (SKI) de X.509 o un identificador de seguridad de huella digital de X.509, un certificado debe firmar el token emitido en la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> de la clase <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>.  
  
- Cuando se firma el token emitido utilizando un certificado X.509, el certificado debe validarse por la semántica especificada por el valor de la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A>, sin tener en cuenta si el certificado se envió al usuario de confianza como <xref:System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause> o se obtuvo de la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>. Para obtener más información acerca de la validación de certificados X. 509, consulte [trabajar con certificados](working-with-certificates.md).  
  
 Por ejemplo, establecer <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerTrust> autenticaría cualquier token emitido cuyo certificado de firma esté en el almacén de certificados `TrustedPeople`. En ese caso, defina la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.TrustedStoreLocation%2A> en <xref:System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser> o <xref:System.Security.Cryptography.X509Certificates.StoreLocation.LocalMachine>. Puede seleccionar otros modos, incluidos <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>. Cuando `Custom` está seleccionado, debe asignar una instancia de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> a la propiedad <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CustomCertificateValidator%2A>. El validador personalizado puede validar los certificados utilizando cualquier criterio que le guste. Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## <a name="see-also"></a>Vea también

- [Federación](federation.md)
- [Federación y confianza](federation-and-trust.md)
- [Ejemplo de federación](../samples/federation-sample.md)
- [Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Procedimiento para crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)
- [Procedimiento para crear un cliente federado](how-to-create-a-federated-client.md)
- [Trabajar con certificados](working-with-certificates.md)
- [Modos de autenticación de SecurityBindingElement](securitybindingelement-authentication-modes.md)
