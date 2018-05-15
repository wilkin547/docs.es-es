---
title: Tutoriales y technical obtienen información general de introducción
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Tutoriales y technical obtienen información general de introducción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 27de9d1c5475855a22f2d8a3518982605277f6d9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="a5e03-103">Tutoriales y technical obtienen información general de introducción</span><span class="sxs-lookup"><span data-stu-id="a5e03-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="a5e03-104">Para limitar el tamaño de este libro electrónico, documentación técnica adicional y los tutoriales completos se encontraban disponibles en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a5e03-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="a5e03-105">La serie de tutoriales que se describen en este capítulo en línea trata el programa de instalación paso a paso de los entornos de varios que se basan en los contenedores de Windows y la implementación en Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="a5e03-106">Las siguientes secciones explican lo que cada tutorial trata sobre sus objetivos y la visión de alto nivel y proporciona un diagrama de las tareas que están implicados.</span><span class="sxs-lookup"><span data-stu-id="a5e03-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="a5e03-107">Puede obtener los tutoriales por sí mismos en el *eShopModernizing* wiki de repositorio de GitHub de aplicaciones en [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="a5e03-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="a5e03-108">Lista de tutoriales técnicos</span><span class="sxs-lookup"><span data-stu-id="a5e03-108">Technical walkthrough list</span></span>

<span data-ttu-id="a5e03-109">Los siguientes tutoriales iniciada por get proporcionan orientación técnica de coherente y completo para las aplicaciones de ejemplo que puede levantar y desplazar mediante el uso de contenedores y, a continuación, mueva con varias opciones de implementación de Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="a5e03-110">Cada uno de los siguientes tutoriales utiliza el nuevo eShopLegacy y eShopModernizing aplicaciones de ejemplo, que están disponibles en GitHub en [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="a5e03-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="a5e03-111">**Paseo por aplicaciones heredadas de compras (aplicaciones de línea de base para modernizar)**</span><span class="sxs-lookup"><span data-stu-id="a5e03-111">**Tour of eShop legacy apps (baseline apps to modernize)**</span></span>

- <span data-ttu-id="a5e03-112">**Incluya las aplicaciones web existentes en ASP.NET (formularios Web Forms y MVC) con contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="a5e03-112">**Containerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**</span></span>

- <span data-ttu-id="a5e03-113">**Incluya los servicios WCF existentes (aplicaciones de N niveles) con contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="a5e03-113">**Containerize your existing WCF services (N-Tier apps) with Windows Containers**</span></span>

- <span data-ttu-id="a5e03-114">**Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure**</span><span class="sxs-lookup"><span data-stu-id="a5e03-114">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="a5e03-115">**Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure**</span><span class="sxs-lookup"><span data-stu-id="a5e03-115">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="a5e03-116">**Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-116">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="a5e03-117">Tutorial 1: Paseo de compras de aplicaciones heredadas</span><span class="sxs-lookup"><span data-stu-id="a5e03-117">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a5e03-118">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="a5e03-118">Technical walkthrough availability</span></span>

<span data-ttu-id="a5e03-119">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a5e03-119">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="a5e03-120">tutoriales de wiki de eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="a5e03-120">eShopModernizing wiki walkthroughs</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a><span data-ttu-id="a5e03-121">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-121">Overview</span></span>

<span data-ttu-id="a5e03-122">En este tutorial, puede explorar la implementación inicial de tres aplicaciones heredadas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5e03-122">In this walkthrough, you can explore the initial implementation of three sample legacy applications.</span></span> <span data-ttu-id="a5e03-123">Las dos primeras aplicaciones web de ejemplo tienen una arquitectura monolítica y creadas utilizando ASP.NET clásico.</span><span class="sxs-lookup"><span data-stu-id="a5e03-123">The first two sample web apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="a5e03-124">Una aplicación se basa en ASP.NET 4.x MVC; la segunda aplicación se basa en formularios Web Forms ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="a5e03-124">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="a5e03-125">La tercera aplicación es una aplicación de 3 niveles compuesta por una aplicación de formularios Windows Forms de cliente y un servidor [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) servicio.</span><span class="sxs-lookup"><span data-stu-id="a5e03-125">The third app is a 3-Tier app composed by a client WinForms app and a server-side [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) service.</span></span>

<span data-ttu-id="a5e03-126">Todas estas aplicaciones están disponibles en la [repositorio de GitHub de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="a5e03-126">All these applications are available at the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-127">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-127">Goals</span></span>

<span data-ttu-id="a5e03-128">El objetivo principal de este tutorial es simplemente para familiarizarse con estas aplicaciones y con su código y la configuración.</span><span class="sxs-lookup"><span data-stu-id="a5e03-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="a5e03-129">Puede configurar las aplicaciones para que puedan generarán y utilizar los datos simulados, sin utilizar la base de datos SQL, con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="a5e03-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="a5e03-130">Esta configuración opcional se basa en la inserción de dependencias, de una manera desconectada.</span><span class="sxs-lookup"><span data-stu-id="a5e03-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario-1-aspnet-web-apps"></a><span data-ttu-id="a5e03-131">Escenario 1: Las aplicaciones Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a5e03-131">Scenario 1: ASP.NET Web apps</span></span>

<span data-ttu-id="a5e03-132">La siguiente ilustración muestra el escenario sencillo de las aplicaciones de web ASP.NET heredados originales.</span><span class="sxs-lookup"><span data-stu-id="a5e03-132">The figure below shows the simple scenario of the original legacy ASP.NET web applications.</span></span>

> ![Escenario de arquitectura simple de la original heredado las aplicaciones web ASP.NET](./media/image5-1.png)
>

<span data-ttu-id="a5e03-134">Desde una perspectiva de dominio empresarial, ambas aplicaciones ofrecen el mismo catálogo de características de administración.</span><span class="sxs-lookup"><span data-stu-id="a5e03-134">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="a5e03-135">Los miembros del equipo de enterprise compras utilizaría la aplicación para ver y editar el catálogo de productos.</span><span class="sxs-lookup"><span data-stu-id="a5e03-135">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> 

<span data-ttu-id="a5e03-136">La ilustración siguiente muestra las capturas de pantalla de la aplicación inicial.</span><span class="sxs-lookup"><span data-stu-id="a5e03-136">The next figure shows the initial app screenshots.</span></span>

![Aplicaciones de MVC de ASP.NET y formularios Web Forms de ASP.NET (tecnologías existentes/heredado)](./media/image5-2.png)

<span data-ttu-id="a5e03-138">Dependencias en ASP.NET 4.x o versiones anteriores (ya sea para MVC o Web Forms) significa que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se ha reescrito completamente mediante el uso de núcleo de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="a5e03-138">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won’t run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a><span data-ttu-id="a5e03-139">Escenario 2: Servicio WCF y aplicación de cliente de WinForms (aplicación de nivel 3)</span><span class="sxs-lookup"><span data-stu-id="a5e03-139">Scenario 2: WCF service and WinForms client app (3-Tier app)</span></span>

<span data-ttu-id="a5e03-140">La siguiente ilustración muestra el escenario sencillo de la aplicación heredada de 3 niveles original.</span><span class="sxs-lookup"><span data-stu-id="a5e03-140">The figure below shows the simple scenario of the original 3-Tier legacy application.</span></span>

> ![Escenario de arquitectura simple de la aplicación de 3 niveles heredada original con un servicio WCF y una aplicación de cliente de WinForms](./media/image5-1.5.png)
>

### <a name="benefits"></a><span data-ttu-id="a5e03-142">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-142">Benefits</span></span>

<span data-ttu-id="a5e03-143">Las ventajas de este tutorial son sencillas: simplemente familiarizarse con el código y aplicaciones iniciales.</span><span class="sxs-lookup"><span data-stu-id="a5e03-143">The benefits of this walkthrough are simple: Just get familiar with the code and initial apps.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a5e03-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-144">Next steps</span></span>

<span data-ttu-id="a5e03-145">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a5e03-145">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="a5e03-146">La visita de la línea de base de ASP.NET MVC y aplicaciones de formularios Web Forms "heredadas"</span><span class="sxs-lookup"><span data-stu-id="a5e03-146">Tour on the baseline ASP.NET MVC and Web Forms “legacy” apps</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [<span data-ttu-id="a5e03-147">Paseo en el servicio WCF de línea de base y la aplicación de formularios Windows Forms (nivel 3) "heredado"</span><span class="sxs-lookup"><span data-stu-id="a5e03-147">Tour on the baseline WCF service and WinForms (3-Tier) “legacy” app</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="a5e03-148">Tutorial 2: Incluya las aplicaciones de .NET existentes con contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="a5e03-148">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="overview"></a><span data-ttu-id="a5e03-149">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-149">Overview</span></span>

<span data-ttu-id="a5e03-150">Utilice contenedores de Windows para mejorar la implementación de aplicaciones .NET existentes, como las basadas en MVC, formularios Web Forms o WCF, para entornos de prueba, desarrollo y producción.</span><span class="sxs-lookup"><span data-stu-id="a5e03-150">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-151">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-151">Goals</span></span>

<span data-ttu-id="a5e03-152">El objetivo de este tutorial es mostrar varias opciones para containerizing una aplicación existente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5e03-152">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="a5e03-153">Puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5e03-153">You can:</span></span>

- <span data-ttu-id="a5e03-154">Incluya la aplicación mediante el uso de [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (2017 de Visual Studio o versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="a5e03-154">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="a5e03-155">Incluya la aplicación agregando manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)y, a continuación, usar el [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="a5e03-155">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="a5e03-156">Incluya la aplicación mediante el uso de la [Img2Docker](https://github.com/docker/communitytools-image2docker-win) herramienta (una herramienta de código abierto de Docker).</span><span class="sxs-lookup"><span data-stu-id="a5e03-156">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="a5e03-157">En este tutorial se centra en Visual Studio de 2017 Tools para el enfoque de Docker, pero los otros dos enfoques son muy parecidos en relación con usando Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="a5e03-157">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario-1-containerized-aspnet-web-apps"></a><span data-ttu-id="a5e03-158">Escenario 1: Aplicaciones web ASP.NET en contenedores</span><span class="sxs-lookup"><span data-stu-id="a5e03-158">Scenario 1: Containerized ASP.NET web apps</span></span>

<span data-ttu-id="a5e03-159">La figura siguiente muestra el escenario para aplicaciones de aplicaciones web heredadas de compras en contenedores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-159">Figure below shows the scenario for containerized eShop legacy web apps applications.</span></span>

> ![Diagrama de arquitectura simplificada de en contenedores de aplicaciones de ASP.NET en un entorno de desarrollo](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a><span data-ttu-id="a5e03-161">Escenario 2: Servicio WCF en contenedores</span><span class="sxs-lookup"><span data-stu-id="a5e03-161">Scenario 2: Containerized WCF service</span></span>

<span data-ttu-id="a5e03-162">La figura siguiente muestra el escenario para una aplicación de 3 niveles con un servicio WCF en contenedores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-162">Figure below shows the scenario for a 3-Tier app with a containerized WCF service.</span></span> 

> ![Diagrama de arquitectura de servicio WCF en contenedores en un entorno de desarrollo ha simplificado](./media/image5-3.5.png)
>

### <a name="benefits"></a><span data-ttu-id="a5e03-164">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-164">Benefits</span></span>

<span data-ttu-id="a5e03-165">Existen ventajas a la ejecución de la aplicación monolítica en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="a5e03-165">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="a5e03-166">En primer lugar, cree una imagen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5e03-166">First, you create an image for the application.</span></span> <span data-ttu-id="a5e03-167">Desde ese momento, cada implementación se ejecuta en el mismo entorno.</span><span class="sxs-lookup"><span data-stu-id="a5e03-167">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="a5e03-168">Cada contenedor usa la misma versión de sistema operativo, tiene la misma versión de dependencias instalada, usa la misma versión de .NET framework y se compila mediante el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="a5e03-168">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="a5e03-169">Básicamente, controlar las dependencias de la aplicación mediante una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="a5e03-169">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="a5e03-170">Las dependencias de viajan con la aplicación al implementar los contenedores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-170">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="a5e03-171">Otra ventaja adicional es que los programadores pueden ejecutar la aplicación en el entorno coherente que se ofrecen los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="a5e03-171">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="a5e03-172">Los problemas que aparezcan únicamente con determinadas versiones se pueden observar inmediatamente, en lugar de así como la exposición en un entorno de ensayo o de producción.</span><span class="sxs-lookup"><span data-stu-id="a5e03-172">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="a5e03-173">Las diferencias en los entornos de desarrollo que usan los miembros del equipo de desarrollo importan menor cuando las aplicaciones que se ejecutan en ellos.</span><span class="sxs-lookup"><span data-stu-id="a5e03-173">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="a5e03-174">Aplicaciones en contenedores también tienen una curva de escalado horizontal más plana.</span><span class="sxs-lookup"><span data-stu-id="a5e03-174">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="a5e03-175">Aplicaciones en contenedores le permiten tener más aplicaciones e instancias de servicio (basados en contenedores) en una máquina virtual o la máquina física en comparación con las implementaciones de aplicaciones normal por máquina.</span><span class="sxs-lookup"><span data-stu-id="a5e03-175">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="a5e03-176">Esto se traduce en mayor densidad y menos requiere recursos, especialmente cuando se usa orchestrators como Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="a5e03-176">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="a5e03-177">Inclusión en contenedores, en situaciones ideales, no requiere realizar cambios en el código de aplicación (C\#).</span><span class="sxs-lookup"><span data-stu-id="a5e03-177">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="a5e03-178">En la mayoría de los escenarios, solo tiene los archivos de metadatos de implementación de Docker (archivos Dockerfiles y Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="a5e03-178">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="a5e03-179">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-179">Next steps</span></span>

<span data-ttu-id="a5e03-180">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a5e03-180">Explore this content more in-depth on the GitHub wiki:</span></span>

  - [<span data-ttu-id="a5e03-181">Cómo incluya las aplicaciones web de .NET Framework con contenedores de Windows y Docker</span><span class="sxs-lookup"><span data-stu-id="a5e03-181">How to containerize the .NET Framework web apps with Windows Containers and Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [<span data-ttu-id="a5e03-182">Agregar compatibilidad de Docker a un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="a5e03-182">Adding Docker Support to a WCF service</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="a5e03-183">Tutorial 3: Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure</span><span class="sxs-lookup"><span data-stu-id="a5e03-183">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a5e03-184">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="a5e03-184">Technical walkthrough availability</span></span>

<span data-ttu-id="a5e03-185">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="a5e03-185">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="a5e03-186">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-186">Overview</span></span>

<span data-ttu-id="a5e03-187">Implementación en un host de Docker en una máquina Virtual de 2016 de servidor de Windows (VM) de Azure le permite configurar rápidamente entornos de desarrollo/pruebas/staging.</span><span class="sxs-lookup"><span data-stu-id="a5e03-187">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="a5e03-188">También proporciona un lugar común para evaluadores o los usuarios empresariales validar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5e03-188">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="a5e03-189">Máquinas virtuales también pueden ser infraestructura válido como un entorno de producción del servicio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="a5e03-189">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-190">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-190">Goals</span></span>

<span data-ttu-id="a5e03-191">El objetivo de este tutorial es mostrar las alternativas varios que tiene al implementar contenedores de Windows en las máquinas virtuales de Azure que se basan en Windows Server 2016 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-191">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a5e03-192">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a5e03-192">Scenarios</span></span>

<span data-ttu-id="a5e03-193">En este tutorial se tratan varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="a5e03-193">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="a5e03-194">Escenario A: implementar en una VM de Azure desde un equipo de desarrollo a través de la conexión con el motor de Docker</span><span class="sxs-lookup"><span data-stu-id="a5e03-194">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker](./media/image5-4.png)

> <span data-ttu-id="a5e03-196">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-196">**Figure 5-4.**</span></span> <span data-ttu-id="a5e03-197">Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker</span><span class="sxs-lookup"><span data-stu-id="a5e03-197">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="a5e03-198">Escenario B: implementar en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="a5e03-198">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Implementar en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

> <span data-ttu-id="a5e03-200">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-200">**Figure 5-5.**</span></span> <span data-ttu-id="a5e03-201">Implementar en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="a5e03-201">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="a5e03-202">Escenario C: implementar en una VM de Azure desde el elemento de configuración/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-202">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="a5e03-204">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="a5e03-204">**Figure 5-6.**</span></span> <span data-ttu-id="a5e03-205">Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-205">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="a5e03-206">Máquinas virtuales de Azure para los contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="a5e03-206">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="a5e03-207">Máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambos con el motor de Docker configurar.</span><span class="sxs-lookup"><span data-stu-id="a5e03-207">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="a5e03-208">En la mayoría de los casos, se utiliza Windows Server 2016 en las máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-208">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="a5e03-209">Actualmente, Azure proporciona una máquina virtual denominada **Windows Server 2016 con contenedores**.</span><span class="sxs-lookup"><span data-stu-id="a5e03-209">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="a5e03-210">Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="a5e03-210">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="a5e03-211">Imágenes del sistema operativo de contenedor se instalan y, a continuación, la máquina virtual está lista para su uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="a5e03-211">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="a5e03-212">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-212">Benefits</span></span>

<span data-ttu-id="a5e03-213">Aunque los contenedores de Windows se pueden implementar en local 2016 máquinas virtuales Windows Server, cuando se implementa en Azure, obtendrá una manera más fácil para empezar a trabajar con máquinas virtuales de contenedor de listos para usar Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a5e03-213">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="a5e03-214">También obtendrá una ubicación en línea común que es accesible para evaluadores y escalabilidad automática a través de conjuntos de escalas de máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-214">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a5e03-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-215">Next steps</span></span>

<span data-ttu-id="a5e03-216">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a5e03-216">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a><span data-ttu-id="a5e03-217">Tutorial 4: Implementar las aplicaciones de Windows basada en contenedores en instancias de contenedor de Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="a5e03-217">Walkthrough 4: Deploy your Windows Containers-based apps to Azure Container Instances (ACI)</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a5e03-218">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="a5e03-218">Technical walkthrough availability</span></span>

<span data-ttu-id="a5e03-219">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a5e03-219">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="a5e03-220">[Implementar las aplicaciones en ACI (instancias de contenedor de Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span><span class="sxs-lookup"><span data-stu-id="a5e03-220">[Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))</span></span>

### <a name="overview"></a><span data-ttu-id="a5e03-221">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-221">Overview</span></span>

<span data-ttu-id="a5e03-222">[Instancias de contenedor de Azure (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) es la forma más rápida con un entorno de desarrollo/pruebas/staging contenedores en el que puede implementar instancias únicas de contenedores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-222">[Azure Container Instances (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) is the quickest way to have a Containers dev/test/staging environment where you can deploy single instances of containers.</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-223">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-223">Goals</span></span>

<span data-ttu-id="a5e03-224">Este tutorial muestra los principales escenarios que al implementar contenedores de Windows para instancias de contenedor de Azure (ACI) y cómo puede implementar aplicaciones eShopModernizing en ACI.</span><span class="sxs-lookup"><span data-stu-id="a5e03-224">This walkthrough shows you the main scenarios when deploying Windows Containers to Azure Container Instances (ACI) and how you can deploy eShopModernizing Apps into ACI.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a5e03-225">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a5e03-225">Scenarios</span></span>

<span data-ttu-id="a5e03-226">Puede haber variaciones sobre cómo implementar las aplicaciones de eShopModernizing en ACI como la implementación de uno o todos los de las aplicaciones (aplicaciones MVC, aplicación de formularios Web Forms o servicio WCF).</span><span class="sxs-lookup"><span data-stu-id="a5e03-226">There can be variations about deploying the eShopModernizing apps into ACI such as deploying just one or all of the apps (MVC app, WebForms app or WCF service).</span></span> <span data-ttu-id="a5e03-227">En el siguiente escenario que se muestra a continuación puede ver la aplicación de ASP.NET MVC y el contenedor de SQL Server de ellos implementan como contenedores en ACI (instancias de contenedor de Azure).</span><span class="sxs-lookup"><span data-stu-id="a5e03-227">In the following scenario shown below you can see the ASP.NET MVC app plus the SQL Server container both of them deployed as containers into ACI (Azure Container Instances).</span></span>

![Implementar en ACI desde un entorno de desarrollo](./media/image5-3.5.6.png)

### <a name="benefits"></a><span data-ttu-id="a5e03-229">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-229">Benefits</span></span>

<span data-ttu-id="a5e03-230">Instancias de contenedor Azure resulta muy sencillo crear y administrar contenedores de Docker en Azure, sin tener que aprovisionar máquinas virtuales o adoptar un servicio de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="a5e03-230">Azure Container Instances makes it easy to create and manage Docker containers in Azure, without having to provision virtual machines or adopt a higher-level service.</span></span> <span data-ttu-id="a5e03-231">Con ACI, se puede implementar un contenedor de Windows en Azure directamente y exponerlo a internet con un nombre de dominio completo (FQDN) en cuestión de segundos (siempre que tenga la imagen de contenedor de Windows listo en un registro de Docker como Docker Hub o un contenedor de Azure Registro).</span><span class="sxs-lookup"><span data-stu-id="a5e03-231">With ACI, you can directly deploy a Windows container in Azure and expose it to the internet with a fully qualified domain name (FQDN) in a matter of seconds (Provided that you have the Windows Container image ready in a Docker registry like Docker Hub or Azure Container Registry).</span></span>

### <a name="considerations"></a><span data-ttu-id="a5e03-232">Consideraciones</span><span class="sxs-lookup"><span data-stu-id="a5e03-232">Considerations</span></span>

<span data-ttu-id="a5e03-233">Implementar contenedores de Windows con cualquier versión completa de .NET Framework o ASP.NET o SQL Server en instancias de contenedor de Azure (ACI) no es bastante tan rápido como la implementación en un Host Docker normales (por ejemplo, Windows Server 2016 con contenedores de Windows) porque la imagen de Docker debe ser Descargar (extraigan desde el registro de Docker) cada vez y los tamaños de la imagen de contenedor SQL (15.1 GB) y la imagen de contenedor ASP.NET (13.9 GB) son significativamente grandes, sin embargo, es mucho más costoso que el mantenimiento de su propio host de docker (permanentemente en línea Windows Server 2016 con la máquina virtual de contenedores de Windows en Azure) no para hacer mención a un orchestrator todo como Kubernetes en Azure (AKS/ACS) o Azure Service Fabric que son, por otro lado, las opciones excelentes para las implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="a5e03-233">Deploying Windows Containers with either full .NET Framework / ASP.NET or SQL Server into Azure Container Instances (ACI) is not quite as fast as deploying to a regular Docker Host (like a Windows Server 2016 with Windows Containers) because the Docker image has to be downloaded (pulled from the Docker registry) every time and the sizes of the SQL container image (15.1 GB) and the ASP.NET container image (13.9 GB) are significantly large, however it is much cheaper than maintaining your own docker host (permanently on-line Windows Server 2016 with Windows Containers VM in Azure) not to mention a whole orchestrator like Kubernetes in Azure (AKS/ACS) or Azure Service Fabric which are, on the other hand, great choices for production deployments.</span></span>

<span data-ttu-id="a5e03-234">Como término principal, con instancias de contenedor de Azure es una opción muy atractiva para escenarios de desarrollo/pruebas y para las canalizaciones de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="a5e03-234">As main conclusion, using Azure Container Instances is a very compelling option for Dev/Test scenarios and for CI/CD pipelines.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5e03-235">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-235">Next steps</span></span>

<span data-ttu-id="a5e03-236">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a5e03-236">Explore this content more in-depth on the GitHub wiki:</span></span> 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="a5e03-237">Tutorial 5: Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure</span><span class="sxs-lookup"><span data-stu-id="a5e03-237">Walkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a5e03-238">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="a5e03-238">Technical walkthrough availability</span></span>

<span data-ttu-id="a5e03-239">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a5e03-239">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="a5e03-240">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-240">Overview</span></span>

<span data-ttu-id="a5e03-241">Una aplicación que se basa en los contenedores de Windows rápidamente necesite usan las plataformas, aleja el aún más de las máquinas virtuales IaaS.</span><span class="sxs-lookup"><span data-stu-id="a5e03-241">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="a5e03-242">Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones.</span><span class="sxs-lookup"><span data-stu-id="a5e03-242">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="a5e03-243">Puede lograr estos objetivos utilizando el orchestrator [Kubernetes](https://kubernetes.io/), disponible en [servicios de contenedor de Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="a5e03-243">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-244">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-244">Goals</span></span>

<span data-ttu-id="a5e03-245">El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows para Kubernetes (también denominada *K8s*) en el servicio de contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-245">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="a5e03-246">Implementación a Kubernetes desde cero es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5e03-246">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="a5e03-247">Implementar un clúster de Kubernetes al servicio de contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-247">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="a5e03-248">Implementar la aplicación y los recursos relacionados en el clúster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a5e03-248">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a5e03-249">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a5e03-249">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="a5e03-250">Escenario A: implementar directamente a un clúster de Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a5e03-250">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

> <span data-ttu-id="a5e03-252">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-252">**Figure 5-7.**</span></span> <span data-ttu-id="a5e03-253">Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a5e03-253">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="a5e03-254">Escenario B: implementar en un clúster Kubernetes desde el elemento de configuración/CD canalizaciones en Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-254">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services](./media/image5-8.png)

> <span data-ttu-id="a5e03-256">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-256">**Figure 5-8.**</span></span> <span data-ttu-id="a5e03-257">Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-257">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="a5e03-258">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-258">Benefits</span></span>

<span data-ttu-id="a5e03-259">Hay muchas ventajas a la implementación en un clúster en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a5e03-259">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="a5e03-260">La mayor ventaja es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de nodos o máquinas virtuales en el clúster ( escalabilidad global del clúster).</span><span class="sxs-lookup"><span data-stu-id="a5e03-260">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="a5e03-261">Servicio de contenedor de Azure optimiza las tecnologías y herramientas de código abierto populares específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-261">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="a5e03-262">Obtener una solución abierta que ofrece la portabilidad tanto para los contenedores de la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5e03-262">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="a5e03-263">Seleccione el tamaño, el número de hosts, y el servicio de contenedor-herramientas de orchestrator controla todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="a5e03-263">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="a5e03-264">Con Kubernetes, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales, para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:</span><span class="sxs-lookup"><span data-stu-id="a5e03-264">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="a5e03-265">Aplicaciones basadas en varios contenedores</span><span class="sxs-lookup"><span data-stu-id="a5e03-265">Applications based on multiple containers</span></span>

- <span data-ttu-id="a5e03-266">La replicación de instancias de contenedor y ajuste automático de escala horizontal</span><span class="sxs-lookup"><span data-stu-id="a5e03-266">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="a5e03-267">Nomenclatura y detectar (por ejemplo, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="a5e03-267">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="a5e03-268">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="a5e03-268">Balancing loads</span></span>

- <span data-ttu-id="a5e03-269">Actualizaciones graduales</span><span class="sxs-lookup"><span data-stu-id="a5e03-269">Rolling updates</span></span>

- <span data-ttu-id="a5e03-270">Distribuir secretos</span><span class="sxs-lookup"><span data-stu-id="a5e03-270">Distributing secrets</span></span>

- <span data-ttu-id="a5e03-271">Comprobaciones de estado de aplicación</span><span class="sxs-lookup"><span data-stu-id="a5e03-271">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5e03-272">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-272">Next steps</span></span>

<span data-ttu-id="a5e03-273">Explorar este contenido más detallada en el sitio wiki de GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="a5e03-273">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="a5e03-274">Tutorial 6: Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="a5e03-274">Walkthrough 6: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="a5e03-275">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="a5e03-275">Technical walkthrough availability</span></span>

<span data-ttu-id="a5e03-276">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="a5e03-276">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="a5e03-277">Información general</span><span class="sxs-lookup"><span data-stu-id="a5e03-277">Overview</span></span>

<span data-ttu-id="a5e03-278">Una aplicación basada en los contenedores de Windows rápidamente debe usar plataformas, aleja el aún más de las máquinas virtuales IaaS.</span><span class="sxs-lookup"><span data-stu-id="a5e03-278">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="a5e03-279">Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones.</span><span class="sxs-lookup"><span data-stu-id="a5e03-279">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="a5e03-280">Puede lograr estos objetivos con el orchestrator Azure Service Fabric, que está disponible en la nube de Azure, pero también disponible para su uso local, o incluso en una nube pública diferente.</span><span class="sxs-lookup"><span data-stu-id="a5e03-280">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="a5e03-281">Objetivos</span><span class="sxs-lookup"><span data-stu-id="a5e03-281">Goals</span></span>

<span data-ttu-id="a5e03-282">El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows a un clúster de Service Fabric en Azure.</span><span class="sxs-lookup"><span data-stu-id="a5e03-282">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="a5e03-283">Implementación a Service Fabric desde cero es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="a5e03-283">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="a5e03-284">Implementar un clúster de Service Fabric en Azure (o en un entorno diferente).</span><span class="sxs-lookup"><span data-stu-id="a5e03-284">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="a5e03-285">Implementar la aplicación y los recursos relacionados en el clúster de Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="a5e03-285">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="a5e03-286">Escenarios</span><span class="sxs-lookup"><span data-stu-id="a5e03-286">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="a5e03-287">Escenario A: implementar directamente a un clúster de Service Fabric desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a5e03-287">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo](./media/image5-9.png)

> <span data-ttu-id="a5e03-289">**Figura 5-9.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-289">**Figure 5-9.**</span></span> <span data-ttu-id="a5e03-290">Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a5e03-290">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="a5e03-291">Escenario B: implementar en un clúster de Service Fabric desde el elemento de configuración/CD canalizaciones en Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-291">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="a5e03-293">**Figura 5-10.**</span><span class="sxs-lookup"><span data-stu-id="a5e03-293">**Figure 5-10.**</span></span> <span data-ttu-id="a5e03-294">Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="a5e03-294">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="a5e03-295">Ventajas</span><span class="sxs-lookup"><span data-stu-id="a5e03-295">Benefits</span></span>

<span data-ttu-id="a5e03-296">Las ventajas de la implementación en un clúster de Service Fabric son similares a las ventajas de usar Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="a5e03-296">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="a5e03-297">Sin embargo, no obstante, es que Service Fabric es un entorno de producción más maduro para aplicaciones de Windows en comparación con Kubernetes, que se encuentra en una fase beta para contenedores de Windows en Kubernetes versión 1.9 (diciembre de 2017).</span><span class="sxs-lookup"><span data-stu-id="a5e03-297">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="a5e03-298">Kubernetes es un entorno más maduro para Linux.</span><span class="sxs-lookup"><span data-stu-id="a5e03-298">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="a5e03-299">La principal ventaja del uso de Azure Service Fabric es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de los nodos o máquinas virtuales del clúster (escalabilidad global del clúster).</span><span class="sxs-lookup"><span data-stu-id="a5e03-299">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="a5e03-300">Azure Service Fabric ofrece portabilidad de los contenedores y para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5e03-300">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="a5e03-301">Puede tener un tejido de servicio de clúster en Azure, o instalar localmente en su propio centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a5e03-301">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="a5e03-302">Incluso puede instalar un clúster de Service Fabric en una nube diferente, como [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="a5e03-302">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="a5e03-303">Con Service Fabric, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:</span><span class="sxs-lookup"><span data-stu-id="a5e03-303">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="a5e03-304">Aplicaciones basadas en varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="a5e03-304">Applications based on multiple containers.</span></span>

- <span data-ttu-id="a5e03-305">Replicación de instancias de contenedor y ajuste automático de escala horizontal.</span><span class="sxs-lookup"><span data-stu-id="a5e03-305">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="a5e03-306">Nomenclatura y detectar (por ejemplo, DNS interno).</span><span class="sxs-lookup"><span data-stu-id="a5e03-306">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="a5e03-307">Equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="a5e03-307">Balancing loads.</span></span>

- <span data-ttu-id="a5e03-308">Actualizaciones graduales.</span><span class="sxs-lookup"><span data-stu-id="a5e03-308">Rolling updates.</span></span>

- <span data-ttu-id="a5e03-309">Distribuir secretos.</span><span class="sxs-lookup"><span data-stu-id="a5e03-309">Distributing secrets.</span></span>

- <span data-ttu-id="a5e03-310">Comprueba el estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5e03-310">Application health checks.</span></span>

<span data-ttu-id="a5e03-311">Las siguientes capacidades son exclusivas de Service Fabric (en comparación con otras orchestrators):</span><span class="sxs-lookup"><span data-stu-id="a5e03-311">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="a5e03-312">Capacidad de servicios con estado, a través del modelo de aplicación de servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="a5e03-312">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="a5e03-313">Patrón de actores a través del modelo de aplicación de Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="a5e03-313">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="a5e03-314">Implementar procesos descubierto, además de los contenedores de Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="a5e03-314">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="a5e03-315">Advanced actualizaciones graduales y comprobaciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="a5e03-315">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="a5e03-316">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a5e03-316">Next steps</span></span>

<span data-ttu-id="a5e03-317">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="a5e03-317">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="a5e03-318">[Anterior](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Siguiente](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="a5e03-318">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
