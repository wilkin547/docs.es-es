---
title: <certificateReference> para <identity>
ms.date: 03/30/2017
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
ms.openlocfilehash: 44bfb2fd77c4f4db6f7fede296b1cdb74e8d5e7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351949"
---
# <a name="certificatereference-for-identity"></a>\<certificateReference > para \<identity >
Especifica los valores para la validación del certificado X.509. Un cliente de Windows Communication Foundation (WCF) seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen la notificación de identidad utilizada para construir esta identidad.  
  
 \<identity>  
\<certificateReference>  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|findValue|Especifica el valor que se va a buscar en el almacén de certificados de X.509 . El tipo contenido en este atributo debe satisfacer los requisitos del valor `X509FindType` especificado. El valor predeterminado es una cadena vacía.|  
|isChainIncluded|Valor de tipo booleano que especifica si la validación se hace mediante una cadena de certificados.|  
|storeLocation|Especifica la ubicación del almacén de certificados que el cliente puede usar para validar el certificado del servidor.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -LocalMachine: El almacén de certificados asignado al equipo local.<br />-   CurrentUser: El almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
|storeName|Especifica el nombre del almacén del certificado X.509 que se va a abrir.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   AddressBook: Almacén de certificados para otros usuarios.<br />-AuthRoot: Almacén de certificados para entidades de certificación de terceros (CAs).<br />-   CertificateAuthority: Almacén de certificados para entidades de certificación intermedias.<br />-No permitido: Almacén de certificados para los certificados revocados.<br />-Mi: Almacén de certificados para los certificados personales.<br />-Raíz: Almacén de certificados de CA raíz de confianza.<br />-TrustedPeople: Almacén de certificados de personas de confianza directa y recursos.<br />-   TrustedPublisher: Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreName>.|  
|X509FindType|Especifica el tipo de búsqueda de X.509 que se va a ejecutar. El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.<br /><br /> Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509FindType>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica los valores que permiten la autenticación de un extremo por otros extremos que intercambian mensajes con él.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.CertificateReferenceElement>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
