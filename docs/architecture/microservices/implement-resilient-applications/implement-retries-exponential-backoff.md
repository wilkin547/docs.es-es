---
title: Implementar reintentos con retroceso exponencial
description: Aprenda a implementar reintentos con retroceso exponencial.
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674542"
---
# <a name="implement-retries-with-exponential-backoff"></a>Implementar reintentos con retroceso exponencial

Los [*reintentos con retroceso exponencial*](/azure/architecture/patterns/retry) son una técnica que reintenta una operación, con un tiempo de espera que aumenta exponencialmente, hasta que se alcanza un número máximo de reintentos (el [retroceso exponencial](https://en.wikipedia.org/wiki/Exponential_backoff)). Esta técnica se basa en el hecho de que los recursos en la nube pueden no estar disponibles de forma intermitente durante más de unos segundos por cualquier motivo. Por ejemplo, un orquestador puede mover un contenedor a otro nodo de un clúster para el equilibrio de carga. Durante ese tiempo se podrían producir errores en algunas solicitudes. Otro ejemplo podría ser una base de datos como SQL Azure, que puede moverse a otro servidor para el equilibrio de carga, lo que haría que la base de datos no estuviera disponible durante unos segundos.

Existen muchos enfoques para implementar la lógica de reintentos con retroceso exponencial.

>[!div class="step-by-step"]
>[Anterior](partial-failure-strategies.md)
>[Siguiente](implement-resilient-entity-framework-core-sql-connections.md)
