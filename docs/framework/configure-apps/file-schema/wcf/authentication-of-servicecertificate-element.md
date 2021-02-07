---
description: 'Más información sobre: <authentication> del <serviceCertificate> elemento'
title: <authentication> del <serviceCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 35a94f4f9c089f86aef38e7e9a1115a7cd22a325
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749888"
---
# <a name="authentication-of-servicecertificate-element"></a>\<authentication> del \<serviceCertificate> elemento

Especifica la configuración utilizada por el proxy del cliente para autenticar certificados del servicio que se obtienen utilizando la negociación de SSL/TLS.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
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
|customCertificateValidatorType|String. Tipo y ensamblado utilizados para validar un tipo personalizado.|  
|certificateValidationMode|Especifica uno de los tres modos utilizados para validar las credenciales. Si se establece en `Custom`, también debe proporcionarse un customCertificateValidator. De manera predeterminada, es `ChainTrust`.|  
|revocationMode|Uno de los modos utilizados para comprobar listas de certificados revocadas (CRL). De manera predeterminada, es `Online`.|  
|trustedStoreLocation|Una de las dos ubicaciones de almacenamiento del sistema: `LocalMachine` o `CurrentUser`. Se utiliza este valor cuando un certificado del servicio se negocia al cliente. La validación se realiza en el almacén de **personas de confianza** en la ubicación de almacén especificada. De manera predeterminada, es `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>Atributo customCertificateValidator  
  
|Value|Descripción|  
|-----------|-----------------|  
|String|Especifica el nombre de tipo y el ensamblado y otros datos utilizados para buscar el tipo.|  
  
## <a name="certificatevalidationmode-attribute"></a>Atributo certificateValidationMode  
  
|Value|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los valores siguientes: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>Atributo revocationMode  
  
|Value|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los valores siguientes: NoCheck, Online, Offline.<br /><br /> Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>Atributo trustedStoreLocation  
  
|Value|Descripción|  
|-----------|-----------------|  
|Enumeración|Uno de los valores siguientes: LocalMachine o CurrentUser. El valor predeterminado es CurrentUser. Si la aplicación cliente se está ejecutando bajo una cuenta del sistema, entonces el certificado está normalmente en LocalMachine. Si la aplicación cliente se está ejecutando en una cuenta de usuario, entonces el certificado se encuentra normalmente en CurrentUser.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.|  
  
## <a name="remarks"></a>Observaciones  

 El atributo `certificateValidationMode` de este elemento de configuración especifica el nivel de confianza utilizado para autenticar certificados. De forma predeterminada, el nivel se establece en `ChainTrust`, que especifica que cada certificado debe encontrarse en una jerarquía de certificados que finalizan en una entidad emisora de certificados de confianza en la parte superior de la cadena. Este es el modo más seguro. También puede establecer el valor en `PeerOrChainTrust`, que especifica que los certificados autoemitidos (confianza del mismo nivel) se aceptan, así como los certificados que están en una cadena de confianza. Se utiliza este valor cuando se desarrollan y depuran clientes y servicios porque los certificados autoemitidos no necesitan adquirirse desde una autoridad de confianza. Al implementar un cliente, utilice en su lugar el valor `ChainTrust`. También puede establecer el valor como `Custom` o `None`. Para utilizar el valor `Custom`, también debe establecer el atributo `customCertificateValidator` en un ensamblado y tipo utilizado para validar el certificado. Para crear su propio validador personalizado, debe heredar a partir de la clase abstracta X509CertificateValidator. Para obtener más información, consulte [Cómo: crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 El atributo `revocationMode` especifica cómo se comprueba la revocación de los certificados. El valor predeterminado es `online` que indica que se comprobará automáticamente la revocación de los certificados. Para obtener más información, consulte [trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo realiza dos tareas: En primer lugar, especifica un certificado de servicio para que el cliente lo utilice al comunicarse con puntos de conexión cuyo nombre de dominio está `www.contoso.com` por encima del protocolo http. En segundo lugar, especifica el modo de revocación y ubicación del almacén utilizado durante la autenticación.  
  
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
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Procedimiento para crear un servicio que emplee un validador de certificado personalizado](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
