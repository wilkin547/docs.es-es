---
title: Arquitectura orientada a servicios
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Arquitectura orientada a servicios
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ce4addefc7b6b1cf82551bf8304b7f06f1614796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573820"
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="0bb67-103">Arquitectura orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="0bb67-103">Service-oriented architecture</span></span> 

<span data-ttu-id="0bb67-104">La arquitectura orientada a servicios (SOA) era un término sobreutilizado que significaba cosas diferentes para cada persona.</span><span class="sxs-lookup"><span data-stu-id="0bb67-104">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="0bb67-105">Pero, como denominador común, SOA significa que se estructura una aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en tipos diferentes, como subsistemas o niveles.</span><span class="sxs-lookup"><span data-stu-id="0bb67-105">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="0bb67-106">Estos servicios ahora se pueden implementar como contenedores de Docker, con lo que se resuelven los problemas de implementación, puesto que todas las dependencias se incluyen en la imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="0bb67-106">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="0bb67-107">Pero cuando se necesita escalar verticalmente aplicaciones SOA, es posible que tenga problemas de escalabilidad y disponibilidad si va a efectuar la implementación en función de hosts de Docker únicos.</span><span class="sxs-lookup"><span data-stu-id="0bb67-107">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="0bb67-108">Aquí es donde le ayudará el software de agrupación en clústeres de Docker, o un orquestador, como se explica en secciones posteriores, donde se describen los enfoques de implementación para microservicios.</span><span class="sxs-lookup"><span data-stu-id="0bb67-108">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="0bb67-109">Los contenedores de Docker son útiles (pero no obligatorios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="0bb67-109">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="0bb67-110">Los microservicios se derivan de SOA, pero SOA no es lo mismo que la arquitectura de microservicios.</span><span class="sxs-lookup"><span data-stu-id="0bb67-110">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="0bb67-111">Características como los grandes agentes centrales, los orquestadores centrales en el nivel de organización y el [Bus de servicio empresarial (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) son habituales en SOA.</span><span class="sxs-lookup"><span data-stu-id="0bb67-111">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="0bb67-112">Pero en la mayoría de los casos son antipatrones en la comunidad de microservicios.</span><span class="sxs-lookup"><span data-stu-id="0bb67-112">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="0bb67-113">De hecho, hay quien argumenta que "la arquitectura de microservicios es SOA bien hecho".</span><span class="sxs-lookup"><span data-stu-id="0bb67-113">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="0bb67-114">Esta guía se centra en los microservicios, puesto que los enfoques SOA son menos prescriptivos que los requisitos y técnicas empleados en una arquitectura de microservicios.</span><span class="sxs-lookup"><span data-stu-id="0bb67-114">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="0bb67-115">Si sabe cómo crear una aplicación basada en microservicios, también sabrá cómo crear una aplicación orientada a servicios más sencilla.</span><span class="sxs-lookup"><span data-stu-id="0bb67-115">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="0bb67-116">[Anterior] (docker-application-state-data.md) [Siguiente] (microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="0bb67-116">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
