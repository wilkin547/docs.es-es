---
title: Aplicaciones SOA
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 81d2b60303e051568b664ec20225d835a09187c0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="soa-applications"></a><span data-ttu-id="99736-104">Aplicaciones SOA</span><span class="sxs-lookup"><span data-stu-id="99736-104">SOA applications</span></span>

<span data-ttu-id="99736-105">SOA era un término sobreutilizado y su fin tantas cosas diferentes a distintas personas.</span><span class="sxs-lookup"><span data-stu-id="99736-105">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="99736-106">Pero como mínimo y como denominador común, SOA, o la orientación al servicio, Media que conforman la arquitectura de la aplicación, descomponiendo en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en diferentes tipos como subsistemas o bien, en otros casos, como niveles.</span><span class="sxs-lookup"><span data-stu-id="99736-106">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="99736-107">Hoy en día, puede implementar estos servicios como contenedores de Docker, que soluciona problemas relacionados con la implementación, ya que todas las dependencias se incluyen dentro de la imagen del contenedor.</span><span class="sxs-lookup"><span data-stu-id="99736-107">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="99736-108">Sin embargo, cuando necesite escalabilidad SOA, podría encontrar desafíos si va a implementar en función de instancias únicas.</span><span class="sxs-lookup"><span data-stu-id="99736-108">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="99736-109">Esto es donde una Docker software de clústeres o orchestrator le ayudará a.</span><span class="sxs-lookup"><span data-stu-id="99736-109">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="99736-110">Echemos un vistazo esto con más detalle en la sección siguiente cuando se examinan microservicios enfoques.</span><span class="sxs-lookup"><span data-stu-id="99736-110">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="99736-111">Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura SOA tradicional o para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="99736-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="99736-112">Y, gracias a varias bases de datos, también puede horizontal el nivel de datos en lugar de trabajar con bases de datos monolíticos compartidas por los servicios SOA.</span><span class="sxs-lookup"><span data-stu-id="99736-112">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="99736-113">Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre la arquitectura y diseño.</span><span class="sxs-lookup"><span data-stu-id="99736-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="99736-114">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="99736-114">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
