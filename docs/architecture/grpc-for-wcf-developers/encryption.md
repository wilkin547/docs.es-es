---
title: 'Cifrado y seguridad de red: gRPC para desarrolladores de WCF'
description: Algunas notas sobre la seguridad de red y el cifrado en gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841622"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="3f109-103">Cifrado y seguridad de red</span><span class="sxs-lookup"><span data-stu-id="3f109-103">Encryption and network security</span></span>

<span data-ttu-id="3f109-104">El modelo de seguridad de red de WCF es amplio y complejo, incluida la seguridad de nivel de transporte mediante HTTPS o TLS a través de TCP, y la seguridad de nivel de mensaje mediante la especificación WS-Security para cifrar mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="3f109-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="3f109-105">gRPC deja redes seguras en el protocolo HTTP/2 subyacente, que se puede proteger mediante certificados TLS normales.</span><span class="sxs-lookup"><span data-stu-id="3f109-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="3f109-106">Los exploradores Web insisten en el uso de conexiones TLS para HTTP/2, pero la mayoría de los clientes de programación, incluido. La `HttpClient`de red, puede usar HTTP/2 a través de conexiones no cifradas.</span><span class="sxs-lookup"><span data-stu-id="3f109-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="3f109-107">`HttpClient` *requiere* cifrado de forma predeterminada, pero puede invalidarlo mediante un modificador de <xref:System.AppContext>.</span><span class="sxs-lookup"><span data-stu-id="3f109-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="3f109-108">En el caso de las API públicas, siempre debe usar las conexiones TLS y proporcionar certificados válidos para los servicios de una autoridad SSL adecuada.</span><span class="sxs-lookup"><span data-stu-id="3f109-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="3f109-109">[LetsEncrypt](https://letsencrypt.org) proporcionan certificados SSL gratuitos y automatizados, y la mayoría de la infraestructura de hospedaje es compatible actualmente con el estándar LetsEncrypt con complementos o extensiones comunes.</span><span class="sxs-lookup"><span data-stu-id="3f109-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="3f109-110">En el caso de los servicios internos a través de una red corporativa, debería considerar el uso de TLS para proteger el tráfico de red hacia y desde los servicios de gRPC.</span><span class="sxs-lookup"><span data-stu-id="3f109-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="3f109-111">En general, la comunicación entre los microservicios de un clúster como Kubernetes o Docker Swarm se cifra automáticamente mediante el nivel de red del contenedor, por lo que no es necesario implementar TLS en servicios que se ejecutan exclusivamente en dicho clúster.</span><span class="sxs-lookup"><span data-stu-id="3f109-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="3f109-112">Habrá más información sobre este tema en la sección "malla de servicio" del siguiente capítulo.</span><span class="sxs-lookup"><span data-stu-id="3f109-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="3f109-113">Si necesita usar TLS explícito entre servicios que se ejecutan en Kubernetes, considere la posibilidad de usar una entidad de certificación en clúster y un controlador de administrador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/) para asignar certificados automáticamente a los servicios en el momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="3f109-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3f109-114">[Anterior](channel-credentials.md)
>[Siguiente](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="3f109-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
