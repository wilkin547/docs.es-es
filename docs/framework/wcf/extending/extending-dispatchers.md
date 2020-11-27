---
title: Extensión de distribuidores
ms.date: 03/30/2017
helpviewer_keywords:
- dispatcher extensions [WCF]
ms.assetid: d0ad15ac-fa12-4f27-80e8-7ac2271e5985
ms.openlocfilehash: fa9d5c40c2ae813493b3643048fa7eaba00c431d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273235"
---
# <a name="extending-dispatchers"></a>Extensión de distribuidores

Los distribuidores son los responsables de extraer los mensajes entrantes de los canales subyacentes, de modo que los traducen en código de aplicación en las invocaciones de método y devuelven los resultados al autor de la llamada. Las extensiones de distribuidores le permiten modificar este procesamiento.  Puede implementar inspectores de parámetro o de mensaje que inspeccionen o modifiquen el contenido de los mensajes o los parámetros.  Puede cambiar la manera en la que se enrutan los mensajes a las operaciones o proporcionar otras funcionalidades.

En este tema se describe cómo utilizar <xref:System.ServiceModel.Dispatcher.DispatchRuntime> las <xref:System.ServiceModel.Dispatcher.DispatchOperation> clases y en una aplicación de servicio de Windows Communication Foundation (WCF) para modificar el comportamiento de ejecución predeterminado de un distribuidor o para interceptar o modificar mensajes, parámetros o valores devueltos antes o después de enviarlos o recuperarlos de la capa del canal. Para obtener más información sobre el procesamiento de mensajes en tiempo de ejecución de cliente equivalente, consulte [Extending](extending-clients.md)clients. Para comprender el rol que los <xref:System.ServiceModel.IExtensibleObject%601> tipos desempeñan en el acceso al estado compartido entre varios objetos de personalización en tiempo de ejecución, vea [objetos extensibles](extensible-objects.md).

## <a name="dispatchers"></a>Distribuidores

El nivel del modelo de servicios realiza la conversión entre el modelo de programación del programador y el intercambio de mensajes subyacentes, comúnmente denominado el nivel de canal. En WCF, los distribuidores de canal y punto de conexión ( <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> y <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> , respectivamente) son los componentes de servicio responsables de aceptar nuevos canales, recibir mensajes, operaciones de envío e invocación de operaciones y procesamiento de respuestas. Los objetos de distribuidor son objetos de receptor, pero las implementaciones de contratos de devolución de llamadas en servicios dúplex también exponen sus objetos de distribuidor para la inspección, modificación o extensión.

El distribuidor de canales (y <xref:System.ServiceModel.Channels.IChannelListener> complementario) extrae los mensajes del canal del subordinado y pasa los mensajes a sus distribuidores de extremos respectivos. Cada distribuidor de extremos tiene un <xref:System.ServiceModel.Dispatcher.DispatchRuntime> que enruta los mensajes a la <xref:System.ServiceModel.Dispatcher.DispatchOperation> adecuada, que es responsable de llamar al método que implementa la operación. Durante el proceso, se invocan varias clases de extensiones opcionales y obligatorias. En este tema se explica cómo encajan estas piezas, y cómo podría modificar las propiedades e introducir su propio código para extender la funcionalidad básica.

Las propiedades del distribuidor y los objetos de personalización modificados se insertan utilizando objetos de comportamiento de operación, servicio, punto de conexión, o contrato. En este tema no se describe cómo utilizar los comportamientos. Para obtener más información sobre los tipos que se usan para insertar modificaciones del distribuidor, vea [configurar y extender el Runtime con comportamientos](configuring-and-extending-the-runtime-with-behaviors.md).

El siguiente gráfico proporciona una vista de alto nivel de los elementos arquitectónicos de un servicio.

![La arquitectura para este tiempo de ejecución de envío.](./media/wcfc-dispatchruntimearchc.gif "wcfc_DispatchRuntimeArchc")

### <a name="channel-dispatchers"></a>Distribuidores de canal

Se crea un objeto <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> para asociar un <xref:System.ServiceModel.Channels.IChannelListener> de un URI determinado (denominado URI de escucha) a una instancia de un servicio. Cada objeto <xref:System.ServiceModel.ServiceHost> puede tener muchos objetos <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>, cada uno asociado a un solo agente de escucha y un URI de escucha. Cuando llega un mensaje, el objeto <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> consulta a cada uno de los objetos <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> asociados para saber si el extremo puede aceptar el mensaje, y pasa el mensaje a uno que pueda.

Todas las propiedades que controlan la duración y el comportamiento de una sesión de canal se pueden inspeccionar o modificar en el objeto <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>. Entre ellos se incluyen los inicializadores de canales personalizados, el agente de escuchas de canal, el host, el <xref:System.ServiceModel.InstanceContext>asociado, etc.

### <a name="endpoint-dispatchers"></a>Distribuidores de puntos de conexión

El objeto <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> es responsable de procesar los mensajes de un objeto <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> cuando la dirección de destino de un mensaje coincide con la propiedad <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> y la acción del mensaje coincide con la propiedad <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>. Si dos objetos <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> pueden aceptar un mensaje, el valor de la propiedad <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.FilterPriority%2A> determina el punto de conexión de mayor prioridad.

Utilice el <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> para adquirir los dos puntos de extensión de modelo de servicio principales, las clases <xref:System.ServiceModel.Dispatcher.DispatchRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchOperation>, que puede utilizar para personalizar el procesamiento del distribuidor. La clase <xref:System.ServiceModel.Dispatcher.DispatchRuntime> permite a los usuarios interceptar y extender el distribuidor en el ámbito del contrato (es decir, para todos los mensajes de un contrato). La clase <xref:System.ServiceModel.Dispatcher.DispatchOperation> permite a los usuarios interceptar y extender el distribuidor en un ámbito de operación (es decir, para todos los mensajes de una operación).

## <a name="scenarios"></a>Escenarios

Hay varias razones para extender el distribuidor:

- Validación personalizada del mensaje. Los usuarios pueden exigir que un mensaje sea válido para un determinado esquema. Esto se puede hacer implementando las interfaces del interceptor de mensajes. Para ver un ejemplo, consulte [inspectores de mensajes](../samples/message-inspectors.md).

- Registro personalizado de mensajes. Los usuarios pueden inspeccionar y registrar un conjunto de mensajes de la aplicación que fluyen a través de un punto de conexión. Esto también se puede lograr con las interfaces del interceptor de mensajes.

- Transformaciones personalizadas del mensaje. Los usuarios pueden aplicar ciertas transformaciones al mensaje en el runtime (por ejemplo, para el control de versiones). Esto también se puede lograr, de nuevo, con las interfaces del interceptor de mensajes.

- Modelo de datos personalizado. Los usuarios pueden tener un modelo de serialización de datos distinto de los que se admiten de forma predeterminada en WCF (es decir, <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> los mensajes, y sin formato). Esto se puede hacer implementando las interfaces del formateador de mensajes. Para obtener un ejemplo, vea [formateador de operaciones y selector de operaciones](../samples/operation-formatter-and-operation-selector.md).

- Validación personalizada de parámetros. Los usuarios pueden exigir que los parámetros con tipo sean válidos (por oposición a XML). Esto puede hacerse mediante las interfaces del inspector de parámetros.

- Distribución de operaciones personalizadas. Los usuarios pueden implementar la distribución en algo que no sea una acción; por ejemplo, en el elemento de cuerpo o en una propiedad de un mensaje personalizado. Esto se puede hacer mediante la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>. Para obtener un ejemplo, vea [formateador de operaciones y selector de operaciones](../samples/operation-formatter-and-operation-selector.md).

- Agrupación de objetos. Los usuarios pueden agrupar instancias en lugar de asignar una nueva instancia a cada llamada. Esto se puede implementar mediante las interfaces proveedoras de instancias. Para obtener un ejemplo, consulte [agrupación](../samples/pooling.md).

- Arrendamiento de instancias. Los usuarios pueden implementar un patrón de arrendamiento para la duración de instancias, similar al de .NET Framework Remoting. Esto se puede hacer mediante las interfaces de duración de contexto de instancias.

- Control de errores personalizado. Los usuarios pueden controlar cómo se procesan los errores locales y cómo se devuelven los errores a los clientes. Esto se puede implementar utilizando las interfaces <xref:System.ServiceModel.Dispatcher.IErrorHandler>.

- Comportamientos de autorización personalizados. Los usuarios pueden implementar un control de acceso personalizado extendiendo las partes en tiempo de ejecución de contratos u operaciones y agregando comprobaciones de seguridad basadas en los tokens presentes en el mensaje. Esto se puede lograr utilizando las interfaces del interceptor de mensajes o del interceptor de parámetros. Para obtener ejemplos, vea [extensibilidad de seguridad](../samples/security-extensibility.md).

  > [!CAUTION]
  > Dado que la modificación de las propiedades de seguridad tiene la posibilidad de poner en peligro la seguridad de las aplicaciones WCF, se recomienda encarecidamente realizar modificaciones relacionadas con la seguridad con cuidado y realizar pruebas exhaustivas antes de la implementación.

- Validadores personalizados de WCF en tiempo de ejecución. Puede instalar validadores personalizados que examinen servicios, contratos y enlaces para aplicar directivas de nivel empresarial con respecto a las aplicaciones WCF. (Por ejemplo, consulte [Cómo: bloquear puntos de conexión en la empresa](how-to-lock-down-endpoints-in-the-enterprise.md)).

### <a name="using-the-dispatchruntime-class"></a>Uso de la clase DispatchRuntime

Utilice la clase <xref:System.ServiceModel.Dispatcher.DispatchRuntime> para modificar el comportamiento predeterminado de punto de conexión individual o de servicio, o para insertar objetos que implementen modificaciones personalizadas en uno o ambos de los siguientes procesos de servicio (o procesos de cliente en el caso de un cliente dúplex):

- La transformación de mensajes entrantes en los objetos y la suelta de esos objetos como invocaciones de método en un objeto de servicio.

- La transformación de objetos recibidos de la respuesta a una invocación de operación de servicio en mensajes salientes.

<xref:System.ServiceModel.Dispatcher.DispatchRuntime> le permite interceptar y extender el canal o el distribuidor del extremo para todos los mensajes de un contrato determinado, incluso cuando no se reconoce un mensaje. Cuando llega un mensaje que no coincide con ningún mensaje declarado en el contrato, se envía a la operación devuelta por la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.UnhandledDispatchOperation%2A>. Para interceptar o extenderse por todos los mensajes de una operación determinada, vea la clase <xref:System.ServiceModel.Dispatcher.DispatchOperation>.

Hay cuatro áreas principales de extensibilidad del distribuidor expuestas por la clase <xref:System.ServiceModel.Dispatcher.DispatchRuntime>:

1. Los componentes de canal utilizan las propiedades de <xref:System.ServiceModel.Dispatcher.DispatchRuntime> y las del distribuidor del canal asociado devueltas por la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ChannelDispatcher%2A> para personalizar cómo el distribuidor del canal acepta y cierra los canales. Esta categoría incluye las propiedades <xref:System.ServiceModel.Dispatcher.ChannelDispatcher.ChannelInitializers%2A> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InputSessionShutdownHandlers%2A>.

2. Los componentes de mensaje se personalizan para cada mensaje procesado. Esta categoría incluye las propiedades <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>, <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A>, <xref:System.ServiceModel.Dispatcher.DispatchRuntime.Operations%2A> y <xref:System.ServiceModel.Dispatcher.ChannelDispatcher.ErrorHandlers%2A>.

3. Los componentes de instancia personalizan la creación, duración y eliminación de instancias del tipo de servicio. Para obtener más información acerca de la duración de los objetos de servicio, vea la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>. Esta categoría incluye las propiedades <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>.

4. Los componentes relacionados con seguridad pueden utilizar las propiedades siguientes:

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SecurityAuditLogLocation%2A> indica donde se escriben los eventos de auditoría.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ImpersonateCallerForAllOperations%2A> controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageAuthenticationAuditLevel%2A> controla si los eventos de autenticación de mensajes correctos se escriben en el registro de eventos especificado por <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SecurityAuditLogLocation%2A>.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.PrincipalPermissionMode%2A> controla cómo se establece la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A>.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ServiceAuthorizationAuditLevel%2A> especifica cómo se realiza la auditoría de eventos de autorización.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SuppressAuditFailure%2A> especifica si suprimir excepciones no críticas que producen durante el proceso del registro.

Normalmente, un comportamiento de servicio (un objeto que implementa <xref:System.ServiceModel.Dispatcher.DispatchRuntime>), un comportamiento de contrato (un objeto que implementa <xref:System.ServiceModel.Description.IServiceBehavior>) o un comportamiento de extremo (un objeto que implementa <xref:System.ServiceModel.Description.IContractBehavior>) pueden asignar objetos de extensión a una propiedad <xref:System.ServiceModel.Description.IEndpointBehavior> o insertarlos en una colección. Entonces, el objeto de comportamiento de instalación se agrega a la colección adecuada de comportamientos mediante programación o implementando un objeto <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> personalizado para permitir insertar el comportamiento con un archivo de configuración de la aplicación.

Los clientes dúplex (clientes que implementan un contrato de devolución de llamadas especificado por un servicio dúplex) también tienen un objeto <xref:System.ServiceModel.Dispatcher.DispatchRuntime> al que se puede obtener acceso usando la propiedad <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>.

### <a name="using-the-dispatchoperation-class"></a>Uso de la clase DispatchOperation

La clase <xref:System.ServiceModel.Dispatcher.DispatchOperation> es la ubicación para las modificaciones en tiempo de ejecución y el punto de inserción para las extensiones personalizadas cuyo ámbito es solo una operación de servicio. (Para modificar el comportamiento del tiempo de ejecución del servicio para todos los mensajes de un contrato, use la clase <xref:System.ServiceModel.Dispatcher.DispatchRuntime>.)

Instale las modificaciones de <xref:System.ServiceModel.Dispatcher.DispatchOperation> utilizando un objeto de comportamiento del servicio personalizado.

Use la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.Operations%2A> para buscar el objeto <xref:System.ServiceModel.Dispatcher.DispatchOperation> que representa una operación de servicio determinada.

Las siguientes propiedades controlan la ejecución en tiempo de ejecución en el nivel de operación:

- Las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.Action%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReplyAction%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.FaultContractInfos%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.IsOneWay%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.IsTerminating%2A> y <xref:System.ServiceModel.Dispatcher.DispatchOperation.Name%2A> obtienen los valores correspondientes para la operación.

- Las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.TransactionAutoComplete%2A> y <xref:System.ServiceModel.Dispatcher.DispatchOperation.TransactionRequired%2A> especifican el comportamiento de transacciones.

- Las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReleaseInstanceBeforeCall%2A> y <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReleaseInstanceAfterCall%2A> controlan la duración del objeto de servicio definido por el usuario relativo a <xref:System.ServiceModel.InstanceContext>.

- Las propiedades <xref:System.ServiceModel.Dispatcher.DispatchOperation.DeserializeRequest%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.SerializeReply%2A>y <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> habilitan el control explícito sobre la conversión de los mensajes en los objetos, y de los objetos en mensajes.

- La propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.Impersonation%2A> especifica el nivel de suplantación de la operación.

- La propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.CallContextInitializers%2A> inserta extensiones de contexto de llamada personalizadas para la operación.

- La propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.AutoDisposeParameters%2A> controla cuando se destruyen los objetos de parámetro.

- La propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.Invoker%2A> se usa para insertar un objeto autor de llamada personalizado.

- La propiedad <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A> permite insertar un inspector de parámetros personalizado que se puede utilizar para inspeccionar o modificar parámetros y valores devueltos.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Dispatcher.DispatchRuntime>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation>
- [Procedimiento para inspeccionar y modificar mensajes en el servicio](how-to-inspect-and-modify-messages-on-the-service.md)
- [Procedimiento para inspeccionar o modificar parámetros](how-to-inspect-or-modify-parameters.md)
- [Procedimiento para bloquear puntos de conexión en la empresa](how-to-lock-down-endpoints-in-the-enterprise.md)
