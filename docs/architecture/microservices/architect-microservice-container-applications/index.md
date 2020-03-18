---
title: Diseño de la arquitectura de aplicaciones basadas en contenedores y microservicios
description: El diseño de la arquitectura de aplicaciones basadas en contenedores y microservicios no es ninguna tontería y no debe tomarse a la ligera. Conozca sobre los conceptos principales en este capítulo.
ms.date: 09/20/2018
ms.openlocfilehash: aff30c907f1140b94dbcae330ed7cb633b0a744b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "70295022"
---
# <a name="architecting-container-and-microservice-based-applications"></a>Diseño de la arquitectura de aplicaciones basadas en contenedores y microservicios

*Los microservicios ofrecen grandes ventajas, pero también generan nuevos desafíos enormes. Los patrones de arquitectura de microservicios son los pilares fundamentales a la hora de crear una aplicación basada en microservicios.*

Previamente en esta guía, ha aprendido los conceptos básicos sobre los contenedores y Docker. Esta era la información mínima necesaria para empezar a trabajar con contenedores. Aunque los contenedores son habilitadores y se consideran una gran elección para microservicios, no son obligatorios para una arquitectura de microservicios, y muchos conceptos arquitectónicos de esta sección sobre la arquitectura también se podrían aplicar sin contenedores. A pesar de ello, esta guía se centra en la intersección de ambos debido a la importancia actual de los contenedores.

Las aplicaciones empresariales pueden ser complejas y, a menudo, se componen de varios servicios en lugar de una sola aplicación basada en servicios. En esos casos, debe comprender otros enfoques de arquitectura, como son los microservicios y determinados patrones de diseño guiado por el dominio (DDD), además de conceptos de orquestación de contenedores. Tenga en cuenta que en este capítulo no solo se describen los microservicios en contenedor, sino cualquier aplicación en contenedor.

## <a name="container-design-principles"></a>Principios de diseño de contenedores

En el modelo de contenedor, una instancia de imagen de contenedor representa un único proceso. Al definir una imagen de contenedor como un límite de proceso, puede crear primitivas que se usen para escalar el proceso o para procesarlo por lotes.

Al diseñar una imagen de contenedor, verá una definición [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) en el archivo Dockerfile. Esto define el proceso cuya duración controla la duración del contenedor. Cuando se completa el proceso, finaliza el ciclo de vida del contenedor. Los contenedores pueden representar procesos de ejecución prolongada como servidores web, pero también pueden representar procesos de corta duración, como trabajos por lotes, que anteriormente se implementarían como [WebJobs](https://github.com/Azure/azure-webjobs-sdk/wiki) de Azure.

Si se produce un error en el proceso, el contenedor finaliza y lo sustituye el orquestador. Si el orquestador está configurado para mantener cinco instancias en ejecución y se produce un error en una de ellas, el orquestador creará otra instancia del contenedor para reemplazar al proceso con error. En un trabajo por lotes, el proceso se inicia con parámetros. Cuando el proceso finalice, el trabajo se habrá completado. Más adelante en esta guía se exploran en profundidad los orquestadores.

Es posible que en algún momento le interese que varios procesos se ejecuten en un solo contenedor. En ese caso, dado que solo puede haber un punto de entrada por contenedor, puede ejecutar dentro del contenedor un script que inicie todos los programas que sean necesarios. Por ejemplo, puede usar [Supervisor](http://supervisord.org/) o una herramienta similar para que se encargue de iniciar varios procesos dentro de un único contenedor. Este enfoque no es muy habitual, aunque existan arquitecturas que contengan varios procesos por contenedor.

>[!div class="step-by-step"]
>[Anterior](../net-core-net-framework-containers/official-net-docker-images.md)
>[Siguiente](containerize-monolithic-applications.md)
