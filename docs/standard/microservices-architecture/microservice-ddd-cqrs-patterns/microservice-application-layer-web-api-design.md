---
title: "Diseñar la capa de aplicación de microservicio y API de Web"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar la capa de aplicación de microservicio y API de Web"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="fbaa5-104">Diseñar la capa de aplicación de microservicio y API de Web</span><span class="sxs-lookup"><span data-stu-id="fbaa5-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="fbaa5-105">Uso de principios sólidos e inyección de dependencia</span><span class="sxs-lookup"><span data-stu-id="fbaa5-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="fbaa5-106">Principios sólidos son técnicas críticas que se usará en las aplicaciones modernas y críticas, como el desarrollo de un microservicio con patrones DDD.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="fbaa5-107">SÓLIDO es un acrónimo que grupos cinco los principios fundamentales:</span><span class="sxs-lookup"><span data-stu-id="fbaa5-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="fbaa5-108">Principio de responsabilidad única</span><span class="sxs-lookup"><span data-stu-id="fbaa5-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="fbaa5-109">Principio abierto/cerrado</span><span class="sxs-lookup"><span data-stu-id="fbaa5-109">Open/closed principle</span></span>

-   <span data-ttu-id="fbaa5-110">Sustitución de Liskov</span><span class="sxs-lookup"><span data-stu-id="fbaa5-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="fbaa5-111">Principio de segregación de inversión</span><span class="sxs-lookup"><span data-stu-id="fbaa5-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="fbaa5-112">Principio de la inversión de dependencia</span><span class="sxs-lookup"><span data-stu-id="fbaa5-112">Dependency Inversion principle</span></span>

<span data-ttu-id="fbaa5-113">SÓLIDO es más acerca de cómo diseñar la aplicación o capas de microservicio interno y separar las dependencias entre ellos.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="fbaa5-114">No está relacionado con el dominio, pero diseño técnico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="fbaa5-115">La entidad de seguridad final, el principio de la inversión de dependencia (DI), le permite desacoplar el nivel de infraestructura del resto de las capas, lo que permite una mejor implementación desacoplada de las capas DDD.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="fbaa5-116">DI es una manera de implementar el principio de inversión de dependencia.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="fbaa5-117">Es una técnica para lograr el acoplamiento flexible entre los objetos y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="fbaa5-118">En lugar de crear directamente instancias de colaboradores, o mediante las referencias estáticas, los objetos que necesita una clase para realizar sus acciones se proporcionan a (o "inyectar") la clase.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="fbaa5-119">A menudo, las clases declarará sus dependencias a través de su constructor, lo que les permite seguir el principio de dependencias explícitas.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="fbaa5-120">DI normalmente está basada en determinados contenedores de inversión de Control (IoC).</span><span class="sxs-lookup"><span data-stu-id="fbaa5-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="fbaa5-121">ASP.NET Core proporciona un contenedor de IoC sencillo integrado, pero también puede usar el contenedor de IoC favoritos, como Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="fbaa5-122">Siguiendo los principios sólidos, las clases tenderán naturalmente sea pequeño, correctamente factorizada y probados fácilmente.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="fbaa5-123">Pero, ¿cómo puede saber si hay demasiadas dependencias que se va a se insertan en las clases?</span><span class="sxs-lookup"><span data-stu-id="fbaa5-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="fbaa5-124">Si usas DI a través del constructor, resultará fácil detectar que con solo mirar el número de parámetros para el constructor.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="fbaa5-125">Si hay demasiadas dependencias, esto suele ser un inicio de sesión (una [código olor](http://deviq.com/code-smells/)) que está intentando hacer demasiado la clase y, probablemente se infringe el principio de responsabilidad única.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="fbaa5-126">Tardaría otra guía para cubrir sólido en detalle.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="fbaa5-127">Por lo tanto, esta guía requiere tener solo un conocimiento mínimo de estos temas.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="fbaa5-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fbaa5-128">Additional resources</span></span>

-   <span data-ttu-id="fbaa5-129">**SÓLIDO: Principios de programación orientada a objetos fundamentales**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="fbaa5-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="fbaa5-130">**Inversión de contenedores de controles y el modelo de inserción de dependencias**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="fbaa5-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="fbaa5-131">**Steve Smith. Es una novedad adherencia**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="fbaa5-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fbaa5-132">[Anterior] (nosql-base de datos de persistencia-infrastructure.md) [siguiente] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="fbaa5-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
