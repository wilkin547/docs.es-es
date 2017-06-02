---
title: "Nubes PNRP | Microsoft Docs"
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
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: 4
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 4
---
# Nubes PNRP
Un PNRP “nube” representa un conjunto de nodos que pueden comunicarse entre sí a través de la red.  El término “nube” es sinónimo con “malla del mismo nivel” y “gráfico entre iguales”.  
  
 La comunicación entre los nodos nunca debe cruzar de una nube a otra.  Una instancia de <xref:System.Net.PeerToPeer.Cloud> se identifica singularmente con su nombre, que distingue entre mayúsculas y minúsculas.  Un único elemento del mismo nivel o nodo puede estar conectado a más de una nube.  
  
 Las nubes están estrechamente enlazadas a las interfaces de red.  En un equipo multitarjeta con dos tarjetas de red asociadas a subredes diferentes, se devolverán tres nubes: una para cada una de las direcciones locales de vínculo de cada interfaz y una nube de ámbito global única.  
  
 Las aplicaciones tres de PNRP se nublan “los ámbitos”, donde un ámbito es una agrupación de los equipos que pueden encontrarse:  
  
-   Nube global corresponde a la dirección IPv6 el ámbito global y direcciones globales y representa todos los equipos de Internet IPv6 completo.  Hay una sola nube global.  
  
-   Nube de vínculo\- local correspondiente a la dirección IPv6 de vínculo\- local el ámbito y direcciones locales del vínculo.  Una nube de vínculo\- local es para un vínculo específico, que normalmente es igual que la subred local asociada.  Puede haber nubes varias de vínculo\- local.  
  
 Una tercera nube, nube sitio\- concreta, correspondiente a la dirección IPv6 de sitio el ámbito y direcciones locales del sitio.  Ha quedado desusada esta nube, aunque todavía se admiten en PNRP.  
  
## Nubes  
 Las nubes de PNRP están representadas por las instancias de la clase de <xref:System.Net.PeerToPeer.Cloud> .  Los grupos de nubes se utilizó un par se representan por instancias de la clase enumerable de <xref:System.Net.PeerToPeer.CloudCollection> .  Las colecciones de nubes de PNRP conocidas el par de la actual pueden ser obtenidas llamando al método estático de <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A> .  
  
 Las nubes individuales tienen nombres únicos, representados como una cadena Unicode de 256 caracteres.  Estos nombres, junto con el ámbito anterior, se utilizan para construir las instancias únicas de la clase de nube.  Estas instancias se pueden serializar y volver a crear para el uso persistente.  
  
 Una instancia de nube una vez creado o se, los nombres de par se pueden registrar con él para crear una malla de pares conocidos.  
  
## Vea también  
 <xref:System.Net.PeerToPeer.Cloud>   
 [Protocolo de resolución de nombres del mismo nivel](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)