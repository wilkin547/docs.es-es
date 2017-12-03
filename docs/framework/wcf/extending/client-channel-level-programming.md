---
title: "Programación a nivel de canal de cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eac1a8b49ac9936455d11553ccc697897c088cb6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="6eed6-102">Programación a nivel de canal de cliente</span><span class="sxs-lookup"><span data-stu-id="6eed6-102">Client Channel-Level Programming</span></span>
<span data-ttu-id="6eed6-103">En este tema se describe cómo escribir una aplicación de cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sin utilizar la clase <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> y su modelo de objetos asociado.</span><span class="sxs-lookup"><span data-stu-id="6eed6-103">This topic describes how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="6eed6-104">Envío de mensajes</span><span class="sxs-lookup"><span data-stu-id="6eed6-104">Sending Messages</span></span>  
 <span data-ttu-id="6eed6-105">Para estar listo para enviar mensajes y recibir y procesar las respuestas, se han de realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6eed6-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1.  <span data-ttu-id="6eed6-106">Cree un enlace.</span><span class="sxs-lookup"><span data-stu-id="6eed6-106">Create a binding.</span></span>  
  
2.  <span data-ttu-id="6eed6-107">Crear un generador de canales.</span><span class="sxs-lookup"><span data-stu-id="6eed6-107">Build a channel factory.</span></span>  
  
3.  <span data-ttu-id="6eed6-108">Crear un canal.</span><span class="sxs-lookup"><span data-stu-id="6eed6-108">Create a channel.</span></span>  
  
4.  <span data-ttu-id="6eed6-109">Enviar una solicitud y leer la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6eed6-109">Send a request and read the reply.</span></span>  
  
5.  <span data-ttu-id="6eed6-110">Cerrar todos los objetos de canal.</span><span class="sxs-lookup"><span data-stu-id="6eed6-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="6eed6-111">Crear un enlace</span><span class="sxs-lookup"><span data-stu-id="6eed6-111">Creating a Binding</span></span>  
 <span data-ttu-id="6eed6-112">Similar al caso de recepción (consulte [nivel de canal del servicio de programación](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), enviar mensajes comienza creando un enlace.</span><span class="sxs-lookup"><span data-stu-id="6eed6-112">Similar to the receiving case (see [Service Channel-Level Programming](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="6eed6-113">Este ejemplo crea un nuevo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> y agrega un <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> a su colección Elements.</span><span class="sxs-lookup"><span data-stu-id="6eed6-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="6eed6-114">Creación de un ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="6eed6-114">Building a ChannelFactory</span></span>  
 <span data-ttu-id="6eed6-115">En lugar de crear un <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, en esta ocasión creamos un <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> llamando a <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> en el enlace donde está el parámetro de tipo <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6eed6-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6eed6-116">Aunque el lado que espera mensajes entrantes usa los agentes de escuchas de canales, el lado que inicia la comunicación para crear un canal emplea los generadores de canales.</span><span class="sxs-lookup"><span data-stu-id="6eed6-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="6eed6-117">Al igual que los agentes de escuchas de canales, los generadores de canales se han de abrir primero antes de que puedan utilizarse.</span><span class="sxs-lookup"><span data-stu-id="6eed6-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="6eed6-118">Creación de un canal</span><span class="sxs-lookup"><span data-stu-id="6eed6-118">Creating a Channel</span></span>  
 <span data-ttu-id="6eed6-119">A continuación llamamos a <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> para crear un <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="6eed6-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="6eed6-120">Esta llamada toma la dirección del extremo con el que deseamos comunicarnos utilizando el nuevo canal que se crea.</span><span class="sxs-lookup"><span data-stu-id="6eed6-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="6eed6-121">Una vez que tenemos un canal, llamamos a Open para dejarlo listo para la comunicación.</span><span class="sxs-lookup"><span data-stu-id="6eed6-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="6eed6-122">Dependiendo de la naturaleza del transporte, esta llamada a Open puede iniciar una conexión con el extremo de destino o puede que no haga nada en absoluto en la red.</span><span class="sxs-lookup"><span data-stu-id="6eed6-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="6eed6-123">Envío de una solicitud y lectura de la respuesta</span><span class="sxs-lookup"><span data-stu-id="6eed6-123">Sending a Request and Reading the Reply</span></span>  
 <span data-ttu-id="6eed6-124">Una vez que tenemos un canal abierto, podemos crear un mensaje y utilizar el método Request del canal para enviar la solicitud y esperar a que la respuesta regrese.</span><span class="sxs-lookup"><span data-stu-id="6eed6-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="6eed6-125">Cuando este método devuelve, tenemos un mensaje de respuesta que podemos leer para averiguar cuál fue la respuesta del extremo.</span><span class="sxs-lookup"><span data-stu-id="6eed6-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="6eed6-126">Cerrar objetos</span><span class="sxs-lookup"><span data-stu-id="6eed6-126">Closing Objects</span></span>  
 <span data-ttu-id="6eed6-127">Para evitar la pérdida de recursos, cerramos los objetos utilizados en las comunicaciones cuando ya no se necesiten.</span><span class="sxs-lookup"><span data-stu-id="6eed6-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="6eed6-128">El siguiente ejemplo de código muestra un cliente básico que utiliza el generador de canales para enviar un mensaje y leer la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6eed6-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
