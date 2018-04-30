---
title: Servicios de confianza
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF [WCF], reliable messaging
- Windows Communication Foundation [WCF], reliable messaging
- WCF [WCF], reliable sessions
- Windows Communication Foundation [WCF], reliable sessions
- service contracts [WCF], reliable services
ms.assetid: 07814ed0-0775-47f2-987b-d8134fdd5099
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9cbaef77f4dce609d36ba4b679d8c569b648fa5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="reliable-services"></a>Servicios de confianza
Las colas y las sesiones de confianza son las características de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] que implementan la mensajería de confianza. En este tema se explican las características de mensajería confiable de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 *Mensajería de confianza* se muestra cómo un origen de mensajería confiable (denominado el *origen*) transfiere mensajes de forma confiable a un destino de mensajería confiable (denominado el *destino*).  
  
 La mensajería de confianza realiza las funciones siguientes:  
  
-   Transfiere garantías para los mensajes enviados desde un origen a un destino sin tener en cuenta la transferencia de los mensajes o los errores de transporte.  
  
-   Separa el origen del destino. Este hecho proporciona un error independiente y la recuperación del origen y el destino, además de la transferencia confiable y la entrega de los mensajes aun cuando no está disponible el origen o el destino.  
  
 La mensajería de confianza a menudo viene acompañada de una alta latencia. *Latencia* es el tiempo necesario para que el mensaje llegar al destino desde el origen. Por consiguiente, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona los tipos siguientes de mensajería de confianza:  
  
-   [Las sesiones confiables](../../../docs/framework/wcf/feature-details/reliable-sessions.md), que ofrece transferencia confiable sin el costo de latencia alta.  
  
-   [Las colas en WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md), que ofrece transferencias confiables y separación entre el origen y el destino.  
  
## <a name="reliable-sessions"></a>Sesiones de confianza  
 Las sesiones de confianza proporcionan transferencia confiable de un extremo a otro de mensajes entre un origen y un destino mediante el protocolo de mensajería de confianza WS, sin tener en cuenta el número o tipo de intermediarios que separan los extremos de la mensajería (origen y destino). Esto incluye a cualquier intermediario de transporte que no utilice SOAP (por ejemplo, los servidores proxy HTTP) o los intermediarios que utilicen SOAP (por ejemplo, los puentes o enrutadores basados en SOAP) que son necesarios para que los mensajes fluyan entre los extremos. Las sesiones confiables utilizan una ventana de transferencia en memoria para enmascarar errores de nivel de mensaje de SOAP y restablecer las conexiones en el caso de errores de transporte.  
  
 Las sesiones de confianza proporcionan transferencias de mensajes de confianza de latencia baja. Los proporcionan para los mensajes SOAP sobre cualquier proxy o intermediario, el equivalente a lo que TCP proporciona para los paquetes sobre puentes de IP. Para obtener más información acerca de las sesiones confiables, vea [sesiones confiables](../../../docs/framework/wcf/feature-details/reliable-sessions.md).  
  
### <a name="queues"></a>Colas  
 Las colas de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporcionan transferencias confiables de mensajes y separación entre los orígenes y los destinos a costa de una latencia alta. La comunicación puesta en cola de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se basa en Message Queuing (MSMQ).  
  
 MSMQ se distribuye como un componente opcional con Windows. El servicio de MSMQ se ejecuta como un servicio de Windows. Captura mensajes para la transmisión en una cola de transmisión en nombre del origen y lo entrega a una cola de destino. La cola de destino acepta los mensajes en nombre del destino para la entrega posterior siempre que el destino solicite mensajes. Los administradores de MSMQ implementan un protocolo de transferencias de mensajes de confianza de manera que los mensajes no se pierdan durante la transmisión. El protocolo puede ser nativo o un protocolo basado en SOAP denominado "Protocolo de mensajería de confianza de SOAP" (SRMP).  
  
 La separación, acoplada con las transferencias de mensaje de confianza entre colas, permite que las aplicaciones que están acopladas se comuniquen de forma fiable. A diferencia de las sesiones de confianza, el origen y el destino no tienen que ejecutarse a la vez. Esto habilita escenarios de forma implícita allí donde se usan las colas como un mecanismo de nivelación de carga cuando la tasa de origen de la producción de mensajes y la tasa de destino de consumo de mensajes no coinciden. Para obtener más información acerca de las colas, consulte [colas en WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general de sesiones de confianza](../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 [Colas en WCF](../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
