---
title: "&lt;messageSenderAuthentication&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;messageSenderAuthentication&gt;
Especifica los valores de autenticación para el certificado del mismo nivel utilizado por el remitente del mensaje.  
  
## Sintaxis  
  
```  
  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`certificateValidationMode`|Enumeración opcional.  Especifica uno de los cinco modos usados para validar las credenciales.  Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.  Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.|  
|`customCertificateValidatorType`|Cadena opcional.  Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.  Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.  Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona un validador de certificado predeterminado del mismo nivel que comprueba el certificado del mismo nivel con el almacén de personas de confianza.  También comprueba las cadenas de certificados hasta una raíz válida.  Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.|  
|`revocationMode`|Enumeración opcional.  Especifica el modo de revocación de certificados.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.  El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.  Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.  La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.|  
|`trustedStoreLocation`|Enumeración opcional.  Especifica la ubicación del almacén fiable donde el sistema de seguridad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] valida el certificado del mismo nivel.  Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|Especifica las credenciales actuales de un nodo del mismo nivel.|  
  
## Comentarios  
 Se debe configurar este elemento si se elige la autenticación de mensajes.  Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).  Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.  El validador puede aceptar o rechazar la credencial.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Conexión de redes punto a punto](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/es-es/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/es-es/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Protección de las aplicaciones de canal del mismo nivel](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)