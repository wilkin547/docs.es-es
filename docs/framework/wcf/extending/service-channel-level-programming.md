---
title: Programación de servicios a nivel de canal
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8d8dcd85-0a05-4c44-8861-4a0b3b90cca9
ms.openlocfilehash: db50d385bd396ba4de74e08fc1c6d93a67f320b7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290223"
---
# <a name="service-channel-level-programming"></a>Programación de servicios a nivel de canal

En este tema se describe cómo escribir una aplicación de servicio de Windows Communication Foundation (WCF) sin usar <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> y su modelo de objetos asociado.  
  
## <a name="receiving-messages"></a>recibir mensajes  

 Se exigen los pasos siguientes para estar listo para recibir y procesar mensajes:  
  
1. Cree un enlace.  
  
2. Crear una escucha del canal.  
  
3. Abrir la escucha del canal.  
  
4. Leer la solicitud y enviar una respuesta.  
  
5. Cerrar todos los objetos de canal.  
  
#### <a name="creating-a-binding"></a>Crear un enlace  

 El primer paso para escuchar y recibir mensajes es crear un enlace. WCF se suministra con varios enlaces integrados o proporcionados por el sistema que se pueden usar directamente creando instancias de uno de ellos. Además, también puede crear su propio enlace personalizado creando instancias de una clase CustomBinding que es lo que hace el código en la lista 1.  
  
 El ejemplo de código siguiente crea una instancia de <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> y agrega <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> a su colección Elements, que es una colección de elementos de enlace que se utilizan para crear la pila del canal. En este ejemplo, puesto que la colección de elementos tiene solo <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, la pila del canal resultante tiene solo el canal de transporte HTTP.  
  
#### <a name="building-a-channellistener"></a>Crear un ChannelListener  

 Después de crear un enlace, llamamos a <xref:System.ServiceModel.Channels.Binding.BuildChannelListener%2A?displayProperty=nameWithType> para crear la escucha del canal donde el parámetro de tipo es la forma del canal a crear. En este ejemplo estamos utilizando <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> porque deseamos realizar escuchas para los mensajes entrantes en un patrón de intercambio de solicitud/mensaje de respuesta.  
  
 <xref:System.ServiceModel.Channels.IReplyChannel> se utiliza para recibir los mensajes de solicitud y devolver los mensajes de respuesta. Al llamar a <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A?displayProperty=nameWithType>, se devuelve <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>, que se puede utilizar para recibir el mensaje de solicitud y devolver un mensaje de respuesta.  
  
 Al crear el agente de escucha, pasamos la dirección de red en la que se realizan las escuchas, en este caso `http://localhost:8080/channelapp`. En general, cada canal de transporte admite uno o posiblemente varios esquemas de direcciones, por ejemplo, el transporte HTTP admite http y esquemas http.  
  
 También pasamos un <xref:System.ServiceModel.Channels.BindingParameterCollection?displayProperty=nameWithType> vacío al crear el agente de escucha. Un parámetro de enlace es un mecanismo para pasar parámetros que controlan cómo el agente de escucha debe crearse. En nuestro ejemplo, no estamos utilizando ninguno de estos parámetros, por lo que pasamos una colección vacía.  
  
#### <a name="listening-for-incoming-messages"></a>Realizar escuchas para los mensajes entrantes  

 Llamamos a continuación <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> en el agente de escucha e iniciamos los canales de aceptación. El comportamiento de <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A?displayProperty=nameWithType> depende de si el transporte está orientado a la conexión o es sin conexión. Para los transportes orientados a la conexión, <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> se bloquea hasta que llega una nueva solicitud de conexión y, en ese momento, devuelve un nuevo canal que representa esa nueva conexión. Para los transportes sin conexión, como HTTP, <xref:System.ServiceModel.Channels.IChannelListener%601.AcceptChannel%2A> devuelve inmediatamente con el único el canal que el agente de escucha de transporte crea.  
  
 En este ejemplo, el agente de escucha devuelve un canal que implementa <xref:System.ServiceModel.Channels.IReplyChannel>. Para recibir mensajes en este canal, llamamos primero a <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> para colocarlo en un estado listo para la comunicación. Llamamos a continuación a <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> que se bloquea hasta que llega un mensaje.  
  
#### <a name="reading-the-request-and-sending-a-reply"></a>Leer la solicitud y enviar una respuesta  

 Cuando <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> devuelve <xref:System.ServiceModel.Channels.RequestContext>, obtenemos el mensaje recibido mediante su propiedad <xref:System.ServiceModel.Channels.RequestContext.RequestMessage%2A>. Eliminamos la acción del mensaje y el contenido del cuerpo (que suponemos es una cadena).  
  
 Para enviar una respuesta, creamos un nuevo mensaje de respuesta en este caso devolviendo los datos de cadena que recibimos en la solicitud. Llamamos a continuación a <xref:System.ServiceModel.Channels.RequestContext.Reply%2A> para enviar el mensaje de respuesta.  
  
#### <a name="closing-objects"></a>Cerrar objetos  

 Para evitar agotar los recursos, es muy importante cerrar los objetos utilizados en comunicaciones cuando no ya se requieren. En este ejemplo cerramos el mensaje de solicitud, el contexto de solicitud, el canal y el agente de escucha.  
  
 El ejemplo de código siguiente muestra un servicio básico en el que un agente de escucha del canal recibe solo uno mensaje. Un servicio real sigue aceptando los canales y recibiendo los mensajes hasta que se abandone el servicio.  
  
 [!code-csharp[ChannelProgrammingBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/serviceprogram.cs#1)]
 [!code-vb[ChannelProgrammingBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/serviceprogram.vb#1)]
