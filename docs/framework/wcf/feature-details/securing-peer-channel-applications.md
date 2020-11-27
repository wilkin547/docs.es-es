---
title: Protección de las aplicaciones de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: d4a0311d-3f78-4525-9c4b-5c93c4492f28
ms.openlocfilehash: 21bec1279d0f0172aa0e8acbcc05adf30a97c5b9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288429"
---
# <a name="securing-peer-channel-applications"></a>Protección de las aplicaciones de canal del mismo nivel

Al igual que otros enlaces en WinFX, `NetPeerTcpBinding` tiene la seguridad habilitada de forma predeterminada y ofrece seguridad basada en mensajes y en transporte (o ambos). En este tema se tratan estos dos tipos de seguridad. La etiqueta de modo de seguridad especifica el tipo de seguridad en la especificación de enlace (<xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>`Mode`).  
  
## <a name="transport-based-security"></a>Seguridad basada en el transporte.  

 El canal del mismo nivel admite dos tipos de credenciales de autenticación para proteger el transporte, y ambos requieren que se establezca la propiedad `ClientCredentialSettings.Peer` en el `ChannelFactory` asociado:  
  
- Password. Los clientes utilizan una contraseña secreta para autenticar las conexiones. Cuando se utiliza este tipo de credencial, `ClientCredentialSettings.Peer.MeshPassword` debe llevar una contraseña válida y, opcionalmente, una instancia `X509Certificate2`.  
  
- Certificado. Se usa autenticación de aplicación concreta. Cuando se usa este tipo de credencial, debe usar una implementación concreta de <xref:System.IdentityModel.Selectors.X509CertificateValidator> en `ClientCredentialSettings.Peer.PeerAuthentication`.  
  
## <a name="message-based-security"></a>Seguridad basada en mensaje  

 Mediante la seguridad de mensaje, una aplicación puede firmar mensajes salientes para que todas las partes receptoras puedan comprobar que el mensaje ha sido enviado por una parte confiable y que no se ha manipulado. Actualmente, el canal del mismo nivel solo admite la firma de mensajes mediante credenciales X.509.  
  
## <a name="best-practices"></a>Prácticas recomendadas  
  
- En esta sección se analizan los procedimientos recomendados para proteger las aplicaciones de canal del mismo nivel.  
  
### <a name="enable-security-with-peer-channel-applications"></a>Habilitación de la seguridad con aplicaciones de canal del mismo nivel  

 Debido a la naturaleza distribuida de los protocolos de canal del mismo nivel, es difícil imponer la pertenencia a la malla, la confidencialidad y la privacidad en una malla no segura. También es importante recordar proteger la comunicación entre los clientes y el servicio de resolución. Bajo Protocolo de resolución de nombres de mismo nivel (PNRP), use nombres seguros para evitar suplantación y otros ataques comunes. Proteja un servicio de resolución personalizado mediante el permiso de seguridad en las conexiones que el cliente usa para ponerse en contacto con el servicio de resolución,  incluida la seguridad tanto basada en transporte como en mensaje.  
  
### <a name="use-the-strongest-possible-security-model"></a>Use el modelo de seguridad más eficaz posible  

 Por ejemplo, si cada miembro de la malla necesita ser identificado individualmente, utilice el modelo de autenticación basada en certificados. Si eso no es posible, utilice autenticación basada en contraseña teniendo en cuenta las recomendaciones actuales para así poder mantenerlas seguras. Esto incluye compartir contraseñas solo con partes confiables, transmitir contraseñas a través de un medio seguro, cambiar con frecuencia las contraseñas y asegurarse de que las contraseñas sean eficaces (de por lo menos ocho caracteres, entre ellos una letra en minúscula y otra en mayúscula, un dígito y un carácter especial).  
  
### <a name="never-accept-self-signed-certificates"></a>Nunca acepte certificados firmados automáticamente  

 Nunca acepte una credencial de certificado basada en nombres de sujetos. Observe que cualquiera puede crear un certificado, y cualquiera puede elegir un nombre que usted va a validar. Para evitar la posibilidad de suplantación, valide certificados basados en credenciales de autoridades emisoras (un emisor confiable o una entidad de certificados raíz).  
  
### <a name="use-message-authentication"></a>Use autenticación de mensajes  

 Use la autenticación de mensajes para comprobar que un mensaje fue originado por una fuente de confianza y que nadie ha manipulado el mensaje durante la transmisión. Sin la autenticación de mensaje, es fácil que un cliente malintencionado suplante o manipule mensajes en la malla.  
  
## <a name="peer-channel-code-examples"></a>Ejemplos de código del canal del mismo nivel  

 [Escenarios de canal del mismo nivel](peer-channel-scenarios.md)  
  
## <a name="see-also"></a>Vea también

- [Seguridad del canal del mismo nivel](peer-channel-security.md)
- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)
