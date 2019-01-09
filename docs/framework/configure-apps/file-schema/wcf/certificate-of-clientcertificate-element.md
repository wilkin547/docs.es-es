---
title: '&lt;certificate&gt; del elemento &lt;clientCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 784fd818c7225a0f1d87ccde72e04471b92b5308
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147153"
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a>&lt;certificate&gt; del elemento &lt;clientCertificate&gt;
Especifica un certificado X.509 usado para firmar y cifrar mensajes.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<clientCertificate >  
\<certificado >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509. El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado. El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor. Los valores válidos son los siguientes:<br /><br /> -LocalMachine: almacén de certificados asignado al equipo local.<br />-CurrentUser: almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a abrir. Los valores válidos son los siguientes:<br /><br /> -Libreta de direcciones: Almacén de certificados para otros usuarios.<br />-AuthRoot: Almacén de certificados para entidades de certificación de terceros (CAs).<br />-CertificationAuthority: Almacén de certificados para entidades de certificación intermedias (CAs).<br />-No permitido: Almacén de certificados para los certificados revocados.<br />-Mi: Almacén de certificados para los certificados personales.<br />-Raíz: Almacén de certificados para entidades de certificación raíz de confianza (CA).<br />-TrustedPeople: Almacén de certificados de personas de confianza directa y recursos.<br />-TrustedPublisher: Almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.|  
|`X509FindType`|Define el tipo de búsqueda de X.509 que se va a ejecutar. Los valores válidos son los siguientes:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-   FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-FindBySubjectKeyIdentifier<br /><br /> El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<certificate>` se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente. Esto se produce al utilizar el patrón de comunicación dúplex. En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente. Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente. Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento. Para obtener más información sobre los servicios dúplex, vea [Cómo: Crear un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente especifica cómo buscar un certificado X.509 adecuado y un tipo de validación personalizado en el elemento `<authentication>`.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Cómo: Crear un servicio que emplee un validador de certificado personalizada](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
