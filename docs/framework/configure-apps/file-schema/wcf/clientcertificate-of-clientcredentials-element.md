---
description: 'Más información sobre: <clientCertificate> del <clientCredentials> elemento'
title: <clientCertificate> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 4305b94e62c76436a6bce91251049b3eebd2db2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638839"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<clientCertificate> del \<clientCredentials> elemento

Define un certificado X.509 que se usa para autenticar un cliente en un servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509. El tipo contenido en el atributo debe satisfacer los requisitos del valor del atributo `X509FindType`. El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del certificado X.509 que usa el cliente para autenticarse al servicio. Los valores válidos incluyen los siguientes:<br /><br /> -LocalMachine: el almacén de certificados asignado al equipo local.<br />-CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a buscar. Los valores válidos incluyen los siguientes:<br /><br /> -AddressBook: almacén de certificados para otros usuarios.<br />-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.<br />-CertificateAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.<br />-No permitido: almacén de certificados para los certificados revocados.<br />-Mi: almacén de certificados para Certificados personales.<br />-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.<br />-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Define el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos de este atributo. Los valores válidos incluyen los siguientes:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />- FindByIssuerName<br />- FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />- FindByTimeValid<br />- FindByTimeNotYetValid<br />- FindByTemplateName<br />- FindByApplicationPolicy<br />- FindByCertificatePolicy<br />- FindByExtension<br />- FindByKeyUsage<br />- FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
  
## <a name="remarks"></a>Observaciones  

 Este elemento de configuración especifica que el certificado utilizado para autenticar el cliente con este elemento. Para obtener más información, vea [Cómo: especificar valores de credencial de cliente](../../../wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Procedimiento para especificar valores de credenciales de cliente](../../../wcf/how-to-specify-client-credential-values.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
