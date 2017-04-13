---
title: "Publicaci&#243;n y resoluci&#243;n de nombres del mismo nivel | Microsoft Docs"
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
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Publicaci&#243;n y resoluci&#243;n de nombres del mismo nivel
## Publicación de Peer Name  
 Para publicar un nuevo id. de PNRP, un par realiza lo siguiente:  
  
-   Envía mensajes de publicación de PNRP a sus vecinos de caché \(los pares que ha registrado id. de PNRP en el nivel más bajo de caché\) para propagar las memorias caché.  
  
-   Elija los nodos aleatorios en la nube que no son sus vecinos y les envía las solicitudes de resolución de nombres de PNRP para su propia identificador entre PROYECTOS  El proceso resultante de la configuración de extremo utiliza las cachés de nodos aleatorios en la nube con el id. de PNRP de par de publicación.  
  
 Los nodos de la versión 2 de PNRP no publican id. de PNRP si están resolviendo pero otros id. entre PROYECTOS.  El valor del registro HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\PeerNet\\PNRP\\IPV6\-Global\\SearchOnly\=1 \(REG\_DWORD type\)especifica que los pares sólo utilizan PNRP para la resolución de nombres, nunca para publicación de nombre.  Este valor del Registro se puede configurar con la directiva de grupo.  
  
## Resolver a Peer Name  
 La localización de otros pares en una red o una nube de PNRP es un proceso compuesto de dos fases:  
  
1.  Configuración del extremo  
  
2.  Resolución de id. de PNRP  
  
 En la fase de la configuración del extremo, un par que está intentando resolver el id. de PNRP de un servicio en otro equipo determina la dirección IPv6 de ese interlocutor remoto.  El interlocutor remoto es el que publicó, o se asocia a, el id. de PNRP de equipo o servicio.  
  
 Después de confirmar que el extremo remoto se ha registrado en la nube de PNRP, el par que solicita en la fase de resolución de id. de PNRP envía una solicitud a ese extremo del mismo nivel para el id. de PNRP de servicio deseado.  El extremo envía una respuesta que confirma el id. de PNRP de servicio, un comentario, y de hasta 4 kilobytes de información adicional que el par solicitante puede utilizar para la comunicación futura.  Por ejemplo, si el extremo deseada es un servidor de juego, los datos del mismo nivel adicionales del registro del nombre pueden contener información sobre el juego, el nivel de juego, y el número actual de participantes.  
  
 En la fase de la configuración del extremo, PNRP utiliza un proceso iterativo para buscar el nodo que publicó el id. de PNRP, en las que el nodo que realiza la resolución es responsable de establecer los nodos que están sucesivamente más próximo al identificador de destino PNRP  
  
 Para realizar la resolución de nombres de PNRP, el par examina las entradas en su propia memoria caché para una entrada que coincide con el identificador de destino PNRP  Si se encuentra, el par envía un mensaje de solicitud de PNRP el par y espera una respuesta.  Si una entrada para el id. de PNRP no se encuentra, el par envía un mensaje de solicitud de PNRP el par que corresponde a la entrada que tiene un id. de PNRP que más se aproxime al identificador de destino PNRP  El nodo que recibe el mensaje de solicitud de PNRP examina su propia memoria caché y haga lo siguiente:  
  
-   Si se encuentra el id. de PNRP, las respuestas solicitadas del par de extremo directamente el par que solicita.  
  
-   Si el id. de PNRP no se encuentra y un id. de PNRP en caché está más cercano al id. de destino PNRP, el elemento solicitado envía una respuesta al par que solicita que contiene la dirección IPv6 de par que representa la entrada con un id. de PNRP que está más estrechamente la identificación de destino PNRP  Utilizando la dirección IP en la respuesta, el nodo solicitante envía otro mensaje de solicitud de PNRP la dirección IPv6 para responder o examinar su caché.  
  
-   Si el id. de PNRP no se encuentra y no hay ningún id. de PNRP en la memoria caché que está más cercano al id. de destino PNRP, el elemento solicitado envía el par que solicita una respuesta que indica esta condición.  El par que solicita y elija la identificación NeXT\- más cercana de PNRP  
  
 El par que solicita continúa este proceso con las iteraciones sucesivas, ubicar finalmente el nodo que registró la identificación de PNRP  
  
 Dentro del espacio de nombres <xref:System.Net.PeerToPeer> , existe una relación varios a varios entre los registros de <xref:System.Net.PeerToPeer.PeerName> que contienen los extremos y las nubes o mallas de PNRP en las que se comunican.  Cuando hay entradas duplicadas u obsoletos, o varios nodos con el mismo nombre del mismo nivel, los nodos de PNRP pueden obtener información actual utilizando la clase de <xref:System.Net.PeerToPeer.PeerNameResolver> .  Los métodos de <xref:System.Net.PeerToPeer.PeerNameResolver> utilizan un único nombre del mismo nivel para simplificar la perspectiva registros del mismo nivel de uno a par\-a\- muchos nombre y el mismo un par a muchas nubes.  Esto es similar a una consulta realizada utilizando una combinación de la emparentado\- tabla.  A la terminación correcta, el objeto de la resolución de nombres devuelve <xref:System.Net.PeerToPeer.PeerNameRecordCollection> para el nombre del mismo nivel especificado.  Por ejemplo, un nombre del mismo nivel aparecería en todos los registros del mismo nivel del nombre de la colección, ordenada por la nube.  Estas son las instancias del nombre del mismo nivel cuyo datos complementarios se puede solicitar por una aplicación PNRP\- basada en.  
  
## Vea también  
 <xref:System.Net.PeerToPeer>