---
title: Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS
description: Arquitectura de microservicios .NET para aplicaciones .NET en contenedor | Cómo abordar escenarios empresariales complejos donde se aplican patrones DDD y CQRS
ms.date: 10/08/2018
ms.openlocfilehash: 88b105b68307c8587f877bb9ddf370e143d8539b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73739840"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS

*Diseñe un modelo de dominio para cada microservicio o contexto limitado que refleje un conocimiento del ámbito empresarial.*

Esta sección se centra en microservicios más avanzados que se implementan cuando se deben abordar subsistemas complejos y en microservicios derivados de los conocimientos de expertos en el dominio con reglas de negocios cambiantes. Los patrones de arquitectura que se usan en esta sección se basan en los enfoques de diseño guiado por el dominio (DDD) y segregación de responsabilidades de comandos y consultas (CQRS), como se ilustra en la figura 7-1.

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagrama en el que se comparan los patrones de arquitectura externos e internos.":::
Diferencia entre la arquitectura externa: patrones de microservicio, puertas de enlace de API, comunicaciones resistentes, pub/sub, etc., y la arquitectura interna: orientada a datos/CRUD, patrones de DDD, inserción de dependencias, varias bibliotecas, etc.
:::image-end:::

**Figura 7-1**. Arquitectura de microservicios externa frente a patrones de arquitectura interna para cada microservicio.

Pero la mayoría de las técnicas para microservicios orientados a datos, (por ejemplo, cómo implementar un servicio ASP.NET Core Web API o cómo exponer metadatos de Swagger con Swashbuckle o NSwag) también son aplicables a los microservicios más avanzados que se implementan internamente con patrones DDD. Esta sección es una ampliación de las secciones anteriores, ya que la mayoría de las prácticas explicadas anteriormente también se aplican aquí o a cualquier tipo de microservicio.

Esta sección proporciona en primer lugar detalles sobre los patrones CQRS simplificados que se usan en la aplicación de referencia eShopOnContainers. Más adelante, obtendrá información general sobre las técnicas DDD que le permiten encontrar patrones comunes que puede volver a usar en sus aplicaciones.

DDD es un tema amplio con numerosos recursos para obtener más información. Puede empezar con libros como [Domain-Driven Design](https://domainlanguage.com/ddd/) (Diseño guiado por el dominio), de Eric Evans, y materiales adicionales de Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard y muchos otros expertos en DDD y CQRS. Pero, sobre todo, para aprender a aplicar técnicas DDD, debe recurrir a conversaciones, pizarras interactivas y sesiones de modelado de dominio con expertos de su ámbito empresarial específico.

#### <a name="additional-resources"></a>Recursos adicionales

##### <a name="ddd-domain-driven-design"></a>DDD (diseño guiado por el dominio)

- **Eric Evans. Domain Language (Lenguaje de dominio)**  \
  <https://domainlanguage.com/>

- **Martin Fowler. Domain-Driven Design (Diseño orientado al dominio)**  \
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- **Jimmy Bogard. Strengthening your domain: a primer (Reforzar el dominio: conceptos básicos)**  \
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a>Libros sobre DDD

- **Eric Evans. Diseño orientado al dominio: Tackling Complexity in the Heart of Software (Diseño orientado al dominio: abordar la complejidad en el corazón del software)**  \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries (Referencia del diseño orientado al dominio: definiciones y resúmenes de patrones)**  \
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- **Vaughn Vernon. Implementing Domain-Driven Design (Implementación de un diseño orientado al dominio)**  \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Vaughn Vernon. Domain-Driven Design Distilled (Diseño orientado al dominio simplificado)**  \
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- **Jimmy Nilsson. Applying Domain-Driven Design and Patterns (Aplicación de patrones y diseños orientados al dominio)**  \
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- **Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET (Arquitectura orientada al dominio en N capas con .NET)**  \
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- **Abel Avram y Floyd Marinescu. Domain-Driven Design Quickly (Diseño orientado al dominio rápido)**  \
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- **Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design (Patrones, principios y procedimientos del diseño orientado al dominio)**  \
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a>Aprendizaje de DDD

- **Julie Lerman y Steve Smith. Domain-Driven Design Fundamentals (Fundamentos del diseño orientado al dominio)**  \
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
>[Anterior](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Siguiente](apply-simplified-microservice-cqrs-ddd-patterns.md)
