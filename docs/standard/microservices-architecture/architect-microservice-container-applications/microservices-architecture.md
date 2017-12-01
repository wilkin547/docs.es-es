---
title: Arquitectura de microservicios
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Arquitectura de Microservicios
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a>Arquitectura de microservicios

Como su nombre indica, una arquitectura de microservicios es un enfoque para la generación de una aplicación de servidor como un conjunto de servicios pequeños. Cada servicio se ejecuta en su propio proceso y se comunica con otros procesos mediante protocolos como HTTP/HTTPS, WebSockets, o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Cada microservicio implementa un dominio específico de end-to-end o una capacidad de negocio dentro de un determinado límite de contexto, y cada una se debe desarrollar de forma autónoma y se podrá implementar de forma independiente. Por último, cada microservicio debe poseer su modelo de datos de dominio relacionadas y la lógica del dominio (soberanía y administración de datos descentralizado) en función de las tecnologías de almacenamiento de datos diferentes (SQL, NoSQL) y lenguajes de programación diferentes.

¿Qué tamaño debe ser un microservicio? Al desarrollar un microservicio, tamaño no debe ser importante. En su lugar, el punto importante que debe crear débilmente acoplados servicios por lo que tendrá la autonomía de desarrollo, implementación y escala, para cada servicio. Por supuesto, al identificar y diseñar microservicios, debe intentar que sean lo más pequeña posible siempre y cuando no tenga demasiadas dependencias directas con otros microservicios. Más importante que el tamaño de la microservicio es su independencia de otros servicios y la cohesión interna debe tener.

¿Por qué una arquitectura de microservicios? En resumen, proporciona agilidad a largo plazo. Microservicios habilita un mejor mantenimiento en sistemas altamente escalable, grandes y complejos, por lo que le permite crear aplicaciones basadas en muchos servicios pueden implementables de forma independiente que presentan los ciclos de vida granular y autónomos.

Como ventaja adicional, microservicios pueden escalar horizontalmente de forma independiente. En lugar de tener una sola aplicación monolítica que se debe escalar como una unidad, en su lugar, puede escalar horizontalmente microservicios específico. De este modo, puede escalar sólo el área funcional que necesita más procesamiento alimentación eléctrica o red de ancho de banda para admitir la demanda, en lugar de otras áreas de la aplicación que no es necesario escalar el escalado. Esto significa ahorros de costo porque necesita menos hardware.

![](./media/image6.png)

**Figura 4-6**. Implementación monolítico frente al enfoque microservicios

Tal y como se muestra en la figura 4-6, el enfoque de microservicios permite modificaciones ágiles y rápido iteración de cada microservicio, ya que puede cambiar áreas específicas y pequeñas de aplicaciones complejas, grandes y escalables.

Diseñar la arquitectura de integración continua de las aplicaciones específicas basadas en microservicios habilita y prácticas de la entrega continua. También acelera la entrega de nuevas funciones en la aplicación. Composición específica de las aplicaciones también le permite ejecutar y probar microservicios en aislamiento y les evolucionar de forma autónoma manteniendo contratos claros entre ellos. Siempre y cuando no cambie las interfaces o contratos, puede cambiar la implementación interna de cualquier microservicio o agregar nuevas funciones sin que ello interrumpa otros microservicios.

Éstos son aspectos importantes para habilitar el éxito de pasar a producción con un sistema basado en microservicios:

-   Comprobaciones de estado y la supervisión de los servicios y la infraestructura.

-   Infraestructura escalable para los servicios (es decir, en la nube y orchestrators).

-   Diseño de seguridad e implementación en varios niveles: autenticación, autorización, administración de secretos, una comunicación segura, etcetera.

-   Entrega rápido de aplicaciones, normalmente con los distintos equipos que centrarse en microservicios diferentes.

-   Infraestructura y las prácticas de DevOps y CI/CD.

De estos, sólo las tres primeras cubiertas o introducidas en esta guía. Los dos últimos puntos, que están relacionadas con el ciclo de vida de aplicación, se tratan en adicionales [en contenedores Docker Application Lifecycle con Microsoft Platform y herramientas](https://aka.ms/dockerlifecycleebook) libros electrónicos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Mark Russinovich. Microservicios: Una revolución de aplicación con la tecnología de la nube**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)

-   **Martin Fowler. Microservicios**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)

-   **Martin Fowler. Requisitos previos de Microservicio**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)

-   **Jimmy Nilsson. Fragmentar Cloud Computing**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)

-   **Cesar de la Torre. En contenedores Docker ciclo de vida de aplicación con Microsoft Platform y herramientas** (libro electrónico descargable) [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[Anterior] (service-oriented-architecture.md) [siguiente] (datos-soberanía-por-microservice.md)
