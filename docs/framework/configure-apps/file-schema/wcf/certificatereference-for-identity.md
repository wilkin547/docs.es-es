---
title: <certificateReference> para <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 93a6290d780ff61756f7315cd0c32f0e199ca00f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849986"
---
# <a name="certificatereference-for-identity"></a>\<> certificateReference para \<> de identidad
Especifica los valores para la validación del certificado X.509. Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen la notificación de identidad utilizada para construir esta identidad.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de identidad**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateReference**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<certificateReference findValue="String"
                      isChainIncluded="Boolean"
                      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                      storeLocation="LocalMachine/CurrentUser"
                      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier">
</certificateReference>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|findValue|Especifica el valor que se va a buscar en el almacén de certificados de X.509 . El tipo contenido en este atributo debe satisfacer los requisitos del valor `X509FindType` especificado. El valor predeterminado es una cadena vacía.|  
|isChainIncluded|Valor de tipo booleano que especifica si la validación se hace mediante una cadena de certificados.|  
|storeLocation|Especifica la ubicación del almacén de certificados que el cliente puede usar para validar el certificado del servidor.<br /><br /> Los valores válidos son los siguientes:<br /><br /> Almacén El almacén de certificados asignado al equipo local.<br />-   CurrentUser: El almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Especifica el nombre del almacén del certificado X.509 que se va a abrir.<br /><br /> Los valores válidos son los siguientes:<br /><br /> Libreta Almacén de certificados para otros usuarios.<br />AuthRoot Almacén de certificados para entidades de certificación (CA) de terceros.<br />CertificateAuthority Almacén de certificados para las CA intermedias.<br />No permitidos Almacén de certificados para los certificados revocados.<br />Telefónica Almacén de certificados para Certificados personales.<br />Raíces Almacén de certificados para entidades de certificación raíz de confianza.<br />TrustedPeople Almacén de certificados para las personas y los recursos de confianza directa.<br />TrustedPublisher Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Especifica el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />- FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identity>](identity.md)|Especifica los valores que permiten la autenticación de un extremo por otros extremos que intercambian mensajes con él.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
