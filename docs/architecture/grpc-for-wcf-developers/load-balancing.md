---
title: Equilibrio de carga gRPC-gRPC para desarrolladores de WCF
description: Elección de un equilibrador de carga para trabajar con gRPC Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841556"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="4c760-103">Equilibrio de carga gRPC</span><span class="sxs-lookup"><span data-stu-id="4c760-103">Load balancing gRPC</span></span>

<span data-ttu-id="4c760-104">Una implementación típica de una aplicación de gRPC incluye varias instancias idénticas del servicio, lo que proporciona resistencia y escalabilidad horizontal.</span><span class="sxs-lookup"><span data-stu-id="4c760-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="4c760-105">Equilibrio de carga de las solicitudes entrantes distribuidas entre estas instancias para proporcionar el uso completo de todos los recursos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4c760-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="4c760-106">Para que este equilibrio de carga sea invisible para el cliente, es habitual usar un servidor de equilibrador de carga de proxy para controlar las solicitudes de los clientes y enrutarlas a las instancias de back-end.</span><span class="sxs-lookup"><span data-stu-id="4c760-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="4c760-107">Los equilibradores de carga se clasifican según la *capa* en la que operan.</span><span class="sxs-lookup"><span data-stu-id="4c760-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="4c760-108">Los equilibradores de carga de nivel 4 funcionan en el nivel de *transporte* , por ejemplo, con Sockets TCP, conexiones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="4c760-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="4c760-109">Los equilibradores de carga de nivel 7 funcionan en el nivel de *aplicación* , y controlan específicamente las solicitudes HTTP/2 para las aplicaciones gRPC.</span><span class="sxs-lookup"><span data-stu-id="4c760-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="4c760-110">Equilibradores de carga L4</span><span class="sxs-lookup"><span data-stu-id="4c760-110">L4 load balancers</span></span>

<span data-ttu-id="4c760-111">Un equilibrador de carga L4 acepta una solicitud de conexión TCP de un cliente, abre otra conexión a una de las instancias de back-end y copia los datos entre las dos conexiones sin ningún procesamiento real.</span><span class="sxs-lookup"><span data-stu-id="4c760-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="4c760-112">L4 ofrece un rendimiento excelente y una baja latencia, pero muy poco control o inteligencia.</span><span class="sxs-lookup"><span data-stu-id="4c760-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="4c760-113">Siempre que el cliente mantenga abierta la conexión, todas las solicitudes se dirigirán a la misma instancia de back-end.</span><span class="sxs-lookup"><span data-stu-id="4c760-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="4c760-114">Un ejemplo de un equilibrador de carga L4 es el [Azure load balancer](https://azure.microsoft.com/services/load-balancer/).</span><span class="sxs-lookup"><span data-stu-id="4c760-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="4c760-115">Equilibradores de carga L7</span><span class="sxs-lookup"><span data-stu-id="4c760-115">L7 load balancers</span></span>

<span data-ttu-id="4c760-116">Un equilibrador de carga L7 analiza las solicitudes HTTP/2 entrantes y las pasa a las instancias de back-end de manera solicitada, independientemente de cuánto tiempo tenga la conexión el cliente.</span><span class="sxs-lookup"><span data-stu-id="4c760-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="4c760-117">Los ejemplos de equilibradores de carga L7 incluyen:</span><span class="sxs-lookup"><span data-stu-id="4c760-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="4c760-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="4c760-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="4c760-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="4c760-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="4c760-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="4c760-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="4c760-121">Como regla general, los equilibradores de carga L7 son la mejor opción para gRPC y otras aplicaciones HTTP/2 (y, por lo general, para las aplicaciones HTTP).</span><span class="sxs-lookup"><span data-stu-id="4c760-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="4c760-122">Los equilibradores de carga L4 *funcionarán* con las aplicaciones de gRPC, pero son especialmente útiles cuando la baja latencia y la sobrecarga baja son de primordial importancia.</span><span class="sxs-lookup"><span data-stu-id="4c760-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c760-123">En el momento de redactar este documento, no todos los equilibradores de carga L7 admiten todas las partes de la especificación HTTP/2 requerida por gRPC Services, como los encabezados finales.</span><span class="sxs-lookup"><span data-stu-id="4c760-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="4c760-124">Cuando se usa el cifrado TLS, los equilibradores de carga pueden finalizar la conexión TLS y pasar las solicitudes no cifradas a la aplicación back-end, o bien pasar la solicitud cifrada.</span><span class="sxs-lookup"><span data-stu-id="4c760-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="4c760-125">En cualquier caso, el equilibrador de carga tendrá que configurarse con la clave pública y privada del servidor para que pueda descifrar las solicitudes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="4c760-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="4c760-126">Consulte la documentación de su equilibrador de carga preferido para averiguar cómo configurarlo para controlar las solicitudes HTTP/2 con los servicios back-end.</span><span class="sxs-lookup"><span data-stu-id="4c760-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="4c760-127">Equilibrio de carga dentro de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4c760-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="4c760-128">Consulte [la sección sobre las mallas de servicio](service-mesh.md) para obtener una explicación del equilibrio de carga entre servicios internos en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4c760-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4c760-129">[Anterior](service-mesh.md)
>[Siguiente](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="4c760-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
