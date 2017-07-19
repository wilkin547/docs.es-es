---
title: "Configuraci&#243;n autom&#225;tica de IPv6 | Microsoft Docs"
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
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Configuraci&#243;n autom&#225;tica de IPv6
Un objetivo importante para IPv6 es admitir el dispositivo PnP de nodo.  Es decir, debe ser posible conectar un nodo en una red IPv6 y hacer automáticamente configurar sin ninguna intervención humana.  
  
## Tipo de configuración automática  
 IPv6 admite los siguientes tipos de configuración automática:  
  
-   **Stateful auto\-configuration**.  Este tipo de configuración requiere cierto nivel de intervención humana porque necesita Protocolo de configuración dinámica de host para el servidor de IPv6 \(DHCPv6\) para la instalación y la administración de los nodos.  El servidor DHCPv6 mantiene una lista de nodos a los que proporcione la información de configuración.  También mantiene información de estado de modo que el servidor sabe cuánto tiempo cada dirección está en uso, y cuándo puede ser disponibles para la reasignación.  
  
-   **Stateless auto\-configuration**.  Este tipo de configuración es adecuado para las pequeñas organizaciones e individuos.  En este caso, cada hospedada determina a sus direcciones del contenido de anuncios de enrutador recibidos.  Mediante el estándar IEEE EUI\-64 para definir la parte del id. de red de dirección, es razonable asumir la exclusividad de la dirección del host en el vínculo.  
  
 Independientemente de cómo se determina la dirección, el nodo debe comprobar que la dirección posible es única en el vínculo local.  Esto hace enviando un mensaje de solicitud de vecino la dirección potencial.  Si el nodo recibe cualquier respuesta, sabe que la dirección ya está en uso y debe determinar a otra dirección.  
  
## Movilidad de IPv6  
 La proliferación de dispositivos móviles ha introducido un nuevo requisito: Un dispositivo debe poder cambiar arbitrariamente ubicaciones en Internet IPv6 pero mantener conexiones existentes.  Para proporcionar esta funcionalidad, un nodo móvil se asigna una dirección particular en el que se puede tener acceso siempre.  Cuando el nodo móvil está en casa, se conecta al vínculo de inicio y utiliza su dirección particular.  Cuando el nodo móvil es de salida, un agente home, que normalmente es un enrutador, los mensajes de relés entre el nodo móvil y los nodos que se está comunicando.  
  
## Vea también  
 [Protocolo de Internet versión 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)