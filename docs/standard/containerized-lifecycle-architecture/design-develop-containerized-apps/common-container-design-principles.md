---
title: Principios de diseño comunes de contenedor
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c398e2da979637c450e2c9754ff3c9e8d8233aeb
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="common-container-design-principles"></a>Principios de diseño comunes de contenedor

Con antelación de introducción en el proceso de desarrollo son algunos conceptos básicos que vale la pena mencionar con respecto a cómo utilizar contenedores.

## <a name="container-equals-a-process"></a>Contenedor es igual a un proceso

En el modelo de contenedor, un contenedor representa un único proceso. Mediante la definición de un contenedor como un límite de proceso, empezar a crear a los tipos primitivos permiten escala, o fuera de proceso por lotes, los procesos. Al ejecutar un contenedor de Docker, verá un [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definición. Esto define el proceso y la duración del contenedor. Cuando se completa el proceso, se finaliza el ciclo de vida del contenedor. Hay procesos de larga duración, como servidores web y los procesos de corta duración, como los trabajos por lotes, que podrían se han implementado como Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/). Si se produce un error en el proceso, el contenedor finaliza y lo sustituye el orquestador. Si recibió el orchestrator para mantener los cinco instancias que se ejecutan y se produce un error, el orchestrator creará otro contenedor para reemplazar el proceso de errores. En un trabajo por lotes, el proceso se inicia con parámetros. Cuando el proceso finalice, el trabajo se habrá completado.

Es posible un escenario en el que desea que varios procesos en ejecución en un único contenedor. En cualquier documento de arquitectura, nunca hay un "nunca", así como tampoco hay siempre una "siempre". Para los escenarios que requieren varios procesos, un patrón común es utilizar [Supervisor](http://supervisord.org/).


>[!div class="step-by-step"]
[Anterior] (diseño-docker-applications.md) [siguiente] (monolítico-applications.md)
