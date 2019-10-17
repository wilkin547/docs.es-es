---
title: 'Enfoques de arquitectura: aplicaciones sin servidor'
description: Introducción a los enfoques de arquitectura para la creación de aplicaciones empresariales basadas en la nube, desde arquitecturas de N niveles hasta sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522900"
---
# <a name="architecture-approaches"></a><span data-ttu-id="d26ee-103">Enfoques de arquitectura</span><span class="sxs-lookup"><span data-stu-id="d26ee-103">Architecture approaches</span></span>

<span data-ttu-id="d26ee-104">Comprender los enfoques existentes para diseñar aplicaciones empresariales ayuda a aclarar el rol que desempeña sin servidor.</span><span class="sxs-lookup"><span data-stu-id="d26ee-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="d26ee-105">Existen muchos enfoques y patrones que han evolucionado en más de décadas de desarrollo de software y todos tienen sus propias ventajas e inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="d26ee-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="d26ee-106">En muchos casos, es posible que la solución final no implique la decisión de un solo enfoque, sino que pueda integrar varios enfoques.</span><span class="sxs-lookup"><span data-stu-id="d26ee-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="d26ee-107">Los escenarios de migración suelen implicar el cambio de un enfoque de arquitectura a otro a través de un enfoque híbrido.</span><span class="sxs-lookup"><span data-stu-id="d26ee-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="d26ee-108">En este capítulo se proporciona información general sobre los patrones de arquitectura física y lógica de las aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="d26ee-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="d26ee-109">Patrones de arquitectura</span><span class="sxs-lookup"><span data-stu-id="d26ee-109">Architecture patterns</span></span>

<span data-ttu-id="d26ee-110">Las aplicaciones empresariales modernas siguen una variedad de patrones de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="d26ee-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="d26ee-111">En esta sección se representa una encuesta de patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="d26ee-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="d26ee-112">Los patrones que se enumeran aquí no son necesariamente todos los procedimientos recomendados, sino que muestran diferentes enfoques.</span><span class="sxs-lookup"><span data-stu-id="d26ee-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="d26ee-113">Para obtener más información, consulte la [Guía de arquitectura de aplicaciones de Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="d26ee-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="d26ee-114">Monolitos</span><span class="sxs-lookup"><span data-stu-id="d26ee-114">Monoliths</span></span>

<span data-ttu-id="d26ee-115">Muchas aplicaciones empresariales siguen un patrón de monolito.</span><span class="sxs-lookup"><span data-stu-id="d26ee-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="d26ee-116">Las aplicaciones heredadas suelen implementarse como monolíticos.</span><span class="sxs-lookup"><span data-stu-id="d26ee-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="d26ee-117">En el patrón de monolítico, todos los problemas de la aplicación se encuentran en una sola implementación.</span><span class="sxs-lookup"><span data-stu-id="d26ee-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="d26ee-118">Todo lo que se deriva de la interfaz de usuario a las llamadas de base de datos se incluye en el mismo código base.</span><span class="sxs-lookup"><span data-stu-id="d26ee-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Arquitectura de monolito](./media/monolith-architecture.png)

<span data-ttu-id="d26ee-120">El enfoque de monolítico tiene varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="d26ee-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="d26ee-121">A menudo es fácil extraer una sola base de código y comenzar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="d26ee-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="d26ee-122">El tiempo de puesta en marcha puede ser menor y crear entornos de prueba es tan sencillo como proporcionar una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="d26ee-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="d26ee-123">El monolito puede estar diseñado para incluir varios componentes y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d26ee-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="d26ee-124">Desafortunadamente, el patrón de monolítico tiende a desglosar a escala.</span><span class="sxs-lookup"><span data-stu-id="d26ee-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="d26ee-125">Las principales desventajas del enfoque de monolítico incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="d26ee-126">Es difícil trabajar en paralelo en la misma base de código.</span><span class="sxs-lookup"><span data-stu-id="d26ee-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="d26ee-127">Cualquier cambio, con independencia de lo trivial, requiere la implementación de una nueva versión de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d26ee-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="d26ee-128">La refactorización afecta potencialmente a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d26ee-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="d26ee-129">A menudo, la única solución que se debe escalar es crear varias copias de la monolítica que consumen muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="d26ee-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="d26ee-130">A medida que se expandan sistemas o se adquieran otros sistemas, la integración puede ser difícil.</span><span class="sxs-lookup"><span data-stu-id="d26ee-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="d26ee-131">Puede ser difícil de probar debido a la necesidad de configurar todo el monolito.</span><span class="sxs-lookup"><span data-stu-id="d26ee-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="d26ee-132">La reutilización de código es desafiante y a menudo las demás aplicaciones acaban teniendo sus propias copias de código.</span><span class="sxs-lookup"><span data-stu-id="d26ee-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="d26ee-133">Muchas empresas ven a la nube como una oportunidad para migrar aplicaciones monolíticas y, al mismo tiempo, refactorizarlas en patrones más fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="d26ee-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="d26ee-134">Es habitual dividir las aplicaciones y los componentes individuales para que se mantengan, implementen y escalen por separado.</span><span class="sxs-lookup"><span data-stu-id="d26ee-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="d26ee-135">Aplicaciones de N capas</span><span class="sxs-lookup"><span data-stu-id="d26ee-135">N-Layer applications</span></span>

<span data-ttu-id="d26ee-136">Lógica de aplicación de partición de aplicación de N niveles en capas específicas.</span><span class="sxs-lookup"><span data-stu-id="d26ee-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="d26ee-137">Las capas más comunes incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-137">The most common layers include:</span></span>

- <span data-ttu-id="d26ee-138">Interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d26ee-138">User interface</span></span>
- <span data-ttu-id="d26ee-139">Lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="d26ee-139">Business logic</span></span>
- <span data-ttu-id="d26ee-140">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="d26ee-140">Data access</span></span>

<span data-ttu-id="d26ee-141">Otras capas pueden incluir middleware, procesamiento por lotes y API.</span><span class="sxs-lookup"><span data-stu-id="d26ee-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="d26ee-142">Es importante tener en cuenta que las capas son lógicas.</span><span class="sxs-lookup"><span data-stu-id="d26ee-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="d26ee-143">Aunque se desarrollan en aislamiento, se pueden implementar en la misma plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="d26ee-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Arquitectura de N capas](./media/n-layer-architecture.png)

<span data-ttu-id="d26ee-145">Hay varias ventajas en el enfoque de N niveles, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="d26ee-146">La refactorización está aislada en una capa.</span><span class="sxs-lookup"><span data-stu-id="d26ee-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="d26ee-147">Los equipos pueden compilar, probar, implementar y mantener capas independientes de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d26ee-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="d26ee-148">Las capas se pueden intercambiar, por ejemplo, la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios en la capa de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d26ee-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="d26ee-149">Puede usarse sin servidor para implementar una o más capas.</span><span class="sxs-lookup"><span data-stu-id="d26ee-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="d26ee-150">Microservicios</span><span class="sxs-lookup"><span data-stu-id="d26ee-150">Microservices</span></span>

<span data-ttu-id="d26ee-151">Las arquitecturas de **[microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contienen características comunes que incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="d26ee-152">Las aplicaciones se componen de varios servicios pequeños.</span><span class="sxs-lookup"><span data-stu-id="d26ee-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="d26ee-153">Cada servicio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="d26ee-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="d26ee-154">Los servicios están alineados en torno a los dominios empresariales.</span><span class="sxs-lookup"><span data-stu-id="d26ee-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="d26ee-155">Los servicios se comunican a través de API ligeras, normalmente con HTTP como transporte.</span><span class="sxs-lookup"><span data-stu-id="d26ee-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="d26ee-156">Los servicios se pueden implementar y actualizar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="d26ee-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="d26ee-157">Los servicios no dependen de un único almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="d26ee-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="d26ee-158">El sistema se ha diseñado pensando en los errores y la aplicación puede seguir ejecutándose incluso cuando se produce un error en ciertos servicios.</span><span class="sxs-lookup"><span data-stu-id="d26ee-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="d26ee-159">Los microservicios no tienen que ser mutuamente excluyentes a otros enfoques de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="d26ee-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="d26ee-160">Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="d26ee-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="d26ee-161">También es posible implementar microservicios de varias maneras, desde directorios virtuales en hosts de IIS hasta contenedores.</span><span class="sxs-lookup"><span data-stu-id="d26ee-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="d26ee-162">Las características de los microservicios hacen que sean especialmente ideales para implementaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="d26ee-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Arquitectura de microservicios](./media/microservices-architecture.png)

<span data-ttu-id="d26ee-164">Entre las ventajas de las arquitecturas de microservicios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="d26ee-165">La refactorización suele estar aislada en un único servicio.</span><span class="sxs-lookup"><span data-stu-id="d26ee-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="d26ee-166">Los servicios se pueden actualizar de forma independiente entre sí.</span><span class="sxs-lookup"><span data-stu-id="d26ee-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="d26ee-167">La resistencia y la elasticidad se pueden ajustar a las demandas de los servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="d26ee-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="d26ee-168">El desarrollo puede realizarse en paralelo en diferentes equipos y plataformas.</span><span class="sxs-lookup"><span data-stu-id="d26ee-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="d26ee-169">Es más fácil escribir pruebas exhaustivas para servicios aislados.</span><span class="sxs-lookup"><span data-stu-id="d26ee-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="d26ee-170">Los microservicios incluyen sus propios desafíos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d26ee-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="d26ee-171">Determinar qué servicios están disponibles y cómo llamarlos.</span><span class="sxs-lookup"><span data-stu-id="d26ee-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="d26ee-172">Administrar el ciclo de vida de los servicios.</span><span class="sxs-lookup"><span data-stu-id="d26ee-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="d26ee-173">Comprender cómo se ajustan los servicios en la aplicación global.</span><span class="sxs-lookup"><span data-stu-id="d26ee-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="d26ee-174">Pruebas completas del sistema de las llamadas realizadas en servicios dispares.</span><span class="sxs-lookup"><span data-stu-id="d26ee-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="d26ee-175">En última instancia, hay soluciones que abordan todos estos desafíos, entre las que se incluyen las ventajas de sin servidor que se describen más adelante.</span><span class="sxs-lookup"><span data-stu-id="d26ee-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d26ee-176">[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="d26ee-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
