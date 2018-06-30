---
title: Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: af67f94b2c56f6a1ec794abbf7d3dad0d78033ec
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105763"
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="9b425-103">Abordar la complejidad empresarial en un microservicio con patrones DDD y CQRS</span><span class="sxs-lookup"><span data-stu-id="9b425-103">Tackling Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="9b425-104">*Diseñe un modelo de dominio para cada microservicio o contexto limitado que refleje un conocimiento del ámbito empresarial.*</span><span class="sxs-lookup"><span data-stu-id="9b425-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="9b425-105">Esta sección se centra en microservicios más avanzados que se implementan cuando se deben abordar subsistemas complejos y en microservicios derivados de los conocimientos de expertos en el dominio con reglas de negocios cambiantes.</span><span class="sxs-lookup"><span data-stu-id="9b425-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="9b425-106">Los patrones de arquitectura que se usan en esta sección se basan en enfoques de diseño guiado por el dominio (DDD) y separación de la responsabilidad de comandos y consultas (CQRS), como se muestra en la figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="9b425-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 9-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="9b425-107">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="9b425-107">**Figure 9-1**.</span></span> <span data-ttu-id="9b425-108">Arquitectura de microservicios externa frente a patrones de arquitectura interna para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="9b425-108">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="9b425-109">Pero la mayoría de las técnicas para microservicios controlados por datos (por ejemplo, cómo implementar un servicio ASP.NET Core Web API o cómo exponer metadatos de Swagger con Swashbuckle) también son aplicables a los microservicios más avanzados que se implementan internamente con patrones DDD.</span><span class="sxs-lookup"><span data-stu-id="9b425-109">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="9b425-110">Esta sección es una ampliación de las secciones anteriores, ya que la mayoría de las prácticas explicadas anteriormente también se aplican aquí o a cualquier tipo de microservicio.</span><span class="sxs-lookup"><span data-stu-id="9b425-110">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="9b425-111">Esta sección proporciona en primer lugar detalles sobre los patrones CQRS simplificados que se usan en la aplicación de referencia eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="9b425-111">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="9b425-112">Más adelante, obtendrá información general sobre las técnicas DDD que le permiten encontrar patrones comunes que puede volver a usar en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9b425-112">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="9b425-113">DDD es un tema amplio con numerosos recursos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9b425-113">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="9b425-114">Puede empezar con libros como [Domain-Driven Design](https://domainlanguage.com/ddd/) (Diseño guiado por el dominio), de Eric Evans, y materiales adicionales de Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard y muchos otros expertos en DDD y CQRS.</span><span class="sxs-lookup"><span data-stu-id="9b425-114">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="9b425-115">Pero, sobre todo, para aprender a aplicar técnicas DDD, debe recurrir a conversaciones, pizarras interactivas y sesiones de modelado de dominio con expertos de su ámbito empresarial específico.</span><span class="sxs-lookup"><span data-stu-id="9b425-115">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="9b425-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9b425-116">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="9b425-117">DDD (diseño guiado por el dominio)</span><span class="sxs-lookup"><span data-stu-id="9b425-117">DDD (Domain-Driven Design)</span></span>

-   <span data-ttu-id="9b425-118">**Eric Evans. Domain Language**
    [*https://domainlanguage.com/*](https://domainlanguage.com/)</span><span class="sxs-lookup"><span data-stu-id="9b425-118">**Eric Evans. Domain Language**
[*https://domainlanguage.com/*](https://domainlanguage.com/)</span></span>

-   <span data-ttu-id="9b425-119">**Martin Fowler. Domain-Driven Design**
    [*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)</span><span class="sxs-lookup"><span data-stu-id="9b425-119">**Martin Fowler. Domain-Driven Design**
[*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)</span></span>

-   <span data-ttu-id="9b425-120">**Jimmy Bogard. Strengthening your domain: a primer**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span><span class="sxs-lookup"><span data-stu-id="9b425-120">**Jimmy Bogard. Strengthening your domain: a primer**
[*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span></span>

##### <a name="ddd-books"></a><span data-ttu-id="9b425-121">Libros sobre DDD</span><span class="sxs-lookup"><span data-stu-id="9b425-121">DDD books</span></span>

-   <span data-ttu-id="9b425-122">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="9b425-122">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
[*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="9b425-123">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span><span class="sxs-lookup"><span data-stu-id="9b425-123">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
[*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span></span>

-   <span data-ttu-id="9b425-124">**Vaughn Vernon. Implementing Domain-Driven Design**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/) (Implementación del diseño controlado por dominios)</span><span class="sxs-lookup"><span data-stu-id="9b425-124">**Vaughn Vernon. Implementing Domain-Driven Design**
[*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="9b425-125">**Vaughn Vernon. Domain-Driven Design Distilled**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span><span class="sxs-lookup"><span data-stu-id="9b425-125">**Vaughn Vernon. Domain-Driven Design Distilled**
[*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span></span>

-   <span data-ttu-id="9b425-126">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span><span class="sxs-lookup"><span data-stu-id="9b425-126">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
[*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span></span>

-   <span data-ttu-id="9b425-127">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span><span class="sxs-lookup"><span data-stu-id="9b425-127">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
[*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span></span>

-   <span data-ttu-id="9b425-128">**Abel Avram y Floyd Marinescu. Domain-Driven Design Quickly**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span><span class="sxs-lookup"><span data-stu-id="9b425-128">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
[*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span></span>

<span data-ttu-id="9b425-129">Aprendizaje de DDD</span><span class="sxs-lookup"><span data-stu-id="9b425-129">DDD training</span></span>

-   <span data-ttu-id="9b425-130">**Julie Lerman y Steve Smith. Domain-Driven Design Fundamentals**
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span><span class="sxs-lookup"><span data-stu-id="9b425-130">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
[*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9b425-131">[Anterior](../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)
[Siguiente](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="9b425-131">[Previous](../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
