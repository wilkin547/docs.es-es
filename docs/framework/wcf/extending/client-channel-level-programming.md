---
title: "Programaci&#243;n a nivel de canal de cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Programaci&#243;n a nivel de canal de cliente
En este tema se describe cómo escribir una aplicación de cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sin utilizar la clase <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> y su modelo de objetos asociado.  
  
## Envío de mensajes  
 Para estar listo para enviar mensajes y recibir y procesar las respuestas, se han de realizar los pasos siguientes:  
  
1.  Crear un enlace.  
  
2.  Crear un generador de canales.  
  
3.  Crear un canal.  
  
4.  Enviar una solicitud y leer la respuesta.  
  
5.  Cerrar todos los objetos de canal.  
  
#### Creación de un enlace  
 Similar al caso de recepción \(vea [Programación de servicios a nivel de canal](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)\), enviar mensajes se inicia creando un enlace.Este ejemplo crea un nuevo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> y agrega un <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> a su colección Elements.  
  
#### Creación de un ChannelFactory  
 En lugar de crear un <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=fullName>, en esta ocasión creamos un <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> llamando a <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=fullName> en el enlace donde está el parámetro de tipo <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName>.Aunque el lado que espera mensajes entrantes usa los agentes de escuchas de canales, el lado que inicia la comunicación para crear un canal emplea los generadores de canales.Al igual que los agentes de escuchas de canales, los generadores de canales se han de abrir primero antes de que puedan utilizarse.  
  
#### Creación de un canal  
 A continuación llamamos a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=fullName> para crear un <xref:System.ServiceModel.Channels.IRequestChannel>.Esta llamada toma la dirección del extremo con el que deseamos comunicarnos utilizando el nuevo canal que se crea.Una vez que tenemos un canal, llamamos a Open para dejarlo listo para la comunicación.Dependiendo de la naturaleza del transporte, esta llamada a Open puede iniciar una conexión con el extremo de destino o puede que no haga nada en absoluto en la red.  
  
#### Envío de una solicitud y lectura de la respuesta  
 Una vez que tenemos un canal abierto, podemos crear un mensaje y utilizar el método Request del canal para enviar la solicitud y esperar a que la respuesta regrese.Cuando este método devuelve, tenemos un mensaje de respuesta que podemos leer para averiguar cuál fue la respuesta del extremo.  
  
#### Cerrar objetos  
 Para evitar la pérdida de recursos, cerramos los objetos utilizados en las comunicaciones cuando ya no se necesiten.  
  
 El siguiente ejemplo de código muestra un cliente básico que utiliza el generador de canales para enviar un mensaje y leer la respuesta.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]