---
title: 'Cifrado y seguridad de red: gRPC para desarrolladores de WCF'
description: Algunas notas sobre la seguridad de red y el cifrado en gRPC
ms.date: 12/15/2020
ms.openlocfilehash: 0735158ed69ce425c4f00eed6c42689b888a1885
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938629"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="f646c-103">Cifrado y seguridad de red</span><span class="sxs-lookup"><span data-stu-id="f646c-103">Encryption and network security</span></span>

<span data-ttu-id="f646c-104">El modelo de seguridad de red para Windows Communication Foundation (WCF) es amplio y complejo.</span><span class="sxs-lookup"><span data-stu-id="f646c-104">The network security model for Windows Communication Foundation (WCF) is extensive and complex.</span></span> <span data-ttu-id="f646c-105">Incluye seguridad de nivel de transporte mediante HTTPS o TLS a través de TCP, y seguridad de nivel de mensaje mediante el WS-Security especificación para cifrar mensajes individuales.</span><span class="sxs-lookup"><span data-stu-id="f646c-105">It includes transport-level security by using HTTPS or TLS-over-TCP, and message-level security by using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="f646c-106">gRPC deja redes seguras en el protocolo HTTP/2 subyacente, que se puede proteger mediante el uso de certificados TLS.</span><span class="sxs-lookup"><span data-stu-id="f646c-106">gRPC leaves secure networking to the underlying HTTP/2 protocol, which you can secure by using TLS certificates.</span></span>

<span data-ttu-id="f646c-107">Los exploradores Web insisten en el uso de conexiones TLS para HTTP/2, pero la mayoría de los clientes de programación, incluido. La red `HttpClient` , puede usar http/2 a través de conexiones no cifradas.</span><span class="sxs-lookup"><span data-stu-id="f646c-107">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="f646c-108">`HttpClient` requiere el cifrado de forma predeterminada, pero puede invalidar este comportamiento mediante un <xref:System.AppContext> modificador.</span><span class="sxs-lookup"><span data-stu-id="f646c-108">`HttpClient` does require encryption by default, but you can override this behavior by using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="f646c-109">En el caso de las API públicas, siempre debe usar las conexiones TLS y proporcionar certificados válidos para los servicios de una autoridad SSL adecuada.</span><span class="sxs-lookup"><span data-stu-id="f646c-109">For public APIs, you should always use TLS connections, and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="f646c-110">[LetsEncrypt](https://letsencrypt.org) proporciona certificados SSL gratis y automatizados, y la mayoría de la infraestructura de hospedaje es compatible actualmente con el estándar LetsEncrypt con complementos o extensiones comunes.</span><span class="sxs-lookup"><span data-stu-id="f646c-110">[LetsEncrypt](https://letsencrypt.org) provides free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="f646c-111">En el caso de los servicios internos a través de una red corporativa, debería considerar el uso de TLS para proteger el tráfico de red hacia y desde los servicios de gRPC.</span><span class="sxs-lookup"><span data-stu-id="f646c-111">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="f646c-112">Si necesita usar TLS explícito entre servicios que se ejecutan en Kubernetes, considere la posibilidad de usar una entidad de certificación en clúster y un controlador de administrador de certificados como [CERT-Manager](https://docs.cert-manager.io/en/latest/).</span><span class="sxs-lookup"><span data-stu-id="f646c-112">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster certificate authority and a certificate manager controller like [cert-manager](https://docs.cert-manager.io/en/latest/).</span></span> <span data-ttu-id="f646c-113">Después, puede asignar automáticamente certificados a los servicios en el momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f646c-113">You can then automatically assign certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f646c-114">[Anterior](channel-credentials.md)
>[Siguiente](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="f646c-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
