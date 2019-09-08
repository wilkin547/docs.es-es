---
title: 'Servicio: Escuchas de canales y canales'
ms.date: 03/30/2017
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
ms.openlocfilehash: 0a740f5dcf682c3c140adb9c4c7c9678c4eae132
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797172"
---
# <a name="service-channel-listeners-and-channels"></a>Servicio: Escuchas de canales y canales

Hay tres categorías de objetos de canal: canales, agentes de escucha del canal y generadores de canales. Los canales son la interfaz entre la aplicación y la pila de canales. Las escuchas de canales son responsables de crear los canales en el lado de recepción (o escucha), normalmente en respuesta a un nuevo mensaje entrante o conexión. Los generadores de canales son responsables de crear los canales en el lado de envío para iniciar la comunicación con un extremo.

## <a name="channel-listeners-and-channels"></a>Escuchas de canales y canales

Las escuchas de canales son responsables de crear los canales y recibir los mensajes del nivel inferior o de la red. Los mensajes recibidos se entregan al nivel superior utilizando un canal creado por la escucha de canales.

El diagrama siguiente muestra el proceso de recibir mensajes y entregarlos al nivel superior.

![Canales y agentes de escucha del canal](./media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc_WCFChannelsigure1HighLevelc")

Una escucha de canales recibiendo mensajes y entregándolos al nivel superior a través de canales.

El proceso se puede modelar conceptualmente como una cola, aunque dentro de cada canal la implementación puede no utilizar una cola. La escucha de canales es responsable de recibir los mensajes del nivel inferior o de la red y colocarlos en la cola. El canal es responsable de recibir los mensajes de la cola y entregarlos al nivel superior cuando dicho nivel pide un mensaje, por ejemplo llamando a `Receive` en el canal.

WCF proporciona aplicaciones auxiliares de clase base para este proceso. (Para ver un diagrama de las clases de aplicación auxiliar de canal descritas en este artículo, consulte [información general del modelo de canal](channel-model-overview.md)).

- La <xref:System.ServiceModel.Channels.CommunicationObject> clase<xref:System.ServiceModel.ICommunicationObject> implementa y exige el equipo de estado descrito en el paso 2 de [desarrollo de canales](developing-channels.md).

- La <xref:System.ServiceModel.Channels.ChannelManagerBase> clase <xref:System.ServiceModel.Channels.ChannelFactoryBase> <xref:System.ServiceModel.Channels.ChannelListenerBase>implementa y proporciona una clase base unificada para y. <xref:System.ServiceModel.Channels.CommunicationObject> La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.

- La <xref:System.ServiceModel.Channels.ChannelFactoryBase> clase `CreateChannel` `OnCreateChannel` implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y<xref:System.ServiceModel.Channels.IChannelFactory> y consolida las sobrecargas en un método abstracto.

- La <xref:System.ServiceModel.Channels.ChannelListenerBase> clase<xref:System.ServiceModel.Channels.IChannelListener>implementa. Se encarga de la administración de estados básica.

El siguiente debate se basa en el [transporte: Ejemplo](../samples/transport-udp.md) de UDP.

## <a name="creating-a-channel-listener"></a>Creación de un agente de escucha del canal

Que el ejemplo implementa se deriva de la <xref:System.ServiceModel.Channels.ChannelListenerBase> clase. `UdpChannelListener` Utiliza un socket UDP único para recibir datagramas. El método `OnOpen` recibe datos utilizando el socket UDP en un bucle asincrónico. Los datos se convierten en mensajes utilizando el sistema de la codificación de mensajes:

```csharp
message = UdpConstants.MessageEncoder.ReadMessage(
  new ArraySegment<byte>(buffer, 0, count),
  bufferManager
);
```

Dado que el mismo canal del datagrama representa mensajes que llegan de varios orígenes, `UdpChannelListener` es un agente de escucha singleton. Hay a lo sumo un activo <xref:System.ServiceModel.Channels.IChannel> asociado a este agente de escucha a la vez. El ejemplo solo genera otro si se elimina subsiguientemente un canal que es devuelto por el método <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>. Cuando se recibe un mensaje, se pone en cola en este canal singleton.

### <a name="udpinputchannel"></a>UdpInputChannel

La `UdpInputChannel` clase<xref:System.ServiceModel.Channels.IInputChannel>implementa. Está compuesto de una cola de mensajes entrantes que es rellenada por el socket `UdpChannelListener`. Estos mensajes se quitan de la cola mediante el método <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>.
