---
title: Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9e891c6a-d960-45ea-904f-1a00e202d61a
ms.openlocfilehash: d3087021c717d6ee055a4a1f5332d9d259f06381
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289599"
---
# <a name="using-dead-letter-queues-to-handle-message-transfer-failures"></a>Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes

Los mensajes en cola pueden producir un error en la entrega. Estos mensajes que no se han podido entregar se graban en una cola de mensajes no enviados. Los errores en la entrega pueden deberse a motivos como errores de la red, una cola eliminada, una cola completa, error de autenticación o un error para entregar a tiempo.  
  
 Los mensajes en cola pueden permanecer en la cola durante mucho tiempo si la aplicación receptora no los lee puntualmente de la cola. Este comportamiento puede no ser adecuado para los mensajes dependientes del tiempo. Los mensajes dependientes del tiempo tienen un conjunto de propiedades de período de vida (TTL) en el enlace en cola, que indica cuánto tiempo los mensajes pueden estar en la cola antes de que deban expirar. Los mensajes caducados se envían a la cola especial llamada cola de mensajes no enviados. Los mensajes también se pueden colocar en una cola de mensajes no enviados por otras razones, como superar una cuota de la cola o debido a un error de autenticación.  
  
 Generalmente, las aplicaciones escriben lógica de compensación para leer los mensajes de la cola de mensajes no enviados y de los motivos de error. La lógica de compensación depende de la causa del error. Por ejemplo, en el caso de error de autenticación, puede corregir el certificado adjunto al mensaje y reenviar el mensaje. Si se produjo un error en la entrega porque se alcanzó la cuota de la cola de destino, puede reintentar la entrega con la esperanza de que se haya resuelto el problema de la cuota.  
  
 La mayoría de sistemas de puesta en cola tienen una cola de mensajes no enviados para todo el sistema donde se almacenan todos los mensajes erróneos de ese sistema. Message Queuing (MSMQ) proporciona dos colas de mensajes no enviados para todo el sistema: una cola de mensajes no enviados transaccional para todo el sistema que almacena mensajes que produjeron un error en la entrega a la cola transaccional y una cola de mensajes no enviados no transaccional para todo el sistema que almacena mensajes que produjeron un error en la entrega a la cola no transaccional. Si dos clientes envían mensajes a dos servicios diferentes y, por lo tanto, las distintas colas en WCF comparten el mismo servicio de MSMQ para enviar, es posible que haya una mezcla de mensajes en la cola de mensajes no enviados del sistema. Esto es no siempre óptimo. En muchos casos (seguridad, por ejemplo), quizás no desee que un cliente lea los mensajes de otro cliente de una cola de mensajes no enviados. Una cola de mensajes no enviados compartida también requiere que los clientes naveguen por la cola para buscar un mensaje que enviaron, lo que puede resultar prohibitivamente caro en función del número de mensajes en la cola de mensajes no enviados. Por lo tanto, en WCF `NetMsmqBinding` `MsmqIntegrationBinding,` y MSMQ en Windows Vista proporcionan una cola de mensajes no enviados personalizada (a veces denominada cola de mensajes no enviados específica de la aplicación).  
  
 La cola de mensajes no enviados personalizada proporciona aislamiento entre los clientes que comparten el mismo servicio de MSMQ para enviar los mensajes.  
  
 En Windows Server 2003 y Windows XP, Windows Communication Foundation (WCF) proporciona una cola de mensajes no enviados en todo el sistema para todas las aplicaciones cliente en cola. En Windows Vista, WCF proporciona una cola de mensajes no enviados para cada aplicación cliente en cola.  
  
## <a name="specifying-use-of-the-dead-letter-queue"></a>Especificar el uso de la cola de mensajes no enviados  

 Una cola de mensajes no enviados está en el administrador de cola de la aplicación emisora. Almacena mensajes que han expirado o que han producido un error en la transferencia o entrega.  
  
 El enlace tiene las propiedades de cola de mensajes no enviados siguientes:  
  
- <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>  
  
- <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>  
  
## <a name="reading-messages-from-the-dead-letter-queue"></a>Leer mensajes de la cola de mensajes no enviados  

 Una aplicación que lee los mensajes de una cola de mensajes no enviados es similar a un servicio WCF que lee de una cola de aplicaciones, excepto por las siguientes diferencias secundarias:  
  
- Para leer mensajes de una cola de mensajes no enviados transaccional de un sistema, el identificador URI (Uniform Resource Identifier) debe tener el formato siguiente: net.msmq://localhost/system$;DeadXact.  
  
- Para leer mensajes de una cola de mensajes no enviados no transaccional de un sistema, el URI debe tener el formato siguiente: net.msmq://localhost/system$;DeadLetter.  
  
- Para leer los mensajes de una cola de mensajes no enviados personalizada, el URI debe tener el formato siguiente: net. MSMQ://localhost/Private/ \<*custom-dlq-name*> donde *Custom-mensajes fallidos-Name* es el nombre de la cola de mensajes no enviados personalizada.  
  
 Para obtener más información sobre cómo direccionar las colas, consulte [puntos de conexión de servicio y direccionamiento de colas](service-endpoints-and-queue-addressing.md).  
  
 La pila de WCF en el receptor coincide con las direcciones en las que el servicio está escuchando con la dirección del mensaje. Si las direcciones coinciden, se envía el mensaje; si no, no se envía el mensaje. Esto puede producir problemas al leer de la cola de mensajes no enviados, porque los mensajes en la cola de mensajes no enviados normalmente se direccionan al servicio y no al servicio de la cola de mensajes no enviados. Por consiguiente, el servicio que lee de la cola de mensajes no enviados debe instalar un filtro de direcciones `ServiceBehavior` que indique a la pila que haga coincidir todos los mensajes de la cola independientemente del destinatario. Específicamente, debe agregar `ServiceBehavior` con el parámetro <xref:System.ServiceModel.AddressFilterMode.Any> al servicio que lee los mensajes de la cola de mensajes no enviados.  
  
## <a name="poison-message-handling-from-the-dead-letter-queue"></a>Control de mensajes dudosos de la cola de mensajes no enviados  

 El control de mensajes dudosos está disponible en las colas de mensajes no enviados, con algunas condiciones. Dado que no puede crear subcolas a partir de las colas del sistema, al leer de la cola de mensajes no enviados del sistema, `ReceiveErrorHandling` no puede estar establecido en `Move`. Tenga en cuenta que si está leyendo de una cola de mensajes no enviados personalizada, puede tener subcolas y, por consiguiente, `Move` es una disposición válida para el mensaje dudoso.  
  
 Cuando `ReceiveErrorHandling` está establecido en `Reject`, al leer de la cola de mensajes no enviados personalizada, el mensaje dudoso se coloca en la cola de mensajes no enviados del sistema. Si se está leyendo de la cola de mensajes no enviados del sistema, el mensaje se quita (se purga). Un rechazo de una cola de mensajes no enviados del sistema en MSMQ quita (purga) el mensaje.  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente muestra cómo crear una cola de mensajes no enviados y cómo utilizarla para procesar los mensajes caducados. El ejemplo se basa en el ejemplo de [Cómo: intercambiar mensajes en cola con puntos de conexión de WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md). El ejemplo siguiente muestra cómo escribir el código de cliente en el servicio de procesamiento de orden que utiliza una cola de mensajes no enviados para cada aplicación. El ejemplo también muestra cómo procesar los mensajes de la cola de mensajes no enviados.  
  
 A continuación, se muestra el código para un cliente que especifica una cola de mensajes no enviados para cada aplicación.  
  
 [!code-csharp[S_DeadLetter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/client.cs#1)]
 [!code-vb[S_DeadLetter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/client.vb#1)]  
  
 El código siguiente muestra el archivo de configuración del cliente.  

 A continuación, se muestra el código para un servicio que procesa los mensajes de una cola de mensajes no enviados.  
  
 [!code-csharp[S_DeadLetter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/dlservice.cs#3)]
 [!code-vb[S_DeadLetter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/dlservice.vb#3)]  
  
 A continuación, se muestra el código para el archivo de configuración del servicio de cola de mensajes no enviados.  

## <a name="see-also"></a>Vea también

- [Información general de colas](queues-overview.md)
- [Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Control de mensajes dudosos](poison-message-handling.md)
