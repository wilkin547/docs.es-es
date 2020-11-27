---
title: Transportes en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 8623b788b848867f25836a657b07349dd50c2780
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251690"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="91f26-102">Transportes en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="91f26-102">Transports in Windows Communication Foundation</span></span>

<span data-ttu-id="91f26-103">El nivel de transporte está en el nivel más bajo de la pila del canal.</span><span class="sxs-lookup"><span data-stu-id="91f26-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="91f26-104">Los transportes principales utilizados en Windows Communication Foundation (WCF) son HTTP, HTTPS, TCP y canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="91f26-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="91f26-105">Los temas de esta sección tratan sobre la elección entre estos transportes, la configuración del transporte y el establecimiento de propiedades de optimización.</span><span class="sxs-lookup"><span data-stu-id="91f26-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="91f26-106">WCF incluye transportes adicionales.</span><span class="sxs-lookup"><span data-stu-id="91f26-106">WCF includes additional transports.</span></span> <span data-ttu-id="91f26-107">Para obtener información sobre el transporte de Message Queuing (también conocido como MSMQ), vea [colas y sesiones confiables](queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="91f26-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="91f26-108">Para obtener información sobre el transporte punto a punto, vea [redes punto a punto](peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="91f26-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91f26-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="91f26-109">In This Section</span></span>  

 [<span data-ttu-id="91f26-110">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="91f26-110">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="91f26-111">Describe los tres transportes principales y las consideraciones para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="91f26-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="91f26-112">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="91f26-112">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="91f26-113">Describe los factores que considerar al elegir un elemento de enlace de codificación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="91f26-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="91f26-114">Transferencia de mensajes por secuencias</span><span class="sxs-lookup"><span data-stu-id="91f26-114">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="91f26-115">Describe cómo configurar el nivel de transporte para la transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="91f26-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="91f26-116">Configuración de HTTP y HTTPS</span><span class="sxs-lookup"><span data-stu-id="91f26-116">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="91f26-117">Describe cómo configurar los elementos de enlace de transporte HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="91f26-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="91f26-118">Procedimiento para reemplazar la reserva de direcciones URL de WCF por una reserva restringida</span><span class="sxs-lookup"><span data-stu-id="91f26-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="91f26-119">Describe cómo usar las reservas restringidas de WCFURL.</span><span class="sxs-lookup"><span data-stu-id="91f26-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="91f26-120">Cuotas de transporte</span><span class="sxs-lookup"><span data-stu-id="91f26-120">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="91f26-121">Describe las consideraciones para establecer las cuotas disponibles en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="91f26-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="91f26-122">Trabajar con NAT y firewalls</span><span class="sxs-lookup"><span data-stu-id="91f26-122">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="91f26-123">Describe cómo configurar el nivel de transporte cuando los mensajes se envían o reciben detrás de un firewall o cuando la traducción de direcciones de red (NAT) está presente.</span><span class="sxs-lookup"><span data-stu-id="91f26-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="91f26-124">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="91f26-124">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="91f26-125">Describe cómo usar el componente de uso compartido de puertos net. TCP de WCF.</span><span class="sxs-lookup"><span data-stu-id="91f26-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="91f26-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="91f26-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="91f26-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="91f26-127">Related Sections</span></span>  

 [<span data-ttu-id="91f26-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="91f26-128">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="91f26-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="91f26-129">Extending Bindings</span></span>](../extending/extending-bindings.md)
