---
title: Arquitectura orientada a servicios
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Arquitectura orientada a servicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="11781-104">Arquitectura orientada a servicios</span><span class="sxs-lookup"><span data-stu-id="11781-104">Service-oriented architecture</span></span> 

<span data-ttu-id="11781-105">Arquitectura orientada a servicios (SOA) era un término sobreutilizado y objetivo cosas diferentes a distintas personas.</span><span class="sxs-lookup"><span data-stu-id="11781-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="11781-106">Pero como denominador común, SOA significa estructurar la aplicación por descomponer en varios servicios (normalmente como servicios HTTP) que se pueden clasificar como tipos diferentes, como subsistemas o niveles.</span><span class="sxs-lookup"><span data-stu-id="11781-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="11781-107">Dichos servicios ahora se pueden implementar como contenedores de Docker, que resuelve los problemas de implementación, puesto que todas las dependencias se incluyen en la imagen del contenedor.</span><span class="sxs-lookup"><span data-stu-id="11781-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="11781-108">Sin embargo, cuando necesite ampliar aplicaciones SOA, es posible que tenga la escalabilidad y desafíos de disponibilidad si va a implementar en función de los hosts de Docker únicos.</span><span class="sxs-lookup"><span data-stu-id="11781-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="11781-109">Esto es donde Docker software de clústeres u organizador le ayudará a, como se explica en secciones posteriores donde se describen los enfoques de implementación para microservicios.</span><span class="sxs-lookup"><span data-stu-id="11781-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="11781-110">Contenedores de docker son útiles (pero no son necesarios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="11781-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="11781-111">Microservicios se derivan de SOA, pero es diferente de la arquitectura de microservicios SOA.</span><span class="sxs-lookup"><span data-stu-id="11781-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="11781-112">Características como el big corredores de bolsa centrales, orchestrators centrales en el nivel de organización y el [Bus de servicio de empresa (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) son típicos de SOA.</span><span class="sxs-lookup"><span data-stu-id="11781-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="11781-113">Pero en la mayoría de los casos, estos son antipatrones en la Comunidad de microservicio.</span><span class="sxs-lookup"><span data-stu-id="11781-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="11781-114">De hecho, algunas personas argumentan que "la arquitectura de microservicio es SOA bien."</span><span class="sxs-lookup"><span data-stu-id="11781-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="11781-115">Esta guía se centra en microservicios, dado que un enfoque SOA es menos descriptiva de los requisitos y las técnicas que se utilizan en una arquitectura de microservicio.</span><span class="sxs-lookup"><span data-stu-id="11781-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="11781-116">Si sabe cómo crear una aplicación basada en microservicio, sabrá cómo crear una aplicación orientada a servicios más sencilla.</span><span class="sxs-lookup"><span data-stu-id="11781-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="11781-117">[Anterior] (docker-aplicaciones-estado-data.md) [siguiente] (microservicios architecture.md)</span><span class="sxs-lookup"><span data-stu-id="11781-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
