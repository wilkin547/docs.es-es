---
title: Enfoques de arquitectura - aplicaciones sin servidor
description: Una introducción a la arquitectura de enfoques para crear aplicaciones empresariales basadas en la nube, de las arquitecturas de N niveles a sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638835"
---
# <a name="architecture-approaches"></a><span data-ttu-id="25945-103">Enfoques de arquitectura</span><span class="sxs-lookup"><span data-stu-id="25945-103">Architecture approaches</span></span>

<span data-ttu-id="25945-104">Descripción de los enfoques existentes para diseñar aplicaciones empresariales Ayuda a aclarar la función desempeñada por sin servidor.</span><span class="sxs-lookup"><span data-stu-id="25945-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="25945-105">Hay muchos enfoques y patrones que ha evolucionaron a lo largo de décadas de desarrollo de software, y todas tienen sus propias ventajas y desventajas.</span><span class="sxs-lookup"><span data-stu-id="25945-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="25945-106">En muchos casos, la solución final puede implicar la decidir un enfoque único, pero puede integrar varios enfoques.</span><span class="sxs-lookup"><span data-stu-id="25945-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="25945-107">Escenarios de migración suelen implican el cambio de enfoque de arquitectura de uno a otro a través de un enfoque híbrido.</span><span class="sxs-lookup"><span data-stu-id="25945-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="25945-108">Este capítulo proporciona información general de ambos patrones de arquitectura lógica y física para aplicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="25945-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="25945-109">Patrones de arquitectura</span><span class="sxs-lookup"><span data-stu-id="25945-109">Architecture patterns</span></span>

<span data-ttu-id="25945-110">Las aplicaciones empresariales modernas siguen una variedad de patrones de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="25945-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="25945-111">En esta sección representa una encuesta de patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="25945-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="25945-112">Los patrones que se muestran aquí no son necesariamente todas las prácticas recomendadas, pero muestran los distintos enfoques.</span><span class="sxs-lookup"><span data-stu-id="25945-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="25945-113">Para obtener más información, consulte [Guía de arquitectura de aplicación de Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="25945-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="25945-114">Monolitos</span><span class="sxs-lookup"><span data-stu-id="25945-114">Monoliths</span></span>

<span data-ttu-id="25945-115">Muchas aplicaciones empresariales siguen un patrón de monolito.</span><span class="sxs-lookup"><span data-stu-id="25945-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="25945-116">Las aplicaciones heredadas a menudo se implementan como monolitos.</span><span class="sxs-lookup"><span data-stu-id="25945-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="25945-117">En el patrón monolítico, todos los problemas de la aplicación se encuentran en una sola implementación.</span><span class="sxs-lookup"><span data-stu-id="25945-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="25945-118">Todo, desde la interfaz de usuario para las llamadas de base de datos se incluye en el mismo código base.</span><span class="sxs-lookup"><span data-stu-id="25945-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Arquitectura de un monolito](./media/monolith-architecture.png)

<span data-ttu-id="25945-120">Hay varias ventajas del enfoque monolítico.</span><span class="sxs-lookup"><span data-stu-id="25945-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="25945-121">A menudo es fácil extraer un único código base y empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="25945-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="25945-122">Tiempo de inicialización puede ser menor y creación de entornos de prueba es tan sencilla como proporcionar una nueva copia.</span><span class="sxs-lookup"><span data-stu-id="25945-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="25945-123">El monolito puede diseñarse para incluir varios componentes y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="25945-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="25945-124">Lamentablemente, el patrón de monolito tiende a desglosar a escala.</span><span class="sxs-lookup"><span data-stu-id="25945-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="25945-125">Las desventajas importantes del enfoque monolítico incluyen:</span><span class="sxs-lookup"><span data-stu-id="25945-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="25945-126">Difícil trabajar en paralelo en el mismo código base.</span><span class="sxs-lookup"><span data-stu-id="25945-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="25945-127">Cualquier cambio, con independencia de cómo trivial, requiere la implementación de una nueva versión de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25945-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="25945-128">Refactorización potencialmente afecta a toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25945-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="25945-129">A menudo es la única solución a escalar crear varias copias de la gran cantidad de recursos de monolito.</span><span class="sxs-lookup"><span data-stu-id="25945-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="25945-130">Expanda los sistemas o se adquieren a otros sistemas, integración puede ser difícil.</span><span class="sxs-lookup"><span data-stu-id="25945-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="25945-131">Puede ser difícil de probar debido a la necesidad de configurar el monolito todo.</span><span class="sxs-lookup"><span data-stu-id="25945-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="25945-132">Reutilización del código es un desafío y a menudo otras aplicaciones acaban tener sus propias copias del código.</span><span class="sxs-lookup"><span data-stu-id="25945-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="25945-133">Muchas empresas recurren a la nube como una oportunidad para migrar aplicaciones de un monolito y al mismo tiempo los refactorizar más patrones utilizable.</span><span class="sxs-lookup"><span data-stu-id="25945-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="25945-134">Es habitual para desglosar los componentes y aplicaciones individuales para que puedan ser mantiene, implementan y escalan por separado.</span><span class="sxs-lookup"><span data-stu-id="25945-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="25945-135">Aplicaciones de N capas</span><span class="sxs-lookup"><span data-stu-id="25945-135">N-Layer applications</span></span>

<span data-ttu-id="25945-136">Lógica de aplicación de partición de aplicación de N capas en niveles específicos.</span><span class="sxs-lookup"><span data-stu-id="25945-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="25945-137">Las capas más comunes incluyen:</span><span class="sxs-lookup"><span data-stu-id="25945-137">The most common layers include:</span></span>

* <span data-ttu-id="25945-138">Interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="25945-138">User interface</span></span>
* <span data-ttu-id="25945-139">lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="25945-139">Business logic</span></span>
* <span data-ttu-id="25945-140">Acceso a datos</span><span class="sxs-lookup"><span data-stu-id="25945-140">Data access</span></span>

<span data-ttu-id="25945-141">Pueden incluir otras capas middleware, procesamiento por lotes y API.</span><span class="sxs-lookup"><span data-stu-id="25945-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="25945-142">Es importante tener en cuenta que las capas son lógicas.</span><span class="sxs-lookup"><span data-stu-id="25945-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="25945-143">Aunque se desarrollan en aislamiento, todo se puede implementar en la misma plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="25945-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Arquitectura de N capas](./media/n-layer-architecture.png)

<span data-ttu-id="25945-145">Hay varias ventajas del enfoque de N capas, incluidas:</span><span class="sxs-lookup"><span data-stu-id="25945-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="25945-146">Refactorización está aislada en una capa.</span><span class="sxs-lookup"><span data-stu-id="25945-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="25945-147">Por separado los equipos pueden crear, probar, implementar y mantener capas separadas.</span><span class="sxs-lookup"><span data-stu-id="25945-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="25945-148">Se pueden intercambiar las capas, por ejemplo la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios a la capa de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="25945-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="25945-149">Sin servidor puede utilizarse para implementar una o varias capas.</span><span class="sxs-lookup"><span data-stu-id="25945-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="25945-150">Microservicios</span><span class="sxs-lookup"><span data-stu-id="25945-150">Microservices</span></span>

<span data-ttu-id="25945-151">**[Microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  arquitecturas contienen características comunes que incluyen:</span><span class="sxs-lookup"><span data-stu-id="25945-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="25945-152">Las aplicaciones se componen de varios servicios pequeños.</span><span class="sxs-lookup"><span data-stu-id="25945-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="25945-153">Cada servicio se ejecuta en su propio proceso.</span><span class="sxs-lookup"><span data-stu-id="25945-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="25945-154">Los servicios se alinean en torno a dominios empresariales.</span><span class="sxs-lookup"><span data-stu-id="25945-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="25945-155">Los servicios se comunican a través de API ligeras, normalmente mediante HTTP como transporte.</span><span class="sxs-lookup"><span data-stu-id="25945-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="25945-156">Los servicios se pueden implementar y actualizar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="25945-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="25945-157">Servicios no son dependientes de un único almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="25945-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="25945-158">El sistema está diseñado con un error en la cuenta y la aplicación, puede que siga funcionando incluso cuando determinados servicios producirá un error.</span><span class="sxs-lookup"><span data-stu-id="25945-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="25945-159">Microservicios no tienen que ser mutuamente excluyentes para otros enfoques de arquitectura.</span><span class="sxs-lookup"><span data-stu-id="25945-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="25945-160">Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="25945-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="25945-161">También es posible implementar microservicios en una variedad de formas, desde los directorios virtuales en hosts IIS para contenedores.</span><span class="sxs-lookup"><span data-stu-id="25945-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="25945-162">Las características de microservicios que sean especialmente ideal para implementaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="25945-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Arquitectura de microservicios](./media/microservices-architecture.png)

<span data-ttu-id="25945-164">Entre las ventajas de las arquitecturas de microservicios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="25945-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="25945-165">Refactorización a menudo se aísla en un único servicio.</span><span class="sxs-lookup"><span data-stu-id="25945-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="25945-166">Los servicios se pueden actualizar independientemente entre sí.</span><span class="sxs-lookup"><span data-stu-id="25945-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="25945-167">Resistencia y la elasticidad pueden ajustarse a las exigencias de los servicios individuales.</span><span class="sxs-lookup"><span data-stu-id="25945-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="25945-168">Desarrollo puede darse en paralelo en las plataformas y los equipos dispares.</span><span class="sxs-lookup"><span data-stu-id="25945-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="25945-169">Es más fácil escribir pruebas integrales para servicios aislado.</span><span class="sxs-lookup"><span data-stu-id="25945-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="25945-170">Microservicios vienen con sus propios desafíos, incluyendo:</span><span class="sxs-lookup"><span data-stu-id="25945-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="25945-171">Determinación de qué servicios están disponibles y cómo llamarlos.</span><span class="sxs-lookup"><span data-stu-id="25945-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="25945-172">Administrar el ciclo de vida de los servicios.</span><span class="sxs-lookup"><span data-stu-id="25945-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="25945-173">Comprender cómo encajan los servicios en la aplicación general.</span><span class="sxs-lookup"><span data-stu-id="25945-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="25945-174">Total de pruebas del sistema de las llamadas realizadas a través de diferentes servicios.</span><span class="sxs-lookup"><span data-stu-id="25945-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="25945-175">En última instancia, hay soluciones para abordar todos estos desafíos, incluido el aprovechamiento de las ventajas de sin servidor que se describen más adelante.</span><span class="sxs-lookup"><span data-stu-id="25945-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="25945-176">[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="25945-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
