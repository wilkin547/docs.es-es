---
title: Información general sobre seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
ms.openlocfilehash: 1e551572fa6d94e9fd1170eb7e3b258f2e8fb926
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728893"
---
# <a name="windows-communication-foundation-security-overview"></a>Información general sobre seguridad de Windows Communication Foundation
Windows Communication Foundation (WCF) es una plataforma de programación distribuida basada en mensajes SOAP, y la protección de los mensajes entre clientes y servicios es esencial para proteger los datos. WCF proporciona una plataforma versátil e interoperable para intercambiar mensajes seguros basados en la infraestructura de seguridad existente y en los estándares de seguridad reconocidos para los mensajes SOAP.  
  
> [!NOTE]
> Para obtener una guía completa sobre la seguridad de WCF, consulte la [Guía de seguridad de WCF](https://archive.codeplex.com/?p=WCFSecurity).  
  
 WCF usa conceptos que resultan familiares si ha creado aplicaciones seguras y distribuidas con tecnologías existentes, como HTTPS, seguridad integrada de Windows, o nombres de usuario y contraseñas para autenticar a los usuarios. WCF no solo se integra con las infraestructuras de seguridad existentes, sino que también extiende la seguridad distribuida más allá de los dominios solo de Windows mediante mensajes SOAP seguros. Considere WCF una implementación de los mecanismos de seguridad existentes con la principal ventaja de usar SOAP como protocolo, además de los protocolos existentes. Por ejemplo, las credenciales que identifican un cliente o un servicio, como el nombre de usuario y la contraseña, o los certificados X.509, poseen perfiles SOAP interoperables basados en XML. Con estos perfiles, los mensajes se intercambian de manera segura beneficiándose de especificaciones abiertas como las firmas digitales XML y el cifrado XML. Para obtener una lista de especificaciones, consulte [protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Otro paralelismo es el modelo de objetos componentes (COM) de la plataforma de Windows, que habilita aplicaciones seguras y distribuidas. COM tiene un mecanismo de seguridad completo en el que el contexto de seguridad puede fluir entre los componentes; este mecanismo exige integridad, confidencialidad y autenticación. Sin embargo, COM no habilita la mensajería multiplataforma y segura, como hace WCF. Con WCF, puede compilar servicios y clientes que abarcan desde dominios de Windows a través de Internet. Los mensajes interoperables de WCF son esenciales para crear servicios dinámicos orientados al negocio que le ayuden a sentirse tranquilo en la seguridad de su información.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Ventajas de la seguridad de Windows Communication Foundation  
 WCF es una plataforma de programación distribuida basada en mensajes SOAP. Con WCF, puede crear aplicaciones que funcionen como servicios y clientes de servicio, creando y procesando mensajes de un número ilimitado de otros servicios y clientes. En este tipo de aplicación distribuida, los mensajes pueden fluir de nodo a nodo, a través de firewalls, hacia Internet, y a través de los numerosos intermediarios SOAP. Esto introduce una gran variedad de amenazas del modo de seguridad. En los ejemplos siguientes se muestran algunas amenazas comunes que la seguridad de WCF puede ayudar a mitigar al intercambiar mensajes entre entidades:  
  
- Observación del tráfico de red para obtener información confidencial. Por ejemplo, en un escenario de banca electrónica, un cliente solicita la transferencia de fondos desde una cuenta a otra. Un usuario malintencionado intercepta el mensaje y, como tiene el número de cuenta y la contraseña, más tarde realiza una transferencia de fondos desde la cuenta expuesta al peligro.  
  
- Entidades deshonestas que actúan como servicios sin conocimiento del cliente. En este escenario, un usuario malintencionado (el deshonesto) actúa como servicio en línea e intercepta los mensajes del cliente para obtener información confidencial. A continuación, el usuario deshonesto utiliza los datos robados para transferir fondos de la cuenta expuesta al peligro. Este ataque también se conoce como *ataque de suplantación de identidad (phishing)* .  
  
- Alteración de mensajes para obtener un resultado diferente al previsto por el autor de la llamada. Por ejemplo, modificar el número de cuenta en el que se realiza un depósito desvía los fondos a una cuenta deshonesta.  
  
- Una acción por la que un molesto pirata informático reproduce el mismo pedido de compra. Por ejemplo, una librería en línea recibe centenares de pedidos y envía los libros a un cliente que no los ha pedido.  
  
- Incapacidad de un servicio para autenticar un cliente. En este caso, el servicio no puede garantizar que el rol adecuado realizó la transacción.  
  
 Resumiendo, la seguridad de la transferencia proporciona las siguientes garantías:  
  
- Autenticación del punto de conexión de servicio (autor de la respuesta).  
  
- Autenticación de la entidad de seguridad de cliente (iniciador).  
  
- Integridad del mensaje.  
  
- Confidencialidad del mensaje.  
  
- Detección de la reproducción.  
  
### <a name="integration-with-existing-security-infrastructures"></a>Integración con infraestructuras de seguridad existentes  
 A menudo, las implementaciones del servicio Web cuentan con soluciones de seguridad, por ejemplo, la capa de sockets seguros (SSL) o el protocolo Kerberos. Algunas aprovechan una infraestructura de seguridad que ya se ha implementado, como los dominios de Windows que utilizan Active Directory. Con frecuencia es necesario integrar estas tecnologías existentes mientras se evalúan y adoptan otras más recientes.  
  
 La seguridad de WCF se integra con los modelos de seguridad de transporte existentes y puede aprovechar la infraestructura existente para los modelos de seguridad de transferencia más recientes basados en la seguridad del mensaje SOAP.  
  
### <a name="integration-with-existing-authentication-models"></a>Integración con modelos de autenticación existentes  
 Una parte importante de cualquier modelo de seguridad de la comunicación es la capacidad para identificar y autenticar las entidades en comunicación. Estas entidades de la comunicación utilizan "identidades digitales", o credenciales, para su autenticación con los pares con los que se comunican. Dada la evolución de las plataformas de comunicación distribuidas, se han implementado varios modelos relacionados con la seguridad y de autenticación de credenciales. Por ejemplo, en Internet, es habitual el uso de un nombre de usuario y contraseña para identificar a los usuarios. En la intranet, es cada vez más frecuente el uso de un controlador de dominio de Kerberos para hacer una copia de seguridad de la autenticación del servicio y el usuario. En determinados escenarios, como entre dos socios empresariales, los certificados pueden utilizarse para la autenticación mutua de los socios.  
  
 Así, en el mundo de los servicios web, en el que el mismo servicio puede exponerse tanto a clientes corporativos internos como a socios externos o clientes de Internet, es importante que la infraestructura proporcione la integración con estos modelos de autenticación de seguridad existentes. La seguridad de WCF admite una amplia variedad de tipos de credenciales (modelos de autenticación), entre los que se incluyen:  
  
- Autor de la llamada anónimo.  
  
- Credencial de cliente de nombre de usuario.  
  
- Credencial de cliente de certificado.  
  
- Windows (protocolo Kerberos y NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Normas e interoperabilidad  
 En un mundo en el que existen grandes implementaciones, la homogeneidad no es frecuente. Las plataformas informáticas/de comunicación distribuidas necesitan interoperar con las tecnologías que ofrecen los diferentes proveedores. Del mismo modo, la seguridad también debe ser interoperable.  
  
 Para habilitar los sistemas de seguridad interoperables, las compañías activas en la industria de los servicios Web han creado diversas normas. En lo que se refiere a la seguridad, se han propuesto normas importantes: WS-Security: seguridad de Mensaje SOAP (aceptado por las normas OASIS y conocido anteriormente como WS-Security), WS-Trust, WS-SecureConversation, y WS-SecurityPolicy.  
  
 WCF admite una amplia variedad de escenarios de interoperabilidad. La clase <xref:System.ServiceModel.BasicHttpBinding> está destinada al perfil de seguridad básico (BSP), y la clase <xref:System.ServiceModel.WSHttpBinding> está destinada a las normas de seguridad más recientes, como WS-Security 1.1 y WS-SecureConversation. Al cumplir estos estándares, la seguridad de WCF puede interoperar e integrarse con los servicios web que se hospedan en sistemas operativos y plataformas distintos de Microsoft Windows.  
  
## <a name="wcf-security-functional-areas"></a>Áreas funcionales de la seguridad de WCF  
 La seguridad de WCF se divide en tres áreas funcionales: transferencia de seguridad, control de acceso y auditoría. Las siguientes secciones describen brevemente estas áreas y ofrecen vínculos en los que obtener más información.  
  
### <a name="transfer-security"></a>Seguridad de la transferencia  
 La seguridad de la transferencia abarca tres funciones de seguridad principales: integridad, confidencialidad y autenticación. La *integridad* es la capacidad de detectar si un mensaje ha sido alterado. La *confidencialidad* es la capacidad de mantener un mensaje ilegible para cualquier persona que no sea el destinatario previsto; Esto se logra a través de la criptografía. La *autenticación* es la capacidad de comprobar una identidad reclamada. Juntas, estas tres funciones contribuyen a garantizar que los mensajes llegan de manera segura de un punto a otro.  
  
#### <a name="transport-and-message-security-modes"></a>Modos de seguridad de transporte y de mensaje  
 Se usan dos mecanismos principales para implementar la seguridad de transferencia en WCF: el modo de seguridad de *transporte* y el modo de seguridad de *mensajes* .  
  
- El *modo de seguridad de transporte* utiliza un protocolo de nivel de transporte, como https, para lograr la seguridad de la transferencia. El modo de transporte tiene la ventaja de estar ampliamente adoptado, disponible en muchas plataformas y ser menos complejo desde el punto de vista informático. Sin embargo, tiene la desventaja de que solo protege los mensajes punto a punto.  
  
- El *modo de seguridad de mensajes*, por otro lado, utiliza WS-Security (y otras especificaciones) para implementar la seguridad de la transferencia. Dado que la seguridad de mensaje se aplica directamente a los mensajes SOAP, y está incluida en envolturas SOAP junto con los datos de la aplicación, tiene la ventaja de ser independiente del protocolo de transporte, más extensible y de garantizar la seguridad global (frente al protocolo punto a punto). La desventaja es que es mucho más lenta que el modo de seguridad de transporte porque tiene que tratar con la naturaleza XML de los mensajes SOAP.  
  
 Para obtener más información sobre estas diferencias, consulte [protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).  
  
 Un tercer modo de seguridad utiliza los dos modos anteriores y ofrece las ventajas de ambos. Este modo se denomina `TransportWithMessageCredential`. En este modo, se utiliza la seguridad de mensaje para autenticar al cliente, y la seguridad de transporte para la autenticar el servidor y proporcionar confidencialidad e integridad al mensaje. Gracias a esto, el modo de seguridad `TransportWithMessageCredential` es casi tan rápido como el modo de seguridad de transporte y proporciona la misma extensibilidad de autenticación del cliente que el modo de seguridad. No obstante, a diferencia del modo de seguridad de mensaje, no proporciona seguridad completa de extremo a otro.  
  
### <a name="access-control"></a>Control de acceso  
 El *control de acceso* también se conoce como autorización. La *autorización* permite a distintos usuarios tener privilegios diferentes para ver los datos. Por ejemplo, dado que los archivos de recursos humanos de una compañía contienen datos confidenciales de los empleados, solo los administradores pueden consultar estos datos. Lo que es más, los administradores solo pueden consultar datos para sus informes directos. En este caso, el control de acceso está basado tanto en la función ("administrador"), como en la identidad específica del administrador (para evitar que un administrador examine los registros de los empleados de otro administrador).  
  
 En WCF, las características de control de acceso se proporcionan a través de la integración con el <xref:System.Security.Permissions.PrincipalPermissionAttribute> de Common Language Runtime (CLR) y a través de un conjunto de API conocidas como *modelo de identidad*. Para obtener más información sobre el control de acceso y la autorización basada en notificaciones, vea [ampliar la seguridad](../../../../docs/framework/wcf/extending/extending-security.md).  
  
### <a name="auditing"></a>Auditoría  
 La *Auditoría* es el registro de eventos de seguridad en el registro de eventos de Windows. Pueden registrarse eventos relacionados con la seguridad, como autenticaciones con errores (o correctas). Para obtener más información, consulte [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md). Para obtener información sobre la programación, consulte [Cómo: auditar eventos de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)
- [Escenarios de seguridad comunes](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
- [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Orientación de seguridad y procedimientos recomendados](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [Configuración de servicios mediante archivos de configuración](../../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Información general sobre la creación de puntos finales](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Extensión de la seguridad](../../../../docs/framework/wcf/extending/extending-security.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
