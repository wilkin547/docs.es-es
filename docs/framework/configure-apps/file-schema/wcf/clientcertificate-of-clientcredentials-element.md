---
title: '&lt;clientCertificate&gt; de &lt;clientCredentials&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: f6dbc2c7d43558d86f74468adbc7026e8462812c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147946"
---
# <a name="ltclientcertificategt-of-ltclientcredentialsgt-element"></a>&lt;clientCertificate&gt; de &lt;clientCredentials&gt; (elemento)
Define un certificado X.509 que se usa para autenticar un cliente en un servicio.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors >  
\<comportamiento >  
\<clientCredentials >  
\<clientCertificate >  
  
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
|`storeLocation`|Especifica la ubicación del certificado X.509 que usa el cliente para autenticarse al servicio. Los valores válidos son los siguientes:<br /><br /> -LocalMachine: almacén de certificados asignado al equipo local.<br />-CurrentUser: almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a buscar. Los valores válidos son los siguientes:<br /><br /> -Libreta de direcciones: Almacén de certificados para otros usuarios.<br />-AuthRoot: Almacén de certificados para entidades de certificación de terceros (CAs).<br />-CertificateAuthority: Almacén de certificados intermedios de certificación (CA).<br />-No permitido: Almacén de certificados para los certificados revocados.<br />-Mi: Almacén de certificados para los certificados personales.<br />-Raíz: Almacén de certificados entidades emisoras de certificados raíz de confianza (CA).<br />-TrustedPeople: Almacén de certificados de personas de confianza directa y recursos.<br />-TrustedPublisher: Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Define el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos de este atributo. Los valores válidos son los siguientes:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-   FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración especifica que el certificado utilizado para autenticar el cliente con este elemento. Para obtener más información, vea [Cómo: Especificar los valores de credencial de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Cómo: Especificar los valores de credencial de cliente](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)  
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
