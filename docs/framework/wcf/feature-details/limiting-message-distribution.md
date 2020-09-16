---
title: Limitación de la distribución de mensajes
ms.date: 03/30/2017
ms.assetid: 8b5ec4b8-1ce9-45ef-bb90-2c840456bcc1
ms.openlocfilehash: e736aba60d7d2b39d1b8eb958a8c72e6e8d55e13
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555021"
---
# <a name="limiting-message-distribution"></a>Limitación de la distribución de mensajes

El canal del mismo nivel es, por diseño, una malla de difusión. Su modelo de distribución básico implica la distribución de cada mensaje enviado por cualquier miembro de una malla a todos los demás miembros de esa malla. Esto es ideal en situaciones en las que cada mensaje generado por un miembro es relevante y útil para todos los demás miembros (por ejemplo, en un salón de chat). Sin embargo, muchas aplicaciones tienen una necesidad ocasional de limitar la distribución de mensajes. Por ejemplo, si un nuevo miembro se une a una malla y desea recuperar el último mensaje enviado a través de la malla, esta solicitud no necesita ser distribuida a cada miembro. La solicitud se puede limitar a vecinos cercanos o se pueden filtrar los mensajes generados localmente. Los mensajes también se pueden enviar a un nodo individual en la malla. En este tema se analiza el uso del número de saltos, de un filtro de propagación de mensajes, de un filtro local o de una conexión directa para controlar la forma en que los mensajes se reenvían a lo largo de la malla, y se proporcionan instrucciones de carácter general para elegir un enfoque.

## <a name="hop-counts"></a>Números de saltos

El concepto de `PeerHopCount` es similar al de período de vida (TTL) que se usa en el protocolo IP. El valor de `PeerHopCount` se asocia a una instancia de mensaje y especifica cuántas veces se debería reenviar un mensaje antes de entregarse. Cada vez que un cliente del canal del mismo nivel recibe un mensaje, el cliente examina el mensaje para ver si se especifica `PeerHopCount`. Si se especifica, el cliente disminuye en uno el valor de número de saltos antes de reenviar el mensaje a los nodos vecinos. Cuando un cliente recibe un mensaje con un valor cero para el número de saltos, el cliente procesa el mensaje pero no lo reenvía a los vecinos.

El número de saltos se puede agregar a un mensaje agregando `PeerHopCount` como un atributo a la propiedad aplicable o campo en la implementación de la clase de mensaje. Puede establecer esto en un valor concreto antes de enviar el mensaje a la malla. De esta manera, el número de saltos puede servir para limitar la distribución de mensajes a lo largo de la malla cuando sea necesario, evitando así la posible duplicación innecesaria de los mensajes. Esto es útil cuando la malla contiene una gran cantidad de datos redundantes o para enviar un mensaje a los vecinos inmediatos o a los vecinos a pocos saltos de distancia.

- Para obtener fragmentos de código e información relacionada, vea el blog [PeerHopCount: control](/archive/blogs/peerchan/the-peerhopcount-attribute-controlling-message-distribution) de la publicación de distribución de mensajes en el blog del canal del mismo nivel.

## <a name="message-propagation-filter"></a>Filtro de propagación de mensajes

`MessagePropagationFilter` se puede utilizar para el control personalizado de la distribución de mensajes, sobre todo cuando el contenido del mensaje u otros escenarios concretos determinan la propagación. El filtro toma decisiones de propagación para cada mensaje que atraviesa el nodo. Así sucede en el caso de los mensajes originados en otra parte de la malla que el nodo ha recibido, así como los mensajes creados por la aplicación. El filtro tiene acceso tanto al mensaje como a su origen, por lo que las decisiones sobre el reenvío o la entrega del mensaje se pueden basar en toda la información disponible.

<xref:System.ServiceModel.PeerMessagePropagationFilter> es una clase base abstracta con una función única, <xref:System.ServiceModel.PeerMessagePropagationFilter.ShouldMessagePropagate%2A>. El primer argumento de la llamada al método pasa una copia completa del mensaje. Cualquier cambio realizado en el mensaje no afecta al mensaje real. El último argumento de la llamada al método identifica el origen del mensaje (`PeerMessageOrigination.Local` o `PeerMessageOrigination.Remote`). Las implementaciones concretas de este método deben devolver una constante de la enumeración <xref:System.ServiceModel.PeerMessagePropagation> que indique si el mensaje se debe reenviar a la aplicación local (`Local`), a clientes remotos (`Remote`), a ambos (`LocalAndRemote`) o a ninguno (`None`). Para aplicar este filtro, puede tener acceso al objeto `PeerNode` correspondiente y especificar una instancia de la clase de filtro de propagación derivada en la propiedad `PeerNode.MessagePropagationFilter`. Asegúrese de que el filtro de propagación está adjunto antes de abrir el canal del mismo nivel.

- Para obtener fragmentos de código e información relacionada, vea la entrada de [canal del mismo nivel y MessagePropagationFilter](/archive/blogs/peerchan/peer-channel-and-messagepropagationfilter) en el blog del canal del mismo nivel.

## <a name="contacting-an-individual-node-in-the-mesh"></a>Contacto con un nodo Individual de la malla

Es posible establecer contacto con un nodo individual de una malla mediante la configuración de un filtro local o una conexión directa.

Si cada nodo de una malla tiene un identificador individual, se puede especificar un identificador de destino en la implementación del mensaje. Para configurar un filtro local, se puede escribir una función en el contrato de mensaje que muestre el mensaje al nodo actual solo si su identificador coincide con el identificador de destino especificado. La malla transporta el mensaje, de modo que se evita la sobrecarga de configurar una nueva conexión. Sin embargo, se produce una pérdida de eficacia, ya que el mensaje se envía muchas veces a lo largo de la malla. Esto funciona correctamente para el envío de mensajes a miembros individuales de una malla siempre y cuando los mensajes no sean ni demasiado grandes ni demasiado frecuentes.

En el caso de las conexiones prolongadas con un ancho de banda alto, se prefieren las conexiones directas. Puede enviar la información de conexión a través de la malla y después configurar la conexión directa que prefiera para enviar y recibir los mensajes.

## <a name="choosing-an-approach-for-limiting-message-distribution"></a>Elección de un enfoque para limitar la distribución de mensajes

Cuando detecte un escenario para el que es necesario limitar la distribución de mensajes, hágase las preguntas siguientes:

- **¿Quién** debe recibir el mensaje? ¿Simplemente uno nodo vecino? ¿Un nodo en alguna otra parte de la malla? ¿La mitad de la malla?

- **¿Con qué frecuencia** se enviará este mensaje?

- ¿Qué tipo de **ancho de banda** usará este mensaje?

Las respuestas a estas preguntas pueden ayudarle a determinar si debe utilizar el número de saltos, un filtro de propagación de mensajes, un filtro local o una conexión directa. Considere las siguientes pautas de carácter general:

- **Aprovechar**

  - *Nodo individual*: filtro local o conexión directa.

  - *Vecinos dentro de un determinado proximidad*: PeerHopCount.

  - *Subconjunto complejo de la malla*: MessagePropagationFilter.

- **Frecuencia**

  - *Muy frecuente*: conexión directa, PeerHopCount, MessagePropagationFilter.

  - *Ocasional*: filtro local.

- **Uso del ancho de banda**

  - *Alta*: conexión directa, menos recomendable para usar MessagePropagationFilter o filtro local.

  - *Bajo*: cualquier conexión directa probablemente no sea necesaria.

## <a name="see-also"></a>Vea también

- [Creación de una aplicación de canal del mismo nivel](building-a-peer-channel-application.md)
