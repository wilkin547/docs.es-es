---
title: "Arquitectura lógica frente a la arquitectura física"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Arquitectura lógica frente a la arquitectura física"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 635774a8fcd0cf1c0ede6a73c604071f538a37fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a>Arquitectura lógica frente a la arquitectura física

Es útil en este momento detener y analizar la diferencia entre la arquitectura lógica y la arquitectura física y cómo se aplica el diseño de aplicaciones basadas en microservicio.

Para empezar, generar microservicios no requiere el uso de cualquier tecnología específica. Por ejemplo, los contenedores de Docker no son obligatorios para crear una arquitectura basada en microservicio. También se pudieron ejecutar esos microservicios como procesos sin formato. Microservicios es una arquitectura lógica.

Además, incluso cuando un microservicio podría implementarse físicamente como un servicio único, un proceso o un contenedor (para simplificar, que es el enfoque adoptado en la versión inicial de [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), esta paridad entre microservicio de negocios y servicio físico o un contenedor no es necesario necesariamente en todos los casos al compilar una aplicación grande y compleja formada por muchas docenas o incluso cientos de servicios.

Aquí es donde hay una diferencia entre la arquitectura lógica y la arquitectura física de una aplicación. La arquitectura lógica y los límites lógicos de un sistema no necesariamente se asignan uno a uno con la arquitectura física o implementación. Esto puede suceder, pero a menudo no es así.

Aunque podría haya identificado determinados microservicios de negocios o contextos limitado, no significa que siempre es la mejor manera de implementarlos mediante la creación de una única dirección IP (por ejemplo, una API Web de ASP.NET) o contenedor Docker único para cada microservicio de negocios. Tener una regla que indica que cada microservicio de negocios debe implementarse mediante un único servicio o contenedor es demasiado rígido.

Por lo tanto, un negocio microservicio o contexto limitado es una arquitectura lógica que podría coincidir (o no) con la arquitectura física. Lo importante es que un negocio microservicio o contexto limitado debe ser autónomo proporcionando código y estado de forma independiente versiones, implementar y escalar.

Como se muestra en la figura 4-8, el microservicio de negocios de catálogo podría estar compuesta de varios servicios o procesos. Estas podrían ser varios servicios de ASP.NET Web API o cualquier otro tipo de servicios mediante HTTP o cualquier otro protocolo. Lo que es más importante, los servicios pudieron compartir los mismos datos, siempre y cuando estos servicios son coherente en relación con el mismo dominio de negocio.

![](./media/image8.png)

**Figura 4-8**. Microservicio de negocios con varios servicios físicos

Los servicios en el ejemplo comparten el mismo modelo de datos porque el servicio de API Web tiene como destino los mismos datos que el servicio de búsqueda. Por lo tanto, en la implementación física de la microservicio de negocio, se dividen esa funcionalidad de manera que pueda escalar cada uno de esos servicios internos hacia arriba o hacia abajo según sea necesario. Quizás el servicio de API Web normalmente requiere más instancias de que el servicio de búsqueda, o viceversa.)

En resumen, la arquitectura lógica de microservicios no siempre tiene que coincidan con la arquitectura de implementación física. En esta guía, siempre que se mencione un microservicio, se entiende una empresa o microservicio lógico que puede asignar a uno o más servicios. En la mayoría de los casos, se trata de un servicio único, pero puede que sea más.


>[!div class="step-by-step"]
[Anterior] (datos-soberanía-por-microservice.md) [siguiente] (distribuidas de datos-management.md)
