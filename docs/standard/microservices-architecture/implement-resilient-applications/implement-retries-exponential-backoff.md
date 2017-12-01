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
# <a name="implementing-retries-with-exponential-backoff"></a>Implementación de reintentos con retroceso exponencial

[*Vuelve a intentar con retroceso exponencial* ](https://docs.microsoft.com/azure/architecture/patterns/retry) es una técnica que intenta volver a ejecutar una operación, con un tiempo de espera aumenta exponencialmente, hasta que se ha alcanzado un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)). Esta técnica adopta el hecho de que los recursos de nube no de vez en cuando estén disponibles durante más de unos pocos segundos por cualquier motivo. Por ejemplo, un orchestrator puede mover un contenedor a otro nodo en un clúster de equilibrio de carga. Durante ese tiempo, algunas solicitudes podrían producir errores. Otro ejemplo podría ser una base de datos como SQL Azure, donde una base de datos puede mover a otro servidor para equilibrio de carga haciendo que la base de datos no esté disponible durante unos segundos.

Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.


>[!div class="step-by-step"]
[Anterior] (partial-error-strategies.md) [siguiente] (implement-resilient-entity-framework-core-sql-connections.md)
