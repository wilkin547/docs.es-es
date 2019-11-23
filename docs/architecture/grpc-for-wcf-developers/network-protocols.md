---
title: 'Protocolos de red: gRPC para desarrolladores de WCF'
description: Información general de los protocolos de red gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 5e837738bd345608ca7119d04c9221acb220c276
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971703"
---
# <a name="network-protocols"></a><span data-ttu-id="f9a9f-103">Protocolos de red</span><span class="sxs-lookup"><span data-stu-id="f9a9f-103">Network protocols</span></span>

<span data-ttu-id="f9a9f-104">A diferencia de WCF, gRPC usa HTTP/2 como base para sus redes.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-104">Unlike WCF, gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="f9a9f-105">Esto ofrece ventajas significativas con respecto a WCF y SOAP, que solo funcionan en HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-105">This offers significant advantages over WCF and SOAP, which only operate on HTTP/1.1.</span></span> <span data-ttu-id="f9a9f-106">En el caso de los desarrolladores que desean usar gRPC, dado que no hay ninguna alternativa a HTTP/2, parece ser el momento ideal para explorar HTTP/2 con más detalle e identificar las ventajas adicionales del uso de gRPC.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits to using gRPC.</span></span>

<span data-ttu-id="f9a9f-107">HTTP/2, publicado por Internet Engineering Task Force en 2015, se deriva del protocolo SPDY experimental, que ya estaba siendo usado por Google.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="f9a9f-108">Se diseñó específicamente para ser más eficaz, más rápido y más seguro que HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="f9a9f-109">Características clave de HTTP/2</span><span class="sxs-lookup"><span data-stu-id="f9a9f-109">Key features of HTTP/2</span></span>

<span data-ttu-id="f9a9f-110">En la lista siguiente se muestran algunas de las características y ventajas clave de HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="f9a9f-110">The following list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="f9a9f-111">Protocolo binario</span><span class="sxs-lookup"><span data-stu-id="f9a9f-111">Binary protocol</span></span>

<span data-ttu-id="f9a9f-112">Los ciclos de solicitud/respuesta ya no necesitan comandos de texto.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="f9a9f-113">Esto simplifica y acelera la implementación de comandos.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-113">This simplifies and speeds up implementation of commands.</span></span> <span data-ttu-id="f9a9f-114">En concreto, el análisis de los datos es más rápido y usa menos memoria, la latencia de red se reduce con mejoras obvias relacionadas con la velocidad y existe un mejor uso de los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="f9a9f-115">Secuencias</span><span class="sxs-lookup"><span data-stu-id="f9a9f-115">Streams</span></span>

<span data-ttu-id="f9a9f-116">Las secuencias permiten la creación de conexiones de larga duración entre el remitente y el receptor, a través de la cual se pueden enviar varios mensajes o fotogramas de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-116">Streams allow for the creation of long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="f9a9f-117">Varias secuencias pueden funcionar de forma independiente a través de una única conexión HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="f9a9f-118">Solicitar multiplexación a través de una única conexión TCP</span><span class="sxs-lookup"><span data-stu-id="f9a9f-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="f9a9f-119">Esta característica es una de las innovaciones más importantes de HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="f9a9f-120">Al permitir varias solicitudes paralelas de datos, ahora es posible descargar archivos Web simultáneamente desde un único servidor.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-120">By allowing multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="f9a9f-121">Los sitios web se cargan más rápido y se reduce la necesidad de optimización.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-121">Websites load faster and the need for optimization is reduced.</span></span> <span data-ttu-id="f9a9f-122">Bloqueo del encabezado de línea (HOL), en el que las respuestas que están preparadas deben esperar a ser enviadas hasta que se complete una solicitud anterior, también se mitiga (aunque el bloqueo de HOL todavía puede producirse en el nivel de transporte TCP).</span><span class="sxs-lookup"><span data-stu-id="f9a9f-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="f9a9f-123">Rendimiento similar a NetTCP, entre plataformas</span><span class="sxs-lookup"><span data-stu-id="f9a9f-123">NetTCP-like performance, cross-platform</span></span>

<span data-ttu-id="f9a9f-124">Fundamentalmente, la combinación de gRPC y HTTP/2 ofrece a los desarrolladores al menos la velocidad y eficiencia equivalentes de los enlaces de NetTCP para WCF, y en algunos casos, incluso mayor velocidad y eficiencia.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-124">Fundamentally, the combination of gRPC and HTTP/2 offer developers at least the equivalent speed and efficiency of NetTCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="f9a9f-125">Sin embargo, a diferencia de NetTCP, gRPC sobre HTTP/2 no está restringido a las aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="f9a9f-125">However, unlike NetTCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f9a9f-126">[Anterior](interface-definition-language.md)
>[Siguiente](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="f9a9f-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
