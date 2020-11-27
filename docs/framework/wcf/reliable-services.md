---
title: Reliable Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
ms.openlocfilehash: d028af80a30fd18b6aa6e9678e7fd8788e7b7b95
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249753"
---
# <a name="reliable-services"></a>Reliable Services

Las colas y las sesiones de confianza son las características de Windows Communication Foundation (WCF) que implementan la mensajería confiable. En este tema se explican las características de mensajería de confianza de WCF.  
  
 La *mensajería de confianza* es la forma en que un origen de mensajería de confianza (denominado *origen*) transfiere mensajes de manera confiable a un destino de mensajería de confianza (denominado *destino*).  
  
 La mensajería de confianza realiza las funciones siguientes:  
  
- Transfiere garantías para los mensajes enviados desde un origen a un destino sin tener en cuenta la transferencia de los mensajes o los errores de transporte.  
  
- Separa el origen del destino. Este hecho proporciona un error independiente y la recuperación del origen y el destino, además de la transferencia confiable y la entrega de los mensajes aun cuando no está disponible el origen o el destino.  
  
 La mensajería de confianza a menudo viene acompañada de una alta latencia. La *latencia* es el tiempo que tarda el mensaje en alcanzar el destino desde el origen. WCF, por lo tanto, proporciona los siguientes tipos de mensajería de confianza:  
  
- [Sesiones confiables](./feature-details/reliable-sessions.md), que ofrece transferencia confiable sin el costo de alta latencia.  
  
- [Colas en WCF](./feature-details/queues-in-wcf.md), que proporciona transferencias de confianza y separación entre el origen y el destino.  
  
## <a name="reliable-sessions"></a>Sesiones de confianza  

 Las sesiones de confianza proporcionan transferencia confiable de un punto de conexión a otro de mensajes entre un origen y un destino mediante el protocolo de mensajería de confianza WS, sin tener en cuenta el número o tipo de intermediarios que separan los puntos de conexión de la mensajería (origen y destino). Esto incluye a cualquier intermediario de transporte que no utilice SOAP (por ejemplo, los servidores proxy HTTP) o los intermediarios que utilicen SOAP (por ejemplo, los puentes o enrutadores basados en SOAP) que son necesarios para que los mensajes fluyan entre los extremos. Las sesiones confiables utilizan una ventana de transferencia en memoria para enmascarar errores de nivel de mensaje de SOAP y restablecer las conexiones en el caso de errores de transporte.  
  
 Las sesiones de confianza proporcionan transferencias de mensajes de confianza de latencia baja. Los proporcionan para los mensajes SOAP sobre cualquier proxy o intermediario, el equivalente a lo que TCP proporciona para los paquetes sobre puentes de IP. Para obtener más información acerca de las sesiones confiables, vea [sesiones confiables](./feature-details/reliable-sessions.md).  
  
### <a name="queues"></a>Colas  

 Las colas en WCF proporcionan transferencias confiables de mensajes y separación entre orígenes y destinos a costa de una latencia alta. La comunicación en cola de WCF se basa en Message Queuing (MSMQ).  
  
 MSMQ se distribuye como un componente opcional con Windows. El servicio de MSMQ se ejecuta como un servicio de Windows. Captura mensajes para la transmisión en una cola de transmisión en nombre del origen y lo entrega a una cola de destino. La cola de destino acepta los mensajes en nombre del destino para la entrega posterior siempre que el destino solicite mensajes. Los administradores de MSMQ implementan un protocolo de transferencias de mensajes de confianza de manera que los mensajes no se pierdan durante la transmisión. El protocolo puede ser nativo o un protocolo basado en SOAP denominado "Protocolo de mensajería de confianza de SOAP" (SRMP).  
  
 La separación, acoplada con las transferencias de mensaje de confianza entre colas, permite que las aplicaciones que están acopladas se comuniquen de forma fiable. A diferencia de las sesiones de confianza, el origen y el destino no tienen que ejecutarse a la vez. Esto habilita escenarios de forma implícita allí donde se usan las colas como un mecanismo de nivelación de carga cuando la tasa de origen de la producción de mensajes y la tasa de destino de consumo de mensajes no coinciden. Para obtener más información acerca de las colas, vea [colas en WCF](./feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Vea también

- [Información general de sesiones confiables](./feature-details/reliable-sessions-overview.md)
- [Las colas en WCF](./feature-details/queuing-in-wcf.md)
