---
title: Aplicaciones SOA
description: Tenga en cuenta que los contenedores también pueden ser una opción de implementación útil para las aplicaciones SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 353ba738143b7dcd92c7c75ac27ea6a7370f9da6
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745838"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="5ab60-103">Aplicaciones orientadas a servicios</span><span class="sxs-lookup"><span data-stu-id="5ab60-103">Service-oriented applications</span></span>

<span data-ttu-id="5ab60-104">Arquitectura orientada a servicios (SOA) era un término sobreutilizado que significaba muchas cosas diferentes para diferentes personas.</span><span class="sxs-lookup"><span data-stu-id="5ab60-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="5ab60-105">Pero como denominador común, SOA significa que se estructura la arquitectura de la aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en tipos diferentes, como subsistemas o, en otros casos, como los niveles.</span><span class="sxs-lookup"><span data-stu-id="5ab60-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="5ab60-106">Hoy en día, puede implementar estos servicios como contenedores de Docker, lo que resolución problemas relacionados con la implementación, porque todas las dependencias se incluyen en la imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="5ab60-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="5ab60-107">Sin embargo, cuando necesite escalar horizontalmente SOA, pueden surgir desafíos si está implementando en función de instancias únicas.</span><span class="sxs-lookup"><span data-stu-id="5ab60-107">However, when you need to scale out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="5ab60-108">Este desafío puede controlarse mediante software de clústeres o un orquestador de Docker.</span><span class="sxs-lookup"><span data-stu-id="5ab60-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="5ab60-109">Examinaremos los orquestadores con más detalle en la sección siguiente, cuando se exploración los enfoques de microservicios.</span><span class="sxs-lookup"><span data-stu-id="5ab60-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="5ab60-110">Los contenedores de Docker son útiles (pero no obligatorios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="5ab60-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="5ab60-111">Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura tradicional de SOA y para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="5ab60-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="5ab60-112">Y gracias a varias bases de datos, también puede escalar horizontalmente el nivel de datos en lugar de trabajar con bases de datos monolíticas compartidas por los servicios SOA.</span><span class="sxs-lookup"><span data-stu-id="5ab60-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="5ab60-113">Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre arquitectura y diseño.</span><span class="sxs-lookup"><span data-stu-id="5ab60-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5ab60-114">[Anterior](state-and-data-in-docker-applications.md)
>[Siguiente](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="5ab60-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
