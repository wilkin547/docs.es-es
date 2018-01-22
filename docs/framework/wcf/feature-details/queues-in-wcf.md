---
title: Colas en Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4dfc78d355db4bd8c9d43541545e6fac35086b39
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="queues-in-windows-communication-foundation"></a>Colas en Windows Communication Foundation
En los temas de esta sección se describe la compatibilidad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con colas. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite la puesta en cola reutilizando Microsoft Message Queuing (previamente conocido como MSMQ) como un transporte y habilita los siguientes escenarios:  
  
-   Aplicaciones acopladas débilmente Las aplicaciones emisoras pueden enviar mensajes a colas sin necesidad de conocer si la aplicación receptora está disponible para procesar el mensaje. La cola proporciona independencia de procesamiento que permite a una aplicación emisora enviar mensajes a la cola a una tasa que no depende de cómo de rápido las aplicaciones receptoras puedan procesar los mensajes. La disponibilidad del sistema total aumenta al enviar los mensajes a una cola que no está fuertemente acoplada al procesamiento de mensajes.  
  
-   Aislamiento de errores. Las aplicaciones que envían o reciben mensajes a una cola pueden producir un error sin afectar al resto. Por ejemplo, si se produce un error en la aplicación receptora, la aplicación emisora puede continuar enviando mensajes a la cola. Cuando el receptor esté operativo de nuevo, podrá procesar los mensajes de la cola. El aislamiento de errores aumenta la fiabilidad y disponibilidad total del sistema.  
  
-   Nivelación de la carga. Las aplicaciones emisoras pueden agobiar a las aplicaciones receptoras con mensajes. Las colas pueden administrar tasas de consumo y producciones de mensajes desequilibradas, de modo que el receptor no se agobie.  
  
-   Operaciones desconectadas. Las operaciones de envío, recepción y procesamiento se pueden desconectar al comunicar a través de redes de latencia alta o redes de disponibilidad limitada, como es el caso de los dispositivos móviles. Las colas permiten a estas operaciones continuar, incluso cuando los puntos de conexión están desconectados. Cuando se restablece la conexión, la cola reenvía los mensajes a la aplicación receptora.  
  
 Para usar la característica de colas en una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede usar uno de los enlaces estándar o puede crear un enlace personalizado si uno de los enlaces estándar no satisface sus requisitos. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]enlaces estándar relevantes y cómo elegir una de ellas, vea [Cómo: intercambian mensajes con extremos de WCF y las aplicaciones de Message Queue Server](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo crear enlaces personalizados, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general de colas](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 Una información general de conceptos de colas de mensajes.  
  
 [Colas en WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 Una información general de compatibilidad de cola de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Intercambio de mensajes en cola con puntos de conexión de WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 Explica cómo utilizar la clase <xref:System.ServiceModel.NetMsmqBinding> para comunicarse entre un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Intercambio de mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 Explica cómo utilizar <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> para comunicarse entre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y aplicaciones Message Queuing.  
  
 [Agrupación de los mensajes en cola de una sesión](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 Explica cómo agrupar los mensajes en una cola para facilitar el procesamiento de mensajes correlacionado por una aplicación receptora única.  
  
 [Mensajes por lotes en una transacción](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 Explica cómo procesar mensajes por lotes en una transacción.  
  
 [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 Explica cómo administrar los errores de entrega y transferencia de mensajes mediante las colas de mensajes no enviados y cómo procesar mensajes desde la cola de mensajes no enviados.  
  
 [Control de mensajes dudosos](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 Explica cómo administrar los mensajes dudosos (mensajes que han superado el número máximo de intentos de entrega a la aplicación receptora).  
  
 [Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 Resume las diferencias en la característica de colas [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] entre [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
 [Protección de mensajes utilizando la seguridad de transporte](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 Describe cómo utilizar la seguridad de transporte para proteger los mensajes en cola.  
  
 [Protección de mensajes mediante la seguridad de mensajes](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 Describe cómo utilizar la seguridad de mensaje para proteger los mensajes en cola.  
  
 [Solución de problemas de la mensajería en cola](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 Explica cómo solucionar los problemas comunes de la puesta en cola.  
  
 [Procedimientos recomendados para la comunicación en cola](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 Explica los procedimientos recomendados para utilizar la comunicación mediante cola de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Message Queue Server](http://msdn.microsoft.com/library/ff917e87-05d5-478f-9430-0f560675ece1)
