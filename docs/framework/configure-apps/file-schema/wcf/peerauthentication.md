---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd18acaf76b2d5ccceb12b62398357b0b1655cb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpeerauthenticationgt"></a>&lt;peerAuthentication&gt;
Especifica los valores de autenticación para un certificado del mismo nivel usado por el remitente del mensaje.  
  
 \<sistema. ServiceModel >  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<serviceCredentials >  
\<punto >  
\<peerAuthentication >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<peerAuthentication  
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
|`certificateValidationMode`|Enumeración opcional. Especifica uno de los tres modos utilizados para validar las credenciales. Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Cadena opcional. Especifica un tipo y ensamblado utilizados para validar un tipo personalizado. Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`. Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona un validador de certificado predeterminado del mismo nivel que comprueba el certificado del mismo nivel con el almacén de personas de confianza. También comprueba las cadenas de certificados hasta una raíz válida. Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.|  
|`revocationMode`|Enumeración opcional. Especifica el modo de revocación de certificados. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>. El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado. Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché. La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.|  
|`trustedStoreLocation`|Enumeración opcional. Especifica la ubicación del almacén fiable donde el sistema de seguridad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] valida el certificado del mismo nivel. Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<punto >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Especifica las credenciales actuales de un nodo del mismo nivel.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>. Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla. Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde. El validador del contestador se invoca para comprobar la credencial de la parte remota. Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Redes de punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Autenticación de mensajes del canal del mismo nivel](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Canal del mismo nivel de autenticación personalizada](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Proteger las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
