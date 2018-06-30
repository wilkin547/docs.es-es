---
title: Diseñar aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 2f4a3b7675365aa4d1e33328f756439398f3a4de
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105242"
---
# <a name="design-docker-applications"></a><span data-ttu-id="34258-103">Diseñar aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="34258-103">Design Docker applications</span></span>

<span data-ttu-id="34258-104">Capítulo 1 introdujo los conceptos básicos sobre los contenedores y Docker.</span><span class="sxs-lookup"><span data-stu-id="34258-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="34258-105">Esta información es el nivel básico de la información que necesita para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="34258-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="34258-106">Sin embargo, las aplicaciones empresariales pueden ser complejos y está compuesto de varios servicios en lugar de una única dirección IP o el contenedor.</span><span class="sxs-lookup"><span data-stu-id="34258-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="34258-107">Para los casos de uso opcional, debe conocer enfoques adicionales al diseño, por ejemplo, una arquitectura orientada a servicios (SOA) y la microservicios conceptos más avanzados y el contenedor conceptos de orquestación.</span><span class="sxs-lookup"><span data-stu-id="34258-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="34258-108">El ámbito de este documento no se limita a microservicios pero ningún ciclo de vida de aplicación de Docker, por lo tanto, no explore microservicios arquitectura en profundidad porque también puede usar contenedores y Docker con Santo regular, tareas en segundo plano o los trabajos, o incluso con los métodos de implementación de aplicación monolítico.</span><span class="sxs-lookup"><span data-stu-id="34258-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="34258-109">Sin embargo, antes de entrar en el ciclo de vida de aplicación y DevOps, es importante saber cómo va a diseño y construir la aplicación y cuáles son las opciones de diseño.</span><span class="sxs-lookup"><span data-stu-id="34258-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="34258-110">[Anterior](index.md)
[Siguiente](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="34258-110">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
