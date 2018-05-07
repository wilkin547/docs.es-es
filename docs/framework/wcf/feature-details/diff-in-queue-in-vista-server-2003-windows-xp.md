---
title: Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
ms.openlocfilehash: d956a72c9413384176c10effefc0307b09744c4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a>Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP
En este tema se resume las diferencias en la característica de colas de Windows Communication Foundation (WCF) entre [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], y [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
## <a name="application-specific-dead-letter-queue"></a>Cola de mensajes no enviados específica de la aplicación  
 Los mensajes en cola pueden permanecer indefinidamente en la cola si la aplicación receptora no los lee en un modo oportuno. Este comportamiento no es aconsejable si los mensajes son dependientes del tiempo. Los mensajes dependientes del tiempo tienen una propiedad `TimeToLive` establecida en el enlace en cola. Esta propiedad indica cuánto tiempo pueden estar los mensajes en la cola antes de expirar. Los mensajes caducados se envían a la cola especial llamada cola de mensajes no enviados. Un mensaje también puede terminar en una cola de mensajes no enviados por otras razones, como superar una cuota de la cola o experimentar un error de autenticación.  
  
 Normalmente, existe una cola de mensajes no enviados única para todo el sistema para todas las aplicaciones en cola que comparten un administrador de cola. Una cola de mensajes no enviados para cada aplicación permite un mejor aislamiento entre las aplicaciones en cola que comparten un administrador de cola, de modo que permiten que estas aplicaciones especifiquen su propia cola de mensajes no enviados específica de la aplicación. Una aplicación que comparte una cola de mensajes no enviados con otras aplicaciones tiene que examinar la cola para encontrar mensajes que son aplicables. Con una cola de mensajes con problemas de entrega específica de la aplicación, la aplicación puede estar segura de que todos los mensajes de su cola de mensajes con problemas de entrega le corresponden.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)] proporciona colas de mensajes con problemas de entrega específicas de la aplicación. Las colas de mensajes no enviados específicas de la aplicación no están disponibles en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)]y las aplicaciones deben utilizar la cola de mensajes no enviados para todo el sistema.  
  
## <a name="poison-message-handling"></a>Administración de mensajes dudosos  
 Un mensaje dudoso es un mensaje que ha superado el número máximo de intentos de entrega a la aplicación receptora. Esta situación se puede presentar cuando una aplicación que lee un mensaje de una cola transaccional no puede procesar inmediatamente el mensaje debido a los errores. Si la aplicación anula la transacción en la que se recibió el mensaje en cola, devuelve el mensaje a la cola. La aplicación intenta a continuación recuperar de nuevo el mensaje en una nueva transacción. Si no se corrige el problema que produce el error, la aplicación receptora puede entrar en un bucle recibiendo y anulando el mismo mensaje hasta que supere el número máximo de intentos de entrega, y ello provoca un mensaje dudoso.  
  
 Las diferencias clave entre Message Queuing (MSMQ) en [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)] que son pertinentes para la administración dudosa incluyen lo siguiente:  
  
-   MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)] admite subcolas, mientras que [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)] no las admiten. Las subcolas se utilizan en el control de mensajes dudosos. Las colas de reintento y la cola dudosa son subcolas en la cola de la aplicación que se crea dependiendo de los valores de control del mensaje dudoso. `MaxRetryCycles` dicta cuántas subcolas de reintento se crean. Por lo tanto, cuando se ejecutan en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], `MaxRetryCycles` se omiten y no se permite `ReceiveErrorHandling.Move`.  
  
-   MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)] admite una confirmación de que no se pudo realizar la acción, mientras que [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)] no. Una confirmación de que no se pudo realizar la acción del administrador de la cola receptora hace que el administrador de la cola emisora coloque el mensaje rechazado en la cola de mensajes no enviados. Como tal, `ReceiveErrorHandling.Reject` no se permite con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)] admite una propiedad de mensaje que mantiene un recuento del número de veces que se intenta la entrega del mensaje. Esta propiedad de recuento de anulación no está disponible en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. WCF mantiene el recuento de anulación en memoria, por lo que es posible que esta propiedad no contenga un valor preciso cuando el mismo mensaje es leído por más de un servicio WCF en una granja de servidores Web.  
  
## <a name="remote-transactional-read"></a>Lectura transaccional remota  
 MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)] admite lecturas transaccionales remotas. Esto permite que una aplicación que lea de una cola se hospede en un equipo diferente de aquel en el que se hospeda la cola. Así se garantiza la posibilidad de que un conjunto de servicios lea en una cola central, lo que aumenta el rendimiento total del sistema. También se garantiza que, si se produce un error al leer y procesar el mensaje, la transacción se revierte y el mensaje permanece en la cola para su posterior procesamiento.  
  
## <a name="see-also"></a>Vea también  
 [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 [Control de mensajes dudosos](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
