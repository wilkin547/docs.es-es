---
title: Seguridad de servicios
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF], securing services
- WCF security
- WCF, security
ms.assetid: f0ecc6f7-f4b5-42a4-9cb1-b02e28e26620
ms.openlocfilehash: f2a8e10aaf9c1dbe3065344963fcc712776cd2db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242232"
---
# <a name="securing-services"></a>Seguridad de servicios

La seguridad de un servicio de Windows Communication Foundation (WCF) consta de dos requisitos principales: seguridad y autorización de la transferencia. (Un tercer requisito, la auditoría de eventos de seguridad, se describe en [Auditoría](./feature-details/auditing-security-events.md)). En Resumen, la seguridad de transferencia incluye autenticación (comprobación de la identidad del servicio y del cliente), confidencialidad (cifrado de mensajes) e integridad (firma digital para detectar alteraciones). La autorización es el control del acceso a los recursos, por ejemplo, permitiendo la lectura de un archivo solo a usuarios privilegiados. Con las características de WCF, se implementan fácilmente los dos requisitos principales.  
  
 Con la excepción de la <xref:System.ServiceModel.BasicHttpBinding> clase (o el [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) elemento en la configuración), la seguridad de la transferencia está habilitada de forma predeterminada para todos los enlaces predefinidos. Los temas de esta sección tratan dos escenarios básicos: la implementación de la seguridad de la transferencia y la autorización en un servicio de la intranet que se hospeda en IIS (Internet Information Services), y la implementación de la seguridad de la transferencia y la autorización en un servicio hospedado en IIS.  
  
> [!NOTE]
> Windows XP Home no admite la autenticación de Windows. Por lo tanto, no debería ejecutar un servicio en ese sistema.  
  
## <a name="security-basics"></a>Fundamentos de seguridad  

 La seguridad se basa en *las credenciales*. Una credencial demuestra que una entidad es quién notifica ser. (Una *entidad* puede ser una persona, un proceso de software, una empresa o cualquier cosa que se pueda autorizar). Por ejemplo, un cliente de un servicio realiza una *petición* de *identidad*, y la credencial demuestra esa afirmación de alguna manera. En un escenario típico, se produce un intercambio de credenciales. Primero, un servicio realiza una notificación de su identidad y lo prueba ante el cliente con una credencial. A la inversa, el cliente realiza una notificación de identidad y presenta una credencial al servicio. Si ambas partes confían en las respectivas credenciales, a continuación, se puede establecer un *contexto seguro* en el que todos los mensajes se intercambian de manera confidencial, y todos los mensajes están firmados para proteger su integridad. Una vez que el servicio establece la identidad del cliente, puede hacer coincidir las notificaciones de la credencial con una *función* o la *pertenencia* de un grupo. En cualquier caso, mediante la función o el grupo al que pertenece el cliente, el servicio *autoriza* al cliente a realizar un conjunto limitado de operaciones basado en los privilegios de la función o el grupo.  
  
## <a name="windows-security-mechanisms"></a>Mecanismos de seguridad de Windows  

 Si tanto el cliente como el equipo de servicio pertenecen a un dominio de Windows que exige a ambos el inicio de una sesión en la red, la infraestructura de Windows proporcionará las credenciales. En ese caso, las credenciales se establecen cuando un usuario del equipo inicia sesión en la red. Cada usuario y cada equipo de la red deben validarse como pertenecientes al conjunto seguro de usuarios y equipos. En un sistema de Windows, cada uno de estos usuarios y equipos se conoce también como una *entidad de seguridad*.  
  
 En un dominio de Windows respaldado por un controlador de *Kerberos* , éste utiliza un esquema basado en otorgar los vales a cada entidad de seguridad. Los vales que otorga el controlador son de confianza para otros emisores de vales del sistema. Siempre que una entidad intenta realizar alguna operación o tener acceso a un *recurso* (como un archivo o directorio en un equipo), se examina la validez del vale y, si se aprueba, se otorga otro vale para la operación a la entidad de seguridad. Este método de otorgar vales es más eficaz que la alternativa de intentar validar la entidad de seguridad en cada operación.  
  
 Un mecanismo anterior y menos seguro que se utiliza en dominios de Windows es NT LAN Manager (NTLM). En casos donde no se puede utilizar Kerberos (normalmente fuera de un dominio de Windows, como en un grupo de trabajo), se puede utilizar NTLM como alternativa. NTLM también está disponible como opción de seguridad para IIS.  
  
 En un sistema de Windows, la autorización funciona asignando cada equipo y usuario a un conjunto de funciones y grupos. Por ejemplo, cada equipo de Windows debe estar configurado y controlado por una persona (o grupo de personas) con la función de *administrador*. Otra función es la del *usuario*, que tiene un conjunto mucho más restringido de permisos. Además de a la función, los usuarios están asignados a grupos. Un grupo permite a varios usuarios actuar en la misma función. Por lo tanto, en la práctica, un equipo de Windows se administra asignando usuarios a los grupos. Por ejemplo, se pueden asignar varios usuarios al grupo de usuarios de un equipo, y asignar un conjunto mucho más restringido de usuarios al grupo de administradores. En un equipo local, un administrador también puede crear grupos nuevos y asignarle otros usuarios (o incluso otros grupos).  
  
 En un equipo que ejecuta Windows, puede protegerse cada carpeta de un directorio. Es decir, puede seleccionar una carpeta y controlar quién tiene acceso a los archivos y si pueden o no copiarlos, o (en el caso más privilegiado) cambiar o eliminar un archivo, o agregar archivos a la carpeta. Esto se conoce como control de acceso, y su mecanismo como la lista de control de acceso (ACL). Al crear la ACL, puede asignar los privilegios de acceso a cualquier grupo o grupos, así como los miembros individuales de un dominio.  
  
 La infraestructura de WCF está diseñada para utilizar estos mecanismos de seguridad de Windows. Por lo tanto, si está creando un servicio que se implementa en una intranet, y sus clientes están restringidos a los miembros del dominio de Windows, la seguridad se implementará fácilmente. Solo los usuarios válidos pueden iniciar sesión en el dominio. Después de que los usuarios inicien la sesión, el controlador de Kerberos permite a cada uno de ellos establecer contextos seguros con cualquier otro equipo o aplicación. En un equipo local, los grupos pueden crearse fácilmente y al proteger carpetas específicas, pueden utilizarse esos grupos para asignar los privilegios de acceso al equipo.  
  
## <a name="implementing-windows-security-on-intranet-services"></a>Implementación de la seguridad de Windows en servicios de la intranet  

 Para proteger una aplicación que se ejecuta exclusivamente en un dominio de Windows, puede utilizar la configuración de seguridad predeterminada de <xref:System.ServiceModel.WSHttpBinding> , o el enlace <xref:System.ServiceModel.NetTcpBinding> . De forma predeterminada, cualquiera que esté en el mismo dominio de Windows puede tener acceso a los servicios WCF. Dado que esos usuarios han iniciado sesión en la red, son de confianza. Los mensajes entre un servicio y un cliente se cifran para la confidencialidad y se firman para integridad. Para obtener más información sobre cómo crear un servicio que use la seguridad de Windows, consulte [Cómo: proteger un servicio con credenciales de Windows](how-to-secure-a-service-with-windows-credentials.md).  
  
### <a name="authorization-using-the-principalpermissionattribute-class"></a>Autorización utilizando la clase PrincipalPermissionAttribute  

 Si necesita restringir el acceso de recursos de un equipo, la manera más sencilla es utilizar la clase <xref:System.Security.Permissions.PrincipalPermissionAttribute> . Este atributo permite restringir la invocación de operaciones del servicio exigiendo que el usuario pertenezca a un grupo o función de Windows específico, o bien ser un usuario concreto. Para obtener más información, vea [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
### <a name="impersonation"></a>Suplantación  

 La suplantación es otro mecanismo que puede utilizarse para controlar el acceso a los recursos. De forma predeterminada, un servicio hospedado por IIS se ejecutará bajo la identidad de la cuenta ASPNET. La cuenta ASPNET solo puede tener acceso a los recursos para los que tiene permiso. Sin embargo, es posible establecer la ACL para que una carpeta excluya la cuenta de servicio ASPNET, pero permitir que otras identidades tengan acceso a la carpeta. La cuestión entonces es cómo permitir a esos usuarios tener acceso a la carpeta si la cuenta ASPNET no está autorizada a hacerlo. La respuesta es utilizar la suplantación, con lo que el servicio está autorizado a utilizar las credenciales del cliente para tener acceso a un recurso determinado. Otro ejemplo es el acceso a una base de datos de SQL Server para la que solo ciertos usuarios tienen permiso. Para obtener más información acerca del uso de la suplantación, consulte [Cómo: suplantar a un cliente en un servicio](how-to-impersonate-a-client-on-a-service.md) y [delegación y suplantación](./feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="security-on-the-internet"></a>Seguridad en Internet  

 La seguridad en Internet se basa en los mismos requisitos que la seguridad en una intranet. Un servicio necesita presentar sus credenciales para demostrar su autenticidad, y los clientes necesitan demostrar su identidad al servicio. Una vez demostrada la identidad de un cliente, el servicio puede controlar qué tipo de acceso a los recursos posee el cliente. No obstante, debido a la naturaleza heterogénea de Internet, las credenciales presentadas difieren de las utilizadas en un dominio de Windows. Si bien un controlador de Kerberos administra la autenticación de usuarios en un dominio mediante vales para las credenciales, en Internet, los servicios y clientes confían en cualquiera de las distintas maneras de presentar credenciales. El objetivo de este tema, sin embargo, es presentar un enfoque común que le permita crear un servicio WCF que sea accesible en Internet.  
  
### <a name="using-iis-and-aspnet"></a>Utilización de IIS y ASP.NET  

 Los requisitos de seguridad de Internet, así como los mecanismos para resolver esos problemas, no son algo nuevo. IIS es el servidor Web de Microsoft para Internet y tiene muchas características de seguridad que solucionan esos problemas; Además, ASP.NET incluye características de seguridad que los servicios de WCF pueden usar. Para aprovechar estas características de seguridad, hospede un servicio WCF en IIS.  
  
#### <a name="using-aspnet-membership-and-role-providers"></a>Utilización de la pertenencia a ASP.NET y los proveedores de funciones  

 ASP.NET incluye una pertenencia y un proveedor de funciones. El proveedor es una base de datos de pares de nombre de usuario/contraseña para la autenticación de autores de llamadas, que también permite especificar los privilegios de acceso de cada autor de llamada. Con WCF, puede usar fácilmente una pertenencia y un proveedor de roles ya existentes a través de la configuración. Para obtener una aplicación de ejemplo que muestre esto, consulte el ejemplo [Membership and Role Provider](./samples/membership-and-role-provider.md) .  
  
### <a name="credentials-used-by-iis"></a>Credenciales utilizadas por IIS  

 A diferencia de un dominio de Windows respaldado por un controlador de Kerberos, Internet es un entorno sin un único controlador que administre los millones de usuarios que inician sesión al mismo tiempo. En vez de eso, las credenciales en Internet se encuentran con mayor frecuencia en forma de certificados X.509 (que también se conocen como certificados de Capa de sockets seguros, o SSL). Normalmente, estos certificados los emite una *entidad de certificación*, que puede ser una compañía de otro fabricante que responde de la autenticidad del certificado y la persona para la que se emitió. Para exponer su servicio en Internet, también debe proporcionar este tipo de certificado de confianza como autenticación de su servicio.  
  
 La pregunta que surge en este punto es ¿cómo obtener este tipo de certificado? Una solución es acudir a una entidad de certificación de otro fabricante, como Authenticode o VeriSign, cuando esté en disposición de implementar el servicio, y adquirir un certificado para el mismo. Sin embargo, si se encuentra en la fase de desarrollo con WCF y aún no está listo para confirmar la adquisición de un certificado, existen herramientas y técnicas para crear certificados X. 509 que puede usar para simular una implementación de producción. Para obtener más información, consulte [trabajar con certificados](./feature-details/working-with-certificates.md).  
  
## <a name="security-modes"></a>Modos de seguridad  

 La programación de la seguridad de WCF conlleva algunos puntos de decisión críticos. Una de las más básica es la elección del *modo de seguridad*. Los dos modos de seguridad principales son el *modo de transporte* y el *modo de mensaje*.  
  
 Un tercer modo, que combina la semántica de los dos modos principales, es el *modo de transporte con credenciales de mensaje*.  
  
 El modo de seguridad determina la protección de los mensajes, y cada elección presenta ventajas y desventajas, como se indica a continuación. Para obtener más información acerca de cómo establecer el modo de seguridad, consulte [Cómo: establecer el modo de seguridad](how-to-set-the-security-mode.md).  
  
#### <a name="transport-mode"></a>modo de transporte  

 Existen varias capas entre la red y la aplicación. Uno de ellas es la capa de *transporte* ,*que* administra la transferencia de mensajes entre los extremos. Para el propósito actual, solo es necesario comprender que WCF usa varios protocolos de transporte, cada uno de los cuales puede proteger la transferencia de mensajes. (Para obtener más información acerca de los transportes, consulte [transportes](./feature-details/transports.md)).  
  
 Un protocolo utilizado frecuentemente es HTTP; otro es TCP. Cada uno de estos protocolos puede proteger la transferencia del mensaje mediante un mecanismo (o mecanismos) determinado del protocolo. Por ejemplo, el protocolo HTTP se protege utilizando SSL sobre HTTP, normalmente abreviado como "HTTPS". Así, al seleccionar el modo de transporte para la seguridad, está decidiendo utilizar el mecanismo dictado por el protocolo. Por ejemplo, si selecciona la clase <xref:System.ServiceModel.WSHttpBinding> y establece su modo de seguridad en Transporte, está seleccionando SSL sobre HTTP (HTTPS) como mecanismo de seguridad. La ventaja del modo de transporte es que es más eficaz que el modo de mensaje ya que la seguridad se integra en un nivel comparativamente bajo. Al utilizar el modo de transporte, el mecanismo de seguridad se debe implementar según la especificación para el transporte, de este modo los mensajes pueden fluir de manera segura de un punto a otro del transporte.  
  
#### <a name="message-mode"></a>modo de mensaje  

 Por el contrario, el modo de mensaje proporciona seguridad incluyendo los datos de seguridad en cada mensaje. Utilizando XML y encabezados de seguridad de SOAP, las credenciales y otros datos necesarios para garantizar la integridad y confidencialidad del mensaje se incluyen en cada mensaje. Cada mensaje incluye los datos de seguridad, lo que afecta negativamente al rendimiento debido a que cada mensaje debe procesarse de manera individual. (En modo de transporte, una vez protegida la capa de transporte, todos los mensajes fluyen libremente). Sin embargo, la seguridad de los mensajes tiene una ventaja sobre la seguridad de transporte: es más flexible. Es decir, el transporte no determina los requisitos de seguridad. Puede utilizar cualquier tipo de credencial de cliente para proteger el mensaje. En modo de transporte, el protocolo de transporte determina el tipo de credencial de cliente que puede utilizarse.  
  
#### <a name="transport-with-message-credentials"></a>Transporte con credenciales de mensaje  

 El tercer modo combina lo mejor de la seguridad de transporte y de mensaje. En este modo, la seguridad de transporte se utiliza para proteger eficazmente la confidencialidad e integridad de cada mensaje. Al mismo tiempo, cada mensaje incluye sus datos de credencial, lo que permite la autenticación del mensaje. Con la autenticación, también puede implementarse la autorización. Mediante la autenticación de un remitente, el acceso a los recursos puede otorgarse (o denegarse) conforme a la identidad del remitente.  
  
## <a name="specifying-the-client-credential-type-and-credential-value"></a>Especificación del tipo de credencial de cliente y del valor de credencial  

 Después de seleccionar un modo de seguridad, es posible que también desee especificar un tipo de credencial de cliente. El tipo de credencial de cliente especifica qué tipo debe utilizar un cliente para autenticarse al servidor.  
  
 No obstante, no todos los escenarios requieren un tipo de credencial de cliente. Utilizando SSL sobre HTTP (HTTPS), un servicio se autentica al cliente. Como parte de esta autenticación, se envía el certificado del servicio al cliente en un proceso denominado *negociación*. El transporte protegido por SSL garantiza que todos los mensajes son confidenciales.  
  
 Si está creando un servicio que requiere la autenticación del cliente, la elección de un tipo de credencial de cliente depende del transporte y el modo seleccionados. Por ejemplo, si utiliza el transporte HTTP y opta por el modo de transporte, podrá elegir entre varias opciones, como Básica, Implícita, y otras. (Para obtener más información acerca de estos tipos de credenciales, vea Descripción de la [autenticación http](./feature-details/understanding-http-authentication.md)).  
  
 Si crea un servicio en un dominio de Windows que solo estará disponible para otros usuarios de la red, el más fácil de utilizar es el tipo de credencial de cliente de Windows. Sin embargo, también puede que tenga que proporcionar un certificado al servicio. Esto se muestra en [How to: Specify Client Credential Values](how-to-specify-client-credential-values.md).  
  
#### <a name="credential-values"></a>Valores de credencial  

 Un *valor de credencial* es la credencial real utilizada por el servicio. Cuando se especifica un tipo de credencial, también puede ser necesario configurar el servicio con las credenciales reales. Si se selecciona Windows (y el servicio se ejecutará en un dominio de Windows), no será necesario especificar un valor de credencial real.  
  
## <a name="identity"></a>Identidad  

 En WCF, el término *identidad* tiene significados diferentes para el servidor y el cliente. Resumiendo, al ejecutar un servicio, se asigna una identidad al contexto de seguridad después de la autenticación. Para ver la identidad real, compruebe las propiedades <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> y <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> de la clase <xref:System.ServiceModel.ServiceSecurityContext> . Para obtener más información, consulte [Cómo: examinar el contexto de seguridad](how-to-examine-the-security-context.md).  
  
 Por el contrario, en el cliente, la identidad se utiliza para validar el servicio. En tiempo de diseño, un programador del cliente puede establecer el [\<identity>](../configure-apps/file-schema/wcf/identity.md) elemento en un valor obtenido del servicio. Durante la ejecución, el cliente contrasta el valor del elemento con la identidad real del servicio. Si se produce un error en la comprobación, el cliente finaliza la comunicación. El valor puede ser un nombre principal del usuario (UPN), si el servicio se ejecuta bajo la identidad de un usuario determinado, o un nombre de entidad de seguridad de servicio (SPN) si el servicio se ejecuta bajo una cuenta de equipo. Para obtener más información, consulte [identidad de servicio y autenticación](./feature-details/service-identity-and-authentication.md). La credencial también puede ser un certificado, o un campo de un certificado que identifica a éste último.  
  
## <a name="protection-levels"></a>Niveles de protección  

 La propiedad `ProtectionLevel` se encuentra en varias clases de atributos (como las clases <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> ). El nivel de protección es un valor que especifica si los mensajes (o partes del mensaje) que soportan un servicio están firmados, firmados y cifrados, o si se envían sin firmar o cifrar. Para obtener más información sobre la propiedad, vea [Descripción del nivel de protección](understanding-protection-level.md)y, para obtener ejemplos de programación, vea [Cómo: establecer la propiedad ProtectionLevel](how-to-set-the-protectionlevel-property.md). Para obtener más información sobre cómo diseñar un contrato de servicio con `ProtectionLevel` en contexto, consulte [diseño de contratos de servicio](designing-service-contracts.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Identidad del servicio y autenticación](./feature-details/service-identity-and-authentication.md)
- [Descripción de los niveles de protección](understanding-protection-level.md)
- [Delegación y suplantación](./feature-details/delegation-and-impersonation-with-wcf.md)
- [Diseño de contratos de servicios](designing-service-contracts.md)
- [Seguridad](./feature-details/security.md)
- [Información general sobre seguridad](./feature-details/security-overview.md)
- [Procedimiento para establecer la propiedad ProtectionLevel](how-to-set-the-protectionlevel-property.md)
- [Procedimiento para proteger un servicio con credenciales de Windows](how-to-secure-a-service-with-windows-credentials.md)
- [Procedimiento para establecer el modo de seguridad](how-to-set-the-security-mode.md)
- [Procedimiento para especificar el tipo de credencial de cliente](how-to-specify-the-client-credential-type.md)
- [Procedimiento para restringir el acceso con la clase PrincipalPermissionAttribute](how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Procedimiento para suplantar a un cliente en un servicio](how-to-impersonate-a-client-on-a-service.md)
- [Procedimiento para examinar el contexto de seguridad](how-to-examine-the-security-context.md)
