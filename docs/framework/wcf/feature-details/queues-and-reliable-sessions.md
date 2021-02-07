---
description: 'Más información acerca de: colas y sesiones confiables'
title: Colas y sesiones de confianza
ms.date: 03/30/2017
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
ms.openlocfilehash: 87c2d7cd65228f0218082d9126989db8c9275c70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726915"
---
# <a name="queues-and-reliable-sessions"></a>Colas y sesiones de confianza

Las colas y las sesiones de confianza son las características de Windows Communication Foundation (WCF) que implementan la mensajería confiable. En los temas incluidos en esta sección se describen las características de mensajería confiable de WCF.  
  
 La mensajería de confianza se define como la manera en que un origen de mensajería de confianza (denominado origen) transfiere mensajes de manera fiable a un destino de mensajería de confianza (denominado destino).  
  
 La mensajería de confianza tiene los siguientes aspectos clave:  
  
- Transfiera garantías para los mensajes enviados desde un origen a un destino sin tener en cuenta los errores de transporte o de transferencia de los mensajes.  
  
- Separación del origen y el destino, que proporciona errores y recuperaciones independientes del origen y el destino, así como una transferencia y entrega de mensajes confiable, incluso cuando el origen o el destino no están disponibles.  
  
 La mensajería de confianza a menudo viene acompañada de una alta latencia. La latencia es el tiempo que tarda un mensaje en alcanzar el destino desde el origen. WCF, por lo tanto, proporciona los siguientes tipos de mensajería de confianza:  
  
- [Sesiones confiables](reliable-sessions.md), que ofrecen transferencia confiable sin el costo de latencia alta  
  
- [Colas en WCF](queues-in-wcf.md), que ofrecen transferencias de confianza y separación entre el origen y el destino.  
  
## <a name="reliable-sessions"></a>Sesiones de confianza  

 Las sesiones de confianza proporcionan una transferencia confiable de un punto de conexión a otro de mensajes entre un origen y un destino mediante el protocolo WS-ReliableMessaging, sin tener en cuenta el número o tipo de intermediarios que separan los puntos de conexión de la mensajería (origen y destino). Esto incluye a cualquier intermediario de transporte que no utilice SOAP (por ejemplo, los servidores proxy HTTP) o los intermediarios que utilicen SOAP (por ejemplo, los puentes o enrutadores basados en SOAP) que son necesarios para que los mensajes fluyan entre los extremos. Las sesiones confiables utilizan una ventana de transferencia en memoria para enmascarar errores de nivel de mensaje de SOAP y restablecer las conexiones en el caso de errores de transporte.  
  
 Las sesiones de confianza proporcionan transferencias de mensajes de confianza de latencia baja. Los proporcionan para los mensajes SOAP sobre cualquier proxy o intermediario, el equivalente a lo que TCP proporciona para los paquetes sobre puentes de IP. Para obtener más información acerca de las sesiones confiables, vea [sesiones confiables](reliable-sessions.md).  
  
## <a name="queues"></a>Colas  

 Las colas en WCF proporcionan transferencias confiables de mensajes y separación entre orígenes y destinos a costa de una latencia alta. La comunicación en cola de WCF se basa en Message Queue Server (también conocido como MSMQ).  
  
 MSMQ se distribuye como una opción con Windows que se ejecuta como un servicio de NT. Captura mensajes para la transmisión en una cola de transmisión en nombre del origen y lo entrega a una cola de destino. La cola de destino acepta los mensajes en nombre del destino para la entrega posterior siempre que el destino solicite mensajes. Los administradores de cola de MSMQ implementan un protocolo de transferencias de mensajes de confianza para que los mensajes no se pierdan durante la transmisión. El protocolo puede ser nativo o basado en SOAP, como, por ejemplo, Soap Reliable Messaging Protocol (SRMP).  
  
 La separación, acoplada con las transferencias de mensaje de confianza entre colas, permite que las aplicaciones que están acopladas se comuniquen de forma fiable. A diferencia de las sesiones de confianza, el origen y el destino no tienen que ejecutarse a la vez. Esto habilita escenarios de forma implícita allí donde se usan las colas como mecanismo de nivelación de carga cuando hay una discordancia entre la velocidad de producción de mensajes por parte del origen y la velocidad de uso de mensajes por parte del destino. Para obtener más información acerca de las colas, vea [colas en WCF](queues-in-wcf.md).  
  
## <a name="see-also"></a>Vea también

- [Colas en WCF](queues-in-wcf.md)
- [Las colas en WCF](queuing-in-wcf.md)
- [Sesiones de confianza](reliable-sessions.md)
- [Información general de sesiones confiables](reliable-sessions-overview.md)
