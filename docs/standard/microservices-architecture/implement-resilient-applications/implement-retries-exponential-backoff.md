---
title: Implementar reintentos con retroceso exponencial
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar reintentos con retroceso exponencial
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 7f909c6f81abce80bfdf118112271f1f87254793
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571428"
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="6d425-103">Implementar reintentos con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="6d425-103">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="6d425-104">Los [*reintentos con retroceso exponencial*](https://docs.microsoft.com/azure/architecture/patterns/retry) son una técnica que intenta volver a ejecutar una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="6d425-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="6d425-105">Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="6d425-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="6d425-106">Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="6d425-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="6d425-107">Durante ese tiempo se podrían producir errores en algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="6d425-107">During that time, some requests might fail.</span></span> <span data-ttu-id="6d425-108">Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.</span><span class="sxs-lookup"><span data-stu-id="6d425-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="6d425-109">Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="6d425-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6d425-110">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="6d425-110">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
