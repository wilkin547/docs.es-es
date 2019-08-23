---
title: <serviceCertificate> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 36a228da262095bfe05d66c6d44ac73ba0ca401b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936313"
---
# <a name="servicecertificate-of-servicecredentials"></a>\<> serviceCertificate de \<serviceCredentials >
Especifique un certificado X.509 que se vaya a utilizar para autenticar el servicio a los clientes utilizando el modo de seguridad de mensajes.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<serviceCredentials>  
\<serviceCertificate>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509. El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado. El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor. Los valores válidos son los siguientes:<br /><br /> -LocalMachine: el almacén de certificados asignado al equipo local.<br />-CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a abrir. Los valores válidos son los siguientes:<br /><br /> Libreta Almacén de certificados para otros usuarios.<br />AuthRoot Almacén de certificados para entidades de certificación (CA) de terceros.<br />- CertificatAuthority: Almacén de certificados para las entidades de certificación (CA) intermedias.<br />No permitidos Almacén de certificados para los certificados revocados.<br />Telefónica Almacén de certificados para Certificados personales.<br />Raíces Almacén de certificados para entidades de certificación (CA) raíz de confianza.<br />TrustedPeople Almacén de certificados para las personas y los recursos de confianza directa.<br />TrustedPublisher Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.|  
|`x509FindType`|Define el tipo de búsqueda de X.509 que se va a ejecutar. Los valores válidos son los siguientes:<br /><br /> -   FindByThumbprint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />- FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## <a name="remarks"></a>Comentarios  
 Utilice este elemento para especificar un certificado X.509 que se utilizará para autenticar el servicio a los clientes utilizando el modo de seguridad de mensajes. Si está utilizando un certificado que se renovará periódicamente, su huella digital cambiará. En ese caso, utilice el nombre del asunto como el `x509FindType` porque el certificado se puede volver a emitir con el mismo nombre de asunto.  
  
 Para obtener más información acerca del uso del elemento [, consulte Cómo: Especifique los valores](../../../wcf/how-to-specify-client-credential-values.md)de credencial de cliente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [Cómo: Especificar valores de credencial de cliente](../../../wcf/how-to-specify-client-credential-values.md)
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
