---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 118159617a7f4c27ecc5e8fe077c28cfefac8537
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397612"
---
# \<peerAuthentication>
Especifica los valores de autenticación para un certificado del mismo nivel usado por el remitente del mensaje.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`certificateValidationMode`|Enumeración opcional. Especifica uno de los tres modos utilizados para validar las credenciales. Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Cadena opcional. Especifica un tipo y ensamblado utilizados para validar un tipo personalizado. Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`. Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) proporciona un validador de certificado del mismo nivel predeterminado que comprueba el certificado del mismo nivel con el almacén de personas de confianza. También comprueba las cadenas de certificados hasta una raíz válida. Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.|  
|`revocationMode`|Enumeración opcional. Especifica el modo de revocación de certificados. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado. Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché. La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.|  
|`trustedStoreLocation`|Enumeración opcional. Especifica la ubicación del almacén de confianza donde el sistema de seguridad de WCF valida el certificado del mismo nivel. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|Especifica las credenciales actuales de un nodo del mismo nivel.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>. Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla. Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde. El validador del contestador se invoca para comprobar la credencial de la parte remota. Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Trabajar con certificados](../../../wcf/feature-details/working-with-certificates.md)
- [Conexión de redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Protección de las aplicaciones de canal del mismo nivel](../../../wcf/feature-details/securing-peer-channel-applications.md)
