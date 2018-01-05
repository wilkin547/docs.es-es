---
title: Colas y sesiones de confianza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9a78bab9f7c4af23cf01c44e1d22a41a87a96f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="queues-and-reliable-sessions"></a>Colas y sesiones de confianza
Las colas y las sesiones de confianza son las características de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que implementan la mensajería de confianza. Los temas contenidos en esta sección discuten las características de mensajería de confianza de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 La mensajería de confianza se define como la manera en que un origen de mensajería de confianza (denominado origen) transfiere mensajes de manera fiable a un destino de mensajería de confianza (denominado destino).  
  
 La mensajería de confianza tiene los siguientes aspectos clave:  
  
-   Transfiera garantías para los mensajes enviados desde un origen a un destino sin tener en cuenta los errores de transporte o de transferencia de los mensajes.  
  
-   Separación del origen y el destino, que proporciona errores y recuperaciones independientes del origen y el destino, así como una transferencia y entrega de mensajes confiable, incluso cuando el origen o el destino no están disponibles.  
  
 La mensajería de confianza a menudo viene acompañada de una alta latencia. La latencia es el tiempo que tarda un mensaje en alcanzar el destino desde el origen. Por consiguiente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona los tipos siguientes de mensajería de confianza:  
  
-   [Las sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions.md), que ofrecen una transferencia confiable sin el costo de latencia alta  
  
-   [Las colas en WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md), que proporcionan transferencias confiables y separación entre el origen y el destino.  
  
## <a name="reliable-sessions"></a>Sesiones de confianza  
 Las sesiones de confianza proporcionan una transferencia confiable de un punto de conexión a otro de mensajes entre un origen y un destino mediante el protocolo WS-ReliableMessaging, sin tener en cuenta el número o tipo de intermediarios que separan los puntos de conexión de la mensajería (origen y destino). Esto incluye a cualquier intermediario de transporte que no utilice SOAP (por ejemplo, los servidores proxy HTTP) o los intermediarios que utilicen SOAP (por ejemplo, los puentes o enrutadores basados en SOAP) que son necesarios para que los mensajes fluyan entre los puntos de conexión. Las sesiones confiables utilizan una ventana de transferencia en memoria para enmascarar errores de nivel de mensaje de SOAP y restablecer las conexiones en el caso de errores de transporte.  
  
 Las sesiones de confianza proporcionan transferencias de mensajes de confianza de latencia baja. Los proporcionan para los mensajes SOAP sobre cualquier proxy o intermediario, el equivalente a lo que TCP proporciona para los paquetes sobre puentes de IP. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las sesiones confiables, consulte [sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### <a name="queues"></a>Colas  
 Las colas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporcionan transferencias confiables de mensajes y separación entre los orígenes y los destinos a costa de una latencia alta. La comunicación en cola de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se basa en Message Queuing Server (también conocido como MSMQ).  
  
 MSMQ se distribuye como una opción con Windows que se ejecuta como un servicio de NT. Captura mensajes para la transmisión en una cola de transmisión en nombre del origen y lo entrega a una cola de destino. La cola de destino acepta los mensajes en nombre del destino para la entrega posterior siempre que el destino solicite mensajes. Los administradores de cola de MSMQ implementan un protocolo de transferencias de mensajes de confianza para que los mensajes no se pierdan durante la transmisión. El protocolo puede ser nativo o basado en SOAP, como, por ejemplo, Soap Reliable Messaging Protocol (SRMP).  
  
 La separación, acoplada con las transferencias de mensaje de confianza entre colas, permite que las aplicaciones que están acopladas se comuniquen de forma fiable. A diferencia de las sesiones de confianza, el origen y el destino no tienen que ejecutarse a la vez. Esto habilita escenarios de forma implícita allí donde se usan las colas como mecanismo de nivelación de carga cuando hay una discordancia entre la velocidad de producción de mensajes por parte del origen y la velocidad de uso de mensajes por parte del destino. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las colas, consulte [colas en WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Vea también  
 [Colas en WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Colas en WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)  
 [Información general de sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)
