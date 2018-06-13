---
title: Transportes en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498129"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="53ed3-102">Transportes en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="53ed3-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="53ed3-103">El nivel de transporte está en el nivel más bajo de la pila del canal.</span><span class="sxs-lookup"><span data-stu-id="53ed3-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="53ed3-104">Los transportes principales utilizados en Windows Communication Foundation (WCF) son HTTP, HTTPS, TCP y canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="53ed3-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="53ed3-105">Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.</span><span class="sxs-lookup"><span data-stu-id="53ed3-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="53ed3-106">WCF incluye transportes adicionales.</span><span class="sxs-lookup"><span data-stu-id="53ed3-106">WCF includes additional transports.</span></span> <span data-ttu-id="53ed3-107">Para obtener información sobre el transporte de Message Queue Server (también conocido como MSMQ), consulte [colas y sesiones confiables](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="53ed3-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="53ed3-108">Para obtener información sobre transporte peer-to-peer, consulte [redes Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="53ed3-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53ed3-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="53ed3-109">In This Section</span></span>  
 [<span data-ttu-id="53ed3-110">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="53ed3-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="53ed3-111">Describe los tres transportes principales y las consideraciones para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="53ed3-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="53ed3-112">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="53ed3-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="53ed3-113">Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="53ed3-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="53ed3-114">Transferencia de mensajes por streaming</span><span class="sxs-lookup"><span data-stu-id="53ed3-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="53ed3-115">Describe cómo configurar el nivel de transporte para la transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="53ed3-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="53ed3-116">Configuración de HTTP y HTTPS</span><span class="sxs-lookup"><span data-stu-id="53ed3-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="53ed3-117">Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="53ed3-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="53ed3-118">Sustitución de la reserva de direcciones URL de WCF por una reserva restringida</span><span class="sxs-lookup"><span data-stu-id="53ed3-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="53ed3-119">Describe cómo usar las reservas de WCFURL restringido.</span><span class="sxs-lookup"><span data-stu-id="53ed3-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="53ed3-120">Cuotas de transporte</span><span class="sxs-lookup"><span data-stu-id="53ed3-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="53ed3-121">Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="53ed3-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="53ed3-122">Trabajo con NAT y firewalls</span><span class="sxs-lookup"><span data-stu-id="53ed3-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="53ed3-123">Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red (NAT) está presente.</span><span class="sxs-lookup"><span data-stu-id="53ed3-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="53ed3-124">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="53ed3-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="53ed3-125">Describe cómo usar el componente de uso compartido de puertos Net.TCP de WCF.</span><span class="sxs-lookup"><span data-stu-id="53ed3-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="53ed3-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="53ed3-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="53ed3-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="53ed3-127">Related Sections</span></span>  
 [<span data-ttu-id="53ed3-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="53ed3-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="53ed3-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="53ed3-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
