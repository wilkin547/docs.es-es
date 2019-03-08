---
title: Aplicaciones SOA
description: Tenga en cuenta que los contenedores también pueden ser una opción de implementación útil para las aplicaciones SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675802"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="1fd85-103">Aplicaciones orientadas a servicios</span><span class="sxs-lookup"><span data-stu-id="1fd85-103">Service-oriented applications</span></span>

<span data-ttu-id="1fd85-104">Arquitectura orientada a servicios (SOA) era un término sobreutilizado que significaba muchas cosas diferentes para diferentes personas.</span><span class="sxs-lookup"><span data-stu-id="1fd85-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="1fd85-105">Pero como denominador común, SOA significa que se estructura la arquitectura de la aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en tipos diferentes, como subsistemas o, en otros casos, como los niveles.</span><span class="sxs-lookup"><span data-stu-id="1fd85-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="1fd85-106">Hoy en día, puede implementar estos servicios como contenedores de Docker, lo que resolución problemas relacionados con la implementación, porque todas las dependencias se incluyen en la imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1fd85-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="1fd85-107">Sin embargo, cuando necesite escalar horizontalmente SOA, pueden surgir desafíos si va a implementar en función de instancias únicas.</span><span class="sxs-lookup"><span data-stu-id="1fd85-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="1fd85-108">Este desafío puede controlarse mediante software de clústeres o un orquestador de Docker.</span><span class="sxs-lookup"><span data-stu-id="1fd85-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="1fd85-109">Examinaremos los orquestadores con más detalle en la sección siguiente, cuando se exploración los enfoques de microservicios.</span><span class="sxs-lookup"><span data-stu-id="1fd85-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="1fd85-110">Los contenedores de Docker son útiles (pero no obligatorios) para las arquitecturas orientadas a servicios tradicionales y las arquitecturas de microservicios más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="1fd85-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="1fd85-111">Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura tradicional de SOA y para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="1fd85-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="1fd85-112">Y gracias a varias bases de datos, también puede escalar horizontalmente el nivel de datos en lugar de trabajar con bases de datos monolíticas compartidas por los servicios SOA.</span><span class="sxs-lookup"><span data-stu-id="1fd85-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="1fd85-113">Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre arquitectura y diseño.</span><span class="sxs-lookup"><span data-stu-id="1fd85-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1fd85-114">[Anterior](state-and-data-in-docker-applications.md)
>[Siguiente](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="1fd85-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
