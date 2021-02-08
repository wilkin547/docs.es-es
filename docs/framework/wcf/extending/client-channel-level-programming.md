---
description: 'Más información acerca de: programación de Channel-Level de cliente'
title: Programación a nivel de canal de cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: 7e4e977231339fbbede7111e38a67054eb24eed9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803001"
---
# <a name="client-channel-level-programming"></a>Programación a nivel de canal de cliente

En este tema se describe cómo escribir una aplicación cliente de Windows Communication Foundation (WCF) sin utilizar la <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> clase y su modelo de objetos asociado.  
  
## <a name="sending-messages"></a>enviar mensajes  

 Para estar listo para enviar mensajes y recibir y procesar las respuestas, se han de realizar los pasos siguientes:  
  
1. Cree un enlace.  
  
2. Crear un generador de canales.  
  
3. Crear un canal.  
  
4. Enviar una solicitud y leer la respuesta.  
  
5. Cerrar todos los objetos de canal.  
  
#### <a name="creating-a-binding"></a>Crear un enlace  

 De forma similar al caso de recepción (consulte [Service Channel-Level Programming](service-channel-level-programming.md)), el envío de mensajes comienza creando un enlace. Este ejemplo crea un nuevo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> y agrega un <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> a su colección Elements.  
  
#### <a name="building-a-channelfactory"></a>Creación de un ChannelFactory  

 En lugar de crear un <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, en esta ocasión creamos un <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> llamando a <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> en el enlace donde está el parámetro de tipo <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>. Aunque el lado que espera mensajes entrantes usa los agentes de escuchas de canales, el lado que inicia la comunicación para crear un canal emplea los generadores de canales. Al igual que los agentes de escuchas de canales, los generadores de canales se han de abrir primero antes de que puedan utilizarse.  
  
#### <a name="creating-a-channel"></a>Creación de un canal  

 A continuación llamamos a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> para crear un <xref:System.ServiceModel.Channels.IRequestChannel>. Esta llamada toma la dirección del punto de conexión con el que deseamos comunicarnos utilizando el nuevo canal que se crea. Una vez que tenemos un canal, llamamos a Open para dejarlo listo para la comunicación. Dependiendo de la naturaleza del transporte, esta llamada a Open puede iniciar una conexión con el punto de conexión de destino o puede que no haga nada en absoluto en la red.  
  
#### <a name="sending-a-request-and-reading-the-reply"></a>Envío de una solicitud y lectura de la respuesta  

 Una vez que tenemos un canal abierto, podemos crear un mensaje y utilizar el método Request del canal para enviar la solicitud y esperar a que la respuesta regrese. Cuando este método devuelve, tenemos un mensaje de respuesta que podemos leer para averiguar cuál fue la respuesta del punto de conexión.  
  
#### <a name="closing-objects"></a>Cerrar objetos  

 Para evitar la pérdida de recursos, cerramos los objetos utilizados en las comunicaciones cuando ya no se necesiten.  
  
 El siguiente ejemplo de código muestra un cliente básico que utiliza el generador de canales para enviar un mensaje y leer la respuesta.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
