---
description: 'Más información acerca de: Enrutamiento de IPv6'
title: Enrutamiento de IPv6
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: 75499a7380ab0ea7c38c83a6407a0c2a269b5fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672041"
---
# <a name="ipv6-routing"></a>Enrutamiento de IPv6

Una de las ventajas de IPv6 es el mecanismo de enrutamiento flexible. Debido a la manera en que se asignaban y todavía se asignan los identificadores de red IPv4, los enrutadores que se encuentran en las redes troncales de Internet deben mantener grandes tablas de enrutamiento. Estos enrutadores deben conocer todas las rutas con el fin de reenviar los paquetes que se dirigen potencialmente a cualquier nodo de Internet. Con su capacidad para agregar direcciones, IPv6 permite el direccionamiento flexible y reduce drásticamente el tamaño de las tablas de enrutamiento. En esta nueva arquitectura de direccionamiento, los enrutadores intermedios deben realizar un seguimiento únicamente de la parte local de su red para reenviar los mensajes de forma adecuada.  
  
## <a name="neighbor-discovery"></a>Detección de equipos cercanos  

 Algunas de las características proporcionadas por la detección de equipos cercanos son las siguientes:  
  
- Detección de enrutadores. Permite que los hosts identifiquen los enrutadores locales.  
  
- Resolución de direcciones. Permite que los nodos resuelvan una dirección de nivel de vínculo para una dirección de próximo salto correspondiente (sustitución del Protocolo de resolución de direcciones, también denominado ARP).  
  
- Configuración automática de direcciones. Permite a los hosts configurar automáticamente las direcciones globales y locales del sitio.  
  
 La detección de equipos cercanos usa mensajes del Protocolo de mensajes de control de Internet para IPv6 (ICMPv6) que incluyen:  
  
- Anuncio de enrutador. Enviado por un enrutador de forma seudoperiódica o en respuesta a una convocatoria de enrutador. Los enrutadores IPv6 usan anuncios de enrutador para anunciar su disponibilidad, prefijos de direcciones y otros parámetros.  
  
- Convocatoria de enrutador. Enviada por un host para solicitar que los enrutadores del vínculo envíen inmediatamente un anuncio de enrutador.  
  
- Convocatoria de vecino. Enviada por los nodos para la resolución de direcciones, la detección de direcciones duplicadas o la comprobación de que un vecino sigue siendo accesible.  
  
- Anuncio de vecino. Enviada por los nodos para responder a una convocatoria de vecino o para notificar a los vecinos un cambio en la dirección de nivel de vínculo.  
  
- Redireccionamiento. Enviado por los enrutadores para indicar una dirección mejor de próximo salto a un destino determinado para un nodo de envío.  
  
## <a name="see-also"></a>Vea también

- [Protocolo de Internet versión 6](internet-protocol-version-6.md)
- [Sockets](sockets.md)
