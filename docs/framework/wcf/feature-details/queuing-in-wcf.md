---
title: Las colas en WCF
ms.date: 03/30/2017
ms.assetid: e98d76ba-1acf-42cd-b137-0f8214661112
ms.openlocfilehash: 710ddedeb211ae6b874e2957943dbe60425b7476
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601119"
---
# <a name="queuing-in-wcf"></a>Las colas en WCF
En esta sección se describe cómo usar la comunicación en cola en Windows Communication Foundation (WCF).  
  
## <a name="queues-as-a-wcf-transport-binding"></a>Las colas como enlace de transporte de WCF  
 En WCF, los contratos especifican lo que se intercambia. Los contratos son intercambios de mensajes que dependen de lo comercial, o intercambios específicos de la aplicación. El mecanismo utilizado para intercambiar los mensajes (o el "cómo") se especifica en los enlaces. Los enlaces de WCF encapsulan los detalles del intercambio de mensajes. Exponen botones de configuración para que el usuario controle distintos aspectos del transporte o el protocolo que representan los enlaces. La puesta en cola en WCF se trata como cualquier otro enlace de transporte, que es una gran ventaja para muchas aplicaciones de puesta en cola. Hoy en día, muchas aplicaciones de colas se escriben de manera diferente a otras aplicaciones de estilo distribuido de llamada a procedimiento remoto (RPC), lo que dificulta su seguimiento y mantenimiento. Con WCF, el estilo de escritura de una aplicación distribuida es muy similar, lo que facilita su seguimiento y mantenimiento. Es más, separando la factorización del mecanismo de intercambio de la lógica comercial, es más sencillo configurar el transporte o cambiarlo sin alterar el código específico de la aplicación. La figura siguiente muestra la estructura de un servicio y un cliente WCF que utilizan MSMQ como transporte.  
  
 ![Diagrama de aplicaciones puestas en cola](media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Como puede verse en la figura anterior, el cliente y el servicio sólo tienen que definir las semánticas de la aplicación, es decir, el contrato y la implementación. El servicio configura un enlace en cola con los valores preferentes. El cliente usa la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar un cliente de WCF para el servicio y para generar un archivo de configuración que describe los enlaces que se van a usar para enviar mensajes al servicio. Por lo tanto, para enviar un mensaje en cola, el cliente crea una instancia de un cliente WCF e invoca una operación en él. Esto provoca el envío del mensaje a la cola de transmisión y su transferencia a la cola de destino. Toda la complejidad de la comunicación en cola permanece oculta a la aplicación que envía y recibe los mensajes.  
  
 Las advertencias sobre el enlace en cola en WCF incluyen:  
  
- Todas las operaciones de servicio deben ser unidireccionales porque el enlace en cola predeterminado en WCF no admite la comunicación dúplex mediante colas. Un ejemplo de comunicación bidireccional ([comunicación bidireccional](../samples/two-way-communication.md)) muestra cómo usar contratos de 2 1 para implementar la comunicación dúplex mediante colas.  
  
- Para generar un cliente de WCF mediante el intercambio de metadatos, se requiere un extremo HTTP adicional en el servicio para que se pueda consultar directamente para generar el cliente de WCF y obtener información de enlace para configurar correctamente la comunicación en cola.  
  
- Según el enlace en cola, se requiere una configuración adicional fuera de WCF. Por ejemplo, la <xref:System.ServiceModel.NetMsmqBinding> clase que se suministra con WCF requiere la configuración de los enlaces y la configuración mínima de Message Queuing (MSMQ).  
  
 En las secciones siguientes se describen los enlaces en cola específicos que se incluyen con WCF, que se basan en MSMQ.  
  
### <a name="msmq"></a>MSMQ  
 El transporte en cola en WCF utiliza MSMQ para su comunicación en cola.  
  
 MSMQ se distribuye como componente opcional de Windows y se ejecuta como un servicio NT. Captura los mensajes para su transmisión en una cola de transmisión, y para la entrega en una cola de destino. Los administradores de cola de MSMQ implementan un protocolo de transferencias de mensajes de confianza para que los mensajes no se pierdan durante la transmisión. El protocolo puede ser nativo o basado en SOAP, como el protocolo de mensajes de confianza (SRMP) de SOAP.  
  
 En MSMQ, las colas pueden ser transaccionales o no transaccionales. Una cola transaccional permite capturar los mensajes y entregarlos en una transacción y, a continuación, almacenarlos de manera duradera en la cola. Los mensajes enviados a una cola transaccional se transfieren con precisión una vez en orden. Puede utilizar una cola no transaccional para enviar tanto los mensajes volátiles como los duraderos. Un mensaje enviado a una cola no transaccional no posee ninguna garantía de transferencia de confianza, por lo que puede perderse.  
  
 Las colas de MSMQ también pueden protegerse utilizando una identidad de Windows registrada con el servicio de directorio Active Directory. Al instalar MSMQ puede instalar la integración de Active Directory, para lo que es necesario que el equipo forme parte de una red de dominios de Windows.  
  
 Para obtener más información acerca de MSMQ, vea [instalar Message Queue Server (MSMQ)](../samples/installing-message-queuing-msmq.md).  
  
### <a name="netmsmqbinding"></a>NetMsmqBinding  
 [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)Es el enlace en cola que proporciona WCF para que dos extremos de WCF se comuniquen mediante MSMQ. Por lo tanto, el enlace expone propiedades que son específicas de MSMQ. No obstante, no todas las características y propiedades MSMQ se exponen en `NetMsmqBinding`. El `NetMsmqBinding` compacto está diseñado con un conjunto óptimo de características que la mayoría de los clientes debería encontrar suficiente.  
  
 `NetMsmqBinding` expone los conceptos fundamentales de las colas explicados hasta ahora como propiedades de los enlaces. Por su parte, estas propiedades comunican a MSMQ cómo transferir y entregar los mensajes. Hay una descripción de las categorías de propiedad en las secciones siguientes. Para obtener más información, vea los temas conceptuales que describen las propiedades específicas más completamente.  
  
#### <a name="exactlyonce-and-durable-properties"></a>ExactlyOnce y propiedades durables  
 `ExactlyOnce` y las propiedades `Durable` afectan a cómo los mensajes se transfieren entre las colas:  
  
- `ExactlyOnce`: cuando se establece en `true` (el valor predeterminado), el canal en cola garantiza que, si se entrega, el mensaje no se duplica. Además, garantiza que el mensaje no se pierda. Si no puede entregarse el mensaje, o expira el periodo de vida del mismo antes de poder entregarlo, tanto el mensaje fallido como la razón del error en la entrega se registran en una cola de componentes con problemas de entrega. Cuando se establece en `false`, el canal en cola realiza un esfuerzo para transferir el mensaje. En este caso, se puede optar por elegir una cola de mensajes no enviados.  
  
- `Durable:` cuando se establece en `true` (el valor predeterminado), el canal en cola garantiza que MSMQ almacena el mensaje en el disco de manera duradera. Así, si el servicio de MSMQ se detiene y reinicia, los mensajes del disco se transfieren a la cola de destino o se entregan al servicio. Cuando se establece en `false`, los mensajes se guardan en un almacén volátil y se pierden en caso de que se detenga y reinicie el servicio de MSMQ.  
  
 MSMQ exige una cola transaccional para que la transferencia `ExactlyOnce` sea de confianza. Además, MSMQ exige que la transacción lea desde una cola transaccional. Por lo tanto, cuando utilice `NetMsmqBinding`, recuerde que se requiere una transacción para enviar o recibir mensajes cuando `ExactlyOnce` está establecido en `true`. De igual forma, MSMQ exige a la cola que sea no transaccional para una mayor garantía, como cuando `ExactlyOnce` es `false` y en mensajería volátil. Así, al establecer `ExactlyOnce` en `false` o durable en `false`, no puede enviar o recibir mediante una transacción.  
  
> [!NOTE]
> Asegurarse de que la cola correcta (transaccional o no transaccional) se crea basándose en los valores de los enlaces. Si `ExactlyOnce` es `true`, utilice una cola transaccional; de lo contrario, utilice una cola no transaccional.  
  
#### <a name="dead-letter-queue-properties"></a>Propiedades de la cola de mensajes no enviados  
 La cola de mensajes no enviados se utiliza para guardar los mensajes cuya entrega ha sido fallida. El usuario puede escribir una lógica de compensación que expulse los mensajes fuera de la cola de mensajes no enviados.  
  
 Muchos sistemas de colas proporcionan una cola de mensajes no enviados para todo el sistema. MSMQ proporciona una cola de mensajes no enviados no transaccional para todo el sistema, para los mensajes con entrega fallida en colas no transaccionales; y una cola de mensajes no enviados transaccional para todo el sistema para los mensajes con entrega fallida en colas transaccionales.  
  
 Si varios clientes que envían mensajes a distintas colas de destino comparten el servicio MSMQ, todos los mensajes enviados por los clientes irán a la misma cola de mensajes no enviados. Esto no siempre es lo mejor. Para un mejor aislamiento, WCF y MSMQ en Windows Vista proporcionan una cola de mensajes no enviados personalizada (o una cola de mensajes no enviados específica de la aplicación) que el usuario puede especificar para almacenar los mensajes que no se han podido entregar. Por lo tanto, los distintos clientes no comparten la misma cola de mensajes no enviados.  
  
 El enlace tiene dos propiedades interesantes:  
  
- `DeadLetterQueue`: esta propiedad es una enumeración que indica si se envía una solicitud a una cola de mensajes no enviados. La enumeración también contiene el tipo de cola de mensajes no enviados, en caso de que se solicite uno. Los valores son `None`, `System` y `Custom`. Para obtener más información acerca de la interpretación de estas propiedades, consulte [uso de colas de mensajes no enviados para administrar los errores de transferencia de mensajes](using-dead-letter-queues-to-handle-message-transfer-failures.md)  
  
- `CustomDeadLetterQueue`: esta propiedad es la dirección del identificador uniforme de recursos (URI) de la cola de mensajes no enviados específica de la aplicación. Esto es necesario si `DeadLetterQueue` .`Custom` se elige.  
  
#### <a name="poison-message-handling-properties"></a>Propiedades de control de mensajes dudosos  
 Cuando el servicio lee mensajes de la cola de destino en una transacción, puede no procesar el mensaje debido a distintas razones. En este caso, el mensaje se devuelve a la cola para volver a leerse. Para gestionar los mensajes en los que se producen errores repetidamente, se puede configurar un conjunto propiedades de control de mensajes dudosos en el enlace. Hay cuatro propiedades: `ReceiveRetryCount`, `MaxRetryCycles`, `RetryCycleDelay` y `ReceiveErrorHandling`. Para obtener más información acerca de estas propiedades, vea [control de mensajes dudosos](poison-message-handling.md).  
  
#### <a name="security-properties"></a>Propiedades de seguridad  
 MSMQ expone su propio modelo de seguridad, como las listas de control de acceso (ACL) en una cola o el envío de mensajes autenticados. `NetMsmqBinding` expone estas propiedades de seguridad como parte de sus valores de seguridad de transporte. Hay dos propiedades en el enlace para la seguridad de transporte: `MsmqAuthenticationMode` y `MsmqProtectionLevel`. Los valores de estas propiedades dependen de la configuración de MSMQ. Para obtener más información, consulte [protección de mensajes mediante la seguridad de transporte](securing-messages-using-transport-security.md).  
  
 Además de la seguridad de transporte, el propio mensaje SOAP puede protegerse utilizando la seguridad de mensaje. Para obtener más información, consulte [protección de mensajes mediante la seguridad de mensajes](securing-messages-using-message-security.md).  
  
 `MsmqTransportSecurity` también expone dos propiedades, `MsmqEncryptionAlgorithm` y `MsmqHashAlgorithm`. Éstas son enumeraciones de distintos algoritmos que permiten elegir el cifrado de la transferencia cola a cola de mensajes y el algoritmo hash de las firmas.  
  
#### <a name="other-properties"></a>Otras propiedades  
 Además de las propiedades anteriores, existen otras propiedades específicas de MSMQ expuestas en el enlace:  
  
- `UseSourceJournal`: una propiedad que indica la activación del registro en el diario de origen. El registro en el diario de origen es una característica de MSMQ que hace un seguimiento de los mensajes transmitidos correctamente desde la cola de transmisión.  
  
- `UseMsmqTracing`: una propiedad que indica que el seguimiento de la traza de MSMQ está activado. El seguimiento de la traza de MSMQ envía mensajes de informe a una cola de informes cada vez que un mensaje sale o llega a un equipo en el que se aloja un administrador de cola de MSMQ.  
  
- `QueueTransferProtocol`: una enumeración del protocolo utilizado para las transferencias de mensajes cola a cola. MSMQ implementa un protocolo de transferencia cola a cola nativo y un protocolo basado en SOAP, denominado protocolo de mensajería de confianza (SRMP) de SOAP. Se utiliza SRMP cuando se recurre al transporte HTTP para las transferencias cola a cola. La protección SRMP se utiliza cuando se recurre a HTTPS para las transferencias cola a cola.  
  
- `UseActiveDirectory`: un valor booleano que indica si debe utilizarse Active Directory para la resolución de direcciones de cola. De manera predeterminada, está desactivado. Para obtener más información, consulte [puntos de conexión de servicio y direccionamiento de colas](service-endpoints-and-queue-addressing.md).  
  
### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding  
 `MsmqIntegrationBinding`Se usa cuando se desea que un punto de conexión de WCF se comunique con una aplicación MSMQ existente escrita en las API de C, C++, com o System. Messaging.  
  
 Las propiedades de enlace son la mismas que para `NetMsmqBinding`. No obstante, se aplican las siguientes diferencias.  
  
- El contrato de operación para `MsmqIntegrationBinding` está restringido a tomar un único parámetro de tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, en el que el parámetro de tipo, es el tipo del cuerpo.  
  
- Muchas de las propiedades de mensaje nativas de MSMQ se exponen en <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601> para su uso  
  
- Para facilitar la serialización y deserialización del cuerpo del mensaje, se proporcionan serializadores como XML y ActiveX.  
  
### <a name="sample-code"></a>Código de ejemplo  
 Si desea obtener instrucciones paso a paso sobre cómo escribir servicios WCF que usen MSMQ, vea los temas siguientes:  
  
- [Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
  
- [Procedimiento para intercambiar mensajes en cola con puntos de conexión de WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)  
  
 Si desea obtener un ejemplo de código completo que muestre el uso de MSMQ en WCF, vea los temas siguientes:  
  
- [Enlace MSMQ por transacciones](../samples/transacted-msmq-binding.md)  
  
- [Comunicación en cola volátil](../samples/volatile-queued-communication.md)  
  
- [Colas con problemas de entrega](../samples/dead-letter-queues.md)  
  
- [Sesiones y colas](../samples/sessions-and-queues.md)  
  
- [Comunicación bidireccional](../samples/two-way-communication.md)
  
- [SRMP](../samples/srmp.md)  
  
- [Seguridad de mensajes mediante Message Queuing](../samples/message-security-over-message-queuing.md)  
  
## <a name="see-also"></a>Vea también

- [Extremos de servicio y direccionamiento de la cola](service-endpoints-and-queue-addressing.md)
- [Alojamiento web de una aplicación en cola](web-hosting-a-queued-application.md)
