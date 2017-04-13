---
title: "Servicio: Canales y escuchas de canales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ccbe0e8-7e55-441d-80de-5765f67542fa
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Servicio: Canales y escuchas de canales
Hay tres categorías de objetos de canal: canales, escuchas de canales y generadores de canales.Los canales son la interfaz entre la aplicación y la pila de canales.Las escuchas de canales son responsables de crear los canales en el lado de recepción \(o escucha\), normalmente en respuesta a un nuevo mensaje entrante o conexión.Los generadores de canales son responsables de crear los canales en el lado de envío para iniciar la comunicación con un extremo.  
  
## Escuchas de canales y canales  
 Las escuchas de canales son responsables de crear los canales y recibir los mensajes del nivel inferior o de la red.Los mensajes recibidos se entregan al nivel superior utilizando un canal creado por la escucha de canales.  
  
 El diagrama siguiente muestra el proceso de recibir mensajes y entregarlos al nivel superior.  
  
 ![Escuchas de canales y canales](../../../../docs/framework/wcf/extending/media/wcfc-wcfchannelsigure1highlevelc.gif "wcfc\_WCFChannelsigure1HighLevelc")  
Una escucha de canales recibiendo mensajes y entregándolos al nivel superior a través de canales.  
  
 El proceso se puede modelar conceptualmente como una cola, aunque dentro de cada canal la implementación puede no utilizar una cola.La escucha de canales es responsable de recibir los mensajes del nivel inferior o de la red y colocarlos en la cola.El canal es responsable de recibir los mensajes de la cola y entregarlos al nivel superior cuando dicho nivel pide un mensaje, por ejemplo llamando a `Receive` en el canal.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona los elementos auxiliares de clase base para este proceso.\(Para un diagrama de las clases auxiliares de canal discutidas en este tema, vea [Información general del modelo de canales](../../../../docs/framework/wcf/extending/channel-model-overview.md).\)  
  
-   La clase <xref:System.ServiceModel.Channels.CommunicationObject> implementa <xref:System.ServiceModel.ICommunicationObject> y exige el estado de equipo descrito en el paso 2 de [Desarrollo de canales](../../../../docs/framework/wcf/extending/developing-channels.md).  
  
-   La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> implementa la clase <xref:System.ServiceModel.Channels.CommunicationObject> y proporciona una clase base unificada para las clases <xref:System.ServiceModel.Channels.ChannelFactoryBase> y <xref:System.ServiceModel.Channels.ChannelListenerBase>.La clase <xref:System.ServiceModel.Channels.ChannelManagerBase> trabaja junto con <xref:System.ServiceModel.Channels.ChannelBase>, que es una clase base que implementa <xref:System.ServiceModel.Channels.IChannel>.  
  
-   La clase ``<xref:System.ServiceModel.Channels.ChannelFactoryBase> implementa <xref:System.ServiceModel.Channels.ChannelManagerBase> y <xref:System.ServiceModel.Channels.IChannelFactory>, y consolida las sobrecargas de `CreateChannel` en un método abstracto `OnCreateChannel`.  
  
-   La clase <xref:System.ServiceModel.Channels.ChannelListenerBase> implementa la interfaz <xref:System.ServiceModel.Channels.IChannelListener>.Se encarga de la administración de estados básica.  
  
 La discusión siguiente está basada en el ejemplo [Transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).  
  
## Crear una escucha de canales  
 El``UdpChannelListener que implementa el ejemplo se deriva de la clase <xref:System.ServiceModel.Channels.ChannelListenerBase>.Utiliza un socket UDP único para recibir datagramas.El método `OnOpen` recibe datos utilizando el socket UDP en un bucle asincrónico.Los datos se convierten en mensajes utilizando el sistema de la codificación de mensajes:  
  
```  
message = UdpConstants.MessageEncoder.ReadMessage(  
  new ArraySegment<byte>(buffer, 0, count),   
  bufferManager  
);  
```  
  
 Dado que el mismo canal del datagrama representa mensajes que llegan de varios orígenes, `UdpChannelListener` es un agente de escucha singleton.Hay a lo sumo un <xref:System.ServiceModel.Channels.IChannel>``activo asociado a la vez a este agente de escucha.El ejemplo solo genera otro si se elimina subsiguientemente un canal que es devuelto por el método <xref:System.ServiceModel.Channels.ChannelListenerBase%601.AcceptChannel%2A>.Cuando se recibe un mensaje, se pone en cola en este canal singleton.  
  
### UdpInputChannel  
 La clase `UdpInputChannel` implementa la interfaz <xref:System.ServiceModel.Channels.IInputChannel>.Está compuesto de una cola de mensajes entrantes que es rellenada por el socket `UdpChannelListener`.Estos mensajes se quitan de la cola mediante el método <xref:System.ServiceModel.Channels.IInputChannel.Receive%2A>.