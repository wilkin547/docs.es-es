---
title: '&lt;messageSenderAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: 656543ee1908c8fa332e373863aa4dc7ddecaba7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagesenderauthenticationgt"></a>&lt;messageSenderAuthentication&gt;
Especifica los valores de autenticación para el certificado del mismo nivel utilizado por el remitente del mensaje.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<punto >  
\<messageSenderAuthentication >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`certificateValidationMode`|Enumeración opcional. Especifica uno de los cinco modos usados para validar las credenciales. Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Cadena opcional. Especifica un tipo y ensamblado utilizados para validar un tipo personalizado. Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`. Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Windows Communication Foundation (WCF) proporciona un predeterminado del mismo nivel validador de certificado que comprueba el certificado del mismo nivel con el almacén de personas de confianza. También comprueba las cadenas de certificados hasta una raíz válida. Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.|  
|`revocationMode`|Enumeración opcional. Especifica el modo de revocación de certificados. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado. Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché. La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.|  
|`trustedStoreLocation`|Enumeración opcional. Especifica la ubicación del almacén fiable donde el sistema de seguridad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] valida el certificado del mismo nivel. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<punto >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Especifica las credenciales actuales de un nodo del mismo nivel.|  
  
## <a name="remarks"></a>Comentarios  
 Se debe configurar este elemento si se elige la autenticación de mensajes. Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md). Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento. El validador puede aceptar o rechazar la credencial.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [Trabajo con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Autenticación de mensajes del canal del mismo nivel](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Canal del mismo nivel de autenticación personalizada](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
