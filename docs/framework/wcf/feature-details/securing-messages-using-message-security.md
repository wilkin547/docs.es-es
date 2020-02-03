---
title: Protección de mensajes mediante la seguridad de mensajes
ms.date: 03/30/2017
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
ms.openlocfilehash: a6b062d0d6a74ce2a2ff9afa7e8a0a18853dbd22
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746448"
---
# <a name="securing-messages-using-message-security"></a>Protección de mensajes mediante la seguridad de mensajes
En esta sección se describe la seguridad de los mensajes de WCF cuando se usa <xref:System.ServiceModel.NetMsmqBinding>.  
  
> [!NOTE]
> Antes de leer este tema, se recomienda leer los conceptos de [seguridad](../../../../docs/framework/wcf/feature-details/security-concepts.md).  
  
 En la ilustración siguiente se proporciona un modelo conceptual de comunicación en cola mediante WCF. Esta ilustración y la terminología se utilizan para explicar  
  
 los conceptos de seguridad de transporte.  
  
 ![Diagrama de aplicaciones en cola](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Al enviar mensajes en cola mediante WCF, el mensaje de WCF se adjunta como cuerpo del mensaje de Message Queuing (MSMQ). Aunque la seguridad de transporte protege el mensaje de MSMQ completo, la seguridad de mensajes (o SOAP) solo protege el cuerpo del mensaje de MSMQ.  
  
 El concepto clave de la seguridad de mensajes es que el cliente protege el mensaje para la aplicación receptora (servicio), a diferencia de la seguridad de transporte donde el cliente protege el mensaje para la cola de destino. Como tal, MSMQ no juega ninguna parte al proteger el mensaje de WCF mediante la seguridad del mensaje.  
  
 La seguridad de mensajes de WCF agrega encabezados de seguridad al mensaje de WCF que se integran con las infraestructuras de seguridad existentes, como un certificado o el protocolo Kerberos.  
  
## <a name="message-credential-type"></a>Tipo de credencial de mensaje  
 Utilizando la seguridad de mensajes, el servicio y cliente pueden presentar las credenciales para autenticarse entre sí. Puede seleccionar la seguridad de mensajes estableciendo el modo <xref:System.ServiceModel.NetMsmqBinding.Security%2A> en `Message` o `Both` (es decir, utilizar la seguridad de transporte y la seguridad de mensajes).  
  
 El servicio puede utilizar la propiedad <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> para inspeccionar la credencial utilizada para autenticar el cliente. Esto también se puede utilizar para comprobaciones de autorización que el servicio decida implementar.  
  
 Esta sección explica los diferentes tipos de credenciales y cómo utilizarlos con colas.  
  
### <a name="certificate"></a>Certificado  
 El tipo de credencial de certificado utiliza un certificado X.509 para identificar el servicio y el cliente.  
  
 En un escenario típico, una entidad de certificación de confianza emite un certificado válido para el cliente y el servicio. A continuación, se establece la conexión, el cliente autentica la validez del servicio utilizando el certificado del servicio para decidir si puede confiar en el servicio. De forma similar, el servicio utiliza el certificado del cliente para validar la confianza del cliente.  
  
 Teniendo en cuenta la naturaleza desconectada de las colas, es posible que el cliente y el servicio no estén en línea al mismo tiempo. Como tales, el cliente y servicio tienen que intercambiar certificados fuera de banda. En particular, el cliente, en virtud de guardar el certificado del servicio (que se puede encadenar a una entidad de certificación) en su almacén de confianza, debe confiar en que se está comunicando con el servicio correcto. Para autenticar el cliente, el servicio utiliza el certificado X.509 adjunto con el mensaje para compararlo con el certificado en su almacén y verificar la autenticidad del cliente. De nuevo, el certificado se debe encadenar a una entidad de certificación.  
  
 En un equipo que ejecuta Windows, los certificados se conservan en varias clases de almacenes. Para obtener más información sobre los diferentes almacenes, vea [almacenes de certificados](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
### <a name="windows"></a>Windows  
 El tipo de credencial de mensaje de Windows utiliza el protocolo Kerberos.  
  
 El protocolo Kerberos es un mecanismo de seguridad que autentica a los usuarios en un dominio y permite a los usuarios autenticados establecer contextos seguros con otras entidades en un dominio.  
  
 El problema con el uso del protocolo Kerberos para la comunicación en cola es que las etiquetas que contienen identidad del cliente que el Centro de distribución de claves (KDC) distribuye son relativamente efímeras. Una *duración* está asociada al vale de Kerberos que indica la validez del vale. Como tal, aunque la latencia sea elevada, no puede estar seguro de que el token todavía sea válido para el servicio que autentica el cliente.  
  
 Tenga en cuenta que al utilizar este tipo de credencial, el servicio se debe estar ejecutando bajo la cuenta del servicio.  
  
 Se utiliza el protocolo Kerberos de forma predeterminada al elegir la credencial del mensaje.
  
### <a name="username-password"></a>Nombre de usuario/contraseña  
 Con esta propiedad, el cliente puede autenticar al servidor utilizando una contraseña y nombre de usuario en el encabezado de seguridad del mensaje.  
  
### <a name="issuedtoken"></a>IssuedToken  
 El cliente puede utilizar el servicio de token de seguridad para emitir un token que se pueda adjuntar al mensaje para el servicio para autenticar el cliente.  
  
## <a name="using-transport-and-message-security"></a>Utilizar la seguridad de transporte y de mensajes  
 Al utilizar la seguridad de transporte y la seguridad de mensajes, el certificado utilizado para proteger el mensaje tanto en el nivel de transporte como en el nivel de mensaje SOAP debe ser el mismo.  
  
## <a name="see-also"></a>Consulte también

- [Protección de mensajes utilizando la seguridad de transporte](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)
- [Seguridad de mensajes mediante Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
- [Conceptos de seguridad](../../../../docs/framework/wcf/feature-details/security-concepts.md)
- [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
