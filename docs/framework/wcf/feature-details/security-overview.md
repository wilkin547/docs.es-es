---
title: Overview1 de seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6aff25547f02458d894de7235ecfb2f704d8664a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="security-overview"></a>Información general sobre seguridad
Windows Communication Foundation (WCF) es una plataforma de programación distribuida de mensaje SOAP y proteger los mensajes entre clientes y servicios es esencial para proteger los datos. WCF proporciona una plataforma versátil e interoperable para intercambiar mensajes seguros en función de la infraestructura de seguridad existente y los estándares reconocidos de seguridad para los mensajes SOAP.  
  
> [!NOTE]
>  Para obtener una guía completa para la seguridad WCF, vea [Guía de seguridad de WCF](http://go.microsoft.com/fwlink/?LinkID=158912).  
  
 WCF usa conceptos que le resultarán familiares si ha creado aplicaciones distribuidas seguras con tecnologías existentes como HTTPS, Windows la seguridad integran, o nombres de usuario y contraseñas para autenticar a los usuarios. WCF no sólo se integra con infraestructuras de seguridad existentes, sino que también extiende la seguridad distribuida más allá de los dominios sólo para Windows mediante el uso de proteger los mensajes SOAP. Considere la posibilidad de WCF una implementación de mecanismos de seguridad existentes con la principal ventaja de utilizar SOAP como protocolo, además de los protocolos existentes. Por ejemplo, las credenciales que identifican un cliente o un servicio, como el nombre de usuario y la contraseña, o los certificados X.509, poseen perfiles SOAP interoperables basados en XML. Con estos perfiles, los mensajes se intercambian de manera segura beneficiándose de especificaciones abiertas como las firmas digitales XML y el cifrado XML. Para obtener una lista de especificaciones, consulte [protocolos de servicios Web admitidos por los enlaces de interoperabilidad proporcionados](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Otro paralelismo es el modelo de objetos componentes (COM) de la plataforma de Windows, que habilita aplicaciones seguras y distribuidas. COM tiene un mecanismo de seguridad completo en el que el contexto de seguridad puede fluir entre los componentes; este mecanismo exige integridad, confidencialidad y autenticación. Sin embargo COM no habilita multiplataforma, como WCF hace de mensajería segura. Usa WCF, puede crear servicios y clientes que se extienden desde dominios de Windows a través de Internet. Los mensajes interoperables de WCF son esenciales para la compilación dinámica, los servicios orientados al negocio que le ayudarán a confiar en la seguridad de la información.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Ventajas de la seguridad de Windows Communication Foundation  
 WCF es una plataforma de programación distribuida basada en mensajes SOAP. Usa WCF, se pueden crear aplicaciones que funcionen como servicios y clientes del servicio, crear y procesar los mensajes de un número ilimitado de otros servicios y clientes. En este tipo de aplicación distribuida, los mensajes pueden fluir de nodo a nodo, a través de firewalls, hacia Internet, y a través de los numerosos intermediarios SOAP. Esto introduce una gran variedad de amenazas del modo de seguridad. Los ejemplos siguientes muestran algunas amenazas comunes que seguridad de WCF puede ayudar a mitigar al intercambiar mensajes entre las entidades:  
  
-   Observación del tráfico de red para obtener información confidencial. Por ejemplo, en un escenario de banca electrónica, un cliente solicita la transferencia de fondos desde una cuenta a otra. Un usuario malintencionado intercepta el mensaje y, como tiene el número de cuenta y la contraseña, más tarde realiza una transferencia de fondos desde la cuenta expuesta al peligro.  
  
-   Entidades deshonestas que actúan como servicios sin conocimiento del cliente. En este escenario, un usuario malintencionado (el deshonesto) actúa como servicio en línea e intercepta los mensajes del cliente para obtener información confidencial. A continuación, el usuario deshonesto utiliza los datos robados para transferir fondos de la cuenta expuesta al peligro. Este ataque también se conoce un *ataque de suplantación de identidad*.  
  
-   Alteración de mensajes para obtener un resultado diferente al previsto por el autor de la llamada. Por ejemplo, modificar el número de cuenta en el que se realiza un depósito desvía los fondos a una cuenta deshonesta.  
  
-   Una acción por la que un molesto pirata informático reproduce el mismo pedido de compra. Por ejemplo, una librería en línea recibe centenares de pedidos y envía los libros a un cliente que no los ha pedido.  
  
-   Incapacidad de un servicio para autenticar un cliente. En este caso, el servicio no puede garantizar que el rol adecuado realizó la transacción.  
  
 Resumiendo, la seguridad de la transferencia proporciona las siguientes garantías:  
  
-   Autenticación del extremo de servicio (autor de la respuesta).  
  
-   Autenticación de la entidad de seguridad de cliente (iniciador).  
  
-   Integridad del mensaje.  
  
-   Confidencialidad del mensaje.  
  
-   Detección de la reproducción.  
  
### <a name="integration-with-existing-security-infrastructures"></a>Integración con infraestructuras de seguridad existentes  
 A menudo, las implementaciones del servicio Web cuentan con soluciones de seguridad, por ejemplo, la capa de sockets seguros (SSL) o el protocolo Kerberos. Algunas aprovechan una infraestructura de seguridad que ya se ha implementado, como los dominios de Windows que utilizan Active Directory. Con frecuencia es necesario integrar estas tecnologías existentes mientras se evalúan y adoptan otras más recientes.  
  
 Seguridad de WCF se integra con los modelos de seguridad de transporte existentes y aprovecha la infraestructura existente para los modelos de seguridad de transferencia más reciente, en función de seguridad del mensaje SOAP.  
  
### <a name="integration-with-existing-authentication-models"></a>Integración con modelos de autenticación existentes  
 Una parte importante de cualquier modelo de seguridad de la comunicación es la capacidad para identificar y autenticar las entidades en comunicación. Estas entidades de la comunicación utilizan "identidades digitales", o credenciales, para su autenticación con los pares con los que se comunican. Dada la evolución de las plataformas de comunicación distribuidas, se han implementado varios modelos relacionados con la seguridad y de autenticación de credenciales. Por ejemplo, en Internet, es habitual el uso de un nombre de usuario y contraseña para identificar a los usuarios. En la intranet, es cada vez más frecuente el uso de un controlador de dominio de Kerberos para hacer una copia de seguridad de la autenticación del servicio y el usuario. En determinados escenarios, como entre dos socios empresariales, los certificados pueden utilizarse para la autenticación mutua de los socios.  
  
 Así, en el mundo de los servicios web, en el que el mismo servicio puede exponerse tanto a clientes corporativos internos como a socios externos o clientes de Internet, es importante que la infraestructura proporcione la integración con estos modelos de autenticación de seguridad existentes. Seguridad de WCF admite una amplia variedad de tipos de credenciales (modelos de autenticación) incluyendo:  
  
-   Autor de la llamada anónimo.  
  
-   Credencial de cliente de nombre de usuario.  
  
-   Credencial de cliente de certificado.  
  
-   Windows (protocolo Kerberos y NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Normas e interoperabilidad  
 En un mundo en el que existen grandes implementaciones, la homogeneidad no es frecuente. Las plataformas informáticas/de comunicación distribuidas necesitan interoperar con las tecnologías que ofrecen los diferentes proveedores. Del mismo modo, la seguridad también debe ser interoperable.  
  
 Para habilitar los sistemas de seguridad interoperables, las compañías activas en la industria de los servicios Web han creado diversas normas. En lo que se refiere a la seguridad, se han propuesto normas importantes: WS-Security: seguridad de Mensaje SOAP (aceptado por las normas OASIS y conocido anteriormente como WS-Security), WS-Trust, WS-SecureConversation, y WS-SecurityPolicy.  
  
 WCF admite una amplia variedad de escenarios de interoperabilidad. La clase <xref:System.ServiceModel.BasicHttpBinding> está destinada al perfil de seguridad básico (BSP), y la clase <xref:System.ServiceModel.WSHttpBinding> está destinada a las normas de seguridad más recientes, como WS-Security 1.1 y WS-SecureConversation. Mediante la adhesión a estas normas, la seguridad de WCF puede interoperar e integrarse con servicios Web que se hospedan en sistemas operativos y plataformas que no sean de Microsoft Windows.  
  
## <a name="wcf-security-functional-areas"></a>Áreas funcionales de la seguridad de WCF  
 Seguridad de WCF se divide en tres áreas funcionales: transferencia de seguridad, control de acceso y auditoría. Las siguientes secciones describen brevemente estas áreas y ofrecen vínculos en los que obtener más información.  
  
### <a name="transfer-security"></a>Seguridad de la transferencia  
 La seguridad de la transferencia abarca tres funciones de seguridad principales: integridad, confidencialidad y autenticación. *Integridad* es la capacidad para detectar si un mensaje se ha alterado. *Confidencialidad* es la capacidad de mantener un mensaje ilegible para cualquiera que no sea el destinatario previsto; Esto se consigue mediante criptografía. *Autenticación* es la capacidad de comprobar una identidad notificada. Juntas, estas tres funciones contribuyen a garantizar que los mensajes llegan de manera segura de un punto a otro.  
  
#### <a name="transport-and-message-security-modes"></a>Modos de seguridad de transporte y de mensaje  
 Se utilizan dos mecanismos principales para implementar la seguridad de transferencia en WCF: *transporte* modo de seguridad y *mensaje* modo de seguridad.  
  
-   *Modo de seguridad de transporte* utiliza un protocolo de nivel de transporte, como HTTPS, para lograr la seguridad de transferencia. El modo de transporte tiene la ventaja de estar ampliamente adoptado, disponible en muchas plataformas y ser menos complejo desde el punto de vista informático. Sin embargo, tiene la desventaja de que solo protege los mensajes punto a punto.  
  
-   *Modo de seguridad de mensaje*, en el otro lado, utiliza WS-Security (y otras especificaciones) para implementar la seguridad de transferencia. Dado que la seguridad de mensaje se aplica directamente a los mensajes SOAP, y está incluida en envolturas SOAP junto con los datos de la aplicación, tiene la ventaja de ser independiente del protocolo de transporte, más extensible y de garantizar la seguridad global (frente al protocolo punto a punto). La desventaja es que es mucho más lenta que el modo de seguridad de transporte porque tiene que tratar con la naturaleza XML de los mensajes SOAP.  
  
 Para obtener más información sobre estas diferencias, vea [protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).  
  
 Un tercer modo de seguridad utiliza los dos modos anteriores y ofrece las ventajas de ambos. Este modo se denomina `TransportWithMessageCredential`. En este modo, se utiliza la seguridad de mensaje para autenticar al cliente, y la seguridad de transporte para la autenticar el servidor y proporcionar confidencialidad e integridad al mensaje. Gracias a esto, el modo de seguridad `TransportWithMessageCredential` es casi tan rápido como el modo de seguridad de transporte y proporciona la misma extensibilidad de autenticación del cliente que el modo de seguridad. No obstante, a diferencia del modo de seguridad de mensaje, no proporciona seguridad completa de extremo a otro.  
  
### <a name="access-control"></a>Control de acceso  
 *Control de acceso* es también conocida como la autorización. *Autorización* permite a los usuarios diferentes tienen privilegios diferentes para ver los datos. Por ejemplo, dado que los archivos de recursos humanos de una compañía contienen datos confidenciales de los empleados, solo los administradores pueden consultar estos datos. Lo que es más, los administradores solo pueden consultar datos para sus informes directos. En este caso, el control de acceso está basado tanto en la función ("administrador"), como en la identidad específica del administrador (para evitar que un administrador examine los registros de los empleados de otro administrador).  
  
 En WCF, características de control de acceso se proporcionan mediante la integración con common language runtime (CLR) <xref:System.Security.Permissions.PrincipalPermissionAttribute> y a través de un conjunto de API conocido como el *modelo de identidad*. Para obtener más información sobre el control de acceso y la autorización basada en notificaciones, consulte [extender seguridad](../../../../docs/framework/wcf/extending/extending-security.md).  
  
### <a name="auditing"></a>Auditoría  
 *Auditoría* es el registro de eventos de seguridad en el registro de eventos de Windows. Pueden registrarse eventos relacionados con la seguridad, como autenticaciones con errores (o correctas). Para obtener más información, consulte [auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md). Para detalles de programación, vea [Cómo: eventos de auditoría de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)  
 [Escenarios de seguridad comunes](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Orientación de seguridad y procedimientos recomendados](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [Configuración de servicios mediante archivos de configuración](../../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Información general sobre la creación de puntos finales](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Extensión de la seguridad](../../../../docs/framework/wcf/extending/extending-security.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
