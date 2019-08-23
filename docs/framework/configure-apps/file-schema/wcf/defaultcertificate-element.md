---
title: <defaultCertificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919257"
---
# <a name="defaultcertificate-element"></a>\<defaultCertificate >, elemento
Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.  
  
 \<system.ServiceModel>  
\<comportamientos >  
sección endpointBehaviors  
\<comportamiento >  
\<clientCredentials>  
\<serviceCertificate>  
\<defaultCertificate>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|findValue|Cadena. Valor que se va a buscar.|  
|x509FindType|Enumeración. Uno de los campos de certificado en que buscar.|  
|storeLocation|Enumeración. Una de las dos ubicaciones de almacén de sistema en que buscar.|  
|storeName|Enumeración. Uno de los almacenes del sistema en que buscar.|  
  
## <a name="findvalue-attribute"></a>AtributofindValue  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|string|El valor depende del campo (se especifica por el atributo X509FindType) en que se busca. Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.|  
  
## <a name="x509findtype-attribute"></a>Atributo x509FindType  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|Enumeración|Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.|  
  
## <a name="storelocation-attribute"></a>Atributo storeLocation  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|Enumeración|CurrentUser o LocalMachine.|  
  
## <a name="storename-attribute"></a>Atributo storeName  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|Enumeración|Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, no permitido, My, root, TrustedPeople y TrustedPublisher.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente. Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se especifica un certificado que se va a usar para los `http://www.contoso.com` puntos de conexión cuyo URI comienza con y un certificado que se va a usar para todos los demás extremos que no realizan la negociación de certificados.  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [Trabajo con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
