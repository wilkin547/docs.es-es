---
title: Principios de diseño de contenedores comunes
description: 'Conozca un principio fundamental del buen diseño de contenedores: un contenedor solo debe hospedar un único proceso.'
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672502"
---
# <a name="common-container-design-principles"></a>Principios de diseño de contenedores comunes

Antes de entrar en el proceso de desarrollo, hay algunos conceptos básicos que vale la pena mencionar con respecto al uso de los contenedores.

## <a name="container-equals-a-process"></a>Un contenedor equivale a un proceso

En el modelo de contenedor, un contenedor representa un único proceso. Al definir un contenedor como límite de proceso, se empiezan a crear los tipos primitivos que se utilizan en procesos de escalado o generación de lotes. Al ejecutar un contenedor de Docker, verá una definición [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint). Esta define el proceso y la duración del contenedor. Cuando se completa el proceso, finaliza el ciclo de vida del contenedor. Hay procesos de larga ejecución (como servidores web) y procesos de corta duración (como trabajos por lotes), que posiblemente se hayan implementado como Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Si se produce un error en el proceso, el contenedor finaliza y lo sustituye el orquestador. Si se indicó al orquestador que mantuviera cinco instancias en ejecución y se produce un error en una de ellas, el orquestador creará otro contenedor para reemplazar al proceso erróneo. En un trabajo por lotes, el proceso se inicia con parámetros. Cuando el proceso finalice, el trabajo se habrá completado.

Es posible que en algún momento le interese que varios procesos se ejecuten en un solo contenedor. En cualquier documento de arquitectura, nunca hay un "nunca" ni siempre hay un "siempre". Para los escenarios que requieren varios procesos, un patrón común es usar [Supervisor](http://supervisord.org/).

>[!div class="step-by-step"]
>[Anterior](design-docker-applications.md)
>[Siguiente](monolithic-applications.md)
