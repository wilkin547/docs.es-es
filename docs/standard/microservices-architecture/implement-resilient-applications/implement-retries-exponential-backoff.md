---
title: Implementar reintentos con retroceso exponencial
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar reintentos con retroceso exponencial
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7ed97b750d6e3f2aa5def72e90e070a49a7c0e63
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a>Implementar reintentos con retroceso exponencial

Los [*reintentos con retroceso exponencial*](https://docs.microsoft.com/azure/architecture/patterns/retry) son una técnica que intenta volver a ejecutar una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)). Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo. Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga. Durante ese tiempo se podrían producir errores en algunas solicitudes. Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.

Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.


>[!div class="step-by-step"]
[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)
