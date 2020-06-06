---
title: <certificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400551"
---
# <a name="certificate-element"></a>\<certificate> (Elemento)
Especifica un certificado X.509 que se va a usar para firmar y cifrar los mensajes para los clientes punto a punto.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`findValue`|Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509. El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado. El valor predeterminado es una cadena vacía.|  
|`storeLocation`|Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual. Los valores válidos incluyen los siguientes:<br /><br /> -LocalMachine: el almacén de certificados asignado al equipo local.<br />-CurrentUser: el almacén de certificados asignado al usuario actual.<br /><br /> El valor predeterminado es LocalMachine.|  
|`storeName`|Especifica el nombre del almacén del certificado X.509 que se va a abrir. Los valores válidos incluyen los siguientes:<br /><br /> -AddressBook: almacén de certificados para otros usuarios.<br />-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.<br />-CertificateAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.<br />-No permitido: almacén de certificados para los certificados revocados.<br />-Mi: almacén de certificados para Certificados personales.<br />-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.<br />-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.<br />-TrustedPublisher: almacén de certificados para publicadores de confianza directa.<br /><br /> El valor predeterminado es My.|  
|`X509FindType`|Define el tipo de búsqueda de X.509 que se va a ejecutar. Los valores válidos incluyen los siguientes:<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />- FindByIssuerName<br />- FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />- FindByTimeValid<br />- FindByTimeNotYetValid<br />- FindByTemplateName<br />- FindByApplicationPolicy<br />- FindByCertificatePolicy<br />- FindByExtension<br />- FindByKeyUsage<br />- FindBySubjectKeyIdentifier<br /><br /> El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.<br /><br /> El valor predeterminado es FindBySubjectDistinguishedName.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|Especifica las credenciales usadas al autenticar clientes punto a punto.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración contiene una instancia de X509Certificate2 que se usa al autenticar a los vecinos en la malla del mismo nivel.  
  
 Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente especifica cómo buscar el certificado usado en un escenario punto a punto.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Conexión de redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Protección de las aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md)
