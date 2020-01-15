---
title: Seguridad de aplicación distribuida
ms.date: 03/30/2017
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
ms.openlocfilehash: cb271bcf8fb27bae4c8ef6b60df0f8d2940ecb9a
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964820"
---
# <a name="distributed-application-security"></a>Seguridad de aplicación distribuida
La seguridad de Windows Communication Foundation (WCF) se divide en tres áreas funcionales principales: transferencia de seguridad, control de acceso y auditoría. La seguridad de transferencia proporciona integridad, confidencialidad y autenticación. La seguridad de transferencia la proporciona uno de los siguientes elementos: seguridad de transporte, seguridad de mensajes o `TransportWithMessageCredential`.  
  
 Para obtener información general sobre la seguridad de mensajes de WCF, consulte [información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md). Para obtener más información acerca de las otras dos partes de la seguridad de WCF, consulte [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) y [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="transfer-security-scenarios"></a>Escenarios de seguridad de transferencia  
 Entre los escenarios comunes que emplean la seguridad de transferencia de WCF se incluyen los siguientes:  
  
- Transferencia segura mediante Windows. Un cliente y servicio de WCF se implementan en un dominio de Windows (o un bosque de Windows). Los mensajes contienen datos personales, por lo que entre los requisitos se incluye la autenticación mutua de cliente y servicio, la integridad y la confidencialidad de los mensajes. Además, se requiere la prueba de que una transacción determinada se produjo, por ejemplo, el receptor del mensaje debería registrar la información de la firma.  
  
- Transferencia segura mediante `UserName` y HTTPS. Es necesario desarrollar un cliente y un servicio WCF para que funcione a través de Internet. Las credenciales de clientes se autentican frente a una base de datos de pares de nombres de usuario y contraseñas. El servicio se implementa en una dirección HTTPS utilizando un certificado Secure Sockets Layer (SSL) de confianza. Dado que los mensajes viajan a través de Internet, el cliente y servicio deben autenticarse mutuamente y se debe preservar la confidencialidad e integridad de los mensajes durante la transferencia.  
  
- Transferencia segura mediante el uso de certificados. Es necesario desarrollar un servicio y un cliente WCF para que funcione a través de la red pública de Internet. El cliente y el servicio tienen certificados que se pueden utilizar para proteger los mensajes. El cliente y el servicio utilizan Internet para comunicarse entre sí y realizar transacciones de valor alto que requieren integridad del mensaje, confidencialidad y autenticación mutua.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integridad, confidencialidad y autenticación  
 Tres funciones se llaman conjuntamente seguridad de transferencia: integridad, confidencialidad y autenticación. La seguridad de transferencia proporciona funciones que ayudan a mitigar las amenazas para una aplicación distribuida. La siguiente tabla describe brevemente las tres funciones que constituyen la seguridad de transferencia.  
  
|Función|Descripción|  
|--------------|-----------------|  
|Integridad|La *integridad* es la garantía de que los datos están completos y son precisos, especialmente después de que se hayan recorrido de un punto a otro y, posiblemente, sean leídos por muchos actores. La integridad debe mantenerse para evitar la modificación de los datos y normalmente se logra mediante la firma digital de un mensaje.|  
|Confidencialidad|La *confidencialidad* es la garantía de que un mensaje no se ha leído por ningún usuario que no sea el lector previsto. Por ejemplo, un número de tarjeta de crédito se debe mantener de manera confidencial al enviarse a través de Internet. La confidencialidad es a menudo proporcionada por el cifrado de datos utilizando un esquema de clave pública/privada.|  
|Autenticación|La *autenticación* es la comprobación de una identidad reclamada. Por ejemplo, al utilizar una cuenta bancaria, es imperativo que solo el propietario real de la cuenta pueda retirar los fondos. Diversos recursos pueden proporcionar la autenticación. Un método común es el sistema de usuario/contraseña. Otro método consiste en el uso de un certificado X.509 proporcionado por un tercero.|  
  
## <a name="security-modes"></a>Modos de seguridad  
 WCF tiene varios modos de seguridad de transferencia, que se describen en la tabla siguiente.  
  
|Modo|Descripción|  
|----------|-----------------|  
|Ninguno|No se proporciona ninguna seguridad en el nivel de transporte o en el nivel del mensaje. Ninguno de los enlaces predefinidos utiliza este modo de forma predeterminada excepto el elemento [\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) o, cuando se usa código, la clase <xref:System.ServiceModel.BasicHttpBinding>.|  
|Transport|Utiliza un transporte seguro como HTTPS para la integridad, confidencialidad y autenticación mutua.|  
|Mensaje|Utiliza seguridad del mensaje SOAP para la integridad, confidencialidad y autenticación mutua. Los mensajes SOAP se protegen según los estándares de WS-Security.|  
|Modo mixto|Utiliza la seguridad de transporte para la integridad, confidencialidad y autenticación de servidor. Utiliza la seguridad de mensajes (WS-Security y otros estándares) para la autenticación del cliente.<br /><br /> (Esta enumeración para este modo es `TransportWithMessageCredential`.)|  
|Ambas|Lleva a cabo la protección y autenticación en ambos niveles. Este modo solo está disponible en el elemento [\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) .|  
  
## <a name="credentials-and-transfer-security"></a>Seguridad de transferencia y credenciales  
 Una *credencial* de son los datos que se presentan para establecer una identidad reclamada o capacidades. La presentación de una credencial implica la presentación de los datos y de la prueba de posesión de los datos. WCF admite una variedad de tipos de credenciales en los niveles de seguridad de transporte y de mensaje. Puede especificar un tipo de credencial para un enlace de WCF.  
  
 En muchos países o regiones, un permiso de conducción es un ejemplo de credencial. Un permiso contiene datos que representan la identidad y las capacidades de cada uno. Contiene prueba de posesión en forma de la imagen del poseedor. Una entidad emisora de confianza emite la licencia; normalmente, un departamento gubernamental de licencias. Se sella la licencia, que puede contener un holograma, que muestra que no se ha manipulado o falsificado.  
  
 Como ejemplo, considere dos tipos de credenciales que se admiten en WCF: nombre de usuario y credenciales de certificado (X. 509).  
  
 Para la credencial de nombre de usuario, el nombre de usuario representa la identidad reivindicada y la contraseña constituye la prueba de posesión. La autoridad de confianza en este caso es el sistema que valida el nombre de usuario y la contraseña.  
  
 En la credencial del certificado, el nombre del sujeto, el nombre alternativo del sujeto o los campos concretos dentro del certificado se puede utilizar para representar la identidad y/o funciones reivindicadas. La prueba de posesión de los datos en la credencial se establece mediante el uso de la clave privada asociada para generar una firma.  
  
 Para obtener más información sobre la programación de la seguridad de transferencia y la especificación de credenciales, vea [enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) y [comportamientos](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)de seguridad.  
  
### <a name="transport-client-credential-types"></a>Tipos de credenciales de cliente de transporte  
 La siguiente tabla muestra los posibles valores utilizados al crear una aplicación que utiliza la seguridad de transferencia. Puede utilizar estos valores en código o ajustes de enlaces.  
  
|Configuración de|Descripción|  
|-------------|-----------------|  
|Ninguno|Especifica que el cliente no necesita presentar ningún credencial. Realiza una conversión a un cliente anónimo.|  
|Basic|Especifica la autenticación básica. Para obtener más información, vea RFC2617, "[autenticación http: autenticación básica e implícita](http://schemas.xmlsoap.org/ws/2004/10/discovery/ws-discovery.pdf)".|  
|Digest|Especifica la autenticación implícita. Para obtener más información, vea RFC2617, "[autenticación http: autenticación básica e implícita](http://schemas.xmlsoap.org/ws/2004/10/discovery/ws-discovery.pdf)".|  
|Ntlm|Especifica autenticación de Windows mediante negociación SSPI en un dominio de Windows.<br /><br /> La negociación SSPI resulta en el uso del protocolo Kerberos o NT LanMan (NTLM).|  
|Portal|Especifica autenticación de Windows utilizando SSPI en un dominio de Windows. SSPI escoge del protocolo Kerberos o NTLM como servicio de autenticación.<br /><br /> SSPI prueba primero el protocolo Kerberos; si eso falla, utiliza NTLM.|  
|Certificado|Realiza la autenticación de cliente utilizando un certificado, normalmente X.509.|  
  
### <a name="message-client-credential-types"></a>Tipos de credencial de cliente de mensaje  
 La siguiente tabla muestra los posibles valores utilizados al crear una aplicación que utiliza la seguridad de mensajes. Puede utilizar estos valores en código o ajustes de enlaces.  
  
|Configuración de|Descripción|  
|-------------|-----------------|  
|Ninguno|Permite al servicio interactuar con clientes anónimos.|  
|Portal|Permite a los intercambios de mensajes SOAP ocurrir bajo el contexto autenticado de una credencial de Windows. Utiliza el mecanismo de negociación de SSPI para escoger entre el protocolo Kerberos o NTLM como servicio de autenticación.|  
|Nombre de usuario|Permite al servicio requerir que el cliente se autentique con una credencial de nombre de usuario. Tenga en cuenta que WCF no permite ninguna operación criptográfica con el nombre de usuario, como generar una firma o cifrar los datos. Como tal, WCF exige que el transporte esté protegido cuando se usen credenciales de nombre de usuario.|  
|Certificado|Permite al servicio exigir la autenticación del cliente mediante un certificado.|  
|CardSpace|Permite que el servicio requiera que el cliente se autentique mediante un CardSpace.|  
  
### <a name="programming-credentials"></a>Programación de credenciales  
 Para cada uno de los tipos de credenciales de cliente, el modelo de programación de WCF le permite especificar los valores de credenciales y validadores de credenciales mediante comportamientos de servicio y comportamientos de canal.  
  
 La seguridad de WCF tiene dos tipos de credenciales: comportamientos de credenciales de servicio y comportamientos de credenciales de canal. Comportamientos de credenciales en WCF especifique los datos reales, es decir, las credenciales usadas para cumplir los requisitos de seguridad expresados a través de los enlaces. En WCF, una clase de cliente es el componente de tiempo de ejecución que convierte entre la invocación de la operación y los mensajes. Todos los clientes heredan de la clase <xref:System.ServiceModel.ClientBase%601>. La propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> en la clase base permite especificar varios valores de credenciales del cliente.  
  
 En WCF, los comportamientos de servicio son atributos que se aplican a la clase que implementa un contrato de servicios (interfaz) para controlar el servicio mediante programación. La clase <xref:System.ServiceModel.Description.ServiceCredentials> le permite especificar certificados para la configuración de la validación de cliente y credenciales de servicio para varios tipos de credenciales de cliente.  
  
### <a name="negotiation-model-for-message-security"></a>Modelo de negociación para la seguridad de mensajes  
 El modo de seguridad de mensajes le permite realizar la seguridad de transferencia para que la credencial del servicio se configure en el cliente fuera de banda. Por ejemplo, si está utilizando un certificado almacenado en el almacén de certificados de Windows, debe utilizar una herramienta como el complemento Microsoft Management Console (MMC).  
  
 El modo de seguridad de mensajes también permite aplicar la seguridad de transferencia para que la credencial del servicio se intercambie con el cliente como parte de una negociación inicial. Para habilitar la negociación, establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> en `true`.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la creación de puntos finales](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
