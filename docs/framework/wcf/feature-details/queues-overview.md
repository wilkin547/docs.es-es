---
title: Información general de colas
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], MSMQ integration
ms.assetid: b8757992-ffce-40ad-9e9b-3243f6d0fce1
ms.openlocfilehash: 464b82c41fe1268d53d77f7bf3cb9463cf235072
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244644"
---
# <a name="queues-overview"></a>Información general sobre colas

En esta sección se presentan los conceptos generales y básicos detrás de la comunicación puesta en la cola. En las secciones siguientes se describen los detalles sobre cómo se manifiestan los conceptos de colas descritos en Windows Communication Foundation (WCF).  
  
## <a name="basic-queuing-concepts"></a>Conceptos de puesta en cola básicos  

 Cuando se diseña una aplicación distribuida, es importante elegir el transporte adecuado para la comunicación entre los servicios y clientes. Varios factores afectan el tipo de transporte que se va a usar. Un factor importante —aislamiento entre el servicio, el cliente y el transporte— determina el uso de un transporte en cola o un transporte directo, como TCP o HTTP. Debido a la naturaleza de los transportes directos como TCP y HTTP, la comunicación se detiene por completo si el servicio o el cliente para de funcionar o si se produce un error en la red. El servicio, el cliente y la red deben estar en ejecución al mismo tiempo para que funcione la aplicación. Los transportes puestos en cola proporcionan aislamiento, lo cual significa que si hay un error en el servicio o cliente o si los vínculos de comunicaciones fallan entre ellos, el cliente y servicio pueden continuar funcionando.  
  
 Las colas proporcionan comunicación de confianza incluso si hay errores en las partes que se comunican o en la red. Las colas capturan y entregan los mensajes intercambiados entre las partes que se comunican. Normalmente, las colas están respaldadas por un tipo de almacén, que puede ser volátil o durable. Las colas almacenan los mensajes de un cliente en nombre de un servicio y, a continuación, reenvían estos mensajes al servicio. Las colas del direccionamiento indirecto proporcionan aislamiento de error garantizado a cualquier parte, de modo que lo convierte en el mecanismo de comunicación preferido para los sistemas de alta disponibilidad y servicios desconectados. El direccionamiento indirecto viene con el costo de latencia alta. La *latencia* es el tiempo que transcurre entre el momento en que el cliente envía un mensaje y el momento en que el servicio lo recibe. Esto significa que una vez se envía un mensaje, no sabe cuando se puede procesar ese mensaje. La mayoría de las aplicaciones en cola se enfrentan a una latencia elevada. La ilustración siguiente muestra un modelo conceptual de comunicación en cola.  
  
 ![Modelo de comunicación en cola](media/qconceptual-figure1c.gif "QConceptual-Figure1c")  
  
 Modelo conceptual de comunicación en cola  
  
 En realidad, la cola es un concepto distribuido. Como tal, pueden ser locales en cualquier parte o remoto en ambas partes. Normalmente, la cola es local en el servicio. En esta configuración, el cliente no puede depender de la conectividad a la cola remota para estar constantemente disponible. De igual forma, la cola debe estar disponible independiente de la disponibilidad del servicio que lee de la cola. Un administrador de cola administra una colección de colas. Es responsable de aceptar mensajes enviados a sus colas desde otros administradores de cola. También es responsable de administrar la conectividad a las colas remotas y de transferir los mensajes a esas colas remotas. Para garantizar la disponibilidad de las colas a pesar de los errores de aplicación del cliente o de servicio, el administrador de cola se ejecuta normalmente como un servicio externo.  
  
 Cuando un cliente envía un mensaje a una cola, envía el mensaje a la cola de destino, que es la cola administrada por el administrador de cola del servicio. El administrador de cola del cliente envía el mensaje a una cola de transmisión (o de salida). La cola de transmisión es una cola del administrador de cola del cliente que almacena los mensajes para transmitirlos a la cola de destino. A continuación, el administrador de cola busca una ruta de acceso para el administrador de cola que posee la cola de destino y transfiere el mensaje a dicha cola. Para garantizar la comunicación de confianza, los administradores de cola implementan un protocolo de transferencia de confianza para evitar la pérdida de datos. El administrador de la cola de destino acepta los mensajes enviados a las colas de destino que posee y almacena los mensajes. El servicio solicita leer de la cola de destino y, en este momento, el administrador de cola entrega el mensaje a la aplicación destino. La ilustración siguiente muestra la comunicación entre las cuatro partes.  
  
 ![Diagrama de aplicaciones puestas en cola](media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Comunicación en cola en un escenario de implementación habitual  
  
 De este modo, el administrador de cola proporciona el aislamiento necesario para que se pueda producir un error en el remitente y receptor de forma independiente sin afectar a la comunicación real. La ventaja del direccionamiento indirecto adicional que las colas proporcionan también habilita varias instancias de aplicación para leer de la misma cola, para que el trabajo entre los nodos logre el rendimiento más elevado. Por lo tanto, no es raro ver colas que se utilizan para lograr la escala más alta y requisitos de rendimiento.  
  
## <a name="queues-and-transactions"></a>Colas y transacciones  

 Las transacciones le permiten agrupar un conjunto de operaciones de modo que si se produce un error en una operación, se producirá un error en todas las operaciones. Un ejemplo de cómo usar transacciones es cuando una persona usa un cajero automático para transferir $1.000 de su cuenta de ahorro a su cuenta de comprobación. Esto supone las operaciones siguientes:  
  
- Retirar $1,000 de la cuenta de ahorros.  
  
- Depositar $1,000 en la cuenta corriente.  
  
 Si la primera operación es correcta y se retiran $1,000 de la cuenta de los ahorros, pero se produce un error en la segunda operación, se pierden los $1,000 porque ya se han retirado de la cuenta de ahorros. Para mantener las cuentas en estado válido, si se produce un error en una operación, se debe producir un error en ambas operaciones.  
  
 En mensajería transaccional, se pueden enviar mensajes a la cola y recibir mensajes de la cola bajo en una transacción. De este modo, si se envía un mensaje en una transacción y se deshace la transacción, a continuación, el resultado es como si el mensaje nunca se hubiera enviado a la cola. De igual forma, si se recibe un mensaje en una transacción y se deshace la transacción, a continuación, el resultado es como si el mensaje nunca se hubiera recibido. El mensaje permanece en la cola para ser leído.  
  
 Debido a la latencia elevada, cuando envíe un mensaje, usted podrá saber de ninguna manera cuánto tiempo tarda en alcanzar su cola de destino, ni sabrá cuánto tiempo tarda el servicio en procesar el mensaje. Por ello, usted no quiere utilizar una transacción única para enviar el mensaje, recibir el mensaje y, a continuación, procesar el mensaje. Esto crea una transacción que no está confirmada durante un período indeterminado de tiempo. Cuando un cliente y servicio se comunican a través de una cola utilizando una transacción, se implican dos transacciones: una en el cliente y una en el servicio. La ilustración siguiente muestra los límites de una transacción en comunicación en cola habitual.  
  
 ![Cola con transacciones](media/qwithtransactions-figure3.gif "QWithTransactions-Figure3")  
  
 Comunicación en cola que muestra transacciones independientes para la captura y entrega  
  
 La transacción del cliente procesa y envía el mensaje. Cuando se confirma la transacción, el mensaje está en la cola de transmisión. En el servicio, la transacción lee el mensaje desde la cola de destino, procesa el mensaje y, a continuación, confirma la transacción. Si se produce un error durante el procesamiento, se deshace el mensaje y se coloca en la cola de destino.  
  
## <a name="asynchronous-communication-using-queues"></a>Comunicación asincrónica utilizando colas  

 Las colas proporcionan un medio asincrónico de comunicación. Las aplicaciones que envían mensajes mediante colas no pueden esperar a que el receptor reciba y procese el mensaje debido a la latencia elevada introducida por el administrador de cola. Los mensajes pueden permanecer en la cola durante un período de tiempo más largo del previsto por la aplicación. Para evitarlo, la aplicación puede especificar un valor de período de vida en el mensaje. Este valor especifica cuánto tiempo debería permanecer en la cola de transmisión el mensaje. Si se supera este valor de tiempo, y el mensaje todavía no se ha enviado a la cola de destino, se puede transferir el mensaje a una cola de mensajes no enviados.  
  
 Cuando el remitente envía un mensaje, el retorno de la operación enviada implica que el mensaje sólo se envió a la cola de transmisión del remitente. Como tal, si hay un error en el mensaje de la cola de destino, la aplicación emisora no puede saberlo inmediatamente. Para tomar nota de estos errores, el mensaje que no se ha podido enviar se transfiere a una cola de mensajes no enviados.  
  
 Cualquier error, como por ejemplo, un mensaje que no ha alcanzado la cola de destino o un período de vida caducado, se debe procesar por separado. Por lo tanto, no es raro que las aplicaciones en cola escriban dos conjuntos de lógica:  
  
- Cliente normal y lógica del servicio de enviar y recibir mensajes.  
  
- Lógica de la compensación para administrar los mensajes de la transmisión no o entrega no efectuadas.  
  
 Las secciones siguientes discuten estos conceptos.  
  
## <a name="dead-letter-queue-programming"></a>Programación de la cola de mensajes no entregados  

 Las colas de mensajes no enviados contienen mensajes que no pudieron alcanzar la cola de destino por varias razones. Las razones pueden variar desde mensajes expirados a problemas en la conectividad que evitan la transferencia del mensaje a la cola de destino.  
  
 Normalmente, una aplicación puede leer los mensajes desde una cola de mensajes no enviados para todo el sistema, determinar qué salió mal y realizar las acciones necesarias, como corregir los errores y reenviar el mensaje o anotarlo.  
  
## <a name="poison-message-queue-programming"></a>Programación de la cola de mensajes dudosos  

 Una vez el mensaje alcance la cola de destino, puede que el servicio no pueda procesar el mensaje repetidamente. Por ejemplo, una aplicación que lee un mensaje desde la cola de una transacción y actualiza una base de datos puede encontrar la base de datos temporalmente desconectada. En este caso, la transacción se deshace, se crea una nueva transacción y se relee el mensaje de la cola. Puede que un segundo intento funcione o no. En algunos casos, dependiendo de la causa del error, el mensaje puede producir un error repetidamente en la entrega a la aplicación. En este caso, el mensaje se considera "dudoso." Estos mensajes se mueven a una cola de mensajes dudosos, que se puede leer por una aplicación de administración de mensajes dudosos.  
  
## <a name="see-also"></a>Vea también

- [Las colas en WCF](queuing-in-wcf.md)
- [Sesiones y colas](../samples/sessions-and-queues.md)
- [Colas con problemas de entrega](../samples/dead-letter-queues.md)
- [Comunicación en cola volátil](../samples/volatile-queued-communication.md)
- [Windows Communication Foundation a Message Queuing](../samples/wcf-to-message-queuing.md)
- [Instalar Message Queuing (MSMQ)](../samples/installing-message-queuing-msmq.md)
- [Message Queuing a Windows Communication Foundation](../samples/message-queuing-to-wcf.md)
- [Seguridad de mensajes mediante Message Queuing](../samples/message-security-over-message-queuing.md)
