---
title: Autenticación de Windows integrada con protección ampliada
ms.date: 03/30/2017
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
ms.openlocfilehash: d69471f4be0f102381dee4fc5037e8f8b0c625c3
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144856"
---
# <a name="integrated-windows-authentication-with-extended-protection"></a>Autenticación de Windows integrada con protección ampliada
Se han realizado mejoras que afectan al modo en que las clases <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream> y clases relacionadas del espacio de nombres <xref:System.Net> y espacios de nombres relacionados controlan la autenticación integrada de Windows. Se ha agregado compatibilidad para que la protección ampliada mejore la seguridad.  
  
 Estos cambios pueden afectar a las aplicaciones que usan estas clases para realizar solicitudes web y recibir respuestas donde se emplea la autenticación integrada de Windows. Este cambio también puede afectar a los servidores web y a las aplicaciones cliente configurados para usar autenticación integrada de Windows.  
  
 Estos cambios también pueden afectar a las aplicaciones que usan estas clases para realizar otros tipos de solicitudes y recibir respuestas donde se emplea la autenticación integrada de Windows.  
  
 Los cambios para admitir la protección ampliada solo están disponibles para las aplicaciones en Windows 7 y Windows Server 2008 R2. Las características de protección ampliada no están disponibles en versiones anteriores de Windows.  
  
## <a name="overview"></a>Información general  
 El diseño de la autenticación integrada de Windows permite que algunas respuestas de desafío de credenciales sean universales, lo que significa que se pueden volver a usar o reenviar. Las respuestas de desafío deben crearse como mínimo con información específica del destino y, preferiblemente, también con información específica del canal. Después, los servicios pueden proporcionar protección ampliada para asegurarse de que las respuestas de desafío de credenciales contengan información específica de servicio, como un nombre de entidad de seguridad de servicio (SPN). Con esta información en los intercambios de credenciales, los servicios pueden mejorar la protección contra el uso malintencionado de respuestas de desafío de credenciales que podrían haberse usado de forma inapropiada.  
  
 El diseño de protección ampliada es una mejora en los protocolos de autenticación diseñada para mitigar los ataques de retransmisión de autenticación. Está basada en el concepto de información de enlace de canal y servicio.  
  
 Los objetivos generales son los siguientes:  
  
1. Si el cliente está actualizado para admitir la protección ampliada, las aplicaciones deben proporcionar información de enlace de canal y servicio a todos los protocolos de autenticación admitidos. La información de enlace de canal solo se puede proporcionar cuando hay un canal (TLS) con el que enlazar. Siempre se debe proporcionar información de enlace de servicio.  
  
2. Los servidores actualizados que están configurados correctamente podrían comprobar la información de enlace de canal y servicio presente en el token de autenticación de cliente y rechazar el intento de autenticación si los enlaces de canal no coinciden. En función del escenario de implementación, los servidores podrían comprobar el enlace de canal, el enlace de servicio o ambos.  
  
3. Los servidores actualizados tienen la capacidad de aceptar o rechazar solicitudes de cliente de nivel inferior que no contienen la información de enlace de canal basada en la directiva.  
  
 La información que usa la protección ampliada está formada por uno de los elementos siguientes o por ambos:  
  
1. Un token de enlace de canal o CBT.  
  
2. Información de enlace de servicio en forma de nombre de entidad de seguridad de servicio o SPN.  
  
 La información de enlace de servicio es una indicación de la intención del cliente de autenticarse en un punto de conexión de servicio determinado. Se comunica del cliente al servidor con las propiedades siguientes:  
  
- El valor de SPN debe estar disponible para el servidor que realiza la autenticación de cliente en forma de texto no cifrado.  
  
- El valor de SPN es público.  
  
- El SPN se debe proteger criptográficamente durante el tránsito para que un ataque de tipo "Man in the middle" no pueda insertar, quitar o modificar su valor.  
  
 Un CBT es una propiedad del canal seguro exterior (por ejemplo, TLS) usado para relacionarlo (enlazarlo) con una conversación mediante un canal interno autenticado por el cliente. El CBT debe tener las propiedades siguientes (también definidas en la especificación RFC 5056 de IETF):  
  
- Cuando existe un canal externo, el valor del CBT debe ser una propiedad que identifique el canal externo o el punto de conexión del servidor, al que lleguen por separado la parte de cliente y la parte de servidor de una conversación.  
  
- El valor del CBT enviado por el cliente no debe poder verse afectado por un atacante.  
  
- No hay ninguna garantía de la confidencialidad del valor del CBT. Pero esto no significa que otro elemento diferente del servidor que realiza la autenticación pueda examinar siempre el valor de la información de enlace de servicio y de enlace de canal, ya que el protocolo que transporta el CBT podría llevar a cabo su cifrado.  
  
- La integridad del CBT se debe proteger criptográficamente durante el tránsito para que un atacante no pueda insertar, quitar o modificar su valor.  
  
 El enlace de canal lo lleva a cabo el cliente que realiza la transferencia del SPN y del CBT al servidor en un modo a prueba de manipulaciones. El servidor valida la información de enlace de canal según su directiva y rechaza los intentos de autenticación de los que no se considera el destino deseado. De esta manera, los dos canales se enlazan criptográficamente.  
  
 Para mantener la compatibilidad con los clientes y las aplicaciones existentes, puede configurarse un servidor de modo que permita los intentos de autenticación de los clientes que todavía no admiten la protección ampliada. Esto se conoce como una configuración "parcialmente protegida", en contraposición a una configuración "completamente protegida".  
  
 Varios componentes de los espacios de nombres <xref:System.Net> y <xref:System.Net.Security> realizan la autenticación integrada de Windows en nombre de una aplicación que llama. En esta sección se describen los cambios en los componentes de System.Net para agregar protección ampliada al uso de la autenticación integrada de Windows.  
  
 La protección ampliada es actualmente compatible con Windows 7. Se proporciona un mecanismo para que una aplicación pueda determinar si el sistema operativo admite la protección ampliada.  
  
## <a name="changes-to-support-extended-protection"></a>Cambios para admitir la protección ampliada  
 El proceso de autenticación usado con la autenticación integrada de Windows, según el protocolo de autenticación usado, suele incluir un desafío emitido por el equipo de destino y enviado de vuelta al equipo cliente. La protección ampliada agrega nuevas características a este proceso de autenticación.  
  
 El espacio de nombres <xref:System.Security.Authentication.ExtendedProtection> proporciona compatibilidad con la autenticación mediante la protección ampliada de las aplicaciones. La clase <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> de este espacio de nombres representa un enlace de canal. La clase <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> de este espacio de nombres representa la directiva de protección ampliada usada por el servidor para validar las conexiones de cliente entrantes. Se usan otros miembros de clase con la protección ampliada.  
  
 Para las aplicaciones de servidor, entre estas clases se incluyen las siguientes:  
  
 Una clase <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> que tiene los siguientes elementos:  
  
- Una propiedad <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A> que indica si el sistema operativo admite la autenticación integrada de Windows con la protección ampliada.  
  
- Valor <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> que indica cuándo debe exigirse la directiva de protección extendida.  
  
- Un valor <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> que indica el escenario de implementación. Esto influye en la manera en que se comprueba la protección ampliada.  
  
- Una clase <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> opcional que contiene la lista personalizada de SPN que se usa para comparar con el SPN proporcionado por el cliente como destino previsto de la autenticación.  
  
- Una clase <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> opcional que contiene un enlace de canal personalizado para usarlo para la validación. Este escenario no es habitual.  
  
 El espacio de nombres <xref:System.Security.Authentication.ExtendedProtection.Configuration> proporciona compatibilidad con la configuración de la autenticación mediante la protección ampliada de las aplicaciones.  
  
 Se ha realizado una serie de cambios en las características para admitir la protección ampliada en el espacio de nombres <xref:System.Net> existente. Estos cambios incluyen:  
  
- Una nueva clase <xref:System.Net.TransportContext> agregada al espacio de nombres <xref:System.Net> que representa un contexto de transporte.  
  
- Nuevos métodos de sobrecarga <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> y <xref:System.Net.HttpWebRequest.GetRequestStream%2A> en la clase <xref:System.Net.HttpWebRequest> que permiten recuperar la clase <xref:System.Net.TransportContext> para admitir la protección ampliada para las aplicaciones cliente.  
  
- Adiciones a las clases <xref:System.Net.HttpListener> y <xref:System.Net.HttpListenerRequest> para admitir aplicaciones de servidor.  
  
 Se ha realizado un cambio en las características para admitir la protección ampliada para las aplicaciones de cliente SMTP en el espacio de nombres <xref:System.Net.Mail> existente:  
  
- Una propiedad <xref:System.Net.Mail.SmtpClient.TargetName%2A> en la clase <xref:System.Net.Mail.SmtpClient> que representa el SPN que se va a usar para la autenticación cuando se emplea la protección ampliada para aplicaciones de cliente SMTP.  
  
 Se ha realizado una serie de cambios en las características para admitir la protección ampliada en el espacio de nombres <xref:System.Net.Security> existente. Estos cambios incluyen:  
  
- Nuevos métodos de sobrecarga <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> y <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> en la clase <xref:System.Net.Security.NegotiateStream> que permiten pasar un CBT para admitir la protección ampliada para las aplicaciones cliente.  
  
- Nuevos métodos de sobrecarga <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> y <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> en la clase <xref:System.Net.Security.NegotiateStream> que permiten pasar una clase <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> para admitir la protección ampliada para las aplicaciones de servidor.  
  
- Una nueva propiedad <xref:System.Net.Security.SslStream.TransportContext%2A> en la clase <xref:System.Net.Security.SslStream> para admitir la protección ampliada para las aplicaciones cliente y servidor.  
  
 Se ha agregado una propiedad <xref:System.Net.Configuration.SmtpNetworkElement> para admitir la configuración de la protección ampliada para los clientes SMTP en el espacio de nombres <xref:System.Net.Security>.  
  
## <a name="extended-protection-for-client-applications"></a>Protección ampliada para aplicaciones cliente  
 La compatibilidad con la protección ampliada tiene lugar de manera automática en la mayoría de las aplicaciones cliente. Las clases <xref:System.Net.HttpWebRequest> y <xref:System.Net.Mail.SmtpClient> admiten la protección ampliada siempre que la versión de Windows subyacente admita la protección ampliada. Una instancia <xref:System.Net.HttpWebRequest> envía un SPN construido a partir del <xref:System.Uri>. De forma predeterminada, una instancia <xref:System.Net.Mail.SmtpClient> envía un SPN construido a partir del nombre de host del servidor de correo SMTP.  
  
 Para una autenticación personalizada, las aplicaciones cliente pueden usar los métodos <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=nameWithType> o <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=nameWithType> en la clase <xref:System.Net.HttpWebRequest> que permiten recuperar la clase <xref:System.Net.TransportContext> y el CBT mediante el método <xref:System.Net.TransportContext.GetChannelBinding%2A>.  
  
 El SPN que se va a usar para la autenticación integrada de Windows enviado por una instancia <xref:System.Net.HttpWebRequest> a un servicio determinado se puede invalidar mediante el establecimiento de la propiedad <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A>.  
  
 Se puede usar la propiedad <xref:System.Net.Mail.SmtpClient.TargetName%2A> para establecer un SPN personalizado que se usará para la autenticación integrada de Windows para la conexión de SMTP.  
  
## <a name="extended-protection-for-server-applications"></a>Protección ampliada para aplicaciones de servidor  
 <xref:System.Net.HttpListener> proporciona automáticamente mecanismos para validar los enlaces de servicio al realizar la autenticación HTTP.  
  
 El escenario más seguro consiste en habilitar la protección ampliada para prefijos `HTTPS://`. En este caso, establezca <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> en <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> establecido en <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> o <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always>, y <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> establecido en <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Un valor de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> coloca <xref:System.Net.HttpListener> en modo parcialmente protegido, mientras que <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> se corresponde con el modo completamente protegido.  
  
 En esta configuración, cuando se realiza una solicitud al servidor a través de un canal seguro externo, se consulta el canal externo para un enlace de canal. Este enlace de canal se pasa a las llamadas SSPI de autenticación, que validan que el enlace de canal del blob de autenticación coincida. Existen tres resultados posibles:  
  
1. El sistema operativo subyacente del servidor no admite la protección ampliada. La solicitud no se expondrá a la aplicación y se devolverá al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
2. Se produce un error en la llamada SSPI y se indica que el cliente ha especificado un enlace de canal que no coincidía con el valor esperado recuperado del canal externo o bien que el cliente no ha proporcionado un enlace de canal al configurar para <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> la directiva de protección ampliada en el servidor. En ambos casos, la solicitud no se expondrá a la aplicación y se devolverá al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
3. El cliente especifica el enlace de canal correcto o se le permite conectarse sin especificar un enlace de canal, puesto que la directiva de protección ampliada en el servidor está configurada con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported>. La solicitud se devuelve a la aplicación para su procesamiento. No se realiza automáticamente la comprobación del nombre del servicio. Una aplicación puede decidir realizar su propia validación del nombre del servicio mediante la propiedad <xref:System.Net.HttpListenerRequest.ServiceName%2A>, pero en estos casos es redundante.  
  
 Si una aplicación realiza sus propias llamadas SSPI para realizar la autenticación basada en los blobs que se pasan dentro del cuerpo de una solicitud HTTP y quiere admitir el enlace de canal, deberá recuperar el enlace de canal esperado del canal seguro externo mediante <xref:System.Net.HttpListener> con el fin de pasarlo a la función nativa [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) de Win32. Para ello, use la propiedad <xref:System.Net.HttpListenerRequest.TransportContext%2A> y llame al método <xref:System.Net.TransportContext.GetChannelBinding%2A> para recuperar el CBT. Solo se admiten enlaces de punto de conexión. Si se especifica cualquier otro <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind.Endpoint>, se iniciará una <xref:System.NotSupportedException>. Si el sistema operativo subyacente admite el enlace de canal, el método <xref:System.Net.TransportContext.GetChannelBinding%2A> devolverá un <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding><xref:System.Runtime.InteropServices.SafeHandle> que encapsula un puntero en un enlace de canal adecuado para pasar a una función [AcceptSecurityContext](/windows/win32/api/sspi/nf-sspi-acceptsecuritycontext) como miembro pvBuffer de una estructura SecBuffer pasada en el parámetro `pInput`. La propiedad <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> contiene la longitud, en bytes, del enlace de canal. Si el sistema operativo subyacente no admite enlaces de canal, la función devolverá `null`.  
  
 Otro escenario posible es habilitar la protección ampliada para prefijos `HTTP://` cuando no se usan servidores proxy. En este caso, establezca <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=nameWithType> en <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> establecido en <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> o <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always>, y <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> establecido en <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario.TransportSelected>. Un valor de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported> coloca <xref:System.Net.HttpListener> en modo parcialmente protegido, mientras que <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always> se corresponde con el modo completamente protegido.  
  
 Se crea una lista predeterminada de nombres de servicio permitidos en función de los prefijos que se han registrado con <xref:System.Net.HttpListener>. Esta lista predeterminada se puede examinar mediante la propiedad <xref:System.Net.HttpListener.DefaultServiceNames%2A>. Si esta lista no es exhaustiva, una aplicación puede especificar una colección personalizada de nombres de servicio en el constructor para la clase <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>, que se usará en lugar de la lista predeterminada de nombres de servicio.  
  
 En esta configuración, cuando se realiza una solicitud al servidor sin un canal seguro externo, la autenticación se realiza normalmente sin llevar a cabo una comprobación del enlace de canal. Si la autenticación se realiza correctamente, se consulta el contexto para obtener el nombre de servicio que ha proporcionado el cliente y se valida con respecto a la lista de nombres de servicio aceptables. Existen cuatro resultados posibles:  
  
1. El sistema operativo subyacente del servidor no admite la protección ampliada. La solicitud no se expondrá a la aplicación y se devolverá al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
2. El sistema operativo subyacente del cliente no admite la protección ampliada. En la configuración <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.WhenSupported>, el intento de autenticación se realizará correctamente y la solicitud se devolverá a la aplicación. En la configuración <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement.Always>, se producirá un error en el intento de autenticación. La solicitud no se expondrá a la aplicación y se devolverá al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
3. El sistema operativo subyacente del cliente admite la protección ampliada, pero la aplicación no ha especificado un enlace de servicio. La solicitud no se expondrá a la aplicación y se devolverá al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
4. El cliente ha especificado un enlace de servicio. El enlace de servicio se compara con la lista de enlaces de servicio permitidos. Si coincide, la solicitud se devuelve a la aplicación. En caso contrario, la solicitud no se expondrá a la aplicación y se devolverá automáticamente al cliente una respuesta No autorizado (401). Se registrará un mensaje en el origen de seguimiento <xref:System.Net.HttpListener> con el motivo del error.  
  
 Si este método simple en el que se usa una lista permitida de nombres de servicio válidos resulta insuficiente, la aplicación puede proporcionar su propia validación del nombre del servicio consultando la propiedad <xref:System.Net.HttpListenerRequest.ServiceName%2A>. En los casos 1 y 2 anteriores, la propiedad devolverá `null`. En el caso 3, devolverá una cadena vacía. En el caso 4, se devolverá el nombre del servicio especificado por el cliente.  
  
 Estas características de protección ampliada también las pueden usar las aplicaciones de servidor para la autenticación con otros tipos de solicitudes y cuando se usan servidores proxy de confianza.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Authentication.ExtendedProtection>
- <xref:System.Security.Authentication.ExtendedProtection.Configuration>
