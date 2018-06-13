---
title: Propiedad de los datos por microservicio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Propiedad de los datos por microservicio
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: d739cc33dec372f6bd9569c05d034dcd25be8395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577298"
---
# <a name="data-sovereignty-per-microservice"></a>Propiedad de los datos por microservicio

Una regla importante de la arquitectura de microservicios es que cada microservicio debe ser propietario de sus datos de dominio y su lógica. Al igual que una aplicación completa posee su lógica y sus datos, cada microservicio debe poseer su lógica y sus datos en un ciclo de vida autónomo, con implementación independiente por microservicio.

Esto significa que el modelo conceptual del dominio variará entre subsistemas o microservicios. Piense en las aplicaciones empresariales, donde las aplicaciones de administración de las relaciones con el cliente (CRM), los subsistemas de compras transaccionales y los subsistemas de asistencia al cliente llaman cada uno de ellos a datos y atributos de entidades de cliente únicos y usan un contexto enlazado diferente.

Este principio es similar en el [diseño guiado por el dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), donde cada [contexto enlazado](https://martinfowler.com/bliki/BoundedContext.html) o subsistema o servicio autónomo debe ser propietario de su modelo de dominio (datos más lógica y comportamiento). Cada contexto enlazado de DDD se correlaciona con un microservicio de negocios (uno o varios servicios). (En la sección siguiente se ofrece más información sobre el patrón de contexto enlazado).

Por otro lado, el enfoque tradicional (datos monolíticos) usado en muchas aplicaciones es tener una sola base de datos centralizada o solo algunas bases de datos. Suele ser una base de datos SQL normalizada que se usa para toda la aplicación y todos los subsistemas internos, como se muestra en la figura 4-7.

![](./media/image7.png)

**Figura 4-7**. Comparación de propiedad de datos: base de datos monolítica frente a microservicios

El enfoque de la base de datos centralizada en principio parece más sencillo y parece permitir la reutilización de entidades de diferentes subsistemas para que todo sea coherente. Pero la realidad es que se acaban teniendo tablas enormes que sirven a muchos subsistemas distintos e incluyen atributos y columnas que no se necesitan en la mayoría de los casos. Es como intentar usar el mismo mapa físico para actividades tan dispares como hacer una excursión de un par de horas, viajar en coche durante todo un día y aprender geografía.

Una aplicación monolítica con una sola base de datos relacional presenta dos ventajas importantes: las [transacciones ACID](https://en.wikipedia.org/wiki/ACID) y el lenguaje SQL, que funcionan en todas las tablas y los datos relacionados con la aplicación. Este enfoque proporciona una manera sencilla de escribir una consulta que combina datos de varias tablas.

Pero el acceso a los datos es mucho más complejo cuando se migra a una arquitectura de microservicios. Aun cuando las transacciones ACID puedan o deban usarse en un microservicio o contexto enlazado, los datos que pertenecen a cada microservicio son privados de ese microservicio y solo pueden obtenerse a través de su API de microservicio. La encapsulación de los datos garantiza que los microservicios estén acoplados de forma imprecisa y puedan evolucionar independientemente unos de otros. Si varios servicios estuvieran accediendo a los mismos datos, las actualizaciones de esquema exigirían actualizaciones coordinadas de todos los servicios. Esto interrumpiría la autonomía del ciclo de vida del microservicio. Pero las estructuras de datos distribuidas significan que no se puede realizar una única transacción ACID en microservicios. A su vez, esto significa que debe usar la coherencia final cuando un proceso empresarial abarque varios microservicios. Esto es mucho más difícil de implementar que las meras combinaciones SQL; del mismo modo, muchas otras características de base de datos relacional no están disponibles en varios microservicios.

Si vamos aún más allá, los distintos microservicios suelen usar *tipos* diferentes de bases de datos. Las aplicaciones modernas almacenan y procesan distintos tipos de datos, así que una base de datos relacional no siempre es la mejor opción. En algunos casos de uso, una base de datos no SQL, como Azure DocumentDB o MongoDB, podría tener un modelo de datos más adecuado y ofrecer un mejor rendimiento y escalabilidad que una base de datos SQL como SQL Server o Azure SQL Database. En otros casos, una base de datos relacional sigue siendo el mejor enfoque. Por lo tanto, las aplicaciones basadas en microservicios suelen usar una combinación de bases de datos SQL y no SQL, lo que a veces se denomina enfoque de [persistencia políglota](https://martinfowler.com/bliki/PolyglotPersistence.html).

Una arquitectura con particiones de persistencia políglota para el almacenamiento de datos tiene muchas ventajas. Estas incluyen servicios acoplados de forma imprecisa y mejor rendimiento, escalabilidad, costos y manejabilidad. Pero puede presentar algunos desafíos de administración de datos distribuida, como se va a explicar en "[Identificar los límites del modelo de dominio para cada microservicio](#identifying-domain-model-boundaries-for-each-microservice)" más adelante en este capítulo.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>Relación entre microservicios y el patrón de contexto enlazado

El concepto de microservicio deriva del [patrón de contexto enlazado](https://martinfowler.com/bliki/BoundedContext.html) en el [diseño guiado por el dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design). DDD trabaja con modelos grandes al dividirlos en varios contextos enlazados y ser explícito sobre sus límites. Cada contexto enlazado debe tener su propio modelo y base de datos; del mismo modo, cada microservicio es propietario de sus datos relacionados. Además, cada contexto enlazado normalmente tiene su propio [lenguaje ubicuo](https://martinfowler.com/bliki/UbiquitousLanguage.html) para la comunicación entre desarrolladores de software y expertos de dominio.

Esos términos (principalmente entidades de dominio) en el lenguaje ubicuo pueden tener nombres diferentes en distintos contextos enlazados, aun cuando varias entidades de dominio compartan la misma identidad (es decir, el identificador único que se usa para leer la entidad desde el almacenamiento). Por ejemplo, en un contexto enlazado de perfil de usuario, la entidad de dominio User puede compartir identidad con la entidad de dominio Buyer en el contexto enlazado Ordering.

Un microservicio es, por tanto, como un contexto enlazado, pero además especifica que es un servicio distribuido. Se compila como un proceso independiente para cada contexto enlazado y debe usar los protocolos distribuidos indicados anteriormente, como HTTP/HTTPS, WebSockets o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Pero el patrón de contexto enlazado no especifica si el contexto enlazado es un servicio distribuido o si es simplemente un límite lógico (por ejemplo, un subsistema genérico) de una aplicación de implementación monolítica.

Es importante resaltar que la definición de un servicio para cada contexto enlazado es un buen principio. Pero no es necesario restringir el diseño a esto. A veces debe diseñar un contexto enlazado o microservicio de negocios formado por varios servicios físicos. Pero, en última instancia, ambos patrones, contexto enlazado y microservicio, están estrechamente relacionados.

DDD se beneficia de los microservicios al obtener límites reales en forma de microservicios distribuidos. Pero ideas como no compartir el modelo entre microservicios son las que también se quieren en un contexto enlazado.

### <a name="additional-resources"></a>Recursos adicionales

-   **Chris Richardson. Pattern: Database per service (Patrón: base de datos por servicio)**
    [*https://microservices.io/patterns/data/database-per-service.html*](https://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*https://martinfowler.com/bliki/BoundedContext.html*](https://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*https://martinfowler.com/bliki/PolyglotPersistence.html*](https://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini. Strategic Domain Driven Design with Context Mapping (Diseño orientado a dominios estratégicos con asignación de contexto)**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[Previous] (microservices-architecture.md) [Next] (logical-versus-physical-architecture.md)
