---
title: Tutoriales e introducción técnica
description: Modernización de aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Tutoriales e introducción técnica
ms.date: 04/28/2018
ms.openlocfilehash: 4db6d449d27dcd4316d61305c8c2a8c2aa0bc65b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516130"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="a1375-103">Tutoriales e introducción técnica</span><span class="sxs-lookup"><span data-stu-id="a1375-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="a1375-104">Para limitar el tamaño de este libro electrónico, hay disponible documentación técnica adicional y los tutoriales completos en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a1375-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="a1375-105">En la serie de tutoriales en línea que se describe en este capítulo se abarca la configuración paso a paso de los diversos entornos que están basados en contenedores de Windows y la implementación en Azure.</span><span class="sxs-lookup"><span data-stu-id="a1375-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="a1375-106">En las secciones siguientes se explica en qué consiste cada tutorial, sus objetivos y visión de alto nivel y se proporciona un diagrama de las tareas implicadas.</span><span class="sxs-lookup"><span data-stu-id="a1375-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="a1375-107">Puede obtener los tutoriales en la wiki del repositorio de GitHub de aplicaciones *eShopModernizing* en <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span><span class="sxs-lookup"><span data-stu-id="a1375-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at <https://github.com/dotnet-architecture/eShopModernizing/wiki>.</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="a1375-108">Lista de tutoriales técnicos</span><span class="sxs-lookup"><span data-stu-id="a1375-108">Technical walkthrough list</span></span>

<span data-ttu-id="a1375-109">Los tutoriales de introducción siguientes proporcionan una guía técnica coherente y completa para las aplicaciones de ejemplo que se pueden migrar mediante lift-and-shift a través del uso de contenedores y, a continuación, moverse con varias opciones de implementación en Azure.</span><span class="sxs-lookup"><span data-stu-id="a1375-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="a1375-110">Cada uno de los tutoriales siguientes usa las aplicaciones eShopLegacy e eShopModernizing de ejemplo nuevas, que están disponibles en GitHub en <https://github.com/dotnet-architecture/eShopModernizing>.</span><span class="sxs-lookup"><span data-stu-id="a1375-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at <https://github.com/dotnet-architecture/eShopModernizing>.</span></span>

- <span data-ttu-id="a1375-111">**Un paseo por las aplicaciones heredadas de eShop (aplicaciones de línea de base que se van a modernizar)**</span><span class="sxs-lookup"><span data-stu-id="a1375-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="a1375-112">**Inclusión en contenedores de las aplicaciones web de ASP.NET (WebForms y MVC) con contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="a1375-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="a1375-113">**Inclusión en contenedores de los servicios WCF existentes (aplicaciones de n niveles) con contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="a1375-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="a1375-114">**Implementación de una aplicación basada en contenedores de Windows en máquinas virtuales de Azure**</span><span class="sxs-lookup"><span data-stu-id="a1375-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="a1375-115">**Implementación de aplicaciones basadas en contenedores de Windows en Kubernetes en Azure Container Service**</span><span class="sxs-lookup"><span data-stu-id="a1375-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="a1375-116">Tutorial 1: Un paseo por las aplicaciones heredadas de eShop</span><span class="sxs-lookup"><span data-stu-id="a1375-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a1375-117">Disponibilidad del tutorial técnico</span><span class="sxs-lookup"><span data-stu-id="a1375-117">Technical walkthrough availability</span></span>

<span data-ttu-id="a1375-118">El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a1375-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="a1375-119">Tutoriales de la wiki de eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="a1375-119">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a><span data-ttu-id="a1375-120">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-120">Overview</span></span>

<span data-ttu-id="a1375-121">En este tutorial puede explorar la implementación inicial de tres aplicaciones heredadas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a1375-121">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="a1375-122">Las dos primeras aplicaciones web de ejemplo tienen una arquitectura monolítica y se crearon con ASP.NET clásico.</span><span class="sxs-lookup"><span data-stu-id="a1375-122">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="a1375-123">Una aplicación se basa en ASP.NET 4.x MVC, mientras que la segunda, en formularios ASP.NET 4.x Web Forms.</span><span class="sxs-lookup"><span data-stu-id="a1375-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span>
<span data-ttu-id="a1375-124">La tercera es una aplicación de 3 niveles que consta de una aplicación de WinForms de cliente y un servicio [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="a1375-124">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="a1375-125">Todas estas aplicaciones están disponibles en el [repositorio eShopModernizing de GitHub](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="a1375-125">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-126">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-126">Goals</span></span>

<span data-ttu-id="a1375-127">El objetivo principal de este tutorial es familiarizarse con estas aplicaciones y con su código y configuración.</span><span class="sxs-lookup"><span data-stu-id="a1375-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="a1375-128">Puede configurar las aplicaciones para que generen y usen datos ficticios, sin usar la base de datos SQL, con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="a1375-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="a1375-129">Esta configuración opcional se basa en la inserción de dependencias de manera desacoplada.</span><span class="sxs-lookup"><span data-stu-id="a1375-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="a1375-130">Escenario 1: Aplicaciones web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a1375-130">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="a1375-131">En la ilustración siguiente se muestra el escenario simple de las aplicaciones web ASP.NET heredadas originales.</span><span class="sxs-lookup"><span data-stu-id="a1375-131">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

![Escenario de arquitectura simple de las aplicaciones web ASP.NET heredadas originales](./media/image5-1.png)

<span data-ttu-id="a1375-133">Desde la perspectiva del dominio empresarial, ambas aplicaciones ofrecen las mismas características de administración de catálogos.</span><span class="sxs-lookup"><span data-stu-id="a1375-133">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="a1375-134">Los miembros del equipo empresarial de eShop usarían la aplicación para ver y editar el catálogo de productos.</span><span class="sxs-lookup"><span data-stu-id="a1375-134">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span>

<span data-ttu-id="a1375-135">En la ilustración siguiente se muestran las capturas de pantallas de las aplicaciones iniciales.</span><span class="sxs-lookup"><span data-stu-id="a1375-135">The next figure shows the initial app screenshots.</span></span>

![Aplicaciones ASP.NET MVC y ASP.NET Web Forms (tecnologías existentes o heredadas)](./media/image5-2.png)

<span data-ttu-id="a1375-137">Las dependencias de ASP.NET 4.x o versiones anteriores (ya sea para MVC o para Web Forms) significan que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se reescriba por completo mediante ASP.NET Core MVC.</span><span class="sxs-lookup"><span data-stu-id="a1375-137">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span>

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="a1375-138">Escenario 2: Servicio WCF y aplicación cliente de WinForms (aplicación de 3 niveles)</span><span class="sxs-lookup"><span data-stu-id="a1375-138">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="a1375-139">En la ilustración siguiente se muestra el escenario simple de la aplicación web de 3 niveles original.</span><span class="sxs-lookup"><span data-stu-id="a1375-139">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

![Escenario de arquitectura simple de la aplicación heredada de 3 niveles original con un servicio WCF y una aplicación cliente de WinForms](./media/image5-1.5.png)

### <a name="benefits"></a><span data-ttu-id="a1375-141">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-141">Benefits</span></span>

<span data-ttu-id="a1375-142">Las ventajas de este tutorial son sencillas: Familiarícese con el código y las aplicaciones iniciales.</span><span class="sxs-lookup"><span data-stu-id="a1375-142">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-143">Next steps</span></span>

<span data-ttu-id="a1375-144">Explore este contenido más en profundidad en la wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a1375-144">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="a1375-145">Un paseo por las aplicaciones ASP.NET MVC y ASP.NET Web Forms de línea de base "heredadas"</span><span class="sxs-lookup"><span data-stu-id="a1375-145">Tour on the baseline ASP.NET MVC and Web Forms "legacy" apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [<span data-ttu-id="a1375-146">Un paseo por la aplicación del servicio WCF y WinForms (de tres niveles) de línea de base "heredadas"</span><span class="sxs-lookup"><span data-stu-id="a1375-146">Tour on the baseline WCF service and WinForms (3-Tier) "legacy" app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="a1375-147">Tutorial 2: Inclusión en contenedores de las aplicaciones .NET existentes con contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="a1375-147">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="a1375-148">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-148">Overview</span></span>

<span data-ttu-id="a1375-149">Use contenedores de Windows para mejorar la implementación de las aplicaciones .NET existentes, como las basadas en MVC, Web Forms o WCF, en entornos de producción, desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="a1375-149">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-150">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-150">Goals</span></span>

<span data-ttu-id="a1375-151">El objetivo de este tutorial es mostrar varias opciones para incluir una aplicación .NET Framework existente en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="a1375-151">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="a1375-152">Puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1375-152">You can:</span></span>

- <span data-ttu-id="a1375-153">Incluir la aplicación en contenedores mediante [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="a1375-153">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="a1375-154">Para incluir la aplicación en un contenedor, agregue manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/) y, a continuación, use la [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="a1375-154">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="a1375-155">Incluya la aplicación en contenedores mediante la herramienta [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (una herramienta de código abierto de Docker).</span><span class="sxs-lookup"><span data-stu-id="a1375-155">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="a1375-156">Este tutorial se centra en el enfoque de Visual Studio 2017 Tools para Docker, pero los otros dos enfoques son muy similares en lo que respecta al uso de Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="a1375-156">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="a1375-157">Escenario 1: Aplicaciones web ASP.NET en contenedores</span><span class="sxs-lookup"><span data-stu-id="a1375-157">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="a1375-158">En la ilustración siguiente se muestra el escenario para las aplicaciones web heredadas de eShop en contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-158">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

![Diagrama de arquitectura simplificado de aplicaciones ASP.NET en contenedores en un entorno de desarrollo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="a1375-160">Escenario 2: Servicio WCF en contenedores</span><span class="sxs-lookup"><span data-stu-id="a1375-160">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="a1375-161">En la ilustración siguiente se muestra el escenario de una aplicación de 3 niveles con un servicio WCF en contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-161">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span>

![Diagrama de arquitectura simplificado de un servicio WCF en contenedores en un entorno de desarrollo](./media/image5-3.5.png)

### <a name="benefits"></a><span data-ttu-id="a1375-163">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-163">Benefits</span></span>

<span data-ttu-id="a1375-164">Ejecutar una aplicación monolítica en un contenedor tiene ciertas ventajas.</span><span class="sxs-lookup"><span data-stu-id="a1375-164">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="a1375-165">En primer lugar, cree una imagen para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1375-165">First, you create an image for the application.</span></span> <span data-ttu-id="a1375-166">A partir de ese momento, todas las implementaciones se ejecutarán en el mismo entorno.</span><span class="sxs-lookup"><span data-stu-id="a1375-166">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="a1375-167">Cada contenedor usa la misma versión de sistema operativo, tiene instalada la misma versión de dependencias, usa la misma versión de .NET Framework y se compila con el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="a1375-167">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="a1375-168">Básicamente, puede controlar las dependencias de la aplicación mediante una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="a1375-168">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="a1375-169">Las dependencias viajan con la aplicación cuando se implementan los contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-169">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="a1375-170">Una ventaja adicional es que los desarrolladores pueden ejecutar la aplicación en el entorno coherente que proporcionan los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="a1375-170">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="a1375-171">Los problemas que solo aparecen con ciertas versiones se pueden solucionar inmediatamente, en lugar de hacerlo en un entorno de ensayo o de producción.</span><span class="sxs-lookup"><span data-stu-id="a1375-171">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="a1375-172">Las diferencias en los entornos de desarrollo que usan los miembros del equipo de desarrollo tienen menos importancia cuando las aplicaciones se ejecutan en contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-172">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="a1375-173">Las aplicaciones en contenedor también tienen una curva de escalado horizontal más plana.</span><span class="sxs-lookup"><span data-stu-id="a1375-173">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="a1375-174">Las aplicaciones en contenedor permiten tener más instancias de aplicaciones y servicios (basadas en contenedores) en una máquina virtual o en una máquina física en comparación con las implementaciones de aplicaciones normales por máquina.</span><span class="sxs-lookup"><span data-stu-id="a1375-174">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="a1375-175">Esto se traduce en una mayor densidad y en menos recursos necesarios, especialmente cuando se usan orquestadores como Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a1375-175">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes.</span></span>

<span data-ttu-id="a1375-176">En situaciones ideales, la inclusión en contenedores no requiere ningún cambio en el código de la aplicación (C\#).</span><span class="sxs-lookup"><span data-stu-id="a1375-176">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="a1375-177">En la mayoría de los escenarios, solo necesita los archivos de metadatos de implementación de Docker (archivos Dockerfiles y Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="a1375-177">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-178">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-178">Next steps</span></span>

<span data-ttu-id="a1375-179">Explore este contenido más en profundidad en la wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a1375-179">Explore this content more in-depth on the GitHub wiki:</span></span>

- [<span data-ttu-id="a1375-180">Inclusión en contenedores de las aplicaciones web de .NET Framework con contenedores de Windows y Dockers</span><span class="sxs-lookup"><span data-stu-id="a1375-180">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [<span data-ttu-id="a1375-181">Incorporación de la compatibilidad con Docker en un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a1375-181">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="a1375-182">Tutorial 3: Implementación de una aplicación basada en contenedores de Windows en máquinas virtuales de Azure</span><span class="sxs-lookup"><span data-stu-id="a1375-182">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a1375-183">Disponibilidad del tutorial técnico</span><span class="sxs-lookup"><span data-stu-id="a1375-183">Technical walkthrough availability</span></span>

<span data-ttu-id="a1375-184">El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="a1375-184">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)></span></span>

### <a name="overview"></a><span data-ttu-id="a1375-185">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-185">Overview</span></span>

<span data-ttu-id="a1375-186">La implementación en un host de Docker en una máquina virtual (VM) con Windows Server 2016 en Azure le permite configurar rápidamente entornos de desarrollo, pruebas y ensayo.</span><span class="sxs-lookup"><span data-stu-id="a1375-186">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="a1375-187">También ofrece un lugar común para que los evaluadores o usuarios empresariales validen la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1375-187">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="a1375-188">Las máquinas virtuales también pueden ser entornos de producción de infraestructura como servicio (IaaS) válidos.</span><span class="sxs-lookup"><span data-stu-id="a1375-188">VMs also can be valid Infrastructure as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-189">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-189">Goals</span></span>

<span data-ttu-id="a1375-190">El objetivo de este tutorial es mostrar las diversas alternativas que se tienen en el momento de implementar contenedores de Windows en máquinas virtuales de Azure basadas en Windows Server 2016 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a1375-190">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a1375-191">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a1375-191">Scenarios</span></span>

<span data-ttu-id="a1375-192">En este tutorial se explican varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="a1375-192">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="a1375-193">Escenario A: Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de la conexión del motor de Docker</span><span class="sxs-lookup"><span data-stu-id="a1375-193">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión del motor de Docker](./media/image5-4.png)

<span data-ttu-id="a1375-195">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="a1375-195">**Figure 5-4.**</span></span> <span data-ttu-id="a1375-196">Implementación en una máquina virtual de Azure desde un equipo de desarrollo a través de una conexión del motor de Docker</span><span class="sxs-lookup"><span data-stu-id="a1375-196">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="a1375-197">Escenario B: Implementación en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="a1375-197">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Implementación en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

<span data-ttu-id="a1375-199">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="a1375-199">**Figure 5-5.**</span></span> <span data-ttu-id="a1375-200">Implementación en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="a1375-200">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="a1375-201">Escenario C: Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="a1375-201">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

![Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services](./media/image5-6.png)

<span data-ttu-id="a1375-203">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="a1375-203">**Figure 5-6.**</span></span> <span data-ttu-id="a1375-204">Implementación en una máquina virtual de Azure desde canalizaciones de CI/CD en Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="a1375-204">Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="a1375-205">Máquinas virtuales de Azure para contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="a1375-205">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="a1375-206">Las máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambas con el motor de Docker configurado.</span><span class="sxs-lookup"><span data-stu-id="a1375-206">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="a1375-207">En la mayoría de los casos, se usa Windows Server 2016 en las máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="a1375-207">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="a1375-208">Actualmente, Azure proporciona una máquina virtual llamada **Windows Server 2016 con contenedores**.</span><span class="sxs-lookup"><span data-stu-id="a1375-208">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="a1375-209">Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="a1375-209">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="a1375-210">Se instalan imágenes de sistema operativo de contenedor y, después, la máquina virtual está lista para usarla con Docker.</span><span class="sxs-lookup"><span data-stu-id="a1375-210">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="a1375-211">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-211">Benefits</span></span>

<span data-ttu-id="a1375-212">Aunque los contenedores de Windows se pueden implementar en máquinas virtuales locales con Windows Server 2016, cuando se implementa en Azure, se obtiene una manera más fácil de empezar, con máquinas virtuales de contenedor de Windows Server listas para usar.</span><span class="sxs-lookup"><span data-stu-id="a1375-212">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="a1375-213">También obtiene una ubicación en línea común a la que pueden acceder los evaluadores y la escalabilidad automática a través de conjuntos de escalado de máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="a1375-213">You also get a common online location that's accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-214">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-214">Next steps</span></span>

<span data-ttu-id="a1375-215">Explore este contenido más en profundidad en la wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a1375-215">Explore this content more in-depth on the GitHub wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="a1375-216">Tutorial 4: Implementación de aplicaciones basadas en contenedores de Windows en Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="a1375-216">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a1375-217">Disponibilidad del tutorial técnico</span><span class="sxs-lookup"><span data-stu-id="a1375-217">Technical walkthrough availability</span></span>

<span data-ttu-id="a1375-218">El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a1375-218">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="a1375-219">[Implementación de aplicaciones en ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="a1375-219">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="a1375-220">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-220">Overview</span></span>

<span data-ttu-id="a1375-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) es la manera más rápida de tener un entorno de desarrollo, pruebas y ensayo de contenedores en el que pueda implementar instancias únicas de contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-221">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-222">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-222">Goals</span></span>

<span data-ttu-id="a1375-223">En este tutorial se muestran los principales escenarios en el momento de implementar contenedores de Windows en Azure Container Instances (ACI) y cómo puede implementar aplicaciones de eShopModernizing en ACI.</span><span class="sxs-lookup"><span data-stu-id="a1375-223">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a1375-224">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a1375-224">Scenarios</span></span>

<span data-ttu-id="a1375-225">Puede haber variaciones sobre la implementación de las aplicaciones de eShopModernizing en ACI, como la implementación de solo una o todas las aplicaciones (aplicación MVC, aplicación WebForms o servicio WCF).</span><span class="sxs-lookup"><span data-stu-id="a1375-225">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="a1375-226">En el escenario siguiente puede ver que tanto la aplicación ASP.NET MVC como el contenedor de SQL Server se han implementado como contenedores en ACI (Azure Container Instances).</span><span class="sxs-lookup"><span data-stu-id="a1375-226">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Implementación en ACI desde un entorno de desarrollo](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="a1375-228">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-228">Benefits</span></span>

<span data-ttu-id="a1375-229">Con Azure Container Instances es muy fácil crear y administrar contenedores de Docker en Azure sin tener que aprovisionar máquinas virtuales ni recurrir a un servicio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="a1375-229">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="a1375-230">Con ACI, puede implementar directamente un contenedor de Windows en Azure y exponerlo a Internet con un nombre de dominio completo (FQDN) en cuestión de segundos (siempre que tenga la imagen de contenedor de Windows lista en un registro de Docker, como Docker Hub o Azure Container Registry).</span><span class="sxs-lookup"><span data-stu-id="a1375-230">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="a1375-231">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="a1375-231">Considerations</span></span>

<span data-ttu-id="a1375-232">La implementación de contenedores de Windows con .NET Framework/ASP.NET completo o SQL Server en Azure Container Instances (ACI) no es tan rápida como la implementación en un host de Docker normal (como Windows Server 2016 con contenedores de Windows) porque la imagen de Docker se debe descargar (extraer del registro de Docker) cada vez y los tamaños de la imagen de contenedor de SQL (15,1 GB) y la imagen de contenedor de ASP.NET (13,9 GB) son considerablemente grandes. Sin embargo, es mucho más barato que mantener su propio host de Docker (Windows Server 2016 en línea permanentemente con una máquina virtual de contenedores de Windows en Azure), por no mencionar un orquestador completo como Kubernetes en Azure (AKS) que, por otro lado, es una excelente opción para las implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="a1375-232">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS) which is, on the other hand, a great choice for production deployments.</span></span>

<span data-ttu-id="a1375-233">Como conclusión principal, el uso de Azure Container Instances es una opción muy atractiva para escenarios de desarrollo/pruebas y para canalizaciones de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="a1375-233">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-234">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-234">Next steps</span></span>

<span data-ttu-id="a1375-235">Explore este contenido más en profundidad en la wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a1375-235">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="a1375-236">Tutorial 5: Implementación de aplicaciones basadas en contenedores de Windows en Kubernetes en Azure Container Service</span><span class="sxs-lookup"><span data-stu-id="a1375-236">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a1375-237">Disponibilidad del tutorial técnico</span><span class="sxs-lookup"><span data-stu-id="a1375-237">Technical walkthrough availability</span></span>

<span data-ttu-id="a1375-238">El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a1375-238">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a><span data-ttu-id="a1375-239">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-239">Overview</span></span>

<span data-ttu-id="a1375-240">Una aplicación basada en contenedores de Windows tendrá que usar rápidamente plataformas, con lo que se alejará aún más de las máquinas virtuales de IaaS.</span><span class="sxs-lookup"><span data-stu-id="a1375-240">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="a1375-241">Esto es necesario para lograr fácilmente una alta escalabilidad y mejor escalabilidad automatizada y para obtener una mejora significativa en las implementaciones automatizadas y el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="a1375-241">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="a1375-242">Puede alcanzar estos objetivos si usa el orquestador [Kubernetes](https://kubernetes.io/), disponible en [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="a1375-242">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-243">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-243">Goals</span></span>

<span data-ttu-id="a1375-244">El objetivo de este tutorial es obtener información sobre cómo implementar una aplicación basada en contenedores de Windows en Kubernetes (que también se conocen como *K8s*) en Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="a1375-244">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="a1375-245">La implementación de Kubernetes desde cero es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a1375-245">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1. <span data-ttu-id="a1375-246">Implementar un clúster de Kubernetes en Azure Container Service.</span><span class="sxs-lookup"><span data-stu-id="a1375-246">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2. <span data-ttu-id="a1375-247">Implementar la aplicación y los recursos relacionados en el clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a1375-247">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a1375-248">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a1375-248">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="a1375-249">Escenario A: Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a1375-249">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

<span data-ttu-id="a1375-251">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="a1375-251">**Figure 5-7.**</span></span> <span data-ttu-id="a1375-252">Implementación directa en un clúster de Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a1375-252">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a><span data-ttu-id="a1375-253">Escenario B: Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="a1375-253">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

![Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services](./media/image5-8.png)

<span data-ttu-id="a1375-255">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="a1375-255">**Figure 5-8.**</span></span> <span data-ttu-id="a1375-256">Implementación en un clúster de Kubernetes desde canalizaciones de CI/CD en Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="a1375-256">Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services</span></span>

### <a name="benefits"></a><span data-ttu-id="a1375-257">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-257">Benefits</span></span>

<span data-ttu-id="a1375-258">La implementación en un clúster en Kubernetes tiene muchas ventajas.</span><span class="sxs-lookup"><span data-stu-id="a1375-258">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="a1375-259">La principal es que se obtiene un entorno listo para la producción en el que se puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que se desean usar (escalabilidad interna en los nodos existentes) y según el número de nodos o máquinas virtuales del clúster (escalabilidad global del clúster).</span><span class="sxs-lookup"><span data-stu-id="a1375-259">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="a1375-260">Azure Container Service optimiza las herramientas y tecnologías de código abierto populares específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="a1375-260">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="a1375-261">Se trata de una solución abierta que ofrece la portabilidad de los contenedores y la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1375-261">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="a1375-262">Seleccione el tamaño, el número de hosts y las herramientas de orquestador; Container Service se encarga de todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="a1375-262">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="a1375-263">Con Kubernetes, los desarrolladores pueden progresar desde pensar en máquinas físicas y virtuales hasta planear una infraestructura centrada en contenedores que facilita, entre otras, las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="a1375-263">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="a1375-264">Aplicaciones basadas en varios contenedores</span><span class="sxs-lookup"><span data-stu-id="a1375-264">Applications based on multiple containers</span></span>

- <span data-ttu-id="a1375-265">Replicación de instancias de contenedor y escalado automático horizontal</span><span class="sxs-lookup"><span data-stu-id="a1375-265">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="a1375-266">Asignaciones de nombres y detección (por ejemplo, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="a1375-266">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="a1375-267">Equilibrio de cargas</span><span class="sxs-lookup"><span data-stu-id="a1375-267">Balancing loads</span></span>

- <span data-ttu-id="a1375-268">Actualizaciones graduales</span><span class="sxs-lookup"><span data-stu-id="a1375-268">Rolling updates</span></span>

- <span data-ttu-id="a1375-269">Distribución de secretos</span><span class="sxs-lookup"><span data-stu-id="a1375-269">Distributing secrets</span></span>

- <span data-ttu-id="a1375-270">Comprobaciones de estado de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a1375-270">Application health checks</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-271">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-271">Next steps</span></span>

<span data-ttu-id="a1375-272">Explore este contenido más en profundidad en la wiki de GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span><span class="sxs-lookup"><span data-stu-id="a1375-272">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)></span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a><span data-ttu-id="a1375-273">Tutorial 6: Implementación de aplicaciones basadas en contenedores de Windows en Azure App Service para contenedores</span><span class="sxs-lookup"><span data-stu-id="a1375-273">Walkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a1375-274">Disponibilidad del tutorial técnico</span><span class="sxs-lookup"><span data-stu-id="a1375-274">Technical walkthrough availability</span></span>

<span data-ttu-id="a1375-275">El tutorial técnico completo está disponible en la wiki del repositorio de GitHub eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a1375-275">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a><span data-ttu-id="a1375-276">Información general</span><span class="sxs-lookup"><span data-stu-id="a1375-276">Overview</span></span>

<span data-ttu-id="a1375-277">Una aplicación sencilla en contenedor que usa contenedores de Windows se puede implementar fácilmente en Azure App Service para contenedores.</span><span class="sxs-lookup"><span data-stu-id="a1375-277">A simple containerized application using Windows Containers can easily be deployed to Azure App Service for Containers.</span></span> <span data-ttu-id="a1375-278">Este es el enfoque recomendado para la mayoría de las aplicaciones basadas en contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="a1375-278">This is the recommended approach for most Windows Container-based applications.</span></span>

### <a name="goals"></a><span data-ttu-id="a1375-279">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a1375-279">Goals</span></span>

<span data-ttu-id="a1375-280">El objetivo de este tutorial es aprender a implementar una aplicación basada en contenedores de Windows en Azure App Service para contenedores de un registro (Docker Hub o Azure Container Registry).</span><span class="sxs-lookup"><span data-stu-id="a1375-280">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Azure App Service for Containers from a registry (Docker Hub or Azure Container Registry).</span></span>

### <a name="scenario"></a><span data-ttu-id="a1375-281">Escenario</span><span class="sxs-lookup"><span data-stu-id="a1375-281">Scenario</span></span>

![Implementación de una aplicación basada en contenedores de Windows en Azure App Service para contenedores](./media/image5-11.png)

### <a name="benefits"></a><span data-ttu-id="a1375-283">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a1375-283">Benefits</span></span>

<span data-ttu-id="a1375-284">La implementación en Azure App Service para contenedores ofrece las ventajas de los contenedores junto con las ventajas de PaaS de Azure App Service.</span><span class="sxs-lookup"><span data-stu-id="a1375-284">Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service.</span></span> <span data-ttu-id="a1375-285">El servicio de aplicación se puede escalar fácilmente de manera vertical y horizontal y puede configurarse para ajustarlo automáticamente a las exigencias cambiantes.</span><span class="sxs-lookup"><span data-stu-id="a1375-285">The app service can easily be scaled both vertically and horizontally, and can be configured to autoscale to meet changing demands.</span></span> <span data-ttu-id="a1375-286">Las actualizaciones se pueden realizar sin tiempo de inactividad y la configuración de la implementación continua desde un registro también se configura fácilmente.</span><span class="sxs-lookup"><span data-stu-id="a1375-286">Updates can be performed with zero downtime and configuration of continuous deployment from a registry is easily configured as well.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a1375-287">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a1375-287">Next steps</span></span>

<span data-ttu-id="a1375-288">Explore este contenido más en profundidad en la wiki de GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span><span class="sxs-lookup"><span data-stu-id="a1375-288">Explore this content more in-depth on the GitHub wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service></span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="a1375-289">[Anterior](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Siguiente](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="a1375-289">[Previous](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span> <!-- Next Chapter -->
