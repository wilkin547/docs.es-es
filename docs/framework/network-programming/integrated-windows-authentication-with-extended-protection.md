---
title: "Autenticaci&#243;n de Windows integrada con protecci&#243;n ampliada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Autenticaci&#243;n de Windows integrada con protecci&#243;n ampliada
Las mejoras se crearon esa afecta a cómo la autenticación de Windows integrada controla <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpListener>, <xref:System.Net.Mail.SmtpClient>, <xref:System.Net.Security.SslStream>, <xref:System.Net.Security.NegotiateStream>, y las clases relacionadas en <xref:System.Net> y los espacios de nombres relacionados.  Compatibilidad se agregó para que la protección extendida extiende seguridad.  
  
 Estos cambios pueden afectar a las aplicaciones que utilizan estas clases para hacer solicitudes web y recibir respuestas donde se utiliza la autenticación de Windows integrada.  Este cambio también puede afectar a los servidores web y las aplicaciones cliente que se configuran para usar la autenticación de Windows integrada.  
  
 Estos cambios también pueden afectar a las aplicaciones que utilizan estas clases para que otros tipos de solicitudes y recibir respuestas donde se utiliza la autenticación de Windows integrada.  
  
 Los cambios para admitir la protección ampliada solo están disponibles para las aplicaciones en Windows 7 y Windows Server 2008 R2.  Las características de protección extendidas no están disponibles en versiones anteriores de Windows.  
  
## Información general  
 El diseño de la autenticación integrada de Windows permite que algunas respuestas de desafío de credenciales sean universales, indicando que se pueden volver a usar o reenviar.  Las respuestas de desafío deben construir en un mínimo con información específica del destino y preferiblemente también cierta información específica del canal.  Los servicios pueden proporcionar protección extendida para garantizar que las respuestas credenciales de desafío contienen información específica del servicio como una entidad de seguridad Name \(SPN\) del servicio.  Con esta información en los intercambios credenciales, los servicios pueden proteger mejor contra el uso malintencionado de las respuestas credenciales de desafío que podrían incorrectamente haberse utilizadas.  
  
 El diseño extendido de protección es un aumento a los protocolos de autenticación diseñados para mitigar los ataques de retransmitir de autenticación.  Gira en el concepto de canal y de información de enlace del servicio.  
  
 Los objetivos totales son los siguientes:  
  
1.  Si se actualiza el cliente para admitir la protección ampliada, las aplicaciones deben proporcionar un enlace de canal e información de enlace del servicio para todos los protocolos de autenticación admitidos.  Información de enlace de canal puede proporcionarse cuando existe un canal \(TLS\) para enlazar a.  Información de enlace de servicio debe proporcionarse siempre.  
  
2.  Los servidores actualizados configurados correctamente pueden comprobar el canal y la información de enlace del servicio cuando está presente en el token de autenticación del cliente y rechazar el intento de autenticación si no coinciden los enlaces de canal.  Dependiendo del escenario de implementación, los servidores pueden comprobar el enlace de canal, el enlace de servicio o ambos.  
  
3.  Los servidores actualizados tienen la capacidad de aceptar o rechazar las solicitudes de cliente de nivel inferior que no contienen información de enlace de canal según la directiva.  
  
 La información utilizada por la protección extendida consta de una o ambas de las dos partes siguientes:  
  
1.  Un token de canal o un CBT de enlace.  
  
2.  Mantener la información de enlace en forma de entidad de seguridad Name o SPN Service.  
  
 Información de enlace de servicio es una indicación del intento de un cliente de autenticar a un extremo de servicio determinado.  Se comunica de cliente al servidor con las propiedades siguientes:  
  
-   El valor de SPN debe estar disponible el servidor que realiza la autenticación del cliente en forma de texto no cifrado.  
  
-   El valor de SPN es público.  
  
-   El SPN se debe proteger criptográficamente en tránsito tales que un ataque de tipo " Man in the middle " no se puede insertar, quitar o modificar su valor.  
  
 Un CBT es una propiedad de canal seguro externo \(como TLS\) utilizado para atarlo \(enlace\) a una conversación sobre un canal interno, cliente\- autenticado.  El CBT debe tener las siguientes propiedades \(también definidas por IETF RFC 5056\):  
  
-   Cuando existe un canal externo, el valor del CBT debe ser una propiedad que identifica tanto el canal externo o extremo del servidor, llegar independientemente por los extremos de cliente y servidor de una conversación.  
  
-   El valor del CBT enviada por el cliente no debería ser similar que un atacante puede influir en.  
  
-   No se crea ninguna garantías sobre la confidencialidad del valor del CBT.  Esto sin embargo no significa que el valor del enlace de servicio así como la información de enlace de canal se puede examinar siempre por cualquier otra pero el servidor que realiza la autenticación, como el protocolo que tarda el CBT puede cifrarlo.  
  
-   El CBT debe ser criptográficamente integridad protegida en tránsito tales que un atacante no puede insertar, quitar o modificar su valor.  
  
 El enlace de canal es realizado por el cliente que transfiere el SPN y el CBT al servidor en un modo inalterable.  El servidor valida la información de enlace de canal de acuerdo con la directiva y rechaza los intentos de autenticación para los que no se cree que haberse el destino deseado.  De esta manera, los dos canales se enlaza criptográficamente conjuntamente.  
  
 Para mantener la compatibilidad con clientes existentes y aplicaciones, un servidor puede configurarse para permitir que los intentos de autenticación por los clientes que no admiten la protección extendida.  Esto se conoce como configuración “parcialmente endurecida”, a diferencia de una configuración “totalmente endurecida”.  
  
 Varios componentes en <xref:System.Net> y espacios de nombres de <xref:System.Net.Security> realizan la autenticación de Windows integrada en nombre de una aplicación de llamada.  Esta sección describe los cambios en los componentes de System.Net para agregar protección extendida en el uso de la autenticación de Windows integrada.  
  
 Protección extendida se admite actualmente en Windows 7.  Se proporciona un mecanismo para que una aplicación puede determinar si el sistema operativo admite la protección extendida.  
  
## Cambios para admitir Protección extendida  
 El proceso de autenticación utilizado con la autenticación de Windows integrada, dependiendo del protocolo de autenticación utilizado, incluye a menudo un desafío emitido por el equipo de destino y el posterior enviado al equipo cliente.  Protección extendida agrega nuevas características a este proceso de autenticación  
  
 El espacio de nombres <xref:System.Security.Authentication.ExtendedProtection> proporciona compatibilidad con la autenticación mediante la protección extendida de las aplicaciones.  La clase de <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> en este espacio de nombres representa un enlace de canal.  La clase de <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> en este espacio de nombres representa la directiva extendida de protección utilizada por el servidor para validar las conexiones de cliente entrantes.  Utilizan a otros miembros de clase con la protección ampliada.  
  
 Para las aplicaciones de servidor, estas clases incluyen:  
  
 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> que tiene los elementos siguientes:  
  
-   Una propiedad de <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A> que indica si el sistema operativo admite la autenticación de windows integrada con la protección ampliada.  
  
-   Valor de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> que indica cuándo debe aplicarse la directiva de protección extendida.  
  
-   Un valor de <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> que indica el escenario de implementación.  Esto influye cómo se comprueba la protección extendida.  
  
-   <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> opcional que contiene custom SPN muestra que se utiliza para comparar el SPN proporcionado por el cliente como destino previsto de la autenticación.  
  
-   <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> opcional que contiene un enlace personalizado de canal para utilizar para la validación.  Este escenario no es un caso común  
  
 El espacio de nombres <xref:System.Security.Authentication.ExtendedProtection.Configuration> proporciona compatibilidad con la configuración de autenticación mediante la protección extendida de las aplicaciones.  
  
 Varios cambios de características se realizaron para admitir la protección ampliada del espacio de nombres existente de <xref:System.Net> .  Estos cambios incluyen:  
  
-   Una nueva clase de <xref:System.Net.TransportContext> agregada al espacio de nombres <xref:System.Net> que representa un contexto de transporte.  
  
-   Nuevo <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> y métodos de la sobrecarga de <xref:System.Net.HttpWebRequest.GetRequestStream%2A> en la clase de <xref:System.Net.HttpWebRequest> que permiten el recuperar de <xref:System.Net.TransportContext> para admitir la protección ampliada para aplicaciones cliente.  
  
-   Adiciones a las clases de <xref:System.Net.HttpListener> y de <xref:System.Net.HttpListenerRequest> para admitir aplicaciones de servidor.  
  
 Un cambio de características se realizó para admitir la protección ampliada para aplicaciones cliente de SMTP en el espacio de nombres existente de <xref:System.Net.Mail> :  
  
-   Una propiedad de <xref:System.Net.Mail.SmtpClient.TargetName%2A> en la clase de <xref:System.Net.Mail.SmtpClient> que representa el SPN para utilizar para la autenticación al utilizar extended protección para aplicaciones cliente de SMTP.  
  
 Varios cambios de características se realizaron para admitir la protección ampliada del espacio de nombres existente de <xref:System.Net.Security> .  Estos cambios incluyen:  
  
-   Nuevo <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> y los métodos de la sobrecarga de <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> en <xref:System.Net.Security.NegotiateStream> ordenan que permiten la transferencia de un CBT para admitir la protección ampliada para aplicaciones cliente.  
  
-   Nuevo <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> y los métodos de la sobrecarga de <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> en <xref:System.Net.Security.NegotiateStream> ordenan que permiten la transferencia de <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> para admitir la protección ampliada para aplicaciones de servidor.  
  
-   Una nueva propiedad de <xref:System.Net.Security.SslStream.TransportContext%2A> en la clase de <xref:System.Net.Security.SslStream> para admitir la protección ampliada para las aplicaciones cliente y servidor.  
  
 Una propiedad de <xref:System.Net.Configuration.SmtpNetworkElement> se agregó a la configuración admiten la protección extendida para los clientes de SMTP en el espacio de nombres <xref:System.Net.Security> .  
  
## Protección extendida para aplicaciones cliente  
 Compatibilidad extendido de protección para la mayoría de las aplicaciones cliente se produce automáticamente.  Compatibilidad de las clases de <xref:System.Net.HttpWebRequest> y de <xref:System.Net.Mail.SmtpClient> extendidas protección siempre que la versión de Windows subyacente admita la protección extendida.  Una instancia de <xref:System.Net.HttpWebRequest> envía un SPN construido de <xref:System.Uri>.  De forma predeterminada, una instancia de <xref:System.Net.Mail.SmtpClient> envía un SPN construido del nombre de host del servidor de correo SMTP.  
  
 Para la autenticación personalizada, las aplicaciones cliente pueden utilizar <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=fullName> o métodos de <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=fullName> en <xref:System.Net.HttpWebRequest> ordenan que permiten el recuperar de <xref:System.Net.TransportContext> y el CBT mediante el método de <xref:System.Net.TransportContext.GetChannelBinding%2A> .  
  
 El SPN a utilizar para la autenticación de Windows integrada enviada por una instancia de <xref:System.Net.HttpWebRequest> a un servicio determinado puede invalidarse estableciendo la propiedad de <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> .  
  
 La propiedad de <xref:System.Net.Mail.SmtpClient.TargetName%2A> se puede utilizar para establecer una personalizada SPN para utilizar para la autenticación de Windows integrada para la conexión de SMTP.  
  
## Protección extendida para aplicaciones de servidor  
 <xref:System.Net.HttpListener> automáticamente proporciona mecanismos para validar los enlaces de servicio al realizar la autenticación de HTTP.  
  
 El escenario más segura es habilitar la protección extendida para los prefijos de HTTPS:\/\/.  En este caso, establezca <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> a <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> establecido en <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> o a <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>, y <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> establecido en el valor de <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> A de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> coloca <xref:System.Net.HttpListener> en modo parcialmente endurecido, mientras que <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> corresponde al modo totalmente endurecido.  
  
 En esta configuración cuando una solicitud se hace al servidor a través de un canal seguro exterior, el canal externo se consulta para un enlace de canal.  Este enlace de canal se pasa a las llamadas de la SSPI de autenticación, que validan que coincide con el enlace de canal en el objeto binario de autenticación.  Hay tres posibles resultados:  
  
1.  El sistema operativo subyacente de servidor no admite la protección extendida.  La solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
2.  La llamada de la SSPI produce un error que indica que el cliente solicitó un enlace de canal que no coincide con el valor esperado recuperado de canal externo o el cliente podría no para proporcionar un enlace de canal cuando la directiva extendida de protección en el servidor se configuró para <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>.  En ambos casos, la solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
3.  El cliente especifica el enlace correcto de canal o se permite conectar sin especificar un enlace de canal desde la directiva extendida de protección en el servidor se configura con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> The que la solicitud se devuelve a la aplicación para procesar.  No se realiza ninguna comprobación del nombre del servicio automáticamente.  Una aplicación puede elegir para realizar su propia validación del nombre del servicio utilizando la propiedad de <xref:System.Net.HttpListenerRequest.ServiceName%2A> , pero en estas circunstancias es redundante.  
  
 Si una aplicación realiza sus propias llamadas de la SSPI para realizar la autenticación basada en objetos binarios pasó de uno a otro en el cuerpo de una solicitud HTTP y deseos el admiten el enlace de canal, es necesario recuperar el enlace esperado del canal de canal seguro externo mediante <xref:System.Net.HttpListener> transferirlos a [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) la función de Win32 nativas.  Para ello, utilice la propiedad de <xref:System.Net.HttpListenerRequest.TransportContext%2A> y llame al método de <xref:System.Net.TransportContext.GetChannelBinding%2A> para recuperar el CBT.  Solo se admiten los enlaces de extremo.  Si se especifica nada otro <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind> , <xref:System.NotSupportedException> se producirá.  Si la del sistema operativo subyacente canalizan el enlace, el método de <xref:System.Net.TransportContext.GetChannelBinding%2A> devolverá <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding><xref:System.Runtime.InteropServices.SafeHandle> que contiene un puntero a enlazar el canal adecuado para que el [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) paso funcione como miembro de pvBuffer de una estructura de SecBuffer pasada en el parámetro de `pInput` .  La propiedad de <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> contiene la longitud, en bytes, del enlace de canal.  Si el sistema operativo subyacente no admite enlaces de canal, la función devolverá `null`.  
  
 Otro escenario posible es habilitar la protección extendida para los prefijos de HTTP:\/\/ a los servidores proxy no se utilizan.  En este caso, establezca <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> a <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> con <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> establecido en <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> o a <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>, y <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> establecido en el valor de <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> A de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> coloca <xref:System.Net.HttpListener> en modo parcialmente endurecido, mientras que <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> corresponde al modo totalmente endurecido.  
  
 Una lista predeterminada de nombres permitidos del servicio se crea en función de los prefijos registrados con <xref:System.Net.HttpListener>.  Este predeterminados la lista puede examinar mediante la propiedad de <xref:System.Net.HttpListener.DefaultServiceNames%2A> .  Si ésta no es completa, una aplicación puede especificar una colección de nombre de servicio personalizado en el constructor para la clase de <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> que se utilizará en lugar de la lista de nombres predeterminada del servicio.  
  
 En esta configuración, cuando una solicitud se hace al servidor sin ingresos externos desde una autenticación de canal seguro normalmente sin una comprobación de enlace de canal.  Si la autenticación se realiza correctamente, el contexto se consulta para el nombre del servicio al que el cliente proporcionado y validó en la lista de nombres aceptados del servicio.  Hay cuatro posibles resultados:  
  
1.  El sistema operativo subyacente de servidor no admite la protección extendida.  La solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
2.  El sistema operativo subyacente del cliente no admite la protección extendida.  En la configuración de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> , el intento de autenticación se realizará correctamente y la solicitud volverá a la aplicación.  En la configuración de <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> , el intento de autenticación no se realizará correctamente.  La solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
3.  La del sistema operativo subyacente de cliente extendidas protección, pero no especificó un enlace de servicio.  La solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
4.  El cliente solicitó un enlace de servicio.  El enlace de servicio se compara con la lista de enlaces permitidos del servicio.  Si coincide, la solicitud se devuelve a la aplicación.  Si no, la solicitud no se exponga a la aplicación, y \(401\) respuestas no autorizada automáticamente se devuelve al cliente.  Un mensaje se registrará el origen de traza de <xref:System.Net.HttpListener> que especifica la razón del error.  
  
 Si este enfoque simple mediante una lista permitida de nombres aceptados de servicio no es suficiente, una aplicación puede proporcionar una validación del nombre de servicio consultando la propiedad de <xref:System.Net.HttpListenerRequest.ServiceName%2A> .  En los casos 1 y 2 anterior, la propiedad devolverá `null`.  En caso de que 3, se devuelve una cadena vacía.  En caso de que 4, el nombre del servicio especificado por el cliente son devueltos.  
  
 Estas características de protección extendidas también se pueden utilizar en aplicaciones de servidor para la autenticación con otros tipos de solicitudes y cuando se utilizan los servidores proxy de confianza.  
  
## Vea también  
 <xref:System.Security.Authentication.ExtendedProtection>   
 <xref:System.Security.Authentication.ExtendedProtection.Configuration>