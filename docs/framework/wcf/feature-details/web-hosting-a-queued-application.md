---
title: Alojamiento web de una aplicación en cola
ms.date: 03/30/2017
ms.assetid: c7a539fa-e442-4c08-a7f1-17b7f5a03e88
ms.openlocfilehash: c2b41ee1d0a82693760bc3e1b6144d2190153f24
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249779"
---
# <a name="web-hosting-a-queued-application"></a>Alojamiento web de una aplicación en cola

El Servicio de activación de procesos de Windows (WAS) administra la activación y la duración de los procesos de trabajo que contienen aplicaciones que hospedan los servicios de Windows Communication Foundation (WCF). El modelo de proceso de WAS generaliza el proceso IIS 6.0 para el servidor HTTP mediante la eliminación de la dependencia en HTTP. Esto permite a los servicios WCF usar protocolos HTTP y que no sean HTTP, como net. MSMQ y MSMQ. FormatName, en un entorno de hospedaje que admita la activación basada en mensaje y ofrece la posibilidad de hospedar un gran número de aplicaciones en un equipo determinado.  
  
 WAS incluye un servicio de activación de Message Queuing (MSMQ) que activa una aplicación en cola cuando hay uno o más mensajes en una de las colas que la aplicación usa. El servicio de activación MSMQ es un servicio NT que se inicia automáticamente de forma predeterminada.  
  
 Para obtener más información acerca de WAS y sus ventajas, consulte [hospedaje en el servicio de activación de procesos de Windows](hosting-in-windows-process-activation-service.md). Para obtener más información acerca de MSMQ, consulte [información general sobre colas](queues-overview.md).
  
## <a name="queue-addressing-in-was"></a>Direccionamiento de la cola en WAS  

 Las aplicaciones de WAS tienen direcciones de Identificador uniforme de recursos (URI). Las direcciones de la aplicación tienen dos partes: un prefijo base de URI y un específico de la aplicación, dirección relativa (ruta de acceso). Estas dos partes proporcionan la dirección externa de una aplicación cuando se combinan. El prefijo de URI base se construye a partir del enlace de sitio y se utiliza para todas las aplicaciones del sitio, por ejemplo, "net. MSMQ: psico", "MSMQ. FormatName: psico" o "net. TCP: combinación". A continuación, las direcciones de la aplicación se construyen tomando fragmentos de la ruta de acceso específica de la aplicación (como "/applicationOne") y agregándolos al prefijo de URI base para llegar al URI completo de la aplicación, por ejemplo, "net. MSMQ://localhost/applicationOne".  
  
 El servicio de activación MSMQ utiliza el URI de la aplicación para coincidir con la cola que el servicio de activación MSMQ debe supervisar para los mensajes. Cuando el servicio de activación MSMQ se inicia, enumera todas las colas privadas y públicas del equipo que está configurado para recibir y las supervisa para los mensajes. Cada 10 minutos, el servicio de activación MSMQ actualiza la lista de colas que tiene que supervisar. Cuando se encuentra un mensaje en una cola, el servicio de activación coincide el nombre de la cola al URI de la aplicación correspondiente más largo para el enlace net.msmq y activa la aplicación.  
  
> [!NOTE]
> La aplicación que se está activando debe coincidir (coincidencia más larga) con el prefijo del nombre de la cola.  
  
 Por ejemplo, un nombre de cola es: msmqWebHost/orderProcessing/service.svc. Si la Aplicación 1 tiene un directorio virtual /msmqWebHost/orderProcessing con un service.svc bajo el mismo y la Aplicación 2 tiene un directorio virtual /msmqWebHost con un orderProcessing.svc debajo de él, se activa la Aplicación 1. Si se elimina la Aplicación 1, se activa la Aplicación 2.  
  
> [!NOTE]
> Cuando se crea una cola, los mensajes enviados a este no activan una aplicación hasta que el servicio de activación MSMQ actualice la lista de la cola, lo cual tarda, como máximo,10 minutos desde el momento en que se creó la cola. Al reiniciar el servicio de activación, también se actualiza la lista de colas.  
  
### <a name="the-effect-of-private-and-public-queues-on-addressing"></a>El efecto de las colas privadas y públicas en Direccionamiento  

 El servicio de activación MSMQ no distingue entre supervisión de colas privadas y públicas. Como tal, no puede tener colas públicas y privadas con el mismo nombre. Si tiene, una aplicación hospedada en Web se puede activar al leer de cualquiera de las colas.  
  
### <a name="queue-configuration-for-activation"></a>Configuración de la cola para la activación  

 El servicio de activación MSMQ se ejecuta como SERVICIO DE RED. Es el servicio que supervisa las colas para activar las aplicaciones. Para que active las aplicaciones desde la cola, la cola debe proporcionar acceso al SERVICIO DE RED para ejecutar el método Peek para los mensajes en su lista de control de acceso (ACL).  
  
### <a name="poison-messaging"></a>Mensajería dudosa  

 El control de mensajes dudosos en WCF se controla mediante el canal, que no solo detecta que un mensaje es dudoso, sino que selecciona una disposición basada en la configuración del usuario. Como resultado, solo hay un mensaje único en la cola. La aplicación hospedada en Web anula las ocasiones sucesivas y el mensaje se mueve a una cola de reintento. En un punto dictado por el retraso del ciclo de reintento, el mensaje se mueve desde la cola de reintento a la cola principal para intentarlo de nuevo. Pero esto exige que el al canal en cola esté activo. Si WAS recicla la aplicación, a continuación, el mensaje permanece en la cola de reintento hasta que otro mensaje llegue a la cola principal para activar la aplicación en cola. La solución alternativa en este caso es mover de nuevo manualmente el mensaje desde la cola de reintento a la cola principal para reactivar la aplicación.  
  
### <a name="subqueue-and-system-queue-caveat"></a>Subcola y advertencia de cola de sistema  

 Una aplicación hospedada en WAS no se puede activar basándose en mensajes en una cola de sistema, como la cola de mensajes no enviados para todo el sistema o subcolas, como subcolas dudosas. Esto supone una limitación para esta versión del producto.  
  
## <a name="see-also"></a>Vea también

- [Control de mensajes dudosos](poison-message-handling.md)
- [Extremos de servicio y direccionamiento de la cola](service-endpoints-and-queue-addressing.md)
