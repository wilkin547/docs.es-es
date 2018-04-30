---
title: puntos de conexión de servicio y direccionamiento de la cola
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2244ccb1637f944f9e3349cf0d94caa2f6676bf
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="service-endpoints-and-queue-addressing"></a>puntos de conexión de servicio y direccionamiento de la cola
En este tema se aborda cómo los clientes direccionan servicios que leen de las colas y cómo los puntos de conexión de servicio se asignan a las colas. A modo de recordatorio, la ilustración siguiente muestra la implementación clásica de aplicaciones puestas en la cola [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 ![Diagrama de aplicaciones en la cola](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "figura de cola distribuida")  
  
 Para que el cliente pueda enviar el mensaje al servicio, el cliente direcciona el mensaje a la cola de destino. Para que el servicio pueda leer mensajes de la cola, establece su dirección de escucha en la cola de destino. Direccionar en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está basado en URI (Identificador Uniforme de Recursos) mientras los nombres de cola de Message Queuing (MSMQ) no están basados en URI. Por consiguiente es esencial entender cómo direccionar las colas creadas en MSMQ utilizando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="msmq-addressing"></a>Direccionamiento MSMQ  
 MSMQ utiliza rutas de acceso y nombres de formato para identificar una cola. Las rutas de acceso especifican un nombre de host y `QueueName`. Opcionalmente, puede haber un `Private$` entre el nombre de host y el `QueueName` para indicar una cola privada que no se publica en el servicio de directorio Active Directory.  
  
 Nombres de ruta de acceso están asignados a "FormatNames" para determinar aspectos adicionales de la dirección, incluido el protocolo de transferencia de administrador de cola y enrutamiento. El Administrador de la cola admite dos protocolos de transferencia: protocolo MSMQ nativo y SOAP Reliable Messaging Protocol (SRMP).  
  
 Para obtener más información acerca de los nombres de ruta de acceso y el formato MSMQ, vea [acerca de Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=94837).  
  
## <a name="netmsmqbinding-and-service-addressing"></a>NetMsmqBinding y direccionamiento del servicio  
 Al direccionar un mensaje a un servicio, el esquema en el URI se selecciona basándose en el transporte utilizado para la comunicación. Cada transporte en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tiene un esquema único. El esquema debe reflejar la naturaleza de transporte utilizada para la comunicación. Por ejemplo, net.tcp, net.pipe, HTTP, etc.  
  
 El transporte MSMQ puesto en cola en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expone un esquema net.msmq. Cualquier mensaje direccionado utilizando el esquema net.msmq se envía utilizando `NetMsmqBinding` a través del canal de transporte puesto en cola.  
  
 El direccionamiento de una cola en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está basado en el patrón siguiente:  
  
 NET.MSMQ: / / \< *nombre de host*> / [privada /] \< *nombre de la cola*>  
  
 donde:  
  
-   \<*nombre de host*> es el nombre del equipo que hospeda la cola de destino.  
  
-   [privado] es opcional. Se utiliza al direccionar una cola de destino que es una cola privada. Para direccionar una cola pública, no debe especificar privado. Tenga en cuenta que, a diferencia de las rutas de acceso de MSMQ, no hay "$" en el formulario URI[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   \<*nombre de la cola*> es el nombre de la cola. El nombre de la cola también puede hacer referencia a una subcola. Por lo tanto, \< *nombre de la cola*> = \< *nombre de cola*> [; *nombre de subdirectorio queue*].  
  
 Ejemplo1: Para direccional una cola privada PurchaseOrders hospedada en el equipo abc atadatum.com, el URI sería net.msmq://abc.adatum.com/private/PurchaseOrders.  
  
 Ejemplo2: Para direccionar una cola pública AccountsPayable hospedada en el equipo def atadatum.com, el URI sería net.msmq://def.adatum.com/AccountsPayable.  
  
 El agente de escucha usa la dirección de la cola como URI de escucha desde donde leer los mensajes. En otras palabras, la dirección de la cola es equivalente al puerto de escucha del socket TCP.  
  
 Un punto de conexión que lee de una cola debe especificar la dirección de la cola utilizando el mismo esquema especificada previamente al abrir ServiceHost. Para obtener ejemplos, vea [enlace de MSMQ Net](../../../../docs/framework/wcf/samples/net-msmq-binding.md) y [ejemplos de enlace de integración de Message Queue Server](http://msdn.microsoft.com/library/997d11cb-f2c5-4ba0-9209-92843d4d0e1a).  
  
### <a name="multiple-contracts-in-a-queue"></a>Varios contratos en una cola  
 Los mensajes en una cola pueden implementar diferentes contratos. En este caso, es esencial que una de las condiciones siguientes sea verdadera para leer correctamente y procesar todos los mensajes:  
  
-   Especifique un extremo para un servicio que implementa todos los contratos. Éste es el enfoque recomendado.  
  
-   Especifique varios extremos con contratos diferentes, pero asegúrese de que todos los extremos utilicen el mismo objeto `NetMsmqBinding`. La lógica de distribución en ServiceModel utiliza una bomba de mensaje que lee los mensajes del canal de transporte para su distribución, lo que eventualmente desmultiplexa mensajes basados en el contrato a extremos diferentes. Una bomba de mensaje se crea para un par de escucha URI/enlace. La dirección de la cola es utilizada como URI de escucha por el agente de escucha puesto en cola. Si todos los extremos utilizan el mismo objeto de enlace, ello garantiza que se utiliza una única bomba de mensaje para leer el mensaje y desmultiplexarlo a los extremos pertinentes basados en el contrato.  
  
### <a name="srmp-messaging"></a>Mensajería SRMP  
 Como se ha abordado previamente, puede utilizar el protocolo SRMP para las transferencias de colas a colas. Ello se utiliza normalmente cuando un transporte http transmite mensajes entre la cola de transmisión y la cola de destino.  
  
 Para utilizar el protocolo de transferencia SRMP, direccione los mensajes utilizando el esquema del URI de net.msmq, como se ha mencionado previamente y especifica la opción de SRMP o SRMP Seguro en la propiedad `QueueTransferProtocol` de `NetMsmqBinding`.  
  
 Especificar la propiedad `QueueTransferProtocol` es una característica de solo envío. Es una indicación por parte del cliente sobre qué tipo de protocolo de transferencia de la cola debe utilizarse.  
  
### <a name="using-active-directory"></a>Utilizar Active Directory  
 MSMQ se entrega con soporte para la integración de Active Directory. Cuando MSMQ se instala con integración de Active Directory, el equipo debe formar parte de un dominio de Windows. Active Directory se usa para publicar las colas para la detección; Estas colas se denominan *colas públicas*. Al direccionar una cola, la cola se puede resolver utilizando Active Directory. Esto es similar a cómo Domain Name System (DNS) se utiliza para resolver la dirección IP de un nombre de red. La propiedad `UseActiveDirectory` en `NetMsmqBinding` es un valor booleano que indica si el canal en cola debe utilizar Active Directory para resolver el URI de la cola. De manera predeterminada, tiene el valor `false`. Si la propiedad `UseActiveDirectory` está establecida en `true`,el canal en cola utiliza Active Directory para convertir el URI net.msmq:// en nombre de formato.  
  
 La propiedad `UseActiveDirectory` solo es significativa para el cliente que está enviando el mensaje porque se utiliza para resolver la dirección de la cola al enviar mensajes.  
  
### <a name="mapping-netmsmq-uri-to-message-queuing-format-names"></a>Asignar el URI net.msmq a nombres de formato de Message Queuing  
 El canal en cola actúa asignando el nombre del URI net.msmq proporcionado al canal a los nombres de formato de MSMQ. La tabla siguiente resume las reglas utilizadas para la asignación entre ellos.  
  
|Dirección de cola basada en URI WCF|Utilizar la propiedad de Active Directory|Propiedad del protocolo de transferencia de la cola|Nombres de formato de MSMQ resultantes|  
|----------------------------------|-----------------------------------|--------------------------------------|---------------------------------|  
|NET.MSMQ://\<machine-name >/private/abc|False (valor predeterminado)|Native (valor predeterminado)|DIRECT=OS:machine-name\private$\abc|  
|NET.MSMQ://\<machine-name >/private/abc|False|SRMP|DIRECT =http://machine/msmq/private$/ abc|  
|NET.MSMQ://\<machine-name >/private/abc|True|Nativo|PUBLIC=some-guid (el GUID de la cola)|  
  
### <a name="reading-messages-from-the-dead-letter-queue-or-the-poison-message-queue"></a>Leer los mensajes de la cola de mensajes no enviados o la cola de mensajes dudosos  
 Para leer los mensajes de una cola de mensajes dudosos que es una subcola de la cola de destino, abra `ServiceHost` con la dirección de la subcola.  
  
 Ejemplo: un servicio que lee de la cola de mensajes dudosos de la cola privada PurchaseOrders del equipo local direccionaría net.msmq://localhost/private/PurchaseOrders;poison.  
  
 Para leer los mensajes de una cola de mensajes con problemas de entrega transaccionales de un sistema, el URI debe tener el formato siguiente: net.msmq://localhost/system$;DeadXact.  
  
 Para leer los mensajes de una cola de mensajes no enviados no transaccionales de un sistema, el URI debe tener la forma siguiente: net.msmq://localhost/system$;DeadLetter.  
  
 Al utilizar una cola de mensajes no enviados personalizada, observe que la cola de mensajes no enviados debe estar situada en el equipo local. Como tal, el URI para la cola de mensajes no enviados está restringido a la forma:  
  
 NET.MSMQ: //localhost/ [privada /] \< *personalizado no enviados letra cola nombre*>.  
  
 Un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba que todos los mensajes que recibe se direccionaron a la cola específica en la que está escuchando. Si la cola de destino del mensaje no coincide con la cola donde se encuentra, el servicio no procesa el mensaje. Se trata de una cuestión que los servicios que escuchan a una cola de mensajes no enviados deben abordar porque cualquier mensaje en la cola de mensajes no enviados debía ser entregado a otra parte. Para leer los mensajes de una cola de mensajes no enviados o de una cola de mensajes dudosos, debe utilizarse `ServiceBehavior` con el parámetro <xref:System.ServiceModel.AddressFilterMode.Any>. Para obtener un ejemplo, vea [colas de mensajes no enviados](../../../../docs/framework/wcf/samples/dead-letter-queues.md).  
  
## <a name="msmqintegrationbinding-and-service-addressing"></a>MsmqIntegrationBinding y direccionamiento del servicio  
 `MsmqIntegrationBinding` se utiliza para la comunicación con aplicaciones MSMQ tradicionales. Para facilitar la interoperación con una aplicación MSMQ existente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite solo el direccionamiento del nombre de formato. Por consiguiente, los mensajes enviados utilizando este enlace deben cumplir el esquema del URI:  
  
 MSMQ.FormatName:\<*nombre de formato de MSMQ*>>  
  
 El nombre de formato de MSMQ tiene el formato especificado por MSMQ en [acerca de Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=94837).  
  
 Observe que solo puede utilizar los nombres de formato directos, y los nombres de formato públicos y privados (requiere la integración de Active Directory) al recibir los mensajes de una cola utilizando `MsmqIntegrationBinding`. Sin embargo, se aconseja que utilice los nombres de formato directos. Por ejemplo, en [!INCLUDE[wv](../../../../includes/wv-md.md)], al utilizar cualquier otro nombre de formato se produce un error porque el sistema intenta abrir una subcola que solo se puede abrir con nombres de formato directos.  
  
 Al direccionar SRMP utilizando `MsmqIntegrationBinding`, no hay ningún requisito para agregar /msmq/ en el nombre de formato directo para ayudar a Internet Information Services (IIS) con la distribución. Por ejemplo: al direccionar una cola abc utilizando el SRMP de protocolo, en lugar de DIRECT =http://adatum.com/msmq/private$/ abc, debería utilizar DIRECT =http://adatum.com/private$/ abc.  
  
 Observe que no puede utilizar net.msmq:// direccionando con `MsmqIntegrationBinding`. Dado que `MsmqIntegrationBinding` admite el direccionamiento de nombre de formato MSMQ de forma libre, puede utilizar un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utilice este enlace para utilizar las características de multidifusión y la lista de distribución en MSMQ. Una excepción es especificar `CustomDeadLetterQueue` al utilizar `MsmqIntegrationBinding`. Debe tener la forma net.msmq://, similar a cómo se especifica utilizando `NetMsmqBinding`.  
  
## <a name="see-also"></a>Vea también  
 [Alojamiento web de una aplicación en cola](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
