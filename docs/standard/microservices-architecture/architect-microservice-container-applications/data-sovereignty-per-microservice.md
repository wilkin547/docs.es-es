---
title: "Soberanía de datos por microservicio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Soberanía de datos por microservicio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c51daae04215cfa6f5b5b8d2158a8ed1a8949652
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="data-sovereignty-per-microservice"></a>Soberanía de datos por microservicio

Una regla para la arquitectura de microservicios importante es que cada microservicio debe ser propietaria de sus datos de dominio y la lógica. Igual que una aplicación completa posee su lógica y los datos, por lo que debe ser propietario cada microservicio su lógica y los datos en un ciclo de vida autónomo, con la implementación independiente por microservicio.

Esto significa que el modelo conceptual del dominio se diferenciarán entre subsistemas o microservicios. Considere la posibilidad de aplicaciones de la empresa que relación administración cliente (CRM), aplicaciones, transaccionales adquieran los subsistemas y los subsistemas de soporte al cliente cada llamada en datos y atributos de la entidad de cliente único, y donde cada uno emplea otro Contexto enlazado (BC).

Este principio es similar en [diseño basado en dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), donde cada [contexto limitado](https://martinfowler.com/bliki/BoundedContext.html) o subsistema autónomo o servicio debe ser propietaria de su modelo de dominio (datos más lógica y comportamiento). Cada contexto limitado de DDD se correlaciona con un negocio microservicio (uno o varios servicios). (Se expanden en este punto sobre el patrón de contexto limitado en la sección siguiente).

Por otro lado, el enfoque tradicional (datos monolítico) usado en muchas aplicaciones es que una sola base de datos centralizada o unas pocas bases de datos. Esto suele ser una base de datos SQL normalizado que se usa para toda la aplicación y todas sus subsistemas internos, tal como se muestra en la figura 4-7.

![](./media/image7.png)

**Figura 4-7**. Comparación de soberanía de datos: base de datos monolítico frente a microservicios

El enfoque de la base de datos centralizada inicialmente es más sencillo y parece permitir la reutilización de las entidades de diferentes subsistemas para realizar todo coherente. Pero la realidad es que terminará con tablas muy grandes que sirven de muchos distintos subsistemas y que incluyen atributos y las columnas que no son necesarios en la mayoría de los casos. es como intentar usar la misma asignación física para excursionismo una pista corta, realizar un viaje de automóvil de día de duración y aprendizaje geography.

Una aplicación normalmente de una base de datos relacional único monolítica presenta dos ventajas importantes: [transacciones ACID](https://en.wikipedia.org/wiki/ACID) y el lenguaje SQL, ambos trabajar a través de todas las tablas y los datos relacionados con la aplicación. Este enfoque proporciona una manera de escribir una consulta que combina los datos de varias tablas con facilidad.

Sin embargo, el acceso a datos es mucho más compleja cuando se mueve a una arquitectura de microservicios. Pero incluso cuando las transacciones ACID pueden o deben utilizarse dentro de un microservicio o contexto limitado, los datos que pertenecen a cada microservicio es privados para ese microservicio y solo pueden obtenerse a través de su API de microservicio. Encapsula los datos, se garantiza que el microservicios están acopladas y pueden evolucionar independientemente unas de otras. Si varios servicios se obtiene acceso a los mismos datos, las actualizaciones del esquema necesitaría coordina las actualizaciones a todos los servicios. Esto interrumpiría la autonomía de ciclo de vida de microservicio. Pero las estructuras de datos distribuidos significan que no se puede realizar una única transacción ACID en microservicios. A su vez, esto significa que debe utilizar coherencia definitiva cuando un proceso empresarial abarque varios microservicios. Esto es mucho más difícil implementar que simple combinaciones de SQL; de forma similar, muchas otras características de base de datos relacional no están disponibles a través de varios microservicios.

Va aún más, microservicios diferentes a menudo usan distintos *tipos* de bases de datos. Almacén de aplicaciones modernas y proceso diversos tipos de datos y una base de datos relacional no siempre es la mejor opción. En algunos casos de uso, una base de datos NoSQL, como documentos de Azure o MongoDB podría tener un modelo de datos más cómodo y ofrecen un mejor rendimiento y la escalabilidad de una base de datos SQL como SQL Server o base de datos de SQL Azure. En otros casos, una base de datos relacional sigue siendo el mejor método. Por lo tanto, las aplicaciones basadas en microservicios suele utilizan una combinación de bases de datos SQL y NoSQL, que a veces se denomina la [polyglot persistencia](http://martinfowler.com/bliki/PolyglotPersistence.html) enfoque.

Una arquitectura con particiones, polyglot persistentes para el almacenamiento de datos tiene muchas ventajas. Estos incluyen servicios de acoplamiento flexible y un mejor rendimiento, escalabilidad, costos y facilidad de uso. Sin embargo, se pueden introducir algunos desafíos de administración de datos distribuidos, tal y como se explicará en "[identifica los límites del modelo de dominio](#identifying-domain-model-boundaries-for-each-microservice)" más adelante en este capítulo.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>La relación entre microservicios y el patrón de contexto limitado

El concepto de microservicio se deriva de la [patrón contexto limitado (BC)](http://martinfowler.com/bliki/BoundedContext.html) en [diseño basado en dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design). DDD trabaja con modelos grandes clasificándolos en varios BCs y sean explícitos sobre sus límites. Cada BC debe tener su propio modelo y la base de datos; del mismo modo, cada microservicio posee los datos relacionados. Además, cada BC normalmente tiene su propio [lenguaje ubicuo](http://martinfowler.com/bliki/UbiquitousLanguage.html) para la comunicación entre los desarrolladores de software y los expertos de dominio.

Dichos términos (principalmente entidades de dominio) en el lenguaje ubicuo pueden tener nombres diferentes en diferentes contextos limitado, entidades de dominio aunque diferentes comparten la misma identidad (es decir, el identificador único que se utiliza para leer la entidad de almacenamiento). Por ejemplo, en un contexto limitado de perfil de usuario, la entidad de dominio de usuario puede compartir identidad con la entidad de dominio de comprador en el contexto limitado ordenación.

Un microservicio es, por tanto, al igual que un contexto limitado, pero también especifica que es un servicio distribuido. Se compila como un proceso independiente para cada contexto limitado y debe utilizar los protocolos distribuidos se ha indicado anteriormente, como HTTP/HTTPS, WebSockets, o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). El patrón de contexto limitado, sin embargo, no especifica si el contexto limitado es un servicio distribuido o si es simplemente un límite lógico (por ejemplo, un subsistema genérico) dentro de una aplicación de implementación monolítico.

Es importante resaltar que la definición de un servicio para cada contexto limitado es un buen lugar para comenzar. Pero no es necesario restringir su diseño a él. A veces, debe diseñar un contexto limitado o business microservicio formada por varios servicios físicos. Pero en última instancia, ambos patrones: contexto limitado y microservicio: están estrechamente relacionados.

DDD se beneficia de microservicios obteniendo límites reales en forma de microservicios distribuida. Pero ideas como el uso no compartido el modelo entre microservicios son las que también desea en un contexto limitado.

### <a name="additional-resources"></a>Recursos adicionales

-   **Chris Richardson. Patrón: La base de datos por cada servicio**
    [*http://microservices.io/patterns/data/database-per-service.html*](http://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*http://martinfowler.com/bliki/BoundedContext.html*](http://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*http://martinfowler.com/bliki/PolyglotPersistence.html*](http://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini. Dominio estratégico controlada por diseño con la asignación de contexto**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[Anterior] (microservicios-architecture.md) [siguiente] (lógico-frente a-física-architecture.md)
