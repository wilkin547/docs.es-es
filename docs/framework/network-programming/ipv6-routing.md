---
title: "Enrutamiento de IPv6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Enrutamiento de IPv6
Un mecanismo de enrutamiento flexible es una ventaja de IPv6.  Debido a la manera en que los id. de red IPv4 estaban y se asignan, las tablas de enrutamiento grandes es necesario mantenida por los enrutadores que están en las redes troncales de internet.  Estos enrutadores deben conocer todas las rutas para reenviar los paquetes que potencialmente se dirigen a un nodo de internet.  Con la capacidad de agregar direcciones IPv6, permite el direccionamiento flexible y reducen drásticamente el tamaño de tablas de enrutamiento.  En esta nueva arquitectura de direccionamiento, los enrutadores intermedios deben mantener un seguimiento sólo la parte local de la red para reenviar los mensajes correctamente.  
  
## Detección de vecinos  
 Algunas de las características proporcionadas por la detección de vecinos son:  
  
-   Detección de enrutador.  Esto permite a los hosts que identifican los enrutadores locales.  
  
-   Resolución de direcciones.  Esto permite que los nodos satisfacen una dirección de nivel de vínculo para una dirección correspondiente para el próximo salto \(un reemplazo para el Protocolo de resolución de direcciones \[ARP\]\).  
  
-   Configuración automática de dirección.  Esto permite a los hosts automáticamente configurar el sitio\- local y direcciones globales.  
  
 La detección de vecinos utiliza el Protocolo de mensajes de control de Internet para los mensajes de IPv6 \(ICMPv6\) que incluyen:  
  
-   Anuncios de enrutador.  Enviado por un enrutador en una base seudo\-periódica o en respuesta a una solicitación de enrutador.  Anuncios de enrutador de los enrutadores de IPv6 para anunciar de su disponibilidad, de prefijos de dirección, y otros parámetros.  
  
-   Solicitación de enrutador.  Enviado por un host solicitar que los enrutadores en el vínculo envía un anuncio de enrutador inmediatamente.  
  
-   Solicitud de vecino.  Enviado por los nodos para la resolución de direcciones, detección duplicada de la dirección, o comprobar que un vecino todavía es alcanzable.  
  
-   Anuncio vecino.  Enviado por nodos para responder a una solicitud de vecino o para notificar a los vecinos de un cambio en dirección de nivel de vínculo.  
  
-   Redirección.  Enviado por los enrutadores para indicar un mejor dirección para el próximo saltar a un destino determinado para un nodo de envío.  
  
## Vea también  
 [Protocolo de Internet versión 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)