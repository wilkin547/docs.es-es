---
title: 'Protocolos de red: gRPC para desarrolladores de WCF'
description: Información general de los protocolos de red gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 801d57c95aec748e5dcf667ca480775ff945b55c
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938564"
---
# <a name="network-protocols"></a><span data-ttu-id="a9e04-103">Protocolos de red</span><span class="sxs-lookup"><span data-stu-id="a9e04-103">Network protocols</span></span>

<span data-ttu-id="a9e04-104">A diferencia de Windows Communication Foundation (WCF), gRPC usa HTTP/2 como base para sus redes.</span><span class="sxs-lookup"><span data-stu-id="a9e04-104">Unlike Windows Communication Foundation (WCF), gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="a9e04-105">Este protocolo ofrece ventajas significativas con respecto a WCF y SOAP, que solo funcionan en HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="a9e04-105">This protocol offers significant advantages over WCF and SOAP, which operate only on HTTP/1.1.</span></span> <span data-ttu-id="a9e04-106">Para los desarrolladores que desean usar gRPC, dado que no hay ninguna alternativa a HTTP/2, parece ser el momento ideal para explorar HTTP/2 con más detalle e identificar las ventajas adicionales del uso de gRPC.</span><span class="sxs-lookup"><span data-stu-id="a9e04-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits of using gRPC.</span></span>

<span data-ttu-id="a9e04-107">HTTP/2, publicado por Internet Engineering Task Force en 2015, se deriva del protocolo SPDY experimental, que ya estaba siendo usado por Google.</span><span class="sxs-lookup"><span data-stu-id="a9e04-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="a9e04-108">Se diseñó específicamente para ser más eficaz, más rápido y más seguro que HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="a9e04-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="a9e04-109">Características clave de HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a9e04-109">Key features of HTTP/2</span></span>

<span data-ttu-id="a9e04-110">Esta lista muestra algunas de las principales características y ventajas de HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="a9e04-110">This list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="a9e04-111">Protocolo binario</span><span class="sxs-lookup"><span data-stu-id="a9e04-111">Binary protocol</span></span>

<span data-ttu-id="a9e04-112">Los ciclos de solicitud/respuesta ya no necesitan comandos de texto.</span><span class="sxs-lookup"><span data-stu-id="a9e04-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="a9e04-113">Esta actividad simplifica y acelera la implementación de comandos.</span><span class="sxs-lookup"><span data-stu-id="a9e04-113">This activity simplifies and speeds up the implementation of commands.</span></span> <span data-ttu-id="a9e04-114">En concreto, el análisis de los datos es más rápido y usa menos memoria, la latencia de red se reduce con mejoras obvias relacionadas con la velocidad y existe un mejor uso de los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="a9e04-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="a9e04-115">Secuencias</span><span class="sxs-lookup"><span data-stu-id="a9e04-115">Streams</span></span>

<span data-ttu-id="a9e04-116">Las secuencias permiten crear conexiones de larga duración entre el remitente y el receptor, a través de la cual se pueden enviar varios mensajes o fotogramas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a9e04-116">Streams allow you to create long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="a9e04-117">Varias secuencias pueden funcionar de forma independiente a través de una única conexión HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a9e04-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="a9e04-118">Solicitar multiplexación a través de una única conexión TCP</span><span class="sxs-lookup"><span data-stu-id="a9e04-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="a9e04-119">Esta característica es una de las innovaciones más importantes de HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a9e04-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="a9e04-120">Dado que permite varias solicitudes paralelas de datos, ahora es posible descargar archivos Web simultáneamente desde un único servidor.</span><span class="sxs-lookup"><span data-stu-id="a9e04-120">Because it allows multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="a9e04-121">Los sitios web se cargan más rápido y se reduce la necesidad de optimización.</span><span class="sxs-lookup"><span data-stu-id="a9e04-121">Websites load faster, and the need for optimization is reduced.</span></span> <span data-ttu-id="a9e04-122">Bloqueo del cabezal de línea (HOL), donde las respuestas que están preparadas deben esperar a ser enviadas hasta que se complete una solicitud anterior, también se mitiga (aunque el bloqueo de HOL todavía puede producirse en el nivel de transporte TCP).</span><span class="sxs-lookup"><span data-stu-id="a9e04-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP-transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="a9e04-123">Rendimiento similar a net. TCP, entre plataformas</span><span class="sxs-lookup"><span data-stu-id="a9e04-123">Net.TCP-like performance, cross-platform</span></span>

<span data-ttu-id="a9e04-124">Fundamentalmente, la combinación de gRPC y HTTP/2 ofrece a los desarrolladores al menos la velocidad y eficiencia equivalentes de los enlaces net. TCP para WCF, y en algunos casos, incluso mayor velocidad y eficacia.</span><span class="sxs-lookup"><span data-stu-id="a9e04-124">Fundamentally, the combination of gRPC and HTTP/2 offers developers at least the equivalent speed and efficiency of Net.TCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="a9e04-125">Sin embargo, a diferencia de net. TCP, gRPC sobre HTTP/2 no está restringido a las aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="a9e04-125">But, unlike Net.TCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a9e04-126">[Anterior](interface-definition-language.md)
>[Siguiente](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="a9e04-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
