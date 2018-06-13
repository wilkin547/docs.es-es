---
title: Seguridad distribuida de aplicaciones
ms.date: 03/30/2017
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d8f34d0c6b0269cc4837313d6613e3cee0eb26c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496170"
---
# <a name="distributed-application-security"></a>Seguridad distribuida de aplicaciones
Seguridad de Windows Communication Foundation (WCF) se divide en tres áreas funcionales principales: transferencia de seguridad, control de acceso y auditoría. La seguridad de transferencia proporciona integridad, confidencialidad y autenticación. La seguridad de transferencia la proporciona uno de los siguientes elementos: seguridad de transporte, seguridad de mensajes o `TransportWithMessageCredential`.  
  
 Para obtener información general de seguridad de mensaje WCF, vea [información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md). Para obtener más información acerca de las otras dos partes de la seguridad WCF, vea [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) y [auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="transfer-security-scenarios"></a>Escenarios de seguridad de transferencia  
 Escenarios comunes que emplean la seguridad de la transferencia WCF son los siguientes:  
  
-   Transferencia segura mediante Windows. Un cliente de WCF y el servicio se implementan en un dominio de Windows (o un bosque de Windows). Los mensajes contienen datos personales, por lo que entre los requisitos se incluye la autenticación mutua de cliente y servicio, la integridad y la confidencialidad de los mensajes. Además, se requiere la prueba de que una transacción determinada se produjo, por ejemplo, el receptor del mensaje debería registrar la información de la firma.  
  
-   Transferencia segura mediante `UserName` y HTTPS. Un cliente de WCF y el servicio necesitan ser desarrollarse para funcionar a través de Internet. Las credenciales de clientes se autentican frente a una base de datos de pares de nombres de usuario y contraseñas. El servicio se implementa en una dirección HTTPS utilizando un certificado Secure Sockets Layer (SSL) de confianza. Dado que los mensajes viajan a través de Internet, el cliente y servicio deben autenticarse mutuamente y se debe preservar la confidencialidad e integridad de los mensajes durante la transferencia.  
  
-   Transferencia segura mediante el uso de certificados. Un cliente WCF y servicio deban desarrollarse para funcionar sobre la red internet pública. El cliente y el servicio tienen certificados que se pueden utilizar para proteger los mensajes. El cliente y el servicio utilizan Internet para comunicarse entre sí y realizar transacciones de valor alto que requieren integridad del mensaje, confidencialidad y autenticación mutua.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integridad, confidencialidad y autenticación  
 Tres funciones se llaman conjuntamente seguridad de transferencia: integridad, confidencialidad y autenticación. La seguridad de transferencia proporciona funciones que ayudan a mitigar las amenazas para una aplicación distribuida. La siguiente tabla describe brevemente las tres funciones que constituyen la seguridad de transferencia.  
  
|Función|Descripción|  
|--------------|-----------------|  
|Integridad|*Integridad* es la garantía de que los datos son completos y precisos, sobre todo después de que se ha pasado desde un punto a otro y posiblemente han sido leídos por muchos actores. La integridad debe mantenerse para evitar la modificación de los datos y normalmente se logra mediante la firma digital de un mensaje.|  
|Confidencialidad|*Confidencialidad* es la garantía de que un mensaje no ha sido leído por nadie que no sea el lector previsto. Por ejemplo, un número de tarjeta de crédito se debe mantener de manera confidencial al enviarse a través de Internet. La confidencialidad es a menudo proporcionada por el cifrado de datos utilizando un esquema de clave pública/privada.|  
|Autenticación|*Autenticación* es la comprobación de una identidad reivindicada. Por ejemplo, al utilizar una cuenta bancaria, es imperativo que solo el propietario real de la cuenta pueda retirar los fondos. Diversos recursos pueden proporcionar la autenticación. Un método común es el sistema de usuario/contraseña. Otro método consiste en el uso de un certificado X.509 proporcionado por un tercero.|  
  
## <a name="security-modes"></a>Modos de seguridad  
 WCF tiene varios modos de seguridad de la transferencia, que se describen en la tabla siguiente.  
  
|Modo|Descripción|  
|----------|-----------------|  
|Ninguna|No se proporciona ninguna seguridad en el nivel de transporte o en el nivel del mensaje. Ninguno de los enlaces predefinidos Utilice este modo de forma predeterminada, excepto la [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento o, si usa el código, la <xref:System.ServiceModel.BasicHttpBinding> clase.|  
|Transporte|Utiliza un transporte seguro como HTTPS para la integridad, confidencialidad y autenticación mutua.|  
|Mensaje|Utiliza seguridad del mensaje SOAP para la integridad, confidencialidad y autenticación mutua. Los mensajes SOAP se protegen según los estándares de WS-Security.|  
|Modo mixto|Utiliza la seguridad de transporte para la integridad, confidencialidad y autenticación de servidor. Utiliza la seguridad de mensajes (WS-Security y otros estándares) para la autenticación del cliente.<br /><br /> (Esta enumeración para este modo es `TransportWithMessageCredential`.)|  
|Ambos|Lleva a cabo la protección y autenticación en ambos niveles. Este modo está disponible solo en el [ \<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) elemento.|  
  
## <a name="credentials-and-transfer-security"></a>Seguridad de transferencia y credenciales  
 A *credencial* son datos que se presentan para establecer una identidad reivindicada o funciones. La presentación de una credencial implica la presentación de los datos y de la prueba de posesión de los datos. WCF admite una variedad de tipos de credenciales en los niveles de seguridad de mensajes y transporte. Puede especificar un tipo de credencial para un enlace de WCF.  
  
 En muchos países o regiones, un permiso de conducción es un ejemplo de credencial. Un permiso contiene datos que representan la identidad y las capacidades de cada uno. Contiene prueba de posesión en forma de la imagen del poseedor. Una entidad emisora de confianza emite la licencia; normalmente, un departamento gubernamental de licencias. Se sella la licencia, que puede contener un holograma, que muestra que no se ha manipulado o falsificado.  
  
 Por ejemplo, considere dos tipos de credenciales admitidos en WCF: nombre de usuario y (X.509) las credenciales del certificado.  
  
 Para la credencial de nombre de usuario, el nombre de usuario representa la identidad reivindicada y la contraseña constituye la prueba de posesión. La autoridad de confianza en este caso es el sistema que valida el nombre de usuario y la contraseña.  
  
 En la credencial del certificado, el nombre del sujeto, el nombre alternativo del sujeto o los campos concretos dentro del certificado se puede utilizar para representar la identidad y/o funciones reivindicadas. La prueba de posesión de los datos en la credencial se establece mediante el uso de la clave privada asociada para generar una firma.  
  
 Para obtener más información sobre la programación de seguridad de la transferencia y especificar las credenciales, vea [enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) y [comportamientos de seguridad](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
### <a name="transport-client-credential-types"></a>Tipos de credenciales de cliente de transporte  
 La siguiente tabla muestra los posibles valores utilizados al crear una aplicación que utiliza la seguridad de transferencia. Puede utilizar estos valores en código o ajustes de enlaces.  
  
|Parámetro|Descripción|  
|-------------|-----------------|  
|Ninguna|Especifica que el cliente no necesita presentar ningún credencial. Realiza una conversión a un cliente anónimo.|  
|Básico|Especifica la autenticación básica.  Para obtener más información, vea RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Implícita|Especifica la autenticación implícita.  Para obtener más información, vea RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Ntlm|Especifica autenticación de Windows mediante negociación SSPI en un dominio de Windows.<br /><br /> La negociación SSPI resulta en el uso del protocolo Kerberos o NT LanMan (NTLM).|  
|Windows|Especifica autenticación de Windows utilizando SSPI en un dominio de Windows. SSPI escoge del protocolo Kerberos o NTLM como servicio de autenticación.<br /><br /> SSPI prueba primero el protocolo Kerberos; si eso falla, utiliza NTLM.|  
|Certificado|Realiza la autenticación de cliente utilizando un certificado, normalmente X.509.|  
  
### <a name="message-client-credential-types"></a>Tipos de credencial de cliente de mensaje  
 La siguiente tabla muestra los posibles valores utilizados al crear una aplicación que utiliza la seguridad de mensajes. Puede utilizar estos valores en código o ajustes de enlaces.  
  
|Parámetro|Descripción|  
|-------------|-----------------|  
|Ninguna|Permite al servicio interactuar con clientes anónimos.|  
|Windows|Permite a los intercambios de mensajes SOAP ocurrir bajo el contexto autenticado de una credencial de Windows. Utiliza el mecanismo de negociación de SSPI para escoger entre el protocolo Kerberos o NTLM como servicio de autenticación.|  
|Nombre de usuario|Permite al servicio requerir que el cliente se autentique con una credencial de nombre de usuario. Tenga en cuenta que WCF no permite ninguna operación criptográfica con el nombre de usuario, como generar una firma o cifrado de datos. Por lo tanto, WCF garantiza que el transporte sea seguro al usar credenciales de nombre de usuario.|  
|Certificado|Permite al servicio exigir la autenticación del cliente mediante un certificado.|  
|[!INCLUDE[infocard](../../../../includes/infocard-md.md)]|Permite al servicio que requiera la autenticación del cliente mediante un [!INCLUDE[infocard](../../../../includes/infocard-md.md)].|  
  
### <a name="programming-credentials"></a>Programación de credenciales  
 Para cada uno de los tipos de credencial de cliente, el modelo de programación de WCF permite especificar los valores de credenciales y validadores de credenciales mediante el uso de comportamientos de servicio y comportamientos de canal.  
  
 La seguridad de WCF tiene dos tipos de credenciales: comportamientos de credenciales y comportamientos de canal de credencial de servicio. Comportamientos de credenciales en WCF especifican los datos reales, es decir, las credenciales utilizadas para cumplir los requisitos de seguridad expresados a través de enlaces. En WCF, una clase de cliente es el componente de tiempo de ejecución que convierte entre los mensajes y la invocación de la operación. Todos los clientes heredan de la clase <xref:System.ServiceModel.ClientBase%601>. La propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> en la clase base permite especificar varios valores de credenciales del cliente.  
  
 En WCF, los comportamientos de servicio son atributos aplicados a la clase que implementa un contrato de servicio (interfaz) para controlar mediante programación el servicio. La clase <xref:System.ServiceModel.Description.ServiceCredentials> le permite especificar certificados para la configuración de la validación de cliente y credenciales de servicio para varios tipos de credenciales de cliente.  
  
### <a name="negotiation-model-for-message-security"></a>Modelo de negociación para la seguridad de mensajes  
 El modo de seguridad de mensajes le permite realizar la seguridad de transferencia para que la credencial del servicio se configure en el cliente fuera de banda. Por ejemplo, si está utilizando un certificado almacenado en el almacén de certificados de Windows, debe utilizar una herramienta como el complemento Microsoft Management Console (MMC).  
  
 El modo de seguridad de mensajes también permite aplicar la seguridad de transferencia para que la credencial del servicio se intercambie con el cliente como parte de una negociación inicial. Para habilitar la negociación, establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> en `true`.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la creación de puntos finales](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
