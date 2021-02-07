---
description: Más información acerca de las diferencias en las características de puesta en cola en Windows Vista, Windows Server 2003 y Windows XP
title: Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
ms.openlocfilehash: 6a6206b3033454528797f3c8f4276add9c35023d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756388"
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a>Diferencias en las características de cola en Windows Vista, Windows Server 2003 y Windows XP

En este tema se resumen las diferencias en la característica de colas de Windows Communication Foundation (WCF) entre Windows Vista, Windows Server 2003 y Windows XP.  
  
## <a name="application-specific-dead-letter-queue"></a>Cola de mensajes no enviados específica de la aplicación  

 Los mensajes en cola pueden permanecer indefinidamente en la cola si la aplicación receptora no los lee en un modo oportuno. Este comportamiento no es aconsejable si los mensajes son dependientes del tiempo. Los mensajes dependientes del tiempo tienen una propiedad `TimeToLive` establecida en el enlace en cola. Esta propiedad indica cuánto tiempo pueden estar los mensajes en la cola antes de expirar. Los mensajes caducados se envían a la cola especial llamada cola de mensajes no enviados. Un mensaje también puede terminar en una cola de mensajes no enviados por otras razones, como superar una cuota de la cola o experimentar un error de autenticación.  
  
 Normalmente, existe una cola de mensajes no enviados única para todo el sistema para todas las aplicaciones en cola que comparten un administrador de cola. Una cola de mensajes no enviados para cada aplicación permite un mejor aislamiento entre las aplicaciones en cola que comparten un administrador de cola, de modo que permiten que estas aplicaciones especifiquen su propia cola de mensajes no enviados específica de la aplicación. Una aplicación que comparte una cola de mensajes no enviados con otras aplicaciones tiene que examinar la cola para encontrar mensajes que son aplicables. Con una cola de mensajes con problemas de entrega específica de la aplicación, la aplicación puede estar segura de que todos los mensajes de su cola de mensajes con problemas de entrega le corresponden.  
  
 Windows Vista proporciona colas de mensajes no enviados específicos de la aplicación. Las colas de mensajes no enviados específicas de la aplicación no están disponibles en Windows Server 2003 y Windows XP, y las aplicaciones deben usar la cola de mensajes no enviados en todo el sistema.  
  
## <a name="poison-message-handling"></a>Administración de mensajes dudosos  

 Un mensaje dudoso es un mensaje que ha superado el número máximo de intentos de entrega a la aplicación receptora. Esta situación se puede presentar cuando una aplicación que lee un mensaje de una cola transaccional no puede procesar inmediatamente el mensaje debido a los errores. Si la aplicación anula la transacción en la que se recibió el mensaje en cola, devuelve el mensaje a la cola. La aplicación intenta a continuación recuperar de nuevo el mensaje en una nueva transacción. Si no se corrige el problema que produce el error, la aplicación receptora puede entrar en un bucle recibiendo y anulando el mismo mensaje hasta que supere el número máximo de intentos de entrega, y ello provoca un mensaje dudoso.  
  
 Entre las principales diferencias entre Message Queue Server (MSMQ) en Windows Vista, Windows Server 2003 y Windows XP que son relevantes para la administración de mensajes dudosos se incluyen las siguientes:  
  
- MSMQ en Windows Vista admite subcolas, mientras que Windows Server 2003 y Windows XP no admiten subcolas. Las subcolas se utilizan en el control de mensajes dudosos. Las colas de reintento y la cola dudosa son subcolas en la cola de la aplicación que se crea dependiendo de los valores de control del mensaje dudoso. `MaxRetryCycles` dicta cuántas subcolas de reintento se crean. Por lo tanto, cuando se ejecuta en Windows Server 2003 o Windows XP, `MaxRetryCycles` se omiten y `ReceiveErrorHandling.Move` no se permiten.  
  
- MSMQ en Windows Vista admite la confirmación negativa, mientras que Windows Server 2003 y Windows XP no lo hacen. Una confirmación de que no se pudo realizar la acción del administrador de la cola receptora hace que el administrador de la cola emisora coloque el mensaje rechazado en la cola de mensajes no enviados. Como tal, `ReceiveErrorHandling.Reject` no se permite con Windows Server 2003 y Windows XP.  
  
- MSMQ en Windows Vista admite una propiedad de mensaje que mantiene el recuento del número de veces que se intenta la entrega del mensaje. Esta propiedad de recuento de anulación no está disponible en Windows Server 2003 y Windows XP. WCF mantiene el recuento de anulación en memoria, por lo que es posible que esta propiedad no contenga un valor preciso cuando el mismo mensaje es leído por más de un servicio WCF en una granja de servidores Web.  
  
## <a name="remote-transactional-read"></a>Lectura transaccional remota  

 MSMQ en Windows Vista admite lecturas transaccionales remotas. Esto permite que una aplicación que lea de una cola se hospede en un equipo diferente de aquel en el que se hospeda la cola. Así se garantiza la posibilidad de que un conjunto de servicios lea en una cola central, lo que aumenta el rendimiento total del sistema. También se garantiza que, si se produce un error al leer y procesar el mensaje, la transacción se revierte y el mensaje permanece en la cola para su posterior procesamiento.  
  
## <a name="see-also"></a>Vea también

- [Utilización de las colas de mensajes no enviados para administrar los errores en la transferencia de mensajes](using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Control de mensajes dudosos](poison-message-handling.md)
