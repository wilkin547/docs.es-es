---
title: Procedimientos recomendados para la comunicación en cola
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], best practices
- best practices [WCF], queued communication
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
ms.openlocfilehash: 412b30a497fcf4c341f80a64c76fcbbc425e70b2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247452"
---
# <a name="best-practices-for-queued-communication"></a>Procedimientos recomendados para la comunicación en cola

En este tema se proporcionan los procedimientos recomendados para la comunicación en cola en Windows Communication Foundation (WCF). Las secciones siguientes discuten los procedimientos recomendados desde una perspectiva del escenario.  
  
## <a name="fast-best-effort-queued-messaging"></a>Mensajería en cola rápida y eficiente  

 Para los escenarios que requieren la separación que proporciona la mensajería en cola y una mensajería rápida y de alto rendimiento con garantías de optimización, utilice una cola no transaccional y establezca la propiedad <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> en `false`.  
  
 Además, puede decidir no incurrir en el costo de escrituras en disco estableciendo la propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> en `false`.  
  
 La seguridad afecta al rendimiento. Para obtener más información, consulte [consideraciones de rendimiento](performance-considerations.md).  
  
## <a name="reliable-end-to-end-queued-messaging"></a>Mensajería en cola fiable de un extremo a otro  

 Las secciones siguientes describen los procedimientos recomendados para escenarios que requieren una mensajería fiable de un extremo a otro.  
  
### <a name="basic-reliable-transfer"></a>Transferencia fiable básica  

 Para obtener una fiabilidad de un extremo a otro, establezca la propiedad <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> en `true` para asegurar la transferencia. La propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> puede establecerse en `true` o `false` en función de sus requisitos (el valor predeterminado es `true`). Generalmente, la propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> está establecida en `true` como parte de la fiabilidad de un extremo a otro. El compromiso es proporcionar un costo de rendimiento, pero hace el mensaje durable para que no se pierda el mensaje si un administrador de cola se bloquea.  
  
### <a name="use-of-transactions"></a>Uso de transacciones  

 Debe usar transacciones para garantizar la confiabilidad de un extremo a otro. Las garantías de`ExactlyOnce` solo aseguran que los mensajes se entreguen a la cola de destino. Para garantizar que se reciba el mensaje, utilice transacciones. Sin transacciones, si el servicio se bloquea, pierde el mensaje que se entrega pero realmente se entrega a la aplicación.  
  
### <a name="use-of-dead-letter-queues"></a>Uso de colas de mensajes no enviados  

 Las colas de mensajes no enviados aseguran que reciba una notificación si no se pudo entregar un mensaje a la cola de destino. Puede utilizar la cola de mensajes no enviados proporcionada por el sistema o una cola de mensajes no enviados personalizada. En general, utilizar una cola de mensajes no enviados personalizada es mejor porque le permite enviar mensajes no enviados de una aplicación en una cola de mensajes no enviados única. De lo contrario, todos los mensajes no enviados que ocurran para todas las aplicaciones que se ejecuten en el sistema se entregan a una cola única. Cada aplicación debe buscar a continuación en la cola de mensajes no enviados para encontrar los mensajes no enviados pertinentes para esa aplicación. A veces, utilizar una cola de mensajes no enviados personalizada no es factible, como cuando se usa MSMQ 3.0.  
  
 No se recomienda desactivar las colas de mensajes no enviados para la comunicación fiable de un extremo a otro.  
  
 Para obtener más información, consulte [uso de colas de Dead-Letter para controlar los errores de transferencia de mensajes](using-dead-letter-queues-to-handle-message-transfer-failures.md).  
  
### <a name="use-of-poison-message-handling"></a>Uso de control de mensajes dudosos  

 El control de mensajes dudosos proporciona la capacidad de recuperarse del error de procesamiento de mensajes.  
  
 Al utilizar la característica de control de mensajes dudosos, asegúrese de que la propiedad <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> está establecida en el valor adecuado. Establecerla en <xref:System.ServiceModel.ReceiveErrorHandling.Drop> implica que los datos se pierdan. Por otro lado, establecerla en <xref:System.ServiceModel.ReceiveErrorHandling.Fault> produce un error en el host de servicios cuando detecta un mensaje dudoso. Utilizar MSMQ 3.0, <xref:System.ServiceModel.ReceiveErrorHandling.Fault> es la mejor opción para evitar la pérdida de datos y quitar el mensaje dudoso. Con MSMQ 4.0, <xref:System.ServiceModel.ReceiveErrorHandling.Move> es el enfoque recomendado. <xref:System.ServiceModel.ReceiveErrorHandling.Move> mueve un mensaje dudoso fuera de la cola para que el servicio pueda continuar procesando los nuevos mensajes. El servicio del mensaje dudoso puede procesar a continuación el mensaje dudoso por separado.  
  
 Para obtener más información, vea [control de mensajes dudosos](poison-message-handling.md).  
  
## <a name="achieving-high-throughput"></a>Obtener un alto rendimiento  

 Para lograr un alto rendimiento en un solo punto de conexión, utilice lo siguiente:  
  
- Procesamiento por lotes con transacciones El procesamiento por lotes con transacciones garantiza que muchos mensajes se puedan leer en una transacción única. Esto optimiza las confirmaciones de transacciones, aumentando el rendimiento total. El costo del procesamiento por lotes es que si se produce un error en un mensaje único dentro de un lote, se deshace el lote completo y se deben procesar los mensajes de uno en uno hasta que sea seguro de nuevo el procesamiento por lotes. En la mayoría de los casos, los mensajes dudosos son raros, así que el procesamiento por lotes es la forma preferida de aumentar el rendimiento del sistema, particularmente cuando se tienen otros administradores de recursos que participan en la transacción. Para obtener más información, consulte [procesamiento por lotes de mensajes en una transacción](batching-messages-in-a-transaction.md).  
  
- Simultaneidad. La simultaneidad aumenta el rendimiento, pero también afecta a la contención a los recursos compartidos. Para obtener más información, vea [Concurrency](../samples/concurrency.md).  
  
- Limitación de peticiones. Para un rendimiento óptimo, limite el número de mensajes en el conductor del distribuidor. Para obtener un ejemplo de cómo hacerlo, consulte [limitación](../samples/throttling.md).  
  
 Al utilizar el procesamiento por lotes, sea consciente que la simultaneidad y la limitación de peticiones se traducen en los lotes simultáneos.  
  
 Para lograr un mayor rendimiento y disponibilidad, use una granja de servicios WCF que lean desde la cola. Esto requiere que todos estos servicios expongan el mismo contrato en el mismo extremo. El enfoque del conjunto funciona mejor para las aplicaciones que tienen tasas altas de producción de mensajes porque permite a varios servicios que lean desde la misma cola.  
  
 Al utilizar los conjuntos, sea consciente de que MSMQ 3.0 no admite las lecturas con transacciones remotas. MSMQ 4.0 admite las lecturas con transacciones remotas.  
  
 Para obtener más información, consulte [procesamiento por lotes de mensajes en una transacción](batching-messages-in-a-transaction.md) y [diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
## <a name="queuing-with-unit-of-work-semantics"></a>Puesta en cola con la unidad de semántica de trabajo  

 En algunos escenarios un grupo de mensajes en una cola se puede relacionar y, por consiguiente, la clasificación de estos mensajes es significativa. En tales escenarios, procese juntos un grupo de mensajes relacionados como una unidad única: o se procesan todos los mensajes correctamente o no se procesa ninguno. Para implementar tal comportamiento, utilice sesiones con colas.  
  
 Para obtener más información, consulte [agrupar los mensajes en cola en una sesión](grouping-queued-messages-in-a-session.md).  
  
## <a name="correlating-request-reply-messages"></a>Correlación de mensajes de solicitud-respuesta  

 Aunque las colas son típicamente unidireccionales, en algunos escenarios puede querer correlacionar una respuesta recibida con una solicitud enviada anteriormente. Si requiere dicha correlación, se recomienda que aplique su propio encabezado de mensaje SOAP que contiene información de correlación con el mensaje. Normalmente, el remitente adjunta este encabezado al mensaje y el receptor, tras procesar el mensaje y responder con un nuevo mensaje en una cola de respuesta, adjunta el encabezado del mensaje del remitente que contiene la información de la correlación al mensaje de solicitud para que el remitente pueda identificar el mensaje de respuesta.  
  
## <a name="integrating-with-non-wcf-applications"></a>Integración en aplicaciones que no son WCF  

 Use `MsmqIntegrationBinding` al integrar clientes o servicios WCF con servicios o clientes que no sean WCF. La aplicación que no es WCF puede ser una aplicación MSMQ escrita con System. Messaging, COM+, Visual Basic o C++.  
  
 Al utilizar `MsmqIntegrationBinding`, sea consciente de lo siguiente:  
  
- Un cuerpo de mensaje de WCF no es el mismo que el cuerpo de un mensaje de MSMQ. Al enviar un mensaje de WCF mediante un enlace en cola, el cuerpo del mensaje de WCF se coloca dentro de un mensaje de MSMQ. La infraestructura de MSMQ es ajena a esta información adicional; solo ve el mensaje de MSMQ.  
  
- `MsmqIntegrationBinding` admite los tipos de serialización populares. Se basa en el tipo de serialización, el tipo de cuerpo del mensaje genérico, <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, toma diferentes tipos de parámetros. Por ejemplo, <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray> requiere `MsmqMessage\<byte[]>`<xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> y `MsmqMessage<Stream>` requiere .  
  
- Con la serialización XML, puede especificar el tipo conocido utilizando el `KnownTypes` atributo en el [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento que se utiliza a continuación para determinar cómo deserializar el mensaje XML.  
  
## <a name="see-also"></a>Vea también

- [Las colas en WCF](queuing-in-wcf.md)
- [Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Agrupación de los mensajes en cola de una sesión](grouping-queued-messages-in-a-session.md)
- [Mensajes por lotes en una transacción](batching-messages-in-a-transaction.md)
- [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Control de mensajes dudosos](poison-message-handling.md)
- [Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md)
- [Protección de mensajes utilizando la seguridad de transporte](securing-messages-using-transport-security.md)
- [Protección de mensajes mediante la seguridad de mensajes](securing-messages-using-message-security.md)
- [Solución de problemas de la mensajería en cola](troubleshooting-queued-messaging.md)
