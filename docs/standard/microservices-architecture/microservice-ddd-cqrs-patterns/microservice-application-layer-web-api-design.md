---
title: Diseñar el nivel de aplicación de microservicios y la API web
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Diseñar el nivel de aplicación de microservicios y la API web
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d623a3bc542e0f044d73f405aa639bef0f6d1ec8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="29590-104">Diseñar el nivel de aplicación de microservicios y la API web</span><span class="sxs-lookup"><span data-stu-id="29590-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="29590-105">Uso de principios SOLID e inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="29590-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="29590-106">Los principios SOLID son técnicas fundamentales para utilizar en cualquier aplicación moderna y crítica, como para el desarrollo de un microservicio con patrones DDD.</span><span class="sxs-lookup"><span data-stu-id="29590-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="29590-107">En inglés, SOLID representa un acrónimo que agrupa cinco principios fundamentales:</span><span class="sxs-lookup"><span data-stu-id="29590-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="29590-108">Principio de responsabilidad única</span><span class="sxs-lookup"><span data-stu-id="29590-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="29590-109">Principio de abierto y cerrado</span><span class="sxs-lookup"><span data-stu-id="29590-109">Open/closed principle</span></span>

-   <span data-ttu-id="29590-110">Principio de sustitución de Liskov</span><span class="sxs-lookup"><span data-stu-id="29590-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="29590-111">Principio de segregación de interfaces</span><span class="sxs-lookup"><span data-stu-id="29590-111">Interface Segregation principle</span></span>

-   <span data-ttu-id="29590-112">Principio de inversión de dependencias</span><span class="sxs-lookup"><span data-stu-id="29590-112">Dependency Inversion principle</span></span>

<span data-ttu-id="29590-113">SOLID hace referencia a la forma de diseñar los niveles internos de una aplicación o de un microservicio, así como a separar las dependencias entre ellas.</span><span class="sxs-lookup"><span data-stu-id="29590-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="29590-114">No está relacionado con el dominio, sino con el diseño técnico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29590-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="29590-115">El principio final, el de inversión de dependencias, le permite desacoplar el nivel de infraestructura del resto de niveles, lo que permite una mejor implementación desacoplada de los niveles de DDD.</span><span class="sxs-lookup"><span data-stu-id="29590-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="29590-116">La inversión de dependencias es una forma de implementar el principio de inversión de dependencias.</span><span class="sxs-lookup"><span data-stu-id="29590-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="29590-117">Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="29590-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="29590-118">En lugar de crear directamente instancias de colaboradores o de usar referencias estáticas, los objetos que una clase necesita para llevar a cabo sus acciones se proporcionan (o se "insertan") a dicha clase.</span><span class="sxs-lookup"><span data-stu-id="29590-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="29590-119">A menudo, las clases declaran sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas.</span><span class="sxs-lookup"><span data-stu-id="29590-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="29590-120">Normalmente la inversión de dependencias está basada en determinados contenedores de Inversión de control (IoC).</span><span class="sxs-lookup"><span data-stu-id="29590-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="29590-121">ASP.NET Core proporciona un sencillo contenedor de IoC integrado. Aun así, usted puede usar el contenedor de IoC que prefiera, como Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="29590-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="29590-122">Siguiendo los principios SOLID, las clases tenderán naturalmente a ser pequeñas, a estar factorizadas correctamente y a poder probarse fácilmente.</span><span class="sxs-lookup"><span data-stu-id="29590-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="29590-123">Pero, ¿cómo puede saber si se van a insertar demasiadas dependencias en sus clases?</span><span class="sxs-lookup"><span data-stu-id="29590-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="29590-124">Si usa la inversión de dependencias a través del constructor, le resultará fácil saberlo con solo mirar el número de parámetros de su constructor.</span><span class="sxs-lookup"><span data-stu-id="29590-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="29590-125">Si hay demasiadas dependencias, esto suele ser una señal (una [intuición de código](http://deviq.com/code-smells/)) de que su clase está intentando hacer demasiado y de que probablemente esté infringiendo el principio de responsabilidad única.</span><span class="sxs-lookup"><span data-stu-id="29590-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="29590-126">Necesitaríamos otra guía para tratar SOLID con detalle.</span><span class="sxs-lookup"><span data-stu-id="29590-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="29590-127">Para esta guía solo necesita tener unos conocimientos mínimos de estos temas.</span><span class="sxs-lookup"><span data-stu-id="29590-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="29590-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="29590-128">Additional resources</span></span>

-   <span data-ttu-id="29590-129">**SOLID: Fundamental OOP Principles**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20) (SOLID: principios fundamentales de OOP)</span><span class="sxs-lookup"><span data-stu-id="29590-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="29590-130">**Inversion of Control Containers and the Dependency Injection pattern**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html) (Inversión de los contenedores de control y el patrón de inserción de dependencias)</span><span class="sxs-lookup"><span data-stu-id="29590-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="29590-131">**Steve Smith. New is Glue**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue) (New es como pegamento)</span><span class="sxs-lookup"><span data-stu-id="29590-131">**Steve Smith. New is Glue**
[*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="29590-132">[Anterior] (nosql-database-persistence-infrastructure.md) [Siguiente] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="29590-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
