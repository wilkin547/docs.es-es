---
title: Denegación de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- denial of service [WCF]
ms.assetid: dfb150f3-d598-4697-a5e6-6779e4f9b600
ms.openlocfilehash: 4a9f3a3b7e69d33a8707a4bed5b9bc369c75f601
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346694"
---
# <a name="denial-of-service"></a>Denegación de servicio
La denegación de servicio se produce cuando un sistema está sobrecargado de tal manera que no se pueden procesar los mensajes, o se procesan muy lentamente.  
  
## <a name="excess-memory-consumption"></a>Consumo de memoria de exceso  
 Al leer un documento XML con numerosos nombres locales, espacios de nombres o prefijos únicos, puede producirse un problema. Si está utilizando una clase que se deriva de <xref:System.Xml.XmlReader>, y llama a la propiedad <xref:System.Xml.XmlReader.LocalName%2A>, <xref:System.Xml.XmlReader.Prefix%2A> o <xref:System.Xml.XmlReader.NamespaceURI%2A> para cada elemento, la cadena devuelta se agrega a <xref:System.Xml.NameTable>. La colección contenida por <xref:System.Xml.NameTable> nunca disminuye de tamaño, creando una "pérdida de memoria" virtual de los identificadores de cadena.  
  
 Algunos procedimientos para mitigarlas son:  
  
- Derive de la clase <xref:System.Xml.NameTable> y exija una cuota de tamaño máximo. (No puede evitar el uso de <xref:System.Xml.NameTable> o intercambiar <xref:System.Xml.NameTable> cuando es completo.)  
  
- Evite el uso de las propiedades mencionadas y utilice en su lugar el método <xref:System.Xml.XmlReader.MoveToAttribute%2A> con el método <xref:System.Xml.XmlReader.IsStartElement%2A> cuando sea posible; estos métodos no devuelven cadenas y, por tanto, evitan el problema de llenar demasiado la colección <xref:System.Xml.NameTable>.  
  
## <a name="malicious-client-sends-excessive-license-requests-to-service"></a>Cliente malintencionado envía solicitudes de licencia en exceso al servicio  
 Si un cliente malintencionado bombardea un servicio con solicitudes de licencia excesivas, puede hacer que el servidor utilice memoria en exceso.  
  
 Mitigación: use las propiedades siguientes de la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>:  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxCachedCookies%2A>: controla el número máximo de `SecurityContextToken`s limitados por tiempo que el servidor almacena en memoria caché después de `SPNego` o negociación `SSL`.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.IssuedCookieLifetime%2A>: controla la duración de `SecurityContextTokens` que el servidor emite tras `SPNego` o una negociación `SSL`. El servidor almacena en memoria caché los `SecurityContextToken`s para este período de tiempo.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxPendingSessions%2A>: controla el número máximo de conversaciones seguras que se establecen en el servidor pero para las que no se ha procesado ningún mensaje de aplicación. Esta cuota evita que los clientes establezcan conversaciones seguras en el servicio, por lo que el servicio mantiene el estado por cliente, pero sin usarlos.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.InactivityTimeout%2A>: controla el tiempo máximo en el que el servicio mantiene viva una conversación segura sin recibir un mensaje de aplicación del cliente para la conversación. Esta cuota evita que los clientes establezcan conversaciones seguras en el servicio, por lo que el servicio mantiene el estado por cliente, pero sin usarlos.  
  
## <a name="wsdualhttpbinding-or-dual-custom-bindings-require-client-authentication"></a>WSDualHttpBinding o los enlaces personalizados duales requieren autenticación del cliente  
 De forma predeterminada, <xref:System.ServiceModel.WSDualHttpBinding> tiene la seguridad habilitada. Es posible, sin embargo, que si la autenticación del cliente se deshabilita estableciendo la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en <xref:System.ServiceModel.MessageCredentialType.None>, un usuario malintencionado pueda producir un ataque de denegación de servicio en un tercer servicio. Esto se puede producir porque un cliente malintencionado puede hacer que el servicio envíe una secuencia de mensajes a un tercer servicio.  
  
 Para mitigarlo, no establezca la propiedad en `None`. También sea consciente de esta posibilidad al crear un enlace personalizado que tiene un patrón de mensaje dual.  
  
## <a name="auditing-event-log-can-be-filled"></a>Se puede rellenar el registro de eventos de auditoría  
 Si un usuario malintencionado sabe que la auditoría está habilitada, el atacante puede enviar mensajes no válidos y así hacer que se escriban entradas de auditoría. Si el registro de auditoría se rellena de esta manera, el sistema de auditoría falla.  
  
 Para mitigar esto, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` y use las propiedades del Visor de eventos para controlar el comportamiento de la auditoría. Para obtener más información sobre el uso de la Visor de eventos para ver y administrar registros de eventos, vea [visor de eventos](https://go.microsoft.com/fwlink/?LinkId=186123). Para obtener más información, consulte [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="invalid-implementations-of-iauthorizationpolicy-can-cause-service-to-become-unresponsive"></a>Las implementaciones no válidas de IAuthorizationPolicy pueden hacer que el servicio deje de responder  
 Llamar al método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> en una implementación defectuosa de la interfaz <xref:System.IdentityModel.Policy.IAuthorizationPolicy> puede hacer que el servicio deje de responder.  
  
 Mitigación: utilice solamente código de confianza. Es decir, solo utilice código que haya escrito y probado, o que provenga de un proveedor confiable. No permita la conexión de extensiones que no son de confianza de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> a su código sin la debida consideración. Esto se aplica a todas las extensiones usadas en una implementación del servicio. WCF no realiza ninguna distinción entre el código de aplicación y el código externo que está conectado mediante puntos de extensibilidad.  
  
## <a name="kerberos-maximum-token-size-may-need-resizing"></a>Puede que el tamaño máximo del token de Kerberos necesite cambio de tamaño  
 Si un cliente pertenece a un número grande de grupos (aproximadamente 900, aunque el número real varía dependiendo de los grupos), puede producirse un problema cuando el bloque de un encabezado de mensaje supera los 64 kilobytes. En ese caso, puede aumentar el tamaño máximo del token de Kerberos, como se describe en el Soporte técnico de Microsoft artículo "la[autenticación Kerberos de Internet Explorer no funciona debido a un búfer insuficiente al conectarse a IIS](https://go.microsoft.com/fwlink/?LinkId=89176)". También puede que necesite aumentar el tamaño máximo del mensaje de WCF para dar cabida al token de Kerberos más grande.  
  
## <a name="autoenrollment-results-in-multiple-certificates-with-same-subject-name-for-machine"></a>La inscripción automática da como resultado varios certificados con el mismo nombre de asunto para el equipo  
 La *inscripción* automática es la capacidad de Windows Server 2003 para inscribir automáticamente usuarios y equipos para certificados. Cuando un equipo está en un dominio con la característica habilitada, se crea automáticamente un certificado X.509 con el propósito intencional de autenticación del cliente y se inserta en el almacén de certificados personales del equipo local siempre que un nuevo equipo se une a la red. Sin embargo, la inscripción automática utiliza el mismo nombre de sujeto para todos los certificados que crea en la memoria caché.  
  
 El impacto es que los servicios de WCF pueden no abrirse en los dominios con inscripción automática. Esto se produce porque el criterio de búsqueda de credenciales X.509 de servicio predeterminado podría ser ambiguo, ya que existen varios certificados con nombre completo del Domain Name System (DNS). Un certificado ha sido originado por la inscripción automática; el otro puede ser un certificado emitido por sí mismo.  
  
 Para mitigar esto, haga referencia al certificado exacto que se va a usar con un criterio de búsqueda más preciso en el [\<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md). Por ejemplo, utilice la opción <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> y especifique el certificado por su huella digital única (hash).  
  
 Para obtener más información acerca de la característica de inscripción automática, consulte [inscripción automática de certificados en Windows Server 2003](https://go.microsoft.com/fwlink/?LinkId=95166).  
  
## <a name="last-of-multiple-alternative-subject-names-used-for-authorization"></a>Último de varios nombres de asunto alternativos que se usan en la autorización  
 En el poco probable caso de que un certificado X.509 contenga varios nombres de asunto alternativos, y que usted autorice el uso del nombre de asunto alternativo, puede que se produzca un error en la autorización.  
  
## <a name="protect-configuration-files-with-acls"></a>Proteger los archivos de configuración con ACL  
 Puede especificar las notificaciones necesarias y opcionales en los archivos de código y configuración para los tokens emitidos por CardSpace. Esto tiene como resultado que se emitan elementos correspondientes en mensajes `RequestSecurityToken` que se envían al servicio de token de seguridad. Un atacante puede modificar código o configuración para eliminar demandas necesarias u opcionales, pudiendo ganar así la posibilidad de que el servicio de token de seguridad emita un token que no permite el acceso al servicio especificado.  
  
 Para mitigar: exija el acceso al equipo para modificar el archivo de configuración. Use listas de control de acceso (ACL) de archivo para proteger los archivos de configuración. WCF requiere que el código esté en el directorio de la aplicación o en la caché global de ensamblados antes de permitir que se cargue ese código desde la configuración. Utilice ACL del directorio para proteger los directorios.  
  
## <a name="maximum-number-of-secure-sessions-for-a-service-is-reached"></a>Se ha alcanzado el número máximo de sesiones seguras para un servicio  
 Cuando un servicio autentica correctamente un cliente y una sesión segura se establece con el servicio, el servicio sigue en contacto con la sesión hasta que el cliente la cancela o la sesión expira. Cada sesión establecida afecta al límite para el número máximo de sesiones simultáneas activas con un servicio. Cuando se alcanza este límite, se rechazan los clientes que intentan crear una nueva sesión con ese servicio hasta que una o más sesiones activas expiren o sean canceladas por un cliente. Un cliente puede tener varias sesiones con un servicio y cada una de esas sesiones afecta al límite.  
  
> [!NOTE]
> Cuando se usan sesiones con estado, el párrafo anterior no se aplica. Para obtener más información acerca de las sesiones con estado, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
 Para mitigar esto, establezca el límite para el número máximo de sesiones activas y la duración máxima para una sesión estableciendo la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Elevación de privilegios](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [Manipulación](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
