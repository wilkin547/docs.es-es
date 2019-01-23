---
title: Implementar reintentos con retroceso exponencial
description: Aprenda a implementar reintentos con retroceso exponencial.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 421a4535888f432974c764b238c06b5b323aefb3
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362085"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="e817c-103">Implementar reintentos con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="e817c-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="e817c-104">Los [*reintentos con retroceso exponencial*](/azure/architecture/patterns/retry) son una técnica que reintenta una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="e817c-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="e817c-105">Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="e817c-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="e817c-106">Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="e817c-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="e817c-107">Durante ese tiempo se podrían producir errores en algunas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="e817c-107">During that time, some requests might fail.</span></span> <span data-ttu-id="e817c-108">Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.</span><span class="sxs-lookup"><span data-stu-id="e817c-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="e817c-109">Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="e817c-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e817c-110">[Anterior](partial-failure-strategies.md)
>[Siguiente](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="e817c-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>