---
title: "Implementación de reintentos con retroceso exponencial"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de reintentos con retroceso exponencial"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="5b203-104">Implementación de reintentos con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="5b203-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="5b203-105">[*Vuelve a intentar con retroceso exponencial* ](https://docs.microsoft.com/azure/architecture/patterns/retry) es una técnica que intenta volver a ejecutar una operación, con un tiempo de espera aumenta exponencialmente, hasta que se ha alcanzado un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="5b203-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="5b203-106">Esta técnica adopta el hecho de que los recursos de nube no de vez en cuando estén disponibles durante más de unos pocos segundos por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="5b203-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="5b203-107">Por ejemplo, un orchestrator puede mover un contenedor a otro nodo en un clúster de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="5b203-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="5b203-108">Durante ese tiempo, algunas solicitudes podrían producir errores.</span><span class="sxs-lookup"><span data-stu-id="5b203-108">During that time, some requests might fail.</span></span> <span data-ttu-id="5b203-109">Otro ejemplo podría ser una base de datos como SQL Azure, donde una base de datos puede mover a otro servidor para equilibrio de carga haciendo que la base de datos no esté disponible durante unos segundos.</span><span class="sxs-lookup"><span data-stu-id="5b203-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="5b203-110">Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="5b203-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5b203-111">[Anterior] (partial-error-strategies.md) [siguiente] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="5b203-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
