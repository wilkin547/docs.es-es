---
title: Transportes en Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 115e2a69c7d990c7d4c59634644fb557e83ad405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="11a0e-102">Transportes en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="11a0e-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="11a0e-103">El nivel de transporte está en el nivel más bajo de la pila del canal.</span><span class="sxs-lookup"><span data-stu-id="11a0e-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="11a0e-104">Los transportes principales utilizados en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] son HTTP, HTTPS, TCP y canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="11a0e-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="11a0e-105">Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.</span><span class="sxs-lookup"><span data-stu-id="11a0e-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="11a0e-106"> incluye transportes adicionales.</span><span class="sxs-lookup"><span data-stu-id="11a0e-106"> includes additional transports.</span></span> <span data-ttu-id="11a0e-107">Para obtener información sobre el transporte de Message Queue Server (también conocido como MSMQ), consulte [colas y sesiones confiables](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="11a0e-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="11a0e-108">Para obtener información sobre transporte peer-to-peer, consulte [redes Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="11a0e-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11a0e-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11a0e-109">In This Section</span></span>  
 [<span data-ttu-id="11a0e-110">Elegir un transporte</span><span class="sxs-lookup"><span data-stu-id="11a0e-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="11a0e-111">Describe los tres transportes principales y las consideraciones para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="11a0e-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="11a0e-112">Elegir un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="11a0e-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="11a0e-113">Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="11a0e-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="11a0e-114">Transferencia de mensajes de transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="11a0e-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="11a0e-115">Describe cómo configurar el nivel de transporte para la transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="11a0e-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="11a0e-116">Configuración de HTTP y HTTPS</span><span class="sxs-lookup"><span data-stu-id="11a0e-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="11a0e-117">Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="11a0e-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="11a0e-118">Cómo: reemplazar la reserva de direcciones URL de WCF con una reserva restringida</span><span class="sxs-lookup"><span data-stu-id="11a0e-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="11a0e-119">Describe cómo usar las reservas de direcciones URL restringidas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11a0e-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="11a0e-120">Cuotas de transporte</span><span class="sxs-lookup"><span data-stu-id="11a0e-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="11a0e-121">Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="11a0e-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="11a0e-122">Trabajar con NAT y Firewalls</span><span class="sxs-lookup"><span data-stu-id="11a0e-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="11a0e-123">Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red (NAT) está presente.</span><span class="sxs-lookup"><span data-stu-id="11a0e-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="11a0e-124">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="11a0e-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="11a0e-125">Describe cómo utilizar el componente compartido de puerto Net.TCP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11a0e-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="11a0e-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="11a0e-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="11a0e-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="11a0e-127">Related Sections</span></span>  
 [<span data-ttu-id="11a0e-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="11a0e-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="11a0e-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="11a0e-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
