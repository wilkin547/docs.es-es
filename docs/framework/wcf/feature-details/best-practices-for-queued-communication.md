---
title: "Procedimientos recomendados para la comunicaci&#243;n en cola | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "procedimientos recomendados [WCF], comunicación en cola"
  - "colas [WCF], procedimientos recomendados"
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Procedimientos recomendados para la comunicaci&#243;n en cola
En este tema se proporcionan procedimientos recomendados para la comunicación en cola en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Las secciones siguientes discuten los procedimientos recomendados desde una perspectiva del escenario.  
  
## Mensajería en cola rápida y eficiente  
 Para los escenarios que requieren la separación que proporciona la mensajería en cola y una mensajería rápida y de alto rendimiento con garantías de optimización, utilice una cola no transaccional y establezca la propiedad <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> en `false`.  
  
 Además, puede decidir no incurrir en el costo de escrituras en disco estableciendo la propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> en `false`.  
  
 La seguridad afecta al rendimiento.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Consideraciones de rendimiento](../../../../docs/framework/wcf/feature-details/performance-considerations.md).  
  
## Mensajería en cola fiable de un extremo a otro  
 Las secciones siguientes describen los procedimientos recomendados para escenarios que requieren una mensajería fiable de un extremo a otro.  
  
### Transferencia fiable básica  
 Para obtener una fiabilidad de un extremo a otro, establezca la propiedad <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> en `true` para asegurar la transferencia.La propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> puede establecerse en `true` o `false` en función de sus requisitos \(el valor predeterminado es `true`\).Generalmente, la propiedad <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> está establecida en `true` como parte de la fiabilidad de un extremo a otro.El compromiso es proporcionar un costo de rendimiento, pero hace el mensaje durable para que no se pierda el mensaje si un administrador de cola se bloquea.  
  
### Uso de transacciones  
 Debe usar transacciones para garantizar la confiabilidad de un extremo a otro.Las garantías de`ExactlyOnce` solo aseguran que los mensajes se entreguen a la cola de destino.Para garantizar que se reciba el mensaje, utilice transacciones.Sin transacciones, si el servicio se bloquea, pierde el mensaje que se entrega pero realmente se entrega a la aplicación.  
  
### Uso de colas de mensajes no enviados  
 Las colas de mensajes no enviados aseguran que reciba una notificación si no se pudo entregar un mensaje a la cola de destino.Puede utilizar la cola de mensajes no enviados proporcionada por el sistema o una cola de mensajes no enviados personalizada.En general, utilizar una cola de mensajes no enviados personalizada es mejor porque le permite enviar mensajes no enviados de una aplicación en una cola de mensajes no enviados única.De lo contrario, todos los mensajes no enviados que ocurran para todas las aplicaciones que se ejecuten en el sistema se entregan a una cola única.Cada aplicación debe buscar a continuación en la cola de mensajes no enviados para encontrar los mensajes no enviados pertinentes para esa aplicación.A veces, utilizar una cola de mensajes no enviados personalizada no es factible, como cuando se usa MSMQ 3.0.  
  
 No se recomienda desactivar las colas de mensajes no enviados para la comunicación fiable de un extremo a otro.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).  
  
### Uso del control de mensajes dudosos  
 El control de mensajes dudosos proporciona capacidad de recuperación cuando se producen errores de procesamiento de mensajes.  
  
 Al utilizar la característica de control de mensajes dudosos, asegúrese de que la propiedad <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> está establecida en el valor adecuado.Establecerla en <xref:System.ServiceModel.ReceiveErrorHandling> implica que los datos se pierdan.Por otro lado, establecerla en <xref:System.ServiceModel.ReceiveErrorHandling> produce un error en el host de servicios cuando detecta un mensaje dudoso.Utilizar MSMQ 3.0, <xref:System.ServiceModel.ReceiveErrorHandling> es la mejor opción para evitar la pérdida de datos y quitar el mensaje dudoso.Con MSMQ 4.0, <xref:System.ServiceModel.ReceiveErrorHandling> es el enfoque recomendado.<xref:System.ServiceModel.ReceiveErrorHandling> mueve un mensaje dudoso fuera de la cola para que el servicio pueda continuar procesando los nuevos mensajes.El servicio de mensajes dudosos puede procesar a continuación el mensaje dudoso por separado.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Control de mensajes dudosos](../../../../docs/framework/wcf/feature-details/poison-message-handling.md).  
  
## Obtener un alto rendimiento  
 Para lograr un alto rendimiento en un solo extremo, utilice lo siguiente:  
  
-   Procesamiento por lotes con transaccionesEl procesamiento por lotes con transacciones garantiza que muchos mensajes se puedan leer en una transacción única.Esto optimiza las confirmaciones de transacciones, aumentando el rendimiento total.El costo del procesamiento por lotes es que si se produce un error en un mensaje único dentro de un lote, se deshace el lote completo y se deben procesar los mensajes de uno en uno hasta que sea seguro de nuevo el procesamiento por lotes.En la mayoría de los casos, los mensajes dudosos son raros, así que el procesamiento por lotes es la forma preferida de aumentar el rendimiento del sistema, particularmente cuando se tienen otros administradores de recursos que participan en la transacción.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Mensajes por lotes en una transacción](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md).  
  
-   Simultaneidad.La simultaneidad aumenta el rendimiento, pero también afecta a la contención a los recursos compartidos.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Simultaneidad](../../../../docs/framework/wcf/samples/concurrency.md).  
  
-   Limitación de peticiones.Para un rendimiento óptimo, limite el número de mensajes en el conductor del distribuidor.Para consultar un ejemplo sobre cómo hacerlo, vea [Limitación de peticiones](../../../../docs/framework/wcf/samples/throttling.md).  
  
 Al utilizar el procesamiento por lotes, sea consciente que la simultaneidad y la limitación de peticiones se traducen en los lotes simultáneos.  
  
 Para lograr un rendimiento y disponibilidad más altos, use un conjunto de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que lean desde la cola.Esto requiere que todos estos servicios expongan el mismo contrato en el mismo extremo.El enfoque del conjunto funciona mejor para las aplicaciones que tienen tasas altas de producción de mensajes porque permite a varios servicios que lean desde la misma cola.  
  
 Al utilizar los conjuntos, sea consciente de que MSMQ 3.0 no admite las lecturas con transacciones remotas.MSMQ 4.0 admite las lecturas con transacciones remotas.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Mensajes por lotes en una transacción](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md) y [Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
## Puesta en cola con la unidad de semántica de trabajo  
 En algunos escenarios un grupo de mensajes en una cola se puede relacionar y, por consiguiente, la clasificación de estos mensajes es significativa.En tales escenarios, procese juntos un grupo de mensajes relacionados como una unidad única: o se procesan todos los mensajes correctamente o no se procesa ninguno.Para implementar tal comportamiento, utilice sesiones con colas.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Agrupación de los mensajes en cola de una sesión](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).  
  
## Correlación de mensajes de solicitud\-respuesta  
 Aunque las colas son típicamente unidireccionales, en algunos escenarios puede ser conveniente correlacionar una respuesta recibida con una solicitud enviada anteriormente.Si requiere dicha correlación, se recomienda que aplique su propio encabezado de mensaje SOAP que contiene información de correlación con el mensaje.Normalmente, el remitente adjunta este encabezado al mensaje y el receptor, tras procesar el mensaje y responder con un nuevo mensaje en una cola de respuesta, adjunta el encabezado del mensaje del remitente que contiene la información de la correlación al mensaje de solicitud para que el remitente pueda identificar el mensaje de respuesta.  
  
## Integración en aplicaciones que no son WCF  
 Utilice `MsmqIntegrationBinding` al integrar servicios o clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con servicios o clientes que no sean de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].La aplicación que no es de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede ser una aplicación MSMQ escrita mediante System.Messaging, COM\+, [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o C\+\+.  
  
 Al utilizar `MsmqIntegrationBinding`, sea consciente de lo siguiente:  
  
-   Un cuerpo del mensaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no es igual que un cuerpo del mensaje de MSMQ.Al enviar un mensaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un enlace en cola, el cuerpo del mensaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se coloca dentro de un mensaje de MSMQ.La infraestructura de MSMQ es ajena a esta información adicional; solo ve el mensaje de MSMQ.  
  
-   `MsmqIntegrationBinding` admite los tipos de serialización populares.Se basa en el tipo de serialización, el tipo de cuerpo del mensaje genérico, <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, toma diferentes tipos de parámetros.Por ejemplo, <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat> requiere `MsmqMessage\<byte[]>`<xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat> y `MsmqMessage<Stream>` requiere .  
  
-   Mediante la serialización XML, puede especificar el tipo conocido utilizando el atributo `KnownTypes` en el elemento [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) que se utiliza a continuación para determinar cómo deserializar el mensaje XML.  
  
## Vea también  
 [Las colas en WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)   
 [Cómo: Intercambiar mensajes en cola con extremos de WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)   
 [Cómo: Intercambiar mensajes con extremos de WCF y aplicaciones de Message Queuing](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Agrupación de los mensajes en cola de una sesión](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)   
 [Mensajes por lotes en una transacción](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)   
 [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)   
 [Control de mensajes dudosos](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)   
 [Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)   
 [Protección de mensajes utilizando la seguridad de transporte](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)   
 [Protección de mensajes mediante la seguridad de mensajes](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)   
 [Solución de problemas de la mensajería en cola](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)