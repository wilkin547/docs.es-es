---
title: Selección de tipos de credenciales
description: Obtenga información sobre las credenciales, cómo se usan en WCF y cómo seleccionar la credencial adecuada para que la aplicación establezca una identidad o funcionalidad reclamada.
ms.date: 03/30/2017
ms.assetid: bf707063-3f30-4304-ab53-0e63413728a8
ms.openlocfilehash: c5a47bf95ab8e22cda1beb7eeca7cb77bfc2a169
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253978"
---
# <a name="selecting-a-credential-type"></a>Selección de tipos de credenciales

Las *credenciales* son el Windows Communication Foundation de datos (WCF) que usa para establecer una identidad reclamada o capacidades. Por ejemplo, una contraseña es una credencial que un gobierno emite para demostrar la ciudadanía en un país o región. En WCF, las credenciales pueden adoptar muchas formas, como los tokens de nombre de usuario y los certificados X. 509. En este tema se describen las credenciales, cómo se usan en WCF y cómo seleccionar las credenciales adecuadas para la aplicación.  
  
 En muchos países y regiones, un permiso de conducir es un ejemplo de credencial. Un permiso de conducir contiene datos que representan la identidad de una persona y su capacitación. Contiene prueba de posesión en forma de la imagen del poseedor. Una entidad emisora de confianza emite las licencias, normalmente, un departamento gubernamental de licencias. Se sella la licencia, que puede contener un holograma, que muestra que no se ha manipulado o falsificado.  
  
 La presentación de una credencial implica la presentación de los datos y de la prueba de posesión de los datos. WCF admite una variedad de tipos de credenciales en los niveles de seguridad de transporte y de mensaje. Por ejemplo, considere dos tipos de credenciales que se admiten en WCF: el nombre de usuario y las credenciales de certificado (X. 509).  
  
 Para la credencial del nombre de usuario, el nombre de usuario representa la identidad exigida y la contraseña proporciona la prueba de posesión. La autoridad de confianza en este caso es el sistema que valida el nombre de usuario y la contraseña.  
  
 Con una credencial de certificado X. 509, el nombre del firmante, el nombre alternativo del firmante o los campos específicos dentro del certificado se pueden usar como notificaciones de identidad, mientras que otros campos, como los `Valid From` `Valid To` campos y, especifican la validez del certificado.  
  
## <a name="transport-credential-types"></a>Tipos de credencial de transporte  

 La tabla siguiente muestra los posibles tipos de credenciales de cliente que pueden ser utilizadas por un enlace en modo de seguridad de transporte. Cuando se crea un servicio, establezca la propiedad `ClientCredentialType` en uno de estos valores para especificar el tipo de credencial que el cliente debe proporcionar con el fin de comunicarse con su servicio. Puede establecer los tipos en código o archivos de configuración.  
  
|Configuración|Descripción|  
|-------------|-----------------|  
|None|Especifica que el cliente no necesita presentar ningún credencial. Realiza una conversión a un cliente anónimo.|  
|Básico|Especifica la autenticación básica para el cliente. Para obtener más información, vea RFC2617:[autenticación http: autenticación básica e implícita](ftp://ftp.rfc-editor.org/in-notes/rfc2617.txt).|  
|Digest|Especifica la autenticación implícita para el cliente. Para obtener más información, vea RFC2617:[autenticación http: autenticación básica e implícita](ftp://ftp.rfc-editor.org/in-notes/rfc2617.txt).|  
|Ntlm|Especifica protocolo de autenticación de Windows NT LAN Manager (NTLM). Se utiliza esto cuando, por algún motivo, no puede utilizar la autenticación Kerberos. También puede deshabilitar su uso como reserva si establece la <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> propiedad en `false` , lo que hace que WCF realice el mejor esfuerzo para producir una excepción si se usa NTLM. Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.|  
|Windows|Especifica la autenticación de Windows. Para especificar solo el protocolo Kerberos en un dominio de Windows, establezca la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> en `false` (el valor predeterminado es `true`).|  
|Certificado|Realiza la autenticación del cliente mediante un certificado X.509.|  
|Contraseña|El usuario debe proporcionar un nombre de usuario y una contraseña. Valide el par nombre de usuario/contraseña mediante autenticación de Windows u otra solución personalizada.|  
  
### <a name="message-client-credential-types"></a>Tipos de credencial de cliente de mensaje  

 La tabla siguiente muestra los posibles tipos de credencial que puede utilizar al crear una aplicación que utiliza el modo de seguridad de mensaje. Puede utilizar estos valores en código o archivos de configuración.  
  
|Configuración|Descripción|  
|-------------|-----------------|  
|None|Especifica que el cliente no necesita presentar una credencial. Realiza una conversión a un cliente anónimo.|  
|Windows|Permite que se produzcan los intercambios del mensaje SOAP bajo el contexto de seguridad establecido con una credencial de Windows.|  
|Nombre de usuario|Permite al servicio requerir que el cliente se autentique con una credencial de nombre de usuario. Tenga en cuenta que WCF no permite ninguna operación criptográfica con nombres de usuario, como generar una firma o cifrar datos. WCF garantiza que el transporte está protegido cuando se usan credenciales de nombre de usuario.|  
|Certificado|Permite que el servicio exija la autenticación del cliente mediante un certificado X.509.|  
|Token emitido|Un tipo de token personalizado configurado según una directiva de seguridad. El tipo de token predeterminado es Lenguaje de marcado de aserción de seguridad (SAML). Un servicio de token seguro emite el token. Para obtener más información, vea [Federación y tokens emitidos](federation-and-issued-tokens.md).|  
  
### <a name="negotiation-model-of-service-credentials"></a>Modelo de negociación de credenciales de servicio  

 La *negociación* es el proceso por el que se establece la confianza entre un cliente y un servicio mediante el intercambio de credenciales. El proceso se realiza de forma iterativa entre el cliente y el servicio, con el fin de divulgar solo la información necesaria para el paso siguiente en el proceso de la negociación. En la práctica, el resultado final es la entrega de un credencial de servicio al cliente que se utilizará en operaciones posteriores.  
  
 Con una excepción, de forma predeterminada, los enlaces proporcionados por el sistema en WCF negocian la credencial de servicio automáticamente al usar la seguridad de nivel de mensaje. (La excepción es <xref:System.ServiceModel.BasicHttpBinding> , que no habilita la seguridad de forma predeterminada). Para deshabilitar este comportamiento, vea <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> las <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> propiedades y.  
  
> [!NOTE]
> Cuando se usa la seguridad SSL con .NET Framework 3,5 y versiones posteriores, un cliente de WCF usa ambos certificados intermedios en su almacén de certificados y los certificados intermedios recibidos durante la negociación SSL para realizar la validación de la cadena de certificados en el certificado del servicio. .NET Framework 3.0 solo usa los certificados intermedios instalados en el almacén de certificados local.  
  
#### <a name="out-of-band-negotiation"></a>Negociación fuera de banda  

 Si la negociación automática está deshabilitada, la credencial de servicio se debe aprovisionar al cliente antes de enviar mensaje al servicio. Esto también se conoce como aprovisionamiento *fuera de banda* . Por ejemplo, si el tipo de credencial especificado es un certificado, y la negociación automática está deshabilitada, el cliente se debe ponerse en contacto con el propietario del servicio para recibir e instalar el certificado en el equipo que ejecuta la aplicación cliente. Se puede hacer, por ejemplo, cuando se desea controlar de forma estricta qué clientes pueden tener acceso a un servicio en un escenario entre empresas. Esta negociación fuera de banda se puede realizar en el correo electrónico y el certificado X. 509 se almacena en el almacén de certificados de Windows, utilizando una herramienta como el complemento certificados de Microsoft Management Console (MMC).  
  
> [!NOTE]
> La propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> se utiliza para proporcionar al servicio un certificado logrado a través de la negociación fuera de banda. Esto es necesario cuando se utiliza la clase <xref:System.ServiceModel.BasicHttpBinding> porque el enlace no permite la negociación automatizada. La propiedad también se utiliza en un escenario dúplex no correlacionado. Éste es un escenario donde un servidor envía un mensaje al cliente sin exigir al cliente que envíe primero una solicitud al servidor. Dado que el servidor no tiene una solicitud del cliente, debe utilizar el certificado del cliente para cifrar el mensaje al cliente.  
  
## <a name="setting-credential-values"></a>Configurar los valores de credenciales  

 Cuando selecciona un modo de seguridad, debe especificar las credenciales reales. Por ejemplo, si el tipo de credencial se establece para "certificado", a continuación, debe asociar una credencial específica (como un certificado X.509 específico) al servicio o cliente.  
  
 Según si está programando un servicio o un cliente, el método para establecer el valor de credencial difiere ligeramente.  
  
### <a name="setting-service-credentials"></a>Establecer credenciales de servicio  

 Si está usando el modo de transporte, y está usando HTTP como el transporte, debe usar Internet Information Services (IIS) o configurar el puerto con un certificado. Para obtener más información, vea [información general sobre la seguridad de transporte](transport-security-overview.md) y seguridad de [transporte http](http-transport-security.md).  
  
 Para proporcionar un servicio con credenciales en código, cree una instancia de la clase <xref:System.ServiceModel.ServiceHost> y especifique la credencial adecuada utilizando la clase <xref:System.ServiceModel.Description.ServiceCredentials>, a la cual se puede obtener acceso a través de la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
#### <a name="setting-a-certificate"></a>Establecer un certificado  

 Para proporcionar un servicio con un certificado X.509 que utilizará para autenticar el servicio a los clientes, utilice el método <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>.  
  
 Para proporcionar un servicio con un certificado de cliente, utilice el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>.  
  
#### <a name="setting-windows-credentials"></a>Configurar las credenciales de Windows.  

 Si el cliente especifica un nombre de usuario y contraseña válidos, esa credencial se utiliza para autenticar el cliente. De lo contrario, se utilizan las credenciales de usuario actualmente conectado.  
  
### <a name="setting-client-credentials"></a>Configurar las credenciales de cliente  

 En WCF, las aplicaciones cliente usan un cliente WCF para conectarse a los servicios. Cada cliente deriva a partir de la clase <xref:System.ServiceModel.ClientBase%601> y la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> en el cliente permite la especificación de varios valores de credenciales de cliente.  
  
#### <a name="setting-a-certificate"></a>Establecer un certificado  

 Para proporcionar un servicio con un certificado X.509 utilizado para autenticar el cliente a un servicio, utilice el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
## <a name="how-client-credentials-are-used-to-authenticate-a-client-to-the-service"></a>Cómo se utilizan las credenciales de cliente para autenticar un cliente al servicio  

 Se proporciona la información de credenciales de cliente exigida para comunicarse con un servicio utilizando la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> o la propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A>. El canal de seguridad utiliza esta información para autenticar el cliente al servicio. La autenticación se logra a través de uno de estos dos modos:  
  
- Las credenciales de cliente se utilizan una vez antes de que se envíe el primer mensaje, utilizando la instancia de cliente de WCF para establecer un contexto de seguridad. Todos los mensajes de la aplicación se protegen a continuación a través del contexto de seguridad.  
  
- Las credenciales del cliente se utilizan para autenticar cada mensaje de la aplicación enviado al servicio. En este caso, no se establece ningún contexto entre el cliente y el servicio.  
  
### <a name="established-identities-cannot-be-changed"></a>No se pueden cambiar las identidades establecidas  

 Cuando se utiliza el primer método, el contexto establecido está asociado permanentemente a la identidad del cliente. Es decir, una vez se ha establecido el contexto de seguridad, no se puede cambiar la identidad asociada al cliente.  
  
> [!IMPORTANT]
> Hay una situación que conviene tener en cuenta, que es cuando no se puede intercambiar la identidad (es decir, cuando el establecimiento del contexto de seguridad está activado, que es el comportamiento predeterminado). Si crea un servicio que se comunica con un segundo servicio, no se puede cambiar la identidad utilizada para abrir el cliente de WCF en el segundo servicio. Esto es un problema si varios clientes pueden utilizar el primer servicio y el servicio suplanta a los clientes cuando tiene acceso al segundo servicio. Si el servicio reutiliza el mismo cliente para todos los autores de llamadas, todas las llamadas al segundo servicio se hacen bajo la identidad del primer autor de llamada que se utilizó para abrir el cliente al segundo servicio. En otras palabras, el servicio utiliza la identidad del primer cliente para que todos sus clientes se comuniquen con el segundo servicio. Esto puede llevar a la elevación de privilegios. Si éste no es el comportamiento deseado de su servicio, debe seguir a cada autor de llamada y crear un nuevo cliente al segundo servicio para cada autor de llamada distinto y asegurarse de que el servicio utiliza solo el cliente correcto para que el autor de llamada se comunique con el segundo servicio.  
  
 Para obtener más información sobre las credenciales y las sesiones seguras, vea [consideraciones de seguridad para las sesiones seguras](security-considerations-for-secure-sessions.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverMsmq.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A?displayProperty=nameWithType>
- [Conceptos de seguridad](security-concepts.md)
- [Protección de servicios y clientes](securing-services-and-clients.md)
- [Programación de la seguridad de WCF](programming-wcf-security.md)
- [Seguridad de transporte HTTP](http-transport-security.md)
