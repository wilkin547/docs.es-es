---
description: 'Más información acerca de: Enrutamiento de IPv6'
title: Enrutamiento de IPv6
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: 75499a7380ab0ea7c38c83a6407a0c2a269b5fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672041"
---
# <a name="ipv6-routing"></a><span data-ttu-id="dbb50-103">Enrutamiento de IPv6</span><span class="sxs-lookup"><span data-stu-id="dbb50-103">IPv6 Routing</span></span>

<span data-ttu-id="dbb50-104">Una de las ventajas de IPv6 es el mecanismo de enrutamiento flexible.</span><span class="sxs-lookup"><span data-stu-id="dbb50-104">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="dbb50-105">Debido a la manera en que se asignaban y todavía se asignan los identificadores de red IPv4, los enrutadores que se encuentran en las redes troncales de Internet deben mantener grandes tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="dbb50-105">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="dbb50-106">Estos enrutadores deben conocer todas las rutas con el fin de reenviar los paquetes que se dirigen potencialmente a cualquier nodo de Internet.</span><span class="sxs-lookup"><span data-stu-id="dbb50-106">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="dbb50-107">Con su capacidad para agregar direcciones, IPv6 permite el direccionamiento flexible y reduce drásticamente el tamaño de las tablas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="dbb50-107">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="dbb50-108">En esta nueva arquitectura de direccionamiento, los enrutadores intermedios deben realizar un seguimiento únicamente de la parte local de su red para reenviar los mensajes de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="dbb50-108">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="dbb50-109">Detección de equipos cercanos</span><span class="sxs-lookup"><span data-stu-id="dbb50-109">Neighbor Discovery</span></span>  

 <span data-ttu-id="dbb50-110">Algunas de las características proporcionadas por la detección de equipos cercanos son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbb50-110">Some of the features provided by Neighbor Discovery are:</span></span>  
  
- <span data-ttu-id="dbb50-111">Detección de enrutadores.</span><span class="sxs-lookup"><span data-stu-id="dbb50-111">Router discovery.</span></span> <span data-ttu-id="dbb50-112">Permite que los hosts identifiquen los enrutadores locales.</span><span class="sxs-lookup"><span data-stu-id="dbb50-112">This allows hosts to identify local routers.</span></span>  
  
- <span data-ttu-id="dbb50-113">Resolución de direcciones.</span><span class="sxs-lookup"><span data-stu-id="dbb50-113">Address resolution.</span></span> <span data-ttu-id="dbb50-114">Permite que los nodos resuelvan una dirección de nivel de vínculo para una dirección de próximo salto correspondiente (sustitución del Protocolo de resolución de direcciones, también denominado ARP).</span><span class="sxs-lookup"><span data-stu-id="dbb50-114">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
- <span data-ttu-id="dbb50-115">Configuración automática de direcciones.</span><span class="sxs-lookup"><span data-stu-id="dbb50-115">Address auto-configuration.</span></span> <span data-ttu-id="dbb50-116">Permite a los hosts configurar automáticamente las direcciones globales y locales del sitio.</span><span class="sxs-lookup"><span data-stu-id="dbb50-116">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="dbb50-117">La detección de equipos cercanos usa mensajes del Protocolo de mensajes de control de Internet para IPv6 (ICMPv6) que incluyen:</span><span class="sxs-lookup"><span data-stu-id="dbb50-117">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
- <span data-ttu-id="dbb50-118">Anuncio de enrutador.</span><span class="sxs-lookup"><span data-stu-id="dbb50-118">Router advertisement.</span></span> <span data-ttu-id="dbb50-119">Enviado por un enrutador de forma seudoperiódica o en respuesta a una convocatoria de enrutador.</span><span class="sxs-lookup"><span data-stu-id="dbb50-119">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="dbb50-120">Los enrutadores IPv6 usan anuncios de enrutador para anunciar su disponibilidad, prefijos de direcciones y otros parámetros.</span><span class="sxs-lookup"><span data-stu-id="dbb50-120">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
- <span data-ttu-id="dbb50-121">Convocatoria de enrutador.</span><span class="sxs-lookup"><span data-stu-id="dbb50-121">Router solicitation.</span></span> <span data-ttu-id="dbb50-122">Enviada por un host para solicitar que los enrutadores del vínculo envíen inmediatamente un anuncio de enrutador.</span><span class="sxs-lookup"><span data-stu-id="dbb50-122">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
- <span data-ttu-id="dbb50-123">Convocatoria de vecino.</span><span class="sxs-lookup"><span data-stu-id="dbb50-123">Neighbor solicitation.</span></span> <span data-ttu-id="dbb50-124">Enviada por los nodos para la resolución de direcciones, la detección de direcciones duplicadas o la comprobación de que un vecino sigue siendo accesible.</span><span class="sxs-lookup"><span data-stu-id="dbb50-124">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
- <span data-ttu-id="dbb50-125">Anuncio de vecino.</span><span class="sxs-lookup"><span data-stu-id="dbb50-125">Neighbor advertisement.</span></span> <span data-ttu-id="dbb50-126">Enviada por los nodos para responder a una convocatoria de vecino o para notificar a los vecinos un cambio en la dirección de nivel de vínculo.</span><span class="sxs-lookup"><span data-stu-id="dbb50-126">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
- <span data-ttu-id="dbb50-127">Redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="dbb50-127">Redirect.</span></span> <span data-ttu-id="dbb50-128">Enviado por los enrutadores para indicar una dirección mejor de próximo salto a un destino determinado para un nodo de envío.</span><span class="sxs-lookup"><span data-stu-id="dbb50-128">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb50-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbb50-129">See also</span></span>

- [<span data-ttu-id="dbb50-130">Protocolo de Internet versión 6</span><span class="sxs-lookup"><span data-stu-id="dbb50-130">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="dbb50-131">Sockets</span><span class="sxs-lookup"><span data-stu-id="dbb50-131">Sockets</span></span>](sockets.md)
