---
title: Aplicar enfoques CQRS y CQS en un microservicio DDD en eShopOnContainers
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Aplicar enfoques CQRS y CQS en un microservicio DDD en eShopOnContainers
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: fa26aa86e09f7a5d390336e460fa0272f76e17a4
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805479"
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>Aplicar enfoques CQRS y CQS en un microservicio DDD en eShopOnContainers

El diseño del microservicio Ordering de la aplicación de referencia eShopOnContainers se basa en los principios CQRS. Pero usa el enfoque más sencillo, que consiste simplemente en separar las consultas de los comandos y usar la misma base de datos para ambas acciones.

La esencia de esos patrones y el punto importante es que las consultas son idempotentes: el estado del sistema no cambia independientemente de las veces que se consulte a ese sistema. Incluso se podría usar un modelo de datos de "lectura" distinto al modelo de dominio de "escritura" de lógica transaccional, aunque los microservicios Ordering usen la misma base de datos. Por lo tanto, se trata de un enfoque CQRS simplificado.

Por otro lado, los comandos, que producen transacciones y actualizaciones de datos, cambian el estado del sistema. Debe tener cuidado con los comandos cuando trabaje con la complejidad y las reglas de negocio cambiantes. Ahí es donde se prefieren aplicar técnicas DDD para tener un sistema mejor modelado.

Los patrones DDD presentados en esta guía no se deben aplicar de forma general, ya que establecen restricciones en el diseño. Esas restricciones proporcionan ventajas como una mayor calidad con el tiempo, especialmente en comandos y otro código que modifican el estado del sistema. Pero las restricciones agregan complejidad con menos ventajas para leer y consultar datos.

Un patrón de este tipo es el patrón Aggregate, que se analiza en más detalle en secciones posteriores. En pocas palabras, en el patrón Aggregate, muchos objetos de dominio se tratan como una sola unidad como resultado de su relación en el dominio. Es posible que no siempre obtenga ventajas de este patrón en las consultas; puede aumentar la complejidad de la lógica de consulta. En las consultas de solo lectura no se obtienen las ventajas de tratar varios objetos como un único agregado. Solo se obtiene la complejidad.

Como se muestra en la figura 9-2, esta guía sugiere usar patrones DDD solo en el área transaccional o de actualizaciones del microservicio (es decir, como se desencadena con comandos). Las consultas pueden seguir un enfoque más simple y deben separarse de los comandos, según un enfoque CQRS.

Para implementar el "lado de consultas", puede elegir entre varios enfoques, desde un ORM completo como EF Core, proyecciones de AutoMapper, procedimientos almacenados, vistas, vistas materializadas o un micro ORM.

En esta guía y en eShopOnContainers (específicamente el microservicio Ordering), se ha optado por implementar consultas directas mediante un micro ORM como [Dapper](https://github.com/StackExchange/dapper-dot-net). Esto permite implementar cualquier consulta basada en instrucciones SQL para obtener el mejor rendimiento, gracias a un marco de trabajo ligero con muy poca sobrecarga.

Observe que al usar este enfoque, las actualizaciones del modelo que afectan a la conservación de las entidades en una base de datos SQL también necesitan actualizaciones independientes de las consultas SQL usadas por Dapper o cualquier otro enfoque independiente (no EF) para las consultas.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>Los patrones CQRS y DDD no son arquitecturas de nivel superior

Es importante entender que CQRS y la mayoría de los patrones DDD (como las capas DDD o un modelo de dominio con agregados) no son estilos arquitectónicos, sino simplemente patrones de arquitectura. Los microservicios, SOA y la arquitectura orientada a eventos (EDA) son ejemplos de estilos de arquitectura. Describen un sistema de muchos componentes, por ejemplo, muchos microservicios. Los patrones CQRS y DDD describen algo dentro de un único sistema o componente; en este caso, algo dentro de un microservicio.

Los diferentes contextos enlazados usan distintos patrones. Tienen responsabilidades diferentes y eso da lugar a distintas soluciones. Merece la pena resaltar que la aplicación del mismo patrón en todos los sitios da lugar a errores. No use patrones CQRS y DDD en cualquier lugar. Muchos subsistemas, contextos enlazados o microservicios son más sencillos y se pueden implementar con más facilidad mediante servicios CRUD simples o con otro enfoque.

Solo hay una arquitectura de aplicación: la arquitectura del sistema o la aplicación de un extremo a otro que se está diseñando (por ejemplo, la arquitectura de microservicios). Pero el diseño de cada contexto enlazado o microservicio de esa aplicación refleja sus propias compensaciones y decisiones de diseño internas en un nivel de patrones de arquitectura. No intente aplicar los mismos patrones arquitectónicos, como CQRS o DDD, en cualquier lugar.

####  <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young. CQS vs. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young. CQRS Documents**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf) (Documentos de CQRS)

-   **Greg Young. CQRS, Task Based UIs and Event Sourcing (CQRS, interfaces de usuario basadas en tareas y origen de eventos)**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **Udi Dahan. Clarified CQRS (CQRS aclarado)**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Event-Sourcing (ES) (Orígenes de eventos)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[Previous] (apply-simplified-microservice-cqrs-ddd-patterns.md) [Next] (cqrs-microservice-reads.md)
