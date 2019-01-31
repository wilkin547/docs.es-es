---
title: <authentication> de <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 8288e530d0164b41a6cf53cc39385a2d29fdb091
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255177"
---
# <a name="authentication-of-servicecertificate-element"></a>\<autenticación > de \<serviceCertificate > elemento
Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.  
  
 \<system.ServiceModel>  
\<comportamientos >  
sección endpointBehaviors  
\<comportamiento >  
\<clientCredentials>  
\<serviceCertificate>  
\<authentication>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|customCertificateValidatorType|Cadena. Tipo y ensamblado utilizados para validar un tipo personalizado.|  
|certificateValidationMode|Especifica uno de los tres modos utilizados para validar las credenciales. Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator. De manera predeterminada, es `ChainTrust`.|  
|revocationMode|Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL). De manera predeterminada, es `Online`.|  
|trustedStoreLocation|Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`. Se utiliza este valor cuando un certificado del servicio se negocia al cliente. Se realiza la validación contra el **personas de confianza** almacenar en la ubicación del almacén especificado. De manera predeterminada, es `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>Atributo customCertificateValidator  
  
|Valor|Descripción|  
|-----------|-----------------|  
|String|Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.|  
  
## <a name="certificatevalidationmode-attribute"></a>Atributo certificateValidationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Atributo revocationMode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: NoCheck, Online, Offline.<br /><br /> Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Atributo trustedStoreLocation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los siguientes valores: LocalMachine o CurrentUser. El valor predeterminado es CurrentUser. Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine. Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.|  
  
## <a name="remarks"></a>Comentarios  
 El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados. De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena. Este es el modo más seguro. También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza. Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza. Al implementar un cliente, utilice en su lugar el valor `ChainTrust`. También puede establecer el valor como `Custom` o `None`. Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado. Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator. Para obtener más información, vea [Cómo: Crear un servicio que emplee un validador de certificado personalizado](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados. El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados. Para obtener más información, consulte [trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo realiza dos tareas: Primero especifica un certificado de servicio para el cliente que se usará al comunicarse con puntos de conexión cuyo nombre de dominio es `www.contoso.com` a través del protocolo HTTP. En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.  
  
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
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Cómo: Crear un servicio que emplee un validador de certificado personalizada](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
