---
title: Publicación y resolución de nombres del mismo nivel
ms.date: 03/30/2017
ms.assetid: f0370e08-9fa6-4ee5-ab78-9a58a20a7da2
ms.openlocfilehash: 4a0787972a61f5700d1e8728be96db8ef9ee749e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "64623198"
---
# <a name="peer-name-publication-and-resolution"></a>Publicación y resolución de nombres del mismo nivel

## <a name="publishing-a-peer-name"></a>Publicación de un nombre del mismo nivel  

 Para publicar un nuevo identificador PNRP, un elemento de mismo nivel realiza lo siguiente:  
  
- Envía mensajes de publicación de PNRP a sus vecinos de caché (los elementos de mismo nivel que han registrado identificadores PNRP en el nivel más bajo de la memoria caché) para inicializar sus cachés.  
  
- Elige nodos aleatorios en la nube que no son sus vecinos y les envía solicitudes de resolución de nombres de PNRP para su propio identificador P2P. El proceso de determinación del punto de conexión resultante inicializa las memorias caché de los nodos aleatorios en la nube con el identificador PNRP del elemento de mismo nivel de publicación.  
  
Los nodos de la versión 2 de PNRP no publican identificadores PNRP si solo resuelven otros identificadores de P2P. El valor del Registro HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\PeerNet\PNRP\IPV6-Global\SearchOnly=1 (tipo REG_DWORD) especifica que los elementos de mismo nivel solo usen PNRP para la resolución de nombres, nunca para la publicación de nombres. Este valor del Registro también se puede configurar mediante Directiva de grupo.  
  
## <a name="resolving-a-peer-name"></a>Resolución de un nombre del mismo nivel

 La búsqueda de otros elementos de mismo nivel en una red de PNRP o en la nube es un proceso que consta de dos fases:  
  
1. Determinación del punto de conexión  
  
2. Resolución de identificadores PNRP  
  
 En la fase de determinación del punto de conexión, un equipo de mismo nivel que está intentando resolver el identificador PNRP de un servicio en otro equipo determina la dirección IPv6 de ese equipo remoto de mismo nivel.  El equipo remoto de mismo nivel es el que publica o está asociado con el identificador PNRP del equipo o servicio.  
  
 Después de confirmar que el punto de conexión remoto se ha registrado en la nube PNRP, el equipo de mismo nivel que realiza la solicitud en la fase de resolución de identificadores PNRP envía una solicitud a ese punto de conexión de mismo nivel para requerir el identificador PNRP del servicio deseado. El punto de conexión envía una respuesta que confirma el identificador PNRP del servicio, un comentario y hasta 4 kilobytes de información adicional que el equipo de mismo nivel que realiza la solicitud puede usar para la comunicación posterior. Por ejemplo, si el punto de conexión deseado es un servidor de juegos, los datos adicionales del registro de nombre de mismo nivel pueden contener información sobre el juego, el nivel de juego y el número actual de jugadores.  
  
 En la fase de determinación de punto de conexión, PNRP usa un proceso iterativo para buscar el nodo que publicó el identificador PNRP, en el que el nodo que realiza la resolución es responsable de ponerse en contacto con los nodos que están más cercanos consecutivamente al identificador PNRP de destino.  
  
 Para realizar la resolución de nombres en PNRP, el equipo de mismo nivel examina las entradas en su propia memoria caché para buscar una que coincida con el identificador PNRP de destino. Si se encuentra, el equipo de mismo nivel envía un mensaje de solicitud de PNRP y espera una respuesta. Si no se encuentra una entrada para el identificador PNRP, el equipo de mismo nivel envía un mensaje de solicitud PNRP al equipo de mismo nivel que se corresponde a la entrada que tiene un identificador PNRP que mejor coincida con el identificador PNRP de destino. El nodo que recibe el mensaje de solicitud de PNRP examina su propia memoria caché y realiza las acciones siguientes:  
  
- Si se encuentra el identificador PNRP, el punto de conexión de mismo nivel solicitado responde directamente al equipo de mismo nivel que realizó la solicitud.  
  
- Si no se encuentra el identificador PNRP y un identificador PNRP de la memoria caché está más próximo al identificador PNRP de destino, el equipo de mismo nivel receptor de la solicitud envía una respuesta al emisor de la solicitud que contiene la dirección IPv6 del equipo de mismo nivel que representa la entrada con un identificador PNRP que mejor coincida con el identificador PNRP de destino. Con la dirección IP en la respuesta, el nodo solicitante envía otro mensaje de solicitud de PNRP a la dirección IPv6 para responder o examinar su caché.  
  
- Si no se encuentra el identificador PNRP y no hay ningún identificador PNRP en su memoria caché que se aproxime más al identificador PNRP de destino, el equipo de mismo nivel al que se realiza la solicitud envía al equipo solicitante una respuesta que indica esta condición. Después, el equipo de mismo nivel solicitante elige el identificador PNRP más cercano siguiente.  
  
El equipo de mismo nivel solicitante continúa con iteraciones sucesivas, hasta localizar el nodo que registró el identificador PNRP.  
  
 En el espacio de nombres <xref:System.Net.PeerToPeer>, hay una relación de varios a varios entre los registros <xref:System.Net.PeerToPeer.PeerName> que contienen puntos de conexión y nubes PNRP o mallas en las que se comunican. Cuando hay entradas duplicadas u obsoletas, o varios nodos con el mismo nombre de mismo nivel, los nodos PNRP pueden obtener información actual mediante la clase <xref:System.Net.PeerToPeer.PeerNameResolver>. Los métodos <xref:System.Net.PeerToPeer.PeerNameResolver> usan un nombre de mismo nivel único para simplificar la perspectiva a registros de nombre de mismo nivel de uno a varios y del mismo equipo de mismo nivel a varias nubes. Esto es similar a una consulta realizada con una combinación de tabla relacional. Tras completarse correctamente, el objeto de resolución devuelve una <xref:System.Net.PeerToPeer.PeerNameRecordCollection> para el nombre de mismo nivel especificado.  Por ejemplo, un nombre de mismo nivel se produciría en todos los registros de nombre de mismo nivel en la colección, ordenados por nube. Estas son las instancias del nombre de mismo nivel cuyos datos auxiliares se pueden solicitar mediante una aplicación basada en PNRP.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer>
