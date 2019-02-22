---
title: Principios de diseño comunes de contenedor
description: Obtenga información sobre un principio fundamental del diseño del contenedor buena, es que un contenedor debe hospedar un solo proceso.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 206963d63cf8e6ab4fc61b9176f1ba095868c6fc
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664307"
---
# <a name="common-container-design-principles"></a>Principios de diseño comunes de contenedor

Con antelación de introducción al proceso de desarrollo son algunos conceptos básicos que vale la pena mencionar con respecto a cómo usar los contenedores.

## <a name="container-equals-a-process"></a>Contenedor es igual a un proceso

En el modelo de contenedor, un contenedor representa un único proceso. Mediante la definición de un contenedor como un límite de proceso, empezar a crear a los tipos primitivos que se usa para escalabilidad, o por lotes off, los procesos. Al ejecutar un contenedor de Docker, verá un [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definición. Esto define el proceso y la duración del contenedor. Cuando finalice el proceso, finaliza el ciclo de vida del contenedor. Hay procesos de larga ejecución, como servidores web y los procesos de corta duración, como trabajos por lotes, que es posible que se han implementado como Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/). Si se produce un error en el proceso, el contenedor finaliza y lo sustituye el orquestador. Si recibió el orquestador para mantener cinco instancias en ejecución y se produce un error, el orquestador creará otro contenedor para reemplazar el proceso con error. En un trabajo por lotes, el proceso se inicia con parámetros. Cuando el proceso finalice, el trabajo se habrá completado.

Podría encontrar un escenario en el que desea que varios procesos en ejecución en un único contenedor. En cualquier documento de arquitectura, nunca hay un "nunca", así como tampoco hay siempre una "siempre". Para los escenarios que requieren varios procesos, un patrón común es usar [Supervisor](http://supervisord.org/).

>[!div class="step-by-step"]
>[Anterior](design-docker-applications.md)
>[Siguiente](monolithic-applications.md)