---
title: Acceso a los servicios utilizando un cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c8329832-bf66-4064-9034-bf39f153fc2d
ms.openlocfilehash: d136e094e4f1ea5258ff568527d10ac25a38f1a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293967"
---
# <a name="accessing-services-using-a-client"></a>Acceso a los servicios utilizando un cliente

Las aplicaciones cliente deben crear, configurar y usar objetos de cliente o de canal de WCF para comunicarse con los servicios. El tema [información general del cliente de WCF](../wcf-client-overview.md) proporciona información general sobre los objetos y los pasos necesarios para crear objetos de cliente y de canal básicos y usarlos.  
  
 Este tema proporciona información detallada sobre algunos de los problemas surgidos en las aplicaciones cliente y clientes y objetos de canal que pueden ser útiles en función de su escenario.  
  
## <a name="overview"></a>Información general  

 Este tema describe el comportamiento y problemas relacionados con:  
  
- Canal y duraciones de la sesión.  
  
- Control de excepciones  
  
- Entender los problemas que ocasionan el bloqueo.  
  
- Inicializar los canales interactivamente .  
  
### <a name="channel-and-session-lifetimes"></a>Duración de canales y sesiones  

 Las aplicaciones de Windows Communication Foundation (WCF) incluyen dos categorías de canales, datagrama y con sesión.  
  
 Un canal de *datagrama* es un canal en el que todos los mensajes no están correlacionados. Con un canal de datagrama, si una operación de entrada o de salida produce un error, normalmente la operación siguiente no estará afectada y se puede reutilizar el mismo canal. Por ello, normalmente, los canales de datagrama no producen errores.  
  
 Los canales con *sesión* , sin embargo, son canales con una conexión al otro extremo. Los mensajes de una sesión en un lado siempre están correlacionados con la misma sesión en el otro lado. Además, para que se considere correcta está sesión, ambos participantes de una sesión deben coincidir en que los requisitos de su conversación se han cumplido. Si no pueden coincidir, el canal con sesión puede producir un error.  
  
 Abra explícitamente o implícitamente los clientes llamando a la primera operación.  
  
> [!NOTE]
> Generalmente, intentar detectar explícitamente los canales con sesión en los cuales se ha producido un error no es útil, porque cuando se notifica depende de la implementación de la sesión. Por ejemplo, dado que <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> (con la sesión de confianza deshabilitada) emerge la sesión de la conexión TCP, si escucha el evento <xref:System.ServiceModel.ICommunicationObject.Faulted?displayProperty=nameWithType> en el servicio o el cliente, probablemente, usted será notificado de forma rápida en caso de un error en la red. Pero las sesiones de confianza (establecidas por enlaces en los que <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> está habilitado) están diseñadas para aislar a los servicios de los errores de red pequeños. Si se puede restablecer la sesión dentro de un período razonable de tiempo, el mismo enlace, configurado para sesiones de confianza, no podría producir un error hasta que la interrupción continuara durante un período más largo de tiempo.  
  
 La mayoría de los enlaces proporcionados por el sistema (qué exponen canales al nivel de aplicación) utiliza sesiones de forma predeterminada, pero <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> no. Para obtener más información, vea [usar sesiones](../using-sessions.md).  
  
### <a name="the-proper-use-of-sessions"></a>El uso apropiado de sesiones  

 Las sesiones proporcionan una manera de conocer si todo el intercambio de mensajes ha finalizado, y si ambos lados lo consideraran correcto. Se recomienda que una aplicación que realiza la llamada abra el canal, lo utilice y cierre el canal dentro de un bloque try. Si un canal de sesión está abierto, y se llama al método <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> una vez y esa llamada se devuelve correctamente, a continuación, la sesión se ha completado correctamente. Correctamente en este caso significa que todas las garantías de entrega especificadas por el enlace se cumplieron y que el otro lado no llamó <xref:System.ServiceModel.ICommunicationObject.Abort%2A?displayProperty=nameWithType> en el canal antes de llamar <xref:System.ServiceModel.ICommunicationObject.Close%2A>.  
  
 La sección siguiente proporciona un ejemplo de este enfoque del cliente.  
  
### <a name="handling-exceptions"></a>Controlar las excepciones  

 Administrar las excepciones en las aplicaciones cliente es sencillo. Si se abre, se utiliza y se cierra un canal dentro de un bloque try, la conversación ha se ha completado correctamente, a menos que se produzca una excepción. En general, si se produce una excepción se anula la conversación.  
  
> [!NOTE]
> No se recomienda el uso de la `using` instrucción ( `Using` en Visual Basic). Esto es debido a que el fin de la instrucción `using` puede producir excepciones que pueden enmascarar otras excepciones que usted pueden necesitar conocer. Para obtener más información, vea [usar Close y Abort para liberar los recursos de cliente de WCF](../samples/use-close-abort-release-wcf-client-resources.md).  
  
 El ejemplo de código siguiente muestra el patrón del cliente recomendado mediante un try/bloque catch y no la instrucción `using`.  
  
 [!code-csharp[FaultContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
> [!NOTE]
> Comprobar el valor de la propiedad <xref:System.ServiceModel.ICommunicationObject.State%2A?displayProperty=nameWithType> es una condición de carrera y no se recomienda para determinar si reutilizar o cerrar un canal.  
  
 Los canales de datagrama nunca producen errores, incluso si se producen excepciones cuando se cierran. Además, los clientes no dúplex que no se autentican mediante una conversación segura, normalmente, inician <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>. Sin embargo, si el cliente dúplex que utiliza una conversación segura no se autentica, el cliente recibe en su lugar <xref:System.TimeoutException?displayProperty=nameWithType>.  
  
 Para obtener información más completa sobre cómo trabajar con información de error en el nivel de aplicación, vea [especificar y controlar errores en contratos y servicios](../specifying-and-handling-faults-in-contracts-and-services.md). [Excepciones esperadas](../samples/expected-exceptions.md) describe las excepciones esperadas y muestra cómo controlarlas. Para obtener más información sobre cómo controlar los errores al desarrollar canales, vea [controlar excepciones y errores](../extending/handling-exceptions-and-faults.md).  
  
### <a name="client-blocking-and-performance"></a>Bloqueo de clientes  y rendimiento  

 Cuando una aplicación llama sincrónicamente a una operación de solicitud-respuesta, el cliente se bloquea hasta que se reciba un valor devuelto o se produzca una excepción (como un <xref:System.TimeoutException?displayProperty=nameWithType>). Este comportamiento es similar al comportamiento local. Cuando una aplicación invoca sincrónicamente una operación en un objeto o canal de cliente WCF, el cliente no devuelve hasta que la capa del canal pueda escribir los datos en la red o hasta que se produzca una excepción. Y mientras el patrón de intercambio de mensaje unidireccional (especificado marcando una operación con <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> establecida en `true`) puede hacer que algunos clientes sean más receptivos, las operaciones unidireccionales también se pueden bloquear, dependiendo del enlace y de los mensajes que ya se han enviado. Las operaciones unidireccionales son solo sobre intercambio de mensajes, nada más y nada menos. Para obtener más información, vea [servicios unidireccionales](one-way-services.md).  
  
 Los fragmentos de datos grandes pueden desacelerar el procesamiento del cliente, independientemente del patrón de intercambio de mensajes. Para entender cómo administrar estos problemas, consulte [datos y streaming de gran tamaño](large-data-and-streaming.md).  
  
 Si la aplicación debe hacer más trabajo mientras se completa una operación, debe crear un par de métodos asincrónicos en la interfaz del contrato de servicio que implementa el cliente de WCF. La forma más fácil de hacerlo es usar el `/async` modificador en la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Para obtener un ejemplo, consulte [Cómo: llamar a las operaciones de servicio de forma asincrónica](how-to-call-wcf-service-operations-asynchronously.md).  
  
 Para obtener más información sobre cómo aumentar el rendimiento del cliente, consulte [aplicaciones cliente de nivel intermedio](middle-tier-client-applications.md).  
  
### <a name="enabling-the-user-to-select-credentials-dynamically"></a>Permitir que el usuario seleccione credenciales dinámicamente  

 La interfaz <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> permite a las aplicaciones mostrar una interfaz de usuario que permite al usuario elegir credenciales con las que crear un canal antes del inicio de los temporizadores de tiempo de espera.  
  
 Hay dos maneras con las que los desarrolladores de aplicaciones pueden hacer uso de un <xref:System.ServiceModel.Dispatcher.IInteractiveChannelInitializer> insertado. La aplicación cliente puede llamar a <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o a una versión asincrónica) antes de abrir el canal (el enfoque *explícito* ) o llamar a la primera operación (el enfoque *implícito* ).  
  
 Si se utiliza el enfoque implícito, la aplicación debe llamar a la primera operación en una extensión de <xref:System.ServiceModel.ClientBase%601> o <xref:System.ServiceModel.IClientChannel>. Si no llama a la primera operación, se inicia una excepción.  
  
 Si se utiliza el enfoque explícito, la aplicación debe realizar los pasos siguientes en orden:  
  
1. Llamar a <xref:System.ServiceModel.ClientBase%601.DisplayInitializationUI%2A?displayProperty=nameWithType> o a <xref:System.ServiceModel.IClientChannel.DisplayInitializationUI%2A?displayProperty=nameWithType> (o una versión asincrónica).  
  
2. Cuando se hayan devuelto los inicializadores, llamar al método <xref:System.ServiceModel.ICommunicationObject.Open%2A> en el objeto <xref:System.ServiceModel.IClientChannel> o en el objeto <xref:System.ServiceModel.IClientChannel> devuelto de la propiedad <xref:System.ServiceModel.ClientBase%601.InnerChannel%2A?displayProperty=nameWithType>.  
  
3. Llame a las operaciones.  
  
 Se recomienda que las aplicaciones de calidad de producción controlen el proceso de la interfaz del usuario mediante el enfoque explícito.  
  
 Las aplicaciones que utilizan el enfoque implícito invocan los inicializadores de la interfaz de usuario, pero si el usuario de la aplicación no responde dentro del plazo de tiempo de espera de envío del enlace, se inicia una excepción cuando se devuelve la interfaz de usuario.  
  
## <a name="see-also"></a>Vea también

- [Servicios dúplex](duplex-services.md)
- [Procedimiento para obtener acceso a los servicios con contratos unidireccionales y de solicitud-respuesta](how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [Procedimiento para obtener acceso a los servicios con un contrato dúplex](how-to-access-services-with-a-duplex-contract.md)
- [Procedimiento para obtener acceso a un servicio WSE 3.0](how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [Procedimiento para usar ChannelFactory](how-to-use-the-channelfactory.md)
- [Procedimiento para llamar a operaciones de servicio de forma asincrónica](how-to-call-wcf-service-operations-asynchronously.md)
- [Aplicaciones cliente de nivel intermedio](middle-tier-client-applications.md)
