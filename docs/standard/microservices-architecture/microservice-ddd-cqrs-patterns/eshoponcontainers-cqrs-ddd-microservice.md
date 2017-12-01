---
title: Aplicar CQRS y CQS enfoques en un microservicio DDD en eShopOnContainers
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Aplicar CQRS y CQS enfoques en un microservicio DDD en eShopOnContainers
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Aplicar CQRS y CQS enfoques en un microservicio DDD en eShopOnContainers

El diseño de la ordenación microservicio en la aplicación de referencia de eShopOnContainers se basa en los principios CQRS. Sin embargo, utiliza el enfoque más sencillo, que simplemente es separar las consultas de los comandos y el uso de la misma base de datos para ambas acciones.

La esencia de esos patrones y en este caso, el punto importante es que las consultas son idempotentes: independientemente de cuántas veces se consulta un sistema, el estado de dicho sistema no cambiará incluso podría utilizar un modelo de datos de "lectura" diferente que la lógica transaccional "escritura" modelo de dominio, aunque la ordenación microservicios está usando la misma base de datos. Por lo tanto, se trata de un enfoque simplificado de CQRS.

Por otro lado, comandos, que se activan las transacciones y las actualizaciones de datos, cambian el estado del sistema. Con los comandos, debe tener cuidado cuando tienen que ver con la complejidad y reglas de negocio cambiantes. Esto es donde desea aplicar técnicas DDD para tener un mejor sistema modelado.

No se deben aplicar universalmente los patrones DDD presentados en esta guía. Presentan restricciones en el diseño. Las restricciones proporcionan beneficios como mayor calidad con el tiempo, especialmente en los comandos y otro código que modifica el estado del sistema. Sin embargo, las restricciones agregan complejidad con menos ventajas para leer y consultar datos.

Un patrón de este tipo es el patrón de agregado, que se examine más en secciones posteriores. En pocas palabras, en el patrón de agregado, tratar muchos objetos de dominio como una sola unidad como resultado de la relación en el dominio. Podría no siempre obtendrá ventajas de este patrón en las consultas; puede aumentar la complejidad de la lógica de la consulta. Para las consultas de solo lectura, no se obtienen las ventajas de tratar varios objetos como un único agregado. Solo se obtiene la complejidad.

Como se muestra en la figura 9-2, esta guía sugiere utilizando patrones DDD sólo en el área de transaccional, actualizaciones de su microservicio (es decir, tal y como se desencadena con comandos). Las consultas pueden seguir un enfoque más simple y deben estar separadas de comandos, un enfoque de CQRS.

Para implementar el "lado de las consultas", puede elegir entre muchos enfoques, desde su ORM completas como EF núcleo AutoMapper proyecciones, procedimientos almacenados, vistas, vistas materializadas o un micro ORM.

En esta guía y en eShopOnContainers (específicamente la ordenación microservicio), hemos optado por implementar consultas rectas mediante un micro ORM como [Dapper](https://github.com/StackExchange/dapper-dot-net). Esto le permite implementar cualquier consulta de acuerdo con las instrucciones de SQL para obtener el mejor rendimiento, gracias a un marco claro con muy poca sobrecarga.

Observe que cuando se usa este enfoque, las actualizaciones al modelo que afectan a cómo se conservan las entidades a una base de datos SQL también necesitan actualizaciones independientes para consultas SQL usadas por Dapper o los otros métodos (no-EF) independientes a las consultas.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>Los modelos CQRS y DDD no son arquitecturas de nivel superior

Es importante entender que CQRS y los patrones DDD mayoría (similares a las capas DDD o un modelo de dominio con agregados) no son estilos arquitectónicos, sino solo los patrones de arquitectura. Microservicios, SOA y arquitectura orientada a eventos (EDA) son ejemplos de estilos de arquitectura. Describen un sistema de muchos componentes, por ejemplo, muchos microservicios. Patrones de CQRS y DDD describen algo dentro de un único sistema o un componente; en este caso, algo dentro de un microservicio.

Diferentes contextos limitado (BCs) utilizarán distintos patrones. Que tienen responsabilidades diferentes, y que conduce a diferentes soluciones. Merece la pena resaltar forzar el mismo patrón que provoca errores. No utilice patrones CQRS y DDD en cualquier lugar. Muchos subsistemas, BCs o microservicios son más sencillas y se pueden implementar más fácilmente mediante servicios simples de CRUD o con otro método.

Hay arquitectura solo una aplicación: la arquitectura de la aplicación de sistema o to-end está diseñando (por ejemplo, la arquitectura de microservicios). Sin embargo, el diseño de cada contexto limitado o microservicio dentro de esa aplicación refleja su propio compensaciones y las decisiones de diseño interno en un nivel de patrones de arquitectura. No intente aplicar los mismos patrones arquitectónicos como CQRS o DDD en cualquier lugar.

####  <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young. CQS vs. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young. Documentos CQRS**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young. CQRS, la tarea basado en interfaces de usuario y el origen de evento**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **UDI Dahan. Se ha aclarado CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **(ES) de origen de evento**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[Anterior] (apply-simplified-microservice-cqrs-ddd-patterns.md) [siguiente] (cqrs-microservicio-reads.md)
