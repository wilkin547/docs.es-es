---
title: Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS
description: Arquitectura de microservicios .NET para aplicaciones .NET en contenedor | Cómo abordar escenarios empresariales complejos donde se aplican patrones DDD y CQRS
ms.date: 10/08/2018
ms.openlocfilehash: 88b105b68307c8587f877bb9ddf370e143d8539b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "73739840"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="29f25-103">Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS</span><span class="sxs-lookup"><span data-stu-id="29f25-103">Tackle Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="29f25-104">*Diseñe un modelo de dominio para cada microservicio o contexto limitado que refleje un conocimiento del ámbito empresarial.*</span><span class="sxs-lookup"><span data-stu-id="29f25-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="29f25-105">Esta sección se centra en microservicios más avanzados que se implementan cuando se deben abordar subsistemas complejos y en microservicios derivados de los conocimientos de expertos en el dominio con reglas de negocios cambiantes.</span><span class="sxs-lookup"><span data-stu-id="29f25-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="29f25-106">Los patrones de arquitectura que se usan en esta sección se basan en los enfoques de diseño guiado por el dominio (DDD) y segregación de responsabilidades de comandos y consultas (CQRS), como se ilustra en la figura 7-1.</span><span class="sxs-lookup"><span data-stu-id="29f25-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 7-1.</span></span>

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagrama en el que se comparan los patrones de arquitectura externos e internos.":::
<span data-ttu-id="29f25-108">Diferencia entre la arquitectura externa: patrones de microservicio, puertas de enlace de API, comunicaciones resistentes, pub/sub, etc., y la arquitectura interna: orientada a datos/CRUD, patrones de DDD, inserción de dependencias, varias bibliotecas, etc.</span><span class="sxs-lookup"><span data-stu-id="29f25-108">Difference between external architecture: microservice patterns, API gateways, resilient communications, pub/sub, etc., and internal architecture: data driven/CRUD, DDD patterns, dependency injection, multiple libraries, etc.</span></span>
:::image-end:::

<span data-ttu-id="29f25-109">**Figura 7-1**.</span><span class="sxs-lookup"><span data-stu-id="29f25-109">**Figure 7-1**.</span></span> <span data-ttu-id="29f25-110">Arquitectura de microservicios externa frente a patrones de arquitectura interna para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="29f25-110">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="29f25-111">Pero la mayoría de las técnicas para microservicios orientados a datos, (por ejemplo, cómo implementar un servicio ASP.NET Core Web API o cómo exponer metadatos de Swagger con Swashbuckle o NSwag) también son aplicables a los microservicios más avanzados que se implementan internamente con patrones DDD.</span><span class="sxs-lookup"><span data-stu-id="29f25-111">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle or NSwag, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="29f25-112">Esta sección es una ampliación de las secciones anteriores, ya que la mayoría de las prácticas explicadas anteriormente también se aplican aquí o a cualquier tipo de microservicio.</span><span class="sxs-lookup"><span data-stu-id="29f25-112">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="29f25-113">Esta sección proporciona en primer lugar detalles sobre los patrones CQRS simplificados que se usan en la aplicación de referencia eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="29f25-113">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="29f25-114">Más adelante, obtendrá información general sobre las técnicas DDD que le permiten encontrar patrones comunes que puede volver a usar en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="29f25-114">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="29f25-115">DDD es un tema amplio con numerosos recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="29f25-115">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="29f25-116">Puede empezar con libros como [Domain-Driven Design](https://domainlanguage.com/ddd/) (Diseño guiado por el dominio), de Eric Evans, y materiales adicionales de Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard y muchos otros expertos en DDD y CQRS.</span><span class="sxs-lookup"><span data-stu-id="29f25-116">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="29f25-117">Pero, sobre todo, para aprender a aplicar técnicas DDD, debe recurrir a conversaciones, pizarras interactivas y sesiones de modelado de dominio con expertos de su ámbito empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="29f25-117">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="29f25-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="29f25-118">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="29f25-119">DDD (diseño guiado por el dominio)</span><span class="sxs-lookup"><span data-stu-id="29f25-119">DDD (Domain-Driven Design)</span></span>

- <span data-ttu-id="29f25-120">**Eric Evans. Domain Language (Lenguaje de dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-120">**Eric Evans. Domain Language** </span></span>\
  <https://domainlanguage.com/>

- <span data-ttu-id="29f25-121">**Martin Fowler. Domain-Driven Design (Diseño orientado al dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-121">**Martin Fowler. Domain-Driven Design** </span></span>\
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- <span data-ttu-id="29f25-122">**Jimmy Bogard. Strengthening your domain: a primer (Reforzar el dominio: conceptos básicos)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-122">**Jimmy Bogard. Strengthening your domain: a primer** </span></span>\
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a><span data-ttu-id="29f25-123">Libros sobre DDD</span><span class="sxs-lookup"><span data-stu-id="29f25-123">DDD books</span></span>

- <span data-ttu-id="29f25-124">**Eric Evans. Diseño orientado al dominio: Tackling Complexity in the Heart of Software (Diseño orientado al dominio: abordar la complejidad en el corazón del software)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-124">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="29f25-125">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries (Referencia del diseño orientado al dominio: definiciones y resúmenes de patrones)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-125">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- <span data-ttu-id="29f25-126">**Vaughn Vernon. Implementing Domain-Driven Design (Implementación de un diseño orientado al dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-126">**Vaughn Vernon. Implementing Domain-Driven Design** </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="29f25-127">**Vaughn Vernon. Domain-Driven Design Distilled (Diseño orientado al dominio simplificado)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-127">**Vaughn Vernon. Domain-Driven Design Distilled** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- <span data-ttu-id="29f25-128">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns (Aplicación de patrones y diseños orientados al dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-128">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns** </span></span>\
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- <span data-ttu-id="29f25-129">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET (Arquitectura orientada al dominio en N capas con .NET)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-129">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET** </span></span>\
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- <span data-ttu-id="29f25-130">**Abel Avram y Floyd Marinescu. Domain-Driven Design Quickly (Diseño orientado al dominio rápido)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-130">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- <span data-ttu-id="29f25-131">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design (Patrones, principios y procedimientos del diseño orientado al dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-131">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design** </span></span>\
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a><span data-ttu-id="29f25-132">Aprendizaje de DDD</span><span class="sxs-lookup"><span data-stu-id="29f25-132">DDD training</span></span>

- <span data-ttu-id="29f25-133">**Julie Lerman y Steve Smith. Domain-Driven Design Fundamentals (Fundamentos del diseño orientado al dominio)**  </span><span class="sxs-lookup"><span data-stu-id="29f25-133">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals** </span></span>\
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
><span data-ttu-id="29f25-134">[Anterior](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Siguiente](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="29f25-134">[Previous](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
