---
title: "Diseñar aplicaciones de Docker"
description: "Ciclo de vida de aplicación de Docker en contenedores con herramientas y plataforma de Microsoft"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: db8376abf95aab51fad23f4b351cb772351117ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="design-docker-applications"></a><span data-ttu-id="822d6-104">Diseñar aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="822d6-104">Design Docker applications</span></span>

<span data-ttu-id="822d6-105">Capítulo 1 introdujo los conceptos básicos sobre los contenedores y Docker.</span><span class="sxs-lookup"><span data-stu-id="822d6-105">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="822d6-106">Esta información es el nivel básico de la información que necesita para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="822d6-106">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="822d6-107">Sin embargo, las aplicaciones empresariales pueden ser complejos y está compuesto de varios servicios en lugar de una única dirección IP o el contenedor.</span><span class="sxs-lookup"><span data-stu-id="822d6-107">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="822d6-108">Para los casos de uso opcional, debe conocer enfoques adicionales al diseño, por ejemplo, una arquitectura orientada a servicios (SOA) y la microservicios conceptos más avanzados y el contenedor conceptos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="822d6-108">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="822d6-109">El ámbito de este documento no se limita a microservicios pero ningún ciclo de vida de aplicación de Docker, por lo tanto, no explore microservicios arquitectura en profundidad porque también puede usar contenedores y Docker con Santo regular, tareas en segundo plano o los trabajos, o incluso con los métodos de implementación de aplicación monolítico.</span><span class="sxs-lookup"><span data-stu-id="822d6-109">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="822d6-110">Sin embargo, antes de entrar en el ciclo de vida de aplicación y DevOps, es importante saber cómo va a diseño y construir la aplicación y cuáles son las opciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="822d6-110">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="822d6-111">[Anterior] (index.md) [siguiente] (comunes contenedor-diseño principles.md)</span><span class="sxs-lookup"><span data-stu-id="822d6-111">[Previous] (index.md) [Next] (common-container-design-principles.md)</span></span>
