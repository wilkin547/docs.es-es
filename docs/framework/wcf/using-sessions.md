---
title: Uso de sesiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sessions [WCF]
ms.assetid: 864ba12f-3331-4359-a359-6d6d387f1035
ms.openlocfilehash: 42159b3871d974e53751468b422cbe9f72b6f908
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273690"
---
# <a name="using-sessions"></a>Uso de sesiones

En las aplicaciones Windows Communication Foundation (WCF), una *sesión* correlaciona un grupo de mensajes en una conversación. Las sesiones de WCF son diferentes del objeto de sesión disponible en las aplicaciones de ASP.NET, admiten diferentes comportamientos y se controlan de maneras diferentes. En este tema se describen las características que habilitan las sesiones en las aplicaciones WCF y cómo usarlas.  
  
## <a name="sessions-in-windows-communication-foundation-applications"></a>Sesiones en aplicaciones de Windows Communication Foundation  

 Cuando un contrato de servicio especifica que requiere una sesión, ese contrato está especificando que todas las llamadas (es decir, los intercambios de mensajes subyacentes que admiten las llamadas) deben formar parte de la misma conversación. Si un contrato especifica que admite sesiones pero no requiere una, los clientes pueden conectarse y establecer o no una sesión. Si la sesión finaliza y se envía un mensaje se envía a través del mismo canal, se produce una excepción.  
  
 Las sesiones de WCF tienen las siguientes características conceptuales principales:  
  
- La aplicación (el cliente WCF) que realiza la llamada inicia y finaliza explícitamente las sesiones.  
  
- Los mensajes entregados durante una sesión se procesan en el orden de recepción.  
  
- Las sesiones correlacionan un grupo de mensajes en una conversación. Son posibles distintos tipos de correlaciones. Por ejemplo, un canal basado en sesión puede correlacionar mensajes basados en una conexión de red compartida, mientras que otro canal basado en sesión puede correlacionar mensajes basados en una etiqueta compartida en el cuerpo del mensaje. Las características que se pueden derivar a partir de la sesión dependen de la naturaleza de la correlación.  
  
- No hay ningún almacén de datos general asociado a una sesión de WCF.  
  
 Si está familiarizado con la <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> clase en las aplicaciones de ASP.net y la funcionalidad que proporciona, podría observar las siguientes diferencias entre ese tipo de sesión y las sesiones de WCF:  
  
- Las sesiones de ASP.NET siempre se inician en el servidor.  
  
- Las sesiones de ASP.NET no están ordenadas de forma implícita.  
  
- Las sesiones de ASP.NET proporcionan un mecanismo de almacenamiento de datos general entre las solicitudes.  
  
 En este tema se describe:  
  
- El comportamiento de ejecución predeterminado al utilizar enlaces basados en sesión en el nivel de modelo de servicio.  
  
- Los tipos de características que proporcionan los enlaces basados en sesión WCF y proporcionados por el sistema.  
  
- Cómo crear un contrato que declare un requisito de sesión.  
  
- Cómo entender y controlar la creación y finalización de la sesión y la relación de la sesión con la instancia del servicio.  
  
## <a name="default-execution-behavior-using-sessions"></a>Comportamiento de ejecución predeterminado mediante sesiones  

 Un enlace que intenta iniciar una sesión se denomina enlace *basado en sesión* . Los contratos de servicio especifican que requieren, permiten o rechazan enlaces basados en sesión estableciendo la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> en la interfaz (o clase) del contrato de servicio en uno de los valores de enumeración del <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> . De forma predeterminada, el valor de esta propiedad es <xref:System.ServiceModel.SessionMode.Allowed> , lo que significa que si un cliente utiliza un enlace basado en sesión con una implementación de servicio WCF, el servicio establece y utiliza la sesión proporcionada.  
  
 Cuando un servicio WCF acepta una sesión de cliente, las características siguientes están habilitadas de forma predeterminada:  
  
1. Todas las llamadas entre un objeto de cliente de WCF se administran mediante la misma instancia de servicio.  
  
2. Los distintos enlaces basados en sesión proporcionan características adicionales.  
  
## <a name="system-provided-session-types"></a>Tipos de sesión proporcionados por el sistema  

 Un enlace basado en sesión admite la asociación predeterminada de una instancia de servicio con una sesión determinada. Sin embargo, diferentes enlaces basados en sesión admiten distintas características además de habilitar el control de creación de instancias basadas en sesión descrito anteriormente.  
  
 WCF proporciona los siguientes tipos de comportamiento de la aplicación basada en sesión:  
  
- El <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType> admite sesiones basadas en seguridad, en las que ambos extremos de la comunicación han acordado una conversación segura concreta. Para obtener más información, vea [proteger los servicios](securing-services.md). Por ejemplo, el enlace <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType> , que admite sesiones de seguridad y sesiones confiables, solo utiliza de forma predeterminada una sesión segura que cifra y firma digitalmente los mensajes.  
  
- El enlace <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType> admite las sesiones basadas en TCP/IP para asegurarse de que todos los mensajes están correlacionados por la conexión en el nivel de socket.  
  
- El elemento <xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType> , que implementa la especificación de WS-ReliableMessaging, proporciona la compatibilidad para las sesiones confiables en las que los mensajes se pueden configurar para que se entreguen en orden y solo una vez, asegurando que los mensajes se reciban aunque estos viajen por varios nodos durante la conversación. Para obtener más información, vea [sesiones confiables](./feature-details/reliable-sessions.md).  
  
- El enlace <xref:System.ServiceModel.NetMsmqBinding?displayProperty=nameWithType> proporciona sesiones de datagrama de MSMQ. Para obtener más información, vea [colas en WCF](./feature-details/queues-in-wcf.md).  
  
 Establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> no especifica el tipo de sesión que el contrato requiere, solo que requiere uno.  
  
## <a name="creating-a-contract-that-requires-a-session"></a>Creación de un contrato que requiere una sesión  

 La creación de un contrato que requiere una sesión hace que el grupo de operaciones que declara el contrato de servicio deba ejecutarse dentro de la misma sesión y que los mensajes deban entregarse en orden. Para validar el nivel de compatibilidad de la sesión que requiere un contrato de servicio, establezca la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> de su clase o interfaz de contrato de servicio en el valor de la enumeración <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> para especificar si el contrato:  
  
- Requiere una sesión.  
  
- Permite a un cliente establecer una sesión.  
  
- Prohíbe una sesión.  
  
 Establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> no especifica, sin embargo, el tipo de comportamiento basado en sesión que requiere el contrato. Indica a WCF que confirme en tiempo de ejecución que el enlace configurado (que crea el canal de comunicación) para el servicio, no o puede establecer una sesión al implementar un servicio. De nuevo, el enlace puede satisfacer ese requisito con cualquier tipo de comportamiento basado en sesión que elija: seguridad, transporte, confiable o alguna combinación. El comportamiento exacto depende del valor de la enumeración <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType> seleccionada. Si el enlace configurado del servicio no cumple con el valor de <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A>, se produce una excepción. Los enlaces, y los canales que esos enlaces crean, que admiten sesiones se dice que son basados en sesión.  
  
 El siguiente contrato de servicio especifica que todas las operaciones de la `ICalculatorSession` se deben intercambiar dentro de una sesión. Ninguna de las operaciones devuelve un valor al llamador, salvo el método `Equals` . Sin embargo, el método `Equals` no toma ningún parámetro y, por consiguiente, solo puede devolver un valor distinto de cero dentro de una sesión en la que los datos ya se han pasado a otras operaciones. Este contrato requiere que una sesión funcione correctamente. Si no hay una sesión asociada a un cliente concreto, la instancia del servicio no tiene forma de saber qué datos anteriores ha enviado este cliente.  
  
 [!code-csharp[S_Service_Session#1](../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
 Si un servicio permite una sesión, se establece una sesión y se utiliza si el cliente inicia una; de lo contrario, no se establece ninguna sesión.  
  
## <a name="sessions-and-service-instances"></a>Sesiones e instancias de servicios  

 Si utiliza el comportamiento de creación de instancias predeterminado en WCF, la misma instancia de servicio administra todas las llamadas entre un objeto de cliente de WCF. Por consiguiente, en el nivel de aplicación, puede considerar una sesión como la habilitación de un comportamiento de aplicación similar al comportamiento de la llamada local. Por ejemplo, al crear un objeto local:  
  
- Se llama a un constructor.  
  
- La misma instancia de objeto procesa todas las llamadas subsiguientes realizadas a la referencia de objeto de cliente de WCF.  
  
- Se llama a un destructor cuando se destruye la referencia del objeto.  
  
 Las sesiones habilitan un comportamiento similar entre clientes y servicios, siempre que se utilice el comportamiento de instancia de servicio predeterminado. Si un contrato de servicio requiere o admite sesiones, se pueden marcar una o más operaciones del contrato como que inician o finalizan una sesión estableciendo las propiedades <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A> y <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A> .  
  
 Las *operaciones de inicio* son aquellas que deben llamarse como la primera operación de una nueva sesión. Las operaciones que no son de inicio sólo pueden llamarse después de que se haya llamado, al menos, a una operación de inicio. Puede crear, por consiguiente, un tipo de constructor de sesión para su servicio mediante la declaración de operaciones de inicio diseñadas para tomar entradas de clientes apropiadas para el inicio de la instancia de servicio. (Sin embargo, el estado se asocia a la sesión, y no el objeto de servicio).  
  
 Las *operaciones de finalización*, por el contrario, son aquellas a las que se debe llamar como el último mensaje de una sesión existente. En el caso predeterminado, WCF recicla el objeto de servicio y su contexto después de que se cierre la sesión a la que se asoció el servicio. Por consiguiente, puede crear un tipo de destructor declarando operaciones de finalización diseñadas para realizar una función adecuada al final de la instancia de servicio.  
  
> [!NOTE]
> Aunque el comportamiento predeterminado se parece algo a los constructores y destructores locales, solo es eso, un parecido. Cualquier operación de servicio de WCF puede ser una operación de inicio o de finalización, o ambas al mismo tiempo. Además, en el caso predeterminado, las operaciones de inicio pueden llamarse cualquier número de veces en cualquier orden; no se crean sesiones adicionales una vez que se establezca la sesión y se asocie a una instancia, a menos que controle explícitamente la duración de la instancia del servicio (manipulando el objeto <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> ). Finalmente, el estado se asocia a la sesión y no al objeto de servicio.  
  
 Por ejemplo, el `ICalculatorSession` contrato utilizado en el ejemplo anterior requiere que el objeto de cliente de WCF llame primero `Clear` a la operación antes que a cualquier otra operación y que la sesión con este objeto de cliente de WCF debe finalizar cuando llame a la `Equals` operación. El ejemplo de código siguiente muestra un contrato que aplica estos requisitos. Se debe llamar primero a`Clear` para iniciar una sesión y esa sesión finaliza cuando se llama a `Equals` .  
  
 [!code-csharp[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.isinitiatingisterminating/cs/service.cs#1)]
 [!code-vb[SCA.IsInitiatingIsTerminating#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.isinitiatingisterminating/vb/service.vb#1)]  
  
 Los servicios no inician sesiones con clientes. En las aplicaciones cliente de WCF, existe una relación directa entre la duración del canal basado en sesión y la duración de la propia sesión. Como tal, los clientes crean nuevas sesiones creando nuevos canales basados en sesión y acaban con las sesiones existentes cerrando correctamente los canales basados en sesión. Un cliente inicia una sesión con un extremo de servicio llamando a uno de los siguientes métodos:  
  
- <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en el canal devuelto por una llamada a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> en el objeto de cliente de WCF generado por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
- Una operación de inicio en cualquier tipo de objeto de cliente de WCF (de forma predeterminada, todas las operaciones se están iniciando). Cuando se llama a la primera operación, el objeto de cliente de WCF abre automáticamente el canal e inicia una sesión.  
  
 Por lo general, un cliente finaliza una sesión con un extremo de servicio llamando a uno de los siguientes métodos:  
  
- <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> en el canal devuelto por una llamada a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>.  
  
- <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType> en el objeto de cliente de WCF generado por Svcutil.exe.  
  
- Una operación de finalización en cualquier tipo de objeto de cliente de WCF (de forma predeterminada, no se terminan las operaciones; el contrato debe especificar explícitamente una operación de finalización). Cuando se llama a la primera operación, el objeto de cliente de WCF abre automáticamente el canal e inicia una sesión.  
  
 Para obtener ejemplos, consulte [How to: Create a Service That Requires Sessions](./feature-details/how-to-create-a-service-that-requires-sessions.md) , así como los ejemplos de [Default Service Behavior](./samples/default-service-behavior.md) y [Instancing](./samples/instancing.md) .  
  
 Para obtener más información acerca de los clientes y las sesiones, consulte [acceso a servicios mediante un cliente WCF](./feature-details/accessing-services-using-a-client.md).  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Las sesiones interactúan con la configuración de InstanceContext  

 Hay una interacción entre la enumeración de <xref:System.ServiceModel.SessionMode> en un contrato y la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> , que controla la asociación entre canales y objetos de servicio concretos. Para obtener más información, vea [sesiones, creación de instancias y simultaneidad](./feature-details/sessions-instancing-and-concurrency.md).  
  
### <a name="sharing-instancecontext-objects"></a>Uso compartido de objetos InstanceContext  

 También puede controlar qué canal basado en sesión o llamada se asocia a qué objeto <xref:System.ServiceModel.InstanceContext> realizando esa asociación usted mismo.
  
## <a name="sessions-and-streaming"></a>Sesiones y transmisión por secuencias  

 Si tiene una gran cantidad de datos para transferir, el modo de transferencia de streaming en WCF es una alternativa factible al comportamiento predeterminado de almacenar en búfer y procesar los mensajes en memoria en su totalidad. Puede obtener un comportamiento inesperado al transmitir mediante secuencias las llamadas con un enlace basado en sesión. Todas las llamadas de transferencias por secuencias se realizan a través de un canal único (el canal del datagrama) que no admite sesiones incluso si el enlace utilizado esté configurado para utilizar sesiones. Si varios clientes realizan llamadas de transferencias por secuencias al mismo objeto de servicio sobre un enlace basado en sesión y el modo de simultaneidad del objeto de servicio se ha establecido como Single y su modo de contexto de instancia está establecido en `PerSession`, todas las llamadas deben pasar por el canal de datagrama y, por lo tanto, solo se procesa una llamada al mismo tiempo. Uno o más clientes pueden agotar el tiempo de espera. Puede solucionar este problema estableciendo el objeto de servicio `InstanceContextMode` en `PerCall` o la simultaneidad en múltiple.  
  
> [!NOTE]
> MaxConcurrentSessions no influye en este caso porque solo hay una "sesión" disponible.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationContractAttribute.IsInitiating%2A>
- <xref:System.ServiceModel.OperationContractAttribute.IsTerminating%2A>
