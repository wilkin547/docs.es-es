---
title: Aplicaciones candidatas para nativos de la nube
description: Conozca qué tipos de aplicaciones se benefician de un enfoque nativo de la nube
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805615"
---
# <a name="candidate-apps-for-cloud-native"></a><span data-ttu-id="af6cf-103">Aplicaciones candidatas para nativos de la nube</span><span class="sxs-lookup"><span data-stu-id="af6cf-103">Candidate apps for cloud native</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="af6cf-104">Mira las aplicaciones de tu portafolio.</span><span class="sxs-lookup"><span data-stu-id="af6cf-104">Look at the apps in your portfolio.</span></span> <span data-ttu-id="af6cf-105">¿Cuántos de ellos califican para una arquitectura nativa de la nube?</span><span class="sxs-lookup"><span data-stu-id="af6cf-105">How many of them qualify for a cloud-native architecture?</span></span> <span data-ttu-id="af6cf-106">¿Todos ellos?</span><span class="sxs-lookup"><span data-stu-id="af6cf-106">All of them?</span></span> <span data-ttu-id="af6cf-107">¿Quizás algo?</span><span class="sxs-lookup"><span data-stu-id="af6cf-107">Perhaps some?</span></span>

<span data-ttu-id="af6cf-108">Al aplicar un análisis de costo/beneficio, existe una buena probabilidad de que la mayoría no admita la etiqueta de precio considerable necesaria para ser nativo de la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-108">Applying a cost/benefit analysis, there's a good chance that most wouldn't support the hefty price tag required to be cloud native.</span></span> <span data-ttu-id="af6cf-109">El costo de ser nativo de la nube superaría con creces el valor empresarial de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af6cf-109">The cost of being cloud native would far exceed the business value of the application.</span></span>

<span data-ttu-id="af6cf-110">¿Qué tipo de aplicación podría ser un candidato para nativo de la nube?</span><span class="sxs-lookup"><span data-stu-id="af6cf-110">What type of application might be a candidate for cloud native?</span></span>

- <span data-ttu-id="af6cf-111">Un sistema empresarial grande y estratégico que necesita evolucionar constantemente las capacidades/características del negocio</span><span class="sxs-lookup"><span data-stu-id="af6cf-111">A large, strategic enterprise system that needs to constantly evolve business capabilities/features</span></span>

- <span data-ttu-id="af6cf-112">Una aplicación que requiere una alta velocidad de liberación - con alta confianza</span><span class="sxs-lookup"><span data-stu-id="af6cf-112">An application that requires a high release velocity - with high confidence</span></span>

- <span data-ttu-id="af6cf-113">Un sistema con características individuales deben liberarse *sin* una redistribución completa de todo el sistema</span><span class="sxs-lookup"><span data-stu-id="af6cf-113">A system with where individual features must release *without* a full redeployment of the entire system</span></span>

- <span data-ttu-id="af6cf-114">Una aplicación desarrollada por equipos con experiencia en diferentes pilas de tecnología</span><span class="sxs-lookup"><span data-stu-id="af6cf-114">An application developed by teams with expertise in different technology stacks</span></span>

- <span data-ttu-id="af6cf-115">Una aplicación con componentes que deben escalar de forma independiente</span><span class="sxs-lookup"><span data-stu-id="af6cf-115">An application with components that must scale independently</span></span>

<span data-ttu-id="af6cf-116">Luego hay sistemas heredados.</span><span class="sxs-lookup"><span data-stu-id="af6cf-116">Then there are legacy systems.</span></span> <span data-ttu-id="af6cf-117">Aunque a todos nos gustaría crear nuevas aplicaciones, a menudo somos responsables de modernizar las cargas de trabajo heredadas que son fundamentales para el negocio.</span><span class="sxs-lookup"><span data-stu-id="af6cf-117">While we'd all like to build new applications, we're often responsible for modernizing legacy workloads that are critical to the business.</span></span> <span data-ttu-id="af6cf-118">Con el tiempo, una aplicación heredada podría descomponerse en microservicios, en contenedores y, en última instancia, "replataforma" en una arquitectura nativa de la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-118">Over time, a legacy application could be decomposed into microservices, containerized, and ultimately "replatformed" into a cloud-native architecture.</span></span>

### <a name="modernizing-legacy-apps"></a><span data-ttu-id="af6cf-119">Modernización de aplicaciones heredadas</span><span class="sxs-lookup"><span data-stu-id="af6cf-119">Modernizing legacy apps</span></span>

<span data-ttu-id="af6cf-120">El libro electrónico gratuito de Microsoft [Moderniza las aplicaciones .NET existentes con Azure Cloud y Contenedores](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) de Windows proporciona instrucciones para migrar cargas de trabajo locales a la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-120">The free Microsoft e-book [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) provides guidance for migrating on-premises workloads into cloud.</span></span> <span data-ttu-id="af6cf-121">La Figura 1-10 muestra que no hay una estrategia única y única para modernizar las aplicaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="af6cf-121">Figure 1-10 shows that there isn't a single, one-size-fits-all strategy for modernizing legacy applications.</span></span>

![Estrategias para migrar cargas de trabajo heredadas](./media/strategies-for-migrating-legacy-workloads.png)

<span data-ttu-id="af6cf-123">**Figura 1-10**.</span><span class="sxs-lookup"><span data-stu-id="af6cf-123">**Figure 1-10**.</span></span> <span data-ttu-id="af6cf-124">Estrategias para migrar cargas de trabajo heredadas</span><span class="sxs-lookup"><span data-stu-id="af6cf-124">Strategies for migrating legacy workloads</span></span>

<span data-ttu-id="af6cf-125">Las aplicaciones monolíticas que no son críticas se benefician en gran medida de una rápida migración de elevación y desplazamiento[(preparada para](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)la infraestructura en la nube).</span><span class="sxs-lookup"><span data-stu-id="af6cf-125">Monolithic apps that are non-critical largely benefit from a quick lift-and-shift ([Cloud Infrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) migration.</span></span> <span data-ttu-id="af6cf-126">Aquí, la carga de trabajo local se vuelve a hospedar en una máquina virtual basada en la nube, sin cambios.</span><span class="sxs-lookup"><span data-stu-id="af6cf-126">Here, the on-premises workload is rehosted to a cloud-based VM, without changes.</span></span> <span data-ttu-id="af6cf-127">Este enfoque utiliza el [modelo IaaS (Infraestructura como servicio).](https://azure.microsoft.com/overview/what-is-iaas/)</span><span class="sxs-lookup"><span data-stu-id="af6cf-127">This approach uses the [IaaS (Infrastructure as a Service) model](https://azure.microsoft.com/overview/what-is-iaas/).</span></span> <span data-ttu-id="af6cf-128">Azure incluye varias herramientas, como [Azure Migrate,](https://azure.microsoft.com/services/azure-migrate/) [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)y Azure Database Migration [Service,](https://azure.microsoft.com/campaigns/database-migration/) para facilitar dicho movimiento.</span><span class="sxs-lookup"><span data-stu-id="af6cf-128">Azure includes several tools such as [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/), and [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) to make such a move easier.</span></span> <span data-ttu-id="af6cf-129">Si bien esta estrategia puede producir algunos ahorros de costos, estas aplicaciones normalmente no se diseñaron para desbloquear y aprovechar los beneficios de la computación en la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-129">While this strategy can yield some cost savings, such applications typically weren't architected to unlock and leverage the benefits of cloud computing.</span></span>

<span data-ttu-id="af6cf-130">Las aplicaciones monolíticas que son fundamentales para el negocio a menudo se benefician de una migración mejorada de elevación y desplazamiento (optimizada en la*nube).*</span><span class="sxs-lookup"><span data-stu-id="af6cf-130">Monolithic apps that are critical to the business oftentimes benefit from an enhanced lift-and-shift (*Cloud Optimized*) migration.</span></span> <span data-ttu-id="af6cf-131">Este enfoque incluye optimizaciones de implementación que habilitan los servicios clave en la nube, sin cambiar la arquitectura principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af6cf-131">This approach includes deployment optimizations that enable key cloud services - without changing the core architecture of the application.</span></span> <span data-ttu-id="af6cf-132">Por ejemplo, puede [contener](https://docs.microsoft.com/virtualization/windowscontainers/about/) la aplicación e implementarla en un orquestador de [contenedores, como Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), que se describe más adelante en este libro.</span><span class="sxs-lookup"><span data-stu-id="af6cf-132">For example, you might [containerize](https://docs.microsoft.com/virtualization/windowscontainers/about/) the application and deploy it to a container orchestrator, like [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), discussed later in this book.</span></span> <span data-ttu-id="af6cf-133">Una vez en la nube, la aplicación podría consumir otros servicios en la nube, como bases de datos, colas de mensajes, supervisión y almacenamiento en caché distribuido.</span><span class="sxs-lookup"><span data-stu-id="af6cf-133">Once in the cloud, the application could consume other cloud services such as databases, message queues, monitoring, and distributed caching.</span></span>

<span data-ttu-id="af6cf-134">Por último, las aplicaciones monolíticas que realizan funciones empresariales estratégicas podrían beneficiarse mejor de un enfoque *nativo* de la nube, el tema de este libro.</span><span class="sxs-lookup"><span data-stu-id="af6cf-134">Finally, monolithic apps that perform strategic enterprise functions might best benefit from a *Cloud-Native* approach, the subject of this book.</span></span> <span data-ttu-id="af6cf-135">Este enfoque proporciona agilidad y velocidad.</span><span class="sxs-lookup"><span data-stu-id="af6cf-135">This approach provides agility and velocity.</span></span> <span data-ttu-id="af6cf-136">Sin más que, tiene un costo de replataforma, rearquitectura y reescritura de código.</span><span class="sxs-lookup"><span data-stu-id="af6cf-136">But, it comes at a cost of replatforming, rearchitecting, and rewriting code.</span></span>

<span data-ttu-id="af6cf-137">Si usted y su equipo creen que un enfoque nativo de la nube es apropiado, le corresponde racionalizar la decisión con su organización.</span><span class="sxs-lookup"><span data-stu-id="af6cf-137">If you and your team believe a cloud-native approach is appropriate, it behooves you to rationalize the decision with your organization.</span></span> <span data-ttu-id="af6cf-138">¿Cuál es exactamente el problema empresarial que resolverá un enfoque nativo de la nube?</span><span class="sxs-lookup"><span data-stu-id="af6cf-138">What exactly is the business problem that a cloud-native approach will solve?</span></span> <span data-ttu-id="af6cf-139">¿Cómo se alinearía con las necesidades del negocio?</span><span class="sxs-lookup"><span data-stu-id="af6cf-139">How would it align with business needs?</span></span>

- <span data-ttu-id="af6cf-140">¿Lanzamientos rápidos de características con mayor confianza?</span><span class="sxs-lookup"><span data-stu-id="af6cf-140">Rapid releases of features with increased confidence?</span></span>

- <span data-ttu-id="af6cf-141">Escalabilidad detallada: ¿un uso más eficiente de los recursos?</span><span class="sxs-lookup"><span data-stu-id="af6cf-141">Fine-grained scalability - more efficient usage of resources?</span></span>

- <span data-ttu-id="af6cf-142">¿Mejora de la resiliencia del sistema?</span><span class="sxs-lookup"><span data-stu-id="af6cf-142">Improved system resiliency?</span></span>

- <span data-ttu-id="af6cf-143">¿Mejora del rendimiento del sistema?</span><span class="sxs-lookup"><span data-stu-id="af6cf-143">Improved system performance?</span></span>

- <span data-ttu-id="af6cf-144">¿Más visibilidad de las operaciones?</span><span class="sxs-lookup"><span data-stu-id="af6cf-144">More visibility into operations?</span></span>

- <span data-ttu-id="af6cf-145">¿Combina plataformas de desarrollo y almacenes de datos para llegar a la mejor herramienta para el trabajo?</span><span class="sxs-lookup"><span data-stu-id="af6cf-145">Blend development platforms and data stores to arrive at the best tool for the job?</span></span>

- <span data-ttu-id="af6cf-146">¿Inversión de solicitud a prueba de futuro?</span><span class="sxs-lookup"><span data-stu-id="af6cf-146">Future-proof application investment?</span></span>

<span data-ttu-id="af6cf-147">La estrategia de migración correcta depende de las prioridades organizativas y de los sistemas a los que se dirige.</span><span class="sxs-lookup"><span data-stu-id="af6cf-147">The right migration strategy depends on organizational priorities and the systems you're targeting.</span></span> <span data-ttu-id="af6cf-148">Para muchos, puede ser más rentable optimizar en la nube una aplicación monolítica o agregar servicios de grano grueso a una aplicación de nivel N.</span><span class="sxs-lookup"><span data-stu-id="af6cf-148">For many, it may be more cost effective to cloud-optimize a monolithic application or add coarse-grained services to an N-Tier app.</span></span> <span data-ttu-id="af6cf-149">En estos casos, todavía puede hacer uso completo de las funcionalidades de PaaS en la nube, como las que ofrece Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="af6cf-149">In these cases, you can still make full use of cloud PaaS capabilities like the ones offered by Azure App Service.</span></span>

## <a name="summary"></a><span data-ttu-id="af6cf-150">Resumen</span><span class="sxs-lookup"><span data-stu-id="af6cf-150">Summary</span></span>

<span data-ttu-id="af6cf-151">En este capítulo, introdujimos la informática nativa de la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-151">In this chapter, we introduced cloud-native computing.</span></span> <span data-ttu-id="af6cf-152">Proporcionamos una definición junto con las capacidades clave que impulsan una aplicación nativa de la nube.</span><span class="sxs-lookup"><span data-stu-id="af6cf-152">We provided a definition along with the key capabilities that drive a cloud-native application.</span></span> <span data-ttu-id="af6cf-153">Examinamos los tipos de solicitudes que podrían justificar esta inversión y esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="af6cf-153">We looked at the types of applications that might justify this investment and effort.</span></span>

<span data-ttu-id="af6cf-154">Con la introducción detrás, ahora nos sumergimos en una mirada mucho más detallada a la nube nativa.</span><span class="sxs-lookup"><span data-stu-id="af6cf-154">With the introduction behind, we now dive into a much more detailed look at cloud native.</span></span>

### <a name="references"></a><span data-ttu-id="af6cf-155">Referencias</span><span class="sxs-lookup"><span data-stu-id="af6cf-155">References</span></span>

- [<span data-ttu-id="af6cf-156">Cloud Native Computing Foundation</span><span class="sxs-lookup"><span data-stu-id="af6cf-156">Cloud Native Computing Foundation</span></span>](https://www.cncf.io/)

- [<span data-ttu-id="af6cf-157">Microservicios de .NET: arquitectura para aplicaciones .NET en contenedores</span><span class="sxs-lookup"><span data-stu-id="af6cf-157">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="af6cf-158">Modernice las aplicaciones .NET existentes con Azure Cloud y Windows Containers</span><span class="sxs-lookup"><span data-stu-id="af6cf-158">Modernize existing .NET applications with Azure cloud and Windows Containers</span></span>](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [<span data-ttu-id="af6cf-159">Cloud Native Patterns de Cornelia Davis</span><span class="sxs-lookup"><span data-stu-id="af6cf-159">Cloud Native Patterns by Cornelia Davis</span></span>](https://www.manning.com/books/cloud-native-patterns)

- [<span data-ttu-id="af6cf-160">Más allá de la aplicación de doce factores</span><span class="sxs-lookup"><span data-stu-id="af6cf-160">Beyond the Twelve-Factor Application</span></span>](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [<span data-ttu-id="af6cf-161">Qué es la infraestructura como código</span><span class="sxs-lookup"><span data-stu-id="af6cf-161">What is Infrastructure as Code</span></span>](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [<span data-ttu-id="af6cf-162">Micro Deploy de Uber Engineering: Implementación diaria con confianza</span><span class="sxs-lookup"><span data-stu-id="af6cf-162">Uber Engineering's Micro Deploy: Deploying Daily with Confidence</span></span>](https://eng.uber.com/micro-deploy/)

- [<span data-ttu-id="af6cf-163">Cómo Netflix implementa el código</span><span class="sxs-lookup"><span data-stu-id="af6cf-163">How Netflix Deploys Code</span></span>](https://www.infoq.com/news/2013/06/netflix/)

- [<span data-ttu-id="af6cf-164">Control de sobrecarga para escalar microservicios de WeChat</span><span class="sxs-lookup"><span data-stu-id="af6cf-164">Overload Control for Scaling WeChat Microservices</span></span>](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
><span data-ttu-id="af6cf-165">[Anterior](definition.md)
>[Siguiente](introduce-eshoponcontainers-reference-app.md)</span><span class="sxs-lookup"><span data-stu-id="af6cf-165">[Previous](definition.md)
[Next](introduce-eshoponcontainers-reference-app.md)</span></span>
