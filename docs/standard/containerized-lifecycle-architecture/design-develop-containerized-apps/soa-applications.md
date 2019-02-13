---
title: Aplicaciones SOA
description: Tenga en cuenta que los contenedores también pueden ser una opción de implementación útil para las aplicaciones SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 4fd39e075c5730cf7fddb0138cdb5267a914c91f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221269"
---
# <a name="soa-applications"></a><span data-ttu-id="4989e-103">Aplicaciones SOA</span><span class="sxs-lookup"><span data-stu-id="4989e-103">SOA applications</span></span>

<span data-ttu-id="4989e-104">SOA era un término sobreutilizado y significaba tantas cosas diferentes para diferentes personas.</span><span class="sxs-lookup"><span data-stu-id="4989e-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="4989e-105">Pero como mínimo y como denominador común, SOA, o la orientación al servicio, Media de esa estructura la arquitectura de la aplicación descomponiéndola en varios servicios (normalmente como servicios HTTP) que se pueden clasificar en diferentes tipos, como subsistemas o bien, en otros casos, como capas.</span><span class="sxs-lookup"><span data-stu-id="4989e-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="4989e-106">Hoy en día, puede implementar estos servicios como contenedores de Docker, que soluciona problemas relacionados con la implementación, ya que todas las dependencias se incluyen dentro de la imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="4989e-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="4989e-107">Sin embargo, cuando necesite escalar horizontalmente SOA, pueden surgir desafíos si está implementando en función de instancias únicas.</span><span class="sxs-lookup"><span data-stu-id="4989e-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="4989e-108">Esto es donde Docker software de clústeres o orchestrator le ayudará.</span><span class="sxs-lookup"><span data-stu-id="4989e-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="4989e-109">Veremos esto más detalladamente en la sección siguiente cuando se examinan los enfoques de microservicios.</span><span class="sxs-lookup"><span data-stu-id="4989e-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="4989e-110">Al final del día, las soluciones de agrupación en clústeres de contenedor son útiles para ambas una arquitectura tradicional de SOA o para una arquitectura de microservicios más avanzada en la que cada microservicio posee su modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="4989e-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="4989e-111">Además, gracias a varias bases de datos, también puede escalar horizontalmente la capa de datos en lugar de trabajar con bases de datos monolíticas compartidas por los servicios SOA.</span><span class="sxs-lookup"><span data-stu-id="4989e-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="4989e-112">Sin embargo, la discusión sobre cómo dividir los datos es puramente sobre arquitectura y diseño.</span><span class="sxs-lookup"><span data-stu-id="4989e-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4989e-113">[Anterior](state-and-data-in-docker-applications.md)
>[Siguiente](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="4989e-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>