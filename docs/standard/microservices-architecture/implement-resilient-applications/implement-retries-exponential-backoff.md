---
title: Implementar reintentos con retroceso exponencial
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar reintentos con retroceso exponencial
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ee5dd711484ba7861eedbd9613fda1209736d5b6
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106923"
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="920e7-103">Implementar reintentos con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="920e7-103">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="920e7-104">Los [*reintentos con retroceso exponencial*](https://docs.microsoft.com/azure/architecture/patterns/retry) son una técnica que intenta volver a ejecutar una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="920e7-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="920e7-105">Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="920e7-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="920e7-106">Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="920e7-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="920e7-107">Durante ese tiempo se podrían producir errores en algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="920e7-107">During that time, some requests might fail.</span></span> <span data-ttu-id="920e7-108">Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.</span><span class="sxs-lookup"><span data-stu-id="920e7-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="920e7-109">Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="920e7-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="920e7-110">[Anterior](partial-failure-strategies.md)
[Siguiente](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="920e7-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
