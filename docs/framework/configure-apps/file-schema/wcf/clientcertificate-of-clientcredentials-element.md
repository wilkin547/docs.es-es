---
title: <clientCertificate>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 3450df921da8c72a555c2faf424c51e0063cb235
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926108"
---
# <a name="clientcertificate-of-clientcredentials-element"></a>\<clientCertificate > del \<elemento > clientCredentials
Define un certificado X.509 que se usa para autenticar un cliente en un servicio.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<clientCredentials>  
\<clientCertificate>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509. El tipo contenido en el atributo debe satisfacer los requisitos del valor del atributo `X509FindType`. El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del certificado X.509 que usa el cliente para autenticarse al servicio. Los valores válidos son los siguientes:<br /><br /> -LocalMachine: el almacén de certificados asignado al equipo local.<br />-CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a buscar. Los valores válidos son los siguientes:<br /><br /> Libreta Almacén de certificados para otros usuarios.<br />AuthRoot Almacén de certificados para entidades de certificación (CA) de terceros.<br />CertificateAuthority Almacén de certificados para las entidades de certificación (CA) intermedias.<br />No permitidos Almacén de certificados para los certificados revocados.<br />Telefónica Almacén de certificados para Certificados personales.<br />Raíces Almacén de certificados para entidades de certificación (CA) raíz de confianza.<br />TrustedPeople Almacén de certificados para las personas y los recursos de confianza directa.<br />TrustedPublisher Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Define el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos de este atributo. Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />- FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración especifica que el certificado utilizado para autenticar el cliente con este elemento. Para obtener más información, consulte [Cómo Especifique los valores](../../../wcf/how-to-specify-client-credential-values.md)de credencial de cliente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Cómo: Especificar valores de credencial de cliente](../../../wcf/how-to-specify-client-credential-values.md)
- [Protección de clientes](../../../wcf/securing-clients.md)
- [Trabajo con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
