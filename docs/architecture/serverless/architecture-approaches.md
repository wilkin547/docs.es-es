---
title: 'Enfoques de arquitectura: aplicaciones sin servidor'
description: Introducción a los enfoques de arquitectura para la creación de aplicaciones empresariales basadas en la nube, desde arquitecturas de N niveles hasta aplicaciones sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522900"
---
# <a name="architecture-approaches"></a><span data-ttu-id="76c9d-103">Enfoques de arquitectura</span><span class="sxs-lookup"><span data-stu-id="76c9d-103">Architecture approaches</span></span>

<span data-ttu-id="76c9d-104">Conocer los enfoques actuales para diseñar aplicaciones empresariales ayuda a aclarar el rol que desempeñan las aplicaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="76c9d-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="76c9d-105">Existen muchos enfoques y patrones que han evolucionado a lo largo de décadas de desarrollo de software, y todos tienen sus ventajas e inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="76c9d-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="76c9d-106">En muchos casos, es posible que la solución final no implique un solo enfoque, sino la integración de varios enfoques.</span><span class="sxs-lookup"><span data-stu-id="76c9d-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="76c9d-107">Los escenarios de migración suelen implicar el cambio de un enfoque de arquitectura a otro mediante un enfoque híbrido.</span><span class="sxs-lookup"><span data-stu-id="76c9d-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="76c9d-108">Este capítulo es una introducción a los patrones de arquitectura física y lógica de las aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="76c9d-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="76c9d-109">Patrones de arquitectura</span><span class="sxs-lookup"><span data-stu-id="76c9d-109">Architecture patterns</span></span>

<span data-ttu-id="76c9d-110">Las aplicaciones empresariales modernas siguen diversos patrones de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="76c9d-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="76c9d-111">En esta sección se recoge una selección de los patrones más comunes.</span><span class="sxs-lookup"><span data-stu-id="76c9d-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="76c9d-112">Los patrones que se enumeran aquí no son necesariamente todos los procedimientos recomendados, sino que muestran diferentes enfoques.</span><span class="sxs-lookup"><span data-stu-id="76c9d-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="76c9d-113">Para más información, consulte [Guía de arquitectura de aplicaciones de Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="76c9d-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="76c9d-114">Monolitos</span><span class="sxs-lookup"><span data-stu-id="76c9d-114">Monoliths</span></span>

<span data-ttu-id="76c9d-115">Muchas aplicaciones empresariales siguen un patrón monolítico.</span><span class="sxs-lookup"><span data-stu-id="76c9d-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="76c9d-116">Las aplicaciones heredadas suelen implementarse como monolitos.</span><span class="sxs-lookup"><span data-stu-id="76c9d-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="76c9d-117">En el patrón monolítico, todos los problemas de la aplicación se reducen a una sola implementación.</span><span class="sxs-lookup"><span data-stu-id="76c9d-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="76c9d-118">Todo, desde la interfaz de usuario a las llamadas de base de datos, está incluido en el mismo código base.</span><span class="sxs-lookup"><span data-stu-id="76c9d-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Arquitectura monolítica](./media/monolith-architecture.png)

<span data-ttu-id="76c9d-120">El enfoque monolítico tiene varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="76c9d-121">Normalmente es fácil comenzar a trabajar con una sola base de código.</span><span class="sxs-lookup"><span data-stu-id="76c9d-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="76c9d-122">El tiempo de puesta en marcha puede ser menor y crear entornos de prueba es tan sencillo como hacer una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="76c9d-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="76c9d-123">El monolito puede estar diseñado para incluir varios componentes y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="76c9d-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="76c9d-124">Lamentablemente, el patrón monolítico tiende a desmoronarse a medida que aumenta su tamaño.</span><span class="sxs-lookup"><span data-stu-id="76c9d-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="76c9d-125">Las principales desventajas del enfoque monolítico son:</span><span class="sxs-lookup"><span data-stu-id="76c9d-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="76c9d-126">Es difícil trabajar en paralelo en la misma base de código.</span><span class="sxs-lookup"><span data-stu-id="76c9d-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="76c9d-127">Cualquier cambio, por pequeño que sea, requiere la implementación de una nueva versión de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76c9d-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="76c9d-128">La refactorización afecta potencialmente a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76c9d-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="76c9d-129">La única solución para escalar suele ser crear varias copias del monolito, que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="76c9d-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="76c9d-130">La integración puede resultar difícil cuando los sistemas se expanden o se adquieren otros sistemas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="76c9d-131">Puede ser difícil de probar debido a la necesidad de configurar todo el monolito.</span><span class="sxs-lookup"><span data-stu-id="76c9d-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="76c9d-132">La reutilización de código supone un reto y, a menudo, las demás aplicaciones acaban teniendo sus propias copias de código.</span><span class="sxs-lookup"><span data-stu-id="76c9d-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="76c9d-133">Muchas empresas ven la nube como una oportunidad para migrar aplicaciones monolíticas y, al mismo tiempo, refactorizarlas en patrones más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="76c9d-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="76c9d-134">Es habitual dividir las aplicaciones y los componentes individuales para mantenerlos, implementarlos y escalarlos por separado.</span><span class="sxs-lookup"><span data-stu-id="76c9d-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="76c9d-135">Aplicaciones de N capas</span><span class="sxs-lookup"><span data-stu-id="76c9d-135">N-Layer applications</span></span>

<span data-ttu-id="76c9d-136">Las aplicaciones de N capas dividen la lógica de la aplicación en capas específicas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="76c9d-137">Las capas más comunes son:</span><span class="sxs-lookup"><span data-stu-id="76c9d-137">The most common layers include:</span></span>

- <span data-ttu-id="76c9d-138">Interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="76c9d-138">User interface</span></span>
- <span data-ttu-id="76c9d-139">Lógica empresarial</span><span class="sxs-lookup"><span data-stu-id="76c9d-139">Business logic</span></span>
- <span data-ttu-id="76c9d-140">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="76c9d-140">Data access</span></span>

<span data-ttu-id="76c9d-141">Otras capas pueden incluir middleware, procesamiento por lotes y API.</span><span class="sxs-lookup"><span data-stu-id="76c9d-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="76c9d-142">Es importante tener en cuenta que las capas son lógicas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="76c9d-143">Aunque se desarrollan de forma aislada, se pueden implementar en la misma plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="76c9d-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Arquitectura de N capas](./media/n-layer-architecture.png)

<span data-ttu-id="76c9d-145">El enfoque de N capas presenta varias ventajas, entre ellas:</span><span class="sxs-lookup"><span data-stu-id="76c9d-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="76c9d-146">La refactorización está aislada en una capa.</span><span class="sxs-lookup"><span data-stu-id="76c9d-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="76c9d-147">Los equipos pueden compilar, probar, implementar y mantener las capas de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="76c9d-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="76c9d-148">Las capas se pueden intercambiar, por ejemplo, la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios en la capa de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="76c9d-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="76c9d-149">Puede usarse sin servidor para implementar una o más capas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="76c9d-150">Microservicios</span><span class="sxs-lookup"><span data-stu-id="76c9d-150">Microservices</span></span>

<span data-ttu-id="76c9d-151">Las arquitecturas de **[microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contienen características comunes que incluyen:</span><span class="sxs-lookup"><span data-stu-id="76c9d-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="76c9d-152">Las aplicaciones se componen de varios servicios pequeños.</span><span class="sxs-lookup"><span data-stu-id="76c9d-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="76c9d-153">Cada servicio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="76c9d-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="76c9d-154">Los servicios se corresponden con los dominios empresariales.</span><span class="sxs-lookup"><span data-stu-id="76c9d-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="76c9d-155">Los servicios se comunican mediante API ligeras, normalmente con HTTP como transporte.</span><span class="sxs-lookup"><span data-stu-id="76c9d-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="76c9d-156">Los servicios se pueden implementar y actualizar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="76c9d-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="76c9d-157">Los servicios no dependen de un único almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="76c9d-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="76c9d-158">El sistema se ha diseñado pensando en los errores y la aplicación puede seguir ejecutándose incluso cuando se produce un error en ciertos servicios.</span><span class="sxs-lookup"><span data-stu-id="76c9d-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="76c9d-159">Los microservicios no excluyen otros enfoques de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="76c9d-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="76c9d-160">Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="76c9d-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="76c9d-161">Los microservicios se pueden implementar de varias maneras, desde directorios virtuales en hosts de IIS hasta contenedores.</span><span class="sxs-lookup"><span data-stu-id="76c9d-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="76c9d-162">Las características de los microservicios hacen que sean especialmente ideales para implementaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="76c9d-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Arquitectura de microservicios](./media/microservices-architecture.png)

<span data-ttu-id="76c9d-164">Entre las ventajas de las arquitecturas de microservicios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="76c9d-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="76c9d-165">La refactorización suele estar aislada en un único servicio.</span><span class="sxs-lookup"><span data-stu-id="76c9d-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="76c9d-166">Los servicios se pueden actualizar de forma independiente entre sí.</span><span class="sxs-lookup"><span data-stu-id="76c9d-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="76c9d-167">La resistencia y la elasticidad se pueden ajustar a las demandas de los servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="76c9d-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="76c9d-168">El desarrollo puede realizarse en paralelo en diferentes equipos y plataformas.</span><span class="sxs-lookup"><span data-stu-id="76c9d-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="76c9d-169">Es más fácil escribir pruebas exhaustivas para servicios aislados.</span><span class="sxs-lookup"><span data-stu-id="76c9d-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="76c9d-170">Los microservicios tienen sus propios desafíos, entre ellos:</span><span class="sxs-lookup"><span data-stu-id="76c9d-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="76c9d-171">Determinar qué servicios hay disponibles y cómo llamarlos.</span><span class="sxs-lookup"><span data-stu-id="76c9d-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="76c9d-172">Administrar el ciclo de vida de los servicios.</span><span class="sxs-lookup"><span data-stu-id="76c9d-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="76c9d-173">Comprender cómo encajan los servicios en la aplicación global.</span><span class="sxs-lookup"><span data-stu-id="76c9d-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="76c9d-174">Probar en todo el sistema las llamadas realizadas a los distintos servicios.</span><span class="sxs-lookup"><span data-stu-id="76c9d-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="76c9d-175">En última instancia, hay soluciones que abordan todos estos desafíos y que permiten aprovechar las ventajas del modelo sin servidor que se describen más adelante.</span><span class="sxs-lookup"><span data-stu-id="76c9d-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="76c9d-176">[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="76c9d-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
