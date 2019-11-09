---
title: Información general de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre el conjunto de principios que definen el desarrollo de gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6980b473a6f9852a4e4f396355e98e2d3300cabe
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841592"
---
# <a name="grpc-overview"></a><span data-ttu-id="70760-103">Información general de gRPC</span><span class="sxs-lookup"><span data-stu-id="70760-103">gRPC overview</span></span>

<span data-ttu-id="70760-104">Después de examinar el Genesis de WCF y gRPC en el último capítulo, en este capítulo se considerarán algunas de las características clave de gRPC y cómo se comparan con WCF.</span><span class="sxs-lookup"><span data-stu-id="70760-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="70760-105">ASP.NET Core 3,0 es la primera versión de ASP.NET que admite de forma nativa gRPC como ciudadano de primera clase, donde Microsoft Teams contribuye a la implementación oficial de .NET de gRPC.</span><span class="sxs-lookup"><span data-stu-id="70760-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="70760-106">Se recomienda como el mejor método para compilar aplicaciones distribuidas con .NET que pueden interoperar con todos los demás Marcos y lenguajes de programación principales.</span><span class="sxs-lookup"><span data-stu-id="70760-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="70760-107">Principios clave</span><span class="sxs-lookup"><span data-stu-id="70760-107">Key principles</span></span>

<span data-ttu-id="70760-108">Como se describe en el capítulo 1, Google quería usar la introducción de HTTP/2 para reemplazar Stubby, su infraestructura RPC interna de uso general.</span><span class="sxs-lookup"><span data-stu-id="70760-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="70760-109">gRPC, basado en Stubby, ahora puede aprovechar la estandarización y ampliar su aplicabilidad a la informática móvil, la nube y el Internet de las cosas.</span><span class="sxs-lookup"><span data-stu-id="70760-109">gRPC, based on Stubby, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="70760-110">Para lograr esto, [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) estableció un conjunto de principios que controlarían gRPC.</span><span class="sxs-lookup"><span data-stu-id="70760-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="70760-111">En la siguiente lista se muestran las más relevantes, que se ocupan principalmente de maximizar la accesibilidad y la facilidad de uso:</span><span class="sxs-lookup"><span data-stu-id="70760-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="70760-112">**Gratis y abierto** : todos los artefactos deben ser de código abierto con licencias que no restrinjan a los desarrolladores la adopción de gRPC.</span><span class="sxs-lookup"><span data-stu-id="70760-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="70760-113">**Cobertura y simplicidad** : gRPC debe estar disponible en cada plataforma popular y lo suficientemente simple como para compilar en cualquier plataforma.</span><span class="sxs-lookup"><span data-stu-id="70760-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="70760-114">**Interoperabilidad y alcance** : debe ser posible usar gRPC en cualquier red, sin tener en consideración el ancho de banda o la latencia, utilizando los estándares de red ampliamente disponibles.</span><span class="sxs-lookup"><span data-stu-id="70760-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="70760-115">Uso **General y rendimiento** : el marco de trabajo debe ser utilizable por una amplia gama de casos de uso posibles sin poner en peligro el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="70760-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="70760-116">**Streaming** : el protocolo debe proporcionar semántica de streaming para grandes conjuntos de datos o mensajería asincrónica.</span><span class="sxs-lookup"><span data-stu-id="70760-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="70760-117">**Intercambio de metadatos** : el protocolo permite que los datos no empresariales, como los tokens de autenticación, se controlen por separado de los datos empresariales reales.</span><span class="sxs-lookup"><span data-stu-id="70760-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="70760-118">**Códigos de estado estandarizados** : la variabilidad de los códigos de error debe reducirse para que las decisiones de control de errores sean más claras y, si se requiere un control de errores más completo, se debe proporcionar un mecanismo para administrar esto dentro del intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="70760-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="70760-119">[Anterior](introduction.md)
>[Siguiente](approach.md)</span><span class="sxs-lookup"><span data-stu-id="70760-119">[Previous](introduction.md)
[Next](approach.md)</span></span>
