---
title: Arquitectura lógica frente a arquitectura física
description: Obtenga más información sobre las diferencias entre arquitecturas físicas y lógicas.
ms.date: 09/20/2018
ms.openlocfilehash: 8d1bfca190eb9b18d46625fa4afdec963eb07054
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834400"
---
# <a name="logical-architecture-versus-physical-architecture"></a>Arquitectura lógica frente a arquitectura física

En este momento, es útil detenerse y analizar la diferencia entre la arquitectura lógica y la arquitectura física, y cómo se aplica al diseño de aplicaciones basadas en microservicios.

Para empezar, la creación de microservicios no requiere el uso de ninguna tecnología específica. Por ejemplo, los contenedores de Docker no son obligatorios para crear una arquitectura basada en microservicios. Esos microservicios también se pueden ejecutar como procesos sin formato. Los microservicios son una arquitectura lógica.

Además, incluso cuando un microservicio podría implementarse físicamente como un único servicio, proceso o contenedor (para simplificar, es el enfoque adoptado en la versión inicial de [eShopOnContainers](https://aka.ms/MicroservicesArchitecture)), esta paridad entre microservicio empresarial y servicio o contenedor físico no es necesaria en todos los casos al compilar una aplicación grande y compleja formada por muchas docenas o incluso cientos de servicios.

Aquí es donde hay una diferencia entre la arquitectura lógica y la arquitectura física de una aplicación. La arquitectura lógica y los límites lógicos de un sistema no se asignan necesariamente uno a uno a la arquitectura física o de implementación. Esto puede suceder, pero a menudo no es así.

Aunque es posible que haya identificado determinados microservicios empresariales o contextos delimitados, esto no significa que la mejor manera de implementarlos sea siempre mediante la creación de un servicio único (como una API web ASP.NET) o un contenedor de Docker único para cada microservicio empresarial. Tener una regla que indique que cada microservicio empresarial debe implementarse mediante un único servicio o contenedor es demasiado rígido.

Por tanto, un microservicio o contexto limitado empresarial es una arquitectura lógica que podría coincidir (o no) con la arquitectura física. Lo importante es que un microservicio o contexto limitado empresarial debe ser autónomo y permitir que el código y el estado se versioneen, implementen y escalen de forma independiente.

Como se muestra en la figura 4-8, el microservicio empresarial de catálogo podría estar compuesto de varios servicios o procesos. Estos podrían ser varios servicios de ASP.NET Web API o cualquier otro tipo de servicio que use HTTP o cualquier otro protocolo. Lo más importante es que los servicios puedan compartir los mismos datos, siempre y cuando estos servicios sean cohesivos con relación al mismo dominio empresarial.

![Diagrama del microservicio empresarial de catálogo con servidores físicos.](./media/logical-versus-physical-architecture/multiple-physical-services.png)

**Figura 4-8**. Microservicio empresarial con varios servicios físicos

Los servicios del ejemplo comparten el mismo modelo de datos porque el servicio Web API tiene como destino los mismos datos que el servicio Search. Por tanto, en la implementación física del microservicio empresarial, esa función se divide de manera que pueda escalar horizontal o verticalmente cada uno de esos servicios internos según sea necesario. Es posible que el servicio Web API normalmente necesite más instancias que el servicio Search, o viceversa.

En resumen, la arquitectura lógica de los microservicios no siempre tiene que coincidir con la arquitectura de implementación física. En esta guía, siempre que se mencione un microservicio, se entiende que es un microservicio empresarial o lógico que se puede asignar a uno o más servicios (físicos). En la mayoría de los casos, se trata de un servicio único, pero puede que sean más.

>[!div class="step-by-step"]
>[Anterior](data-sovereignty-per-microservice.md)
>[Siguiente](distributed-data-management.md)
