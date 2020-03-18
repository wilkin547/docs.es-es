---
title: Diseñar el nivel de aplicación de microservicios y la API web
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Una breve mención de los principios SOLID para diseñar el nivel de aplicación.
ms.date: 10/08/2018
ms.openlocfilehash: 3c3b9f74e76e01deafa1f97de5d3250d57716014
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68676522"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="4c0be-103">Diseño del nivel de aplicación de microservicios y la API web</span><span class="sxs-lookup"><span data-stu-id="4c0be-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="4c0be-104">Uso de principios SOLID e inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="4c0be-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="4c0be-105">Los principios SOLID son técnicas fundamentales para utilizar en cualquier aplicación moderna y crítica, como para el desarrollo de un microservicio con patrones DDD.</span><span class="sxs-lookup"><span data-stu-id="4c0be-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="4c0be-106">En inglés, SOLID representa un acrónimo que agrupa cinco principios fundamentales:</span><span class="sxs-lookup"><span data-stu-id="4c0be-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="4c0be-107">Principio de responsabilidad única</span><span class="sxs-lookup"><span data-stu-id="4c0be-107">Single Responsibility principle</span></span>

- <span data-ttu-id="4c0be-108">Principio de abierto y cerrado</span><span class="sxs-lookup"><span data-stu-id="4c0be-108">Open/closed principle</span></span>

- <span data-ttu-id="4c0be-109">Principio de sustitución de Liskov</span><span class="sxs-lookup"><span data-stu-id="4c0be-109">Liskov substitution principle</span></span>

- <span data-ttu-id="4c0be-110">Principio de segregación de interfaces</span><span class="sxs-lookup"><span data-stu-id="4c0be-110">Interface Segregation principle</span></span>

- <span data-ttu-id="4c0be-111">Principio de inversión de dependencias</span><span class="sxs-lookup"><span data-stu-id="4c0be-111">Dependency Inversion principle</span></span>

<span data-ttu-id="4c0be-112">SOLID hace referencia a la forma de diseñar los niveles internos de una aplicación o de un microservicio, así como a separar las dependencias entre ellas.</span><span class="sxs-lookup"><span data-stu-id="4c0be-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="4c0be-113">No está relacionado con el dominio, sino con el diseño técnico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c0be-113">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="4c0be-114">El principio final, el de inversión de dependencias, le permite desacoplar el nivel de infraestructura del resto de niveles, lo que permite una mejor implementación desacoplada de los niveles de DDD.</span><span class="sxs-lookup"><span data-stu-id="4c0be-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="4c0be-115">La inserción de dependencias (DI) es una forma de implementar el principio de inversión de dependencias.</span><span class="sxs-lookup"><span data-stu-id="4c0be-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="4c0be-116">Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="4c0be-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="4c0be-117">En lugar de crear directamente instancias de colaboradores o de usar referencias estáticas (es decir, usar new...), los objetos que una clase necesita para llevar a cabo sus acciones se proporcionan a la clase (o se "insertan" en ella).</span><span class="sxs-lookup"><span data-stu-id="4c0be-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="4c0be-118">A menudo, las clases declaran sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas.</span><span class="sxs-lookup"><span data-stu-id="4c0be-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="4c0be-119">Normalmente, la inserción de dependencias se basa en determinados contenedores de Inversión de control (IoC).</span><span class="sxs-lookup"><span data-stu-id="4c0be-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="4c0be-120">ASP.NET Core proporciona un sencillo contenedor de IoC integrado. Aun así, usted puede usar el contenedor de IoC que prefiera, como Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="4c0be-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="4c0be-121">Siguiendo los principios SOLID, las clases tenderán naturalmente a ser pequeñas, a estar factorizadas correctamente y a poder probarse fácilmente.</span><span class="sxs-lookup"><span data-stu-id="4c0be-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="4c0be-122">Pero, ¿cómo puede saber si se van a insertar demasiadas dependencias en sus clases?</span><span class="sxs-lookup"><span data-stu-id="4c0be-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="4c0be-123">Si usa la inversión de dependencias a través del constructor, le resultará fácil saberlo con solo mirar el número de parámetros de su constructor.</span><span class="sxs-lookup"><span data-stu-id="4c0be-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="4c0be-124">Si hay demasiadas dependencias, esto suele ser una señal (una [intuición de código](https://deviq.com/code-smells/)) de que su clase está intentando hacer demasiado y de que probablemente esté infringiendo el principio de responsabilidad única.</span><span class="sxs-lookup"><span data-stu-id="4c0be-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="4c0be-125">Necesitaríamos otra guía para tratar SOLID con detalle.</span><span class="sxs-lookup"><span data-stu-id="4c0be-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="4c0be-126">Para esta guía solo necesita tener unos conocimientos mínimos de estos temas.</span><span class="sxs-lookup"><span data-stu-id="4c0be-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="4c0be-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4c0be-127">Additional resources</span></span>

- <span data-ttu-id="4c0be-128">**SOLID: SOLID: principios fundamentales de OOP** </span><span class="sxs-lookup"><span data-stu-id="4c0be-128">**SOLID: Fundamental OOP Principles** </span></span>\
  <https://deviq.com/solid/>

- <span data-ttu-id="4c0be-129">**Contenedores de Inversión de control y el patrón de inserción de dependencias** </span><span class="sxs-lookup"><span data-stu-id="4c0be-129">**Inversion of Control Containers and the Dependency Injection pattern** </span></span>\
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="4c0be-130">**Steve Smith. New es como pegamento** </span><span class="sxs-lookup"><span data-stu-id="4c0be-130">**Steve Smith. New is Glue** </span></span>\
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="4c0be-131">[Anterior](nosql-database-persistence-infrastructure.md)
> [Siguiente](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="4c0be-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
