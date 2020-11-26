---
title: Escenarios de canal del mismo nivel
ms.date: 03/30/2017
ms.assetid: dae6e0f7-900c-45ee-8be9-3647698382fb
ms.openlocfilehash: 3c05583a6795eb5b78b54d287f7f4d4fe2c8d39e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247933"
---
# <a name="peer-channel-scenarios"></a>Escenarios de canal del mismo nivel

Las API del canal del mismo nivel admiten los escenarios de desarrollo siguientes.  
  
## <a name="publicationsubscription-messaging"></a>Mensajería de publicación/suscripción  

 Las compañías que crean aplicaciones de publicación/suscripción (por ejemplo, tableros de cotizaciones y editores de titulares de noticias, de resultados deportivos y previsiones meteorológicas) pueden usar el canal del mismo nivel para aplicaciones sin servidor. Por ejemplo, los usuarios pueden obtener los últimos resultados deportivos mediante la unión de una malla común (o grupo de clientes), así como propagar una gran cantidad de datos actualizados del evento deportivo sin aumentar la carga del servidor. Esto ayuda al proveedor de datos a proporcionar una mayor calidad de servicio sin aumentar sustancialmente la inversión en tecnologías basadas en servidor.  
  
## <a name="collaboration"></a>Colaboración  

 Los fabricantes de software independiente (ISV) pueden crear aplicaciones que permiten a la gente crear grupos apretados para la participación en actividades p2p (peer-to-peer). Por ejemplo, esto puede incluir equipos de usuarios que trabajen en proyectos de colaboración, el uso compartido de imágenes entre amigos, actividades para planear fiestas, etc. Por lo general, en estas actividades siempre se usan servidores; sin embargo, el canal del mismo nivel habilita escenarios de acceso sin conexión que no suelen estar implementados tan fácilmente en un modelo cliente-servidor tradicional, con lo que se ofrece un servicio más rentable.  
  
## <a name="distributed-processing-and-compute-clusters"></a>Procesamiento distribuido y clústeres de cálculo  

 Los clústeres de cálculo y el procesamiento distribuido se utilizan normalmente para cómputos a gran escala, como modelado financiero/meteorológico y descodificación del ADN humano. Normalmente, esto se consigue haciendo que los servidores asignen individualmente tareas a todos los clientes que participan en el clúster de cálculo. Estos servidores también pueden tener demandas adicionales; por ejemplo, puede que se necesite que se completen todas las tareas en un intervalo determinado, lo que requiere más de un equipo por tarea. Además, si cualquier cliente que ejecuta una tarea falla, otro cliente debe poder tomar esa tarea y realizar el trabajo en él. De la misma manera, más de un cliente puede que tenga que ejecutar la misma tarea para asegurar que los resultados sean coherentes. Aunque los servidores pueden ejecutar este tipo de coordinación de cliente, puede crear una solución p2p en la que los clientes que reciben independientemente una tarea determinan los requisitos de servidor de la tarea y usan una malla de cálculo para determinar cómo completar esa tarea.  
  
## <a name="gaming"></a>Juegos  

 Con el canal del mismo nivel, los desarrolladores de aplicaciones pueden crear versiones sin servidor de sus juegos, en los cuales, los movimientos se transmiten y se sincronizan con otros jugadores mediante un mecanismo p2p en vez de a través de un servidor central. Para ISVs pequeños, esto ayuda a eliminar costes operacionales asociados a la implementación, manutención y prestación de servicio de los servidores. Se pueden jugar  a los juegos diseñados con una arquitectura p2p en todo Internet, además de en redes locales (también inalámbricas). Se pueden desarrollar algunas actividades de ocio secundarias, como chat (fuera y dentro del juego), mediante una red de punto a punto.  
  
## <a name="see-also"></a>Vea también

- [Conceptos del canal del mismo nivel](peer-channel-concepts.md)
