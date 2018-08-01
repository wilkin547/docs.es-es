---
title: Implementar reintentos con retroceso exponencial
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar reintentos con retroceso exponencial
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: a5ab15299ecb501691c26bbc6d377e22a38ee51e
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874369"
---
# <a name="implement-retries-with-exponential-backoff"></a>Implementar reintentos con retroceso exponencial

Los [*reintentos con retroceso exponencial*](https://docs.microsoft.com/azure/architecture/patterns/retry) son una técnica que intenta volver a ejecutar una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)). Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo. Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga. Durante ese tiempo se podrían producir errores en algunas solicitudes. Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.

Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.


>[!div class="step-by-step"]
[Anterior](partial-failure-strategies.md)
[Siguiente](implement-resilient-entity-framework-core-sql-connections.md)
