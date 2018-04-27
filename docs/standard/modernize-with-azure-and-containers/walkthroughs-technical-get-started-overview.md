---
title: Tutoriales y technical obtienen información general de introducción
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | tutoriales y technical obtienen información general de introducción
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0bad7e3afbdf3e55c447319b3756f2235b9e0a19
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="acdb1-103">Tutoriales y technical obtienen información general de introducción</span><span class="sxs-lookup"><span data-stu-id="acdb1-103">Walkthroughs and technical get started overview</span></span>

<span data-ttu-id="acdb1-104">Para limitar el tamaño de este libro electrónico, documentación técnica adicional y los tutoriales completos se encontraban disponibles en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="acdb1-104">To limit the size of this e-book, additional technical documentation and the full walkthroughs were made available in a GitHub repository.</span></span> <span data-ttu-id="acdb1-105">La serie de tutoriales que se describen en este capítulo en línea trata el programa de instalación paso a paso de los entornos de varios que se basan en los contenedores de Windows y la implementación en Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="acdb1-106">Las siguientes secciones explican lo que cada tutorial trata sobre sus objetivos y la visión de alto nivel y proporciona un diagrama de las tareas que están implicados.</span><span class="sxs-lookup"><span data-stu-id="acdb1-106">The following sections explain what each walkthrough is about, its objectives and high-level vision, and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="acdb1-107">Puede obtener los tutoriales por sí mismos en el *eShopModernizing* wiki de repositorio de GitHub de aplicaciones en [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span><span class="sxs-lookup"><span data-stu-id="acdb1-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

## <a name="technical-walkthrough-list"></a><span data-ttu-id="acdb1-108">Lista de tutoriales técnicos</span><span class="sxs-lookup"><span data-stu-id="acdb1-108">Technical walkthrough list</span></span>

<span data-ttu-id="acdb1-109">Los siguientes tutoriales iniciada por get proporcionan orientación técnica de coherente y completo para las aplicaciones de ejemplo que puede levantar y desplazar mediante el uso de contenedores y, a continuación, mueva con varias opciones de implementación de Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="acdb1-110">Cada uno de los siguientes tutoriales utiliza el nuevo eShopLegacy y eShopModernizing aplicaciones de ejemplo, que están disponibles en GitHub en [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="acdb1-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

- <span data-ttu-id="acdb1-111">**Paseo de compras de aplicaciones heredadas**</span><span class="sxs-lookup"><span data-stu-id="acdb1-111">**Tour of eShop legacy apps**</span></span>

- <span data-ttu-id="acdb1-112">**Incluya las aplicaciones de .NET existentes con contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="acdb1-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

- <span data-ttu-id="acdb1-113">**Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure**</span><span class="sxs-lookup"><span data-stu-id="acdb1-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

- <span data-ttu-id="acdb1-114">**Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure**</span><span class="sxs-lookup"><span data-stu-id="acdb1-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

- <span data-ttu-id="acdb1-115">**Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="acdb1-116">Tutorial 1: Paseo de compras de aplicaciones heredadas</span><span class="sxs-lookup"><span data-stu-id="acdb1-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="acdb1-117">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="acdb1-117">Technical walkthrough availability</span></span>

<span data-ttu-id="acdb1-118">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="acdb1-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="acdb1-119">Información general</span><span class="sxs-lookup"><span data-stu-id="acdb1-119">Overview</span></span>

<span data-ttu-id="acdb1-120">En este tutorial, puede explorar la implementación inicial de dos aplicaciones heredadas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="acdb1-120">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="acdb1-121">Las aplicaciones de ejemplo tienen una arquitectura monolítica y creadas utilizando ASP.NET clásico.</span><span class="sxs-lookup"><span data-stu-id="acdb1-121">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="acdb1-122">Una aplicación se basa en ASP.NET 4.x MVC; la segunda aplicación se basa en formularios Web Forms ASP.NET 4.x.</span><span class="sxs-lookup"><span data-stu-id="acdb1-122">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="acdb1-123">Ambas aplicaciones están en el [repositorio de GitHub de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="acdb1-123">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="acdb1-124">Puede incluya ambas aplicaciones de ejemplo, similar a la forma en que puede incluya un clásico [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) aplicación (WCF) que vayan a usar como una aplicación de escritorio.</span><span class="sxs-lookup"><span data-stu-id="acdb1-124">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](../../framework/wcf/whats-wcf.md) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="acdb1-125">Para obtener un ejemplo, vea [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span><span class="sxs-lookup"><span data-stu-id="acdb1-125">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="acdb1-126">Objetivos</span><span class="sxs-lookup"><span data-stu-id="acdb1-126">Goals</span></span>

<span data-ttu-id="acdb1-127">El objetivo principal de este tutorial es simplemente para familiarizarse con estas aplicaciones y con su código y la configuración.</span><span class="sxs-lookup"><span data-stu-id="acdb1-127">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="acdb1-128">Puede configurar las aplicaciones para que puedan generarán y utilizar los datos simulados, sin utilizar la base de datos SQL, con fines de prueba.</span><span class="sxs-lookup"><span data-stu-id="acdb1-128">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="acdb1-129">Esta configuración opcional se basa en la inserción de dependencias, de una manera desconectada.</span><span class="sxs-lookup"><span data-stu-id="acdb1-129">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="acdb1-130">Escenario</span><span class="sxs-lookup"><span data-stu-id="acdb1-130">Scenario</span></span>

<span data-ttu-id="acdb1-131">La figura 5-1 muestra el escenario sencillo de las aplicaciones heredadas originales.</span><span class="sxs-lookup"><span data-stu-id="acdb1-131">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![Escenario de arquitectura simple de las aplicaciones heredadas originales](./media/image5-1.png)
>
> <span data-ttu-id="acdb1-133">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="acdb1-133">**Figure 5-1.**</span></span> <span data-ttu-id="acdb1-134">Escenario de arquitectura simple de las aplicaciones heredadas originales</span><span class="sxs-lookup"><span data-stu-id="acdb1-134">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="acdb1-135">Desde una perspectiva de dominio empresarial, ambas aplicaciones ofrecen el mismo catálogo de características de administración.</span><span class="sxs-lookup"><span data-stu-id="acdb1-135">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="acdb1-136">Los miembros del equipo de enterprise compras utilizaría la aplicación para ver y editar el catálogo de productos.</span><span class="sxs-lookup"><span data-stu-id="acdb1-136">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="acdb1-137">Figura 5-2 muestra las capturas de pantalla de la aplicación inicial.</span><span class="sxs-lookup"><span data-stu-id="acdb1-137">Figure 5-2 shows the initial app screenshots.</span></span>

![Aplicaciones de MVC de ASP.NET y formularios Web Forms de ASP.NET (tecnologías existentes/heredado)](./media/image5-2.png)

> <span data-ttu-id="acdb1-139">**Figura 5-2.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-139">**Figure 5-2.**</span></span> <span data-ttu-id="acdb1-140">Aplicaciones de MVC de ASP.NET y formularios Web Forms de ASP.NET (tecnologías existentes/heredado)</span><span class="sxs-lookup"><span data-stu-id="acdb1-140">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="acdb1-141">Se trata de aplicaciones web que se utilizan para examinar y modificar las entradas del catálogo.</span><span class="sxs-lookup"><span data-stu-id="acdb1-141">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="acdb1-142">El hecho de que ambas aplicaciones cumplirán las mismas características funcionales y de negocios es simplemente con fines de comparación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-142">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="acdb1-143">Puede ver un proceso de modernización similar para las aplicaciones que se crearon mediante el uso de los marcos de trabajo de ASP.NET MVC y formularios Web Forms de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="acdb1-143">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="acdb1-144">Dependencias en ASP.NET 4.x o versiones anteriores (ya sea para MVC o Web Forms) significa que estas aplicaciones no se ejecutarán en .NET Core a menos que el código se ha reescrito completamente mediante el uso de núcleo de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="acdb1-144">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="acdb1-145">Esto demuestra que el punto de que si no desea volver a diseñar o volver a escribir código, puede incluya las aplicaciones existentes y seguir usando las mismas tecnologías de .NET y el mismo código.</span><span class="sxs-lookup"><span data-stu-id="acdb1-145">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="acdb1-146">Puede ver cómo se pueden ejecutar aplicaciones como estos en contenedores, sin realizar ningún cambio a código heredado.</span><span class="sxs-lookup"><span data-stu-id="acdb1-146">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="acdb1-147">Ventajas</span><span class="sxs-lookup"><span data-stu-id="acdb1-147">Benefits</span></span>

<span data-ttu-id="acdb1-148">Las ventajas de este tutorial son sencillas: simplemente familiarizarse con la configuración de código y la aplicación, en función de inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="acdb1-148">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="acdb1-149">A continuación, puede experimentar con este enfoque cuando incluya e implementar varios entornos en el futuro.</span><span class="sxs-lookup"><span data-stu-id="acdb1-149">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="acdb1-150">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acdb1-150">Next steps</span></span>

<span data-ttu-id="acdb1-151">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="acdb1-151">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="acdb1-152">Tutorial 2: Incluya las aplicaciones de .NET existentes con contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="acdb1-152">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="acdb1-153">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="acdb1-153">Technical walkthrough availability</span></span>

<span data-ttu-id="acdb1-154">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="acdb1-154">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="acdb1-155">Información general</span><span class="sxs-lookup"><span data-stu-id="acdb1-155">Overview</span></span>

<span data-ttu-id="acdb1-156">Utilice contenedores de Windows para mejorar la implementación de aplicaciones .NET existentes, como las basadas en MVC, formularios Web Forms o WCF, para entornos de prueba, desarrollo y producción.</span><span class="sxs-lookup"><span data-stu-id="acdb1-156">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="acdb1-157">Objetivos</span><span class="sxs-lookup"><span data-stu-id="acdb1-157">Goals</span></span>

<span data-ttu-id="acdb1-158">El objetivo de este tutorial es mostrar varias opciones para containerizing una aplicación existente de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="acdb1-158">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="acdb1-159">Puede realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="acdb1-159">You can:</span></span>

- <span data-ttu-id="acdb1-160">Incluya la aplicación mediante el uso de [Visual Studio 2017 Tools para Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (2017 de Visual Studio o versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="acdb1-160">Containerize your application by using [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

- <span data-ttu-id="acdb1-161">Incluya la aplicación agregando manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)y, a continuación, usar el [CLI de Docker](https://docs.docker.com/engine/reference/commandline/cli/).</span><span class="sxs-lookup"><span data-stu-id="acdb1-161">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

- <span data-ttu-id="acdb1-162">Incluya la aplicación mediante el uso de la [Img2Docker](https://github.com/docker/communitytools-image2docker-win) herramienta (una herramienta de código abierto de Docker).</span><span class="sxs-lookup"><span data-stu-id="acdb1-162">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="acdb1-163">En este tutorial se centra en Visual Studio de 2017 Tools para el enfoque de Docker, pero los otros dos enfoques son muy parecidos en relación con usando Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="acdb1-163">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regard to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="acdb1-164">Escenario</span><span class="sxs-lookup"><span data-stu-id="acdb1-164">Scenario</span></span>

<span data-ttu-id="acdb1-165">Figura 5-3 se muestra el escenario para las aplicaciones heredadas de compras en contenedores.</span><span class="sxs-lookup"><span data-stu-id="acdb1-165">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![Diagrama de arquitectura simplificada de aplicaciones en contenedores en un entorno de desarrollo](./media/image5-3.png)
>
> <span data-ttu-id="acdb1-167">**Figura 5-3.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-167">**Figure 5-3.**</span></span> <span data-ttu-id="acdb1-168">Diagrama de arquitectura simplificada de aplicaciones en contenedores en un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="acdb1-168">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="acdb1-169">Ventajas</span><span class="sxs-lookup"><span data-stu-id="acdb1-169">Benefits</span></span>

<span data-ttu-id="acdb1-170">Existen ventajas a la ejecución de la aplicación monolítica en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="acdb1-170">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="acdb1-171">En primer lugar, cree una imagen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-171">First, you create an image for the application.</span></span> <span data-ttu-id="acdb1-172">Desde ese momento, cada implementación se ejecuta en el mismo entorno.</span><span class="sxs-lookup"><span data-stu-id="acdb1-172">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="acdb1-173">Cada contenedor usa la misma versión de sistema operativo, tiene la misma versión de dependencias instalada, usa la misma versión de .NET framework y se compila mediante el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="acdb1-173">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="acdb1-174">Básicamente, controlar las dependencias de la aplicación mediante una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="acdb1-174">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="acdb1-175">Las dependencias de viajan con la aplicación al implementar los contenedores.</span><span class="sxs-lookup"><span data-stu-id="acdb1-175">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="acdb1-176">Otra ventaja adicional es que los programadores pueden ejecutar la aplicación en el entorno coherente que se ofrecen los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="acdb1-176">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="acdb1-177">Los problemas que aparezcan únicamente con determinadas versiones se pueden observar inmediatamente, en lugar de así como la exposición en un entorno de ensayo o de producción.</span><span class="sxs-lookup"><span data-stu-id="acdb1-177">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="acdb1-178">Las diferencias en los entornos de desarrollo que usan los miembros del equipo de desarrollo importan menor cuando las aplicaciones que se ejecutan en ellos.</span><span class="sxs-lookup"><span data-stu-id="acdb1-178">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="acdb1-179">Aplicaciones en contenedores también tienen una curva de escalado horizontal más plana.</span><span class="sxs-lookup"><span data-stu-id="acdb1-179">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="acdb1-180">Aplicaciones en contenedores le permiten tener más aplicaciones e instancias de servicio (basados en contenedores) en una máquina virtual o la máquina física en comparación con las implementaciones de aplicaciones normal por máquina.</span><span class="sxs-lookup"><span data-stu-id="acdb1-180">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="acdb1-181">Esto se traduce en mayor densidad y menos requiere recursos, especialmente cuando se usa orchestrators como Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="acdb1-181">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="acdb1-182">Inclusión en contenedores, en situaciones ideales, no requiere realizar cambios en el código de aplicación (C\#).</span><span class="sxs-lookup"><span data-stu-id="acdb1-182">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="acdb1-183">En la mayoría de los escenarios, solo tiene los archivos de metadatos de implementación de Docker (archivos Dockerfiles y Docker Compose).</span><span class="sxs-lookup"><span data-stu-id="acdb1-183">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="acdb1-184">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acdb1-184">Next steps</span></span>

<span data-ttu-id="acdb1-185">Explorar este contenido más detallada en el sitio wiki de GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="acdb1-185">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="acdb1-186">Tutorial 3: Implementar la aplicación basada en contenedores de Windows en máquinas virtuales de Azure</span><span class="sxs-lookup"><span data-stu-id="acdb1-186">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="acdb1-187">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="acdb1-187">Technical walkthrough availability</span></span>

<span data-ttu-id="acdb1-188">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="acdb1-188">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="acdb1-189">Información general</span><span class="sxs-lookup"><span data-stu-id="acdb1-189">Overview</span></span>

<span data-ttu-id="acdb1-190">Implementación en un host de Docker en una máquina Virtual de 2016 de servidor de Windows (VM) de Azure le permite configurar rápidamente entornos de desarrollo/pruebas/staging.</span><span class="sxs-lookup"><span data-stu-id="acdb1-190">Deploying to a Docker host on a Windows Server 2016 Virtual Machine (VM) in Azure lets you quickly set up development/test/staging environments.</span></span> <span data-ttu-id="acdb1-191">También proporciona un lugar común para evaluadores o los usuarios empresariales validar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-191">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="acdb1-192">Máquinas virtuales también pueden ser infraestructura válido como un entorno de producción del servicio (IaaS).</span><span class="sxs-lookup"><span data-stu-id="acdb1-192">VMs also can be valid Infrastucture as a Service (IaaS) production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="acdb1-193">Objetivos</span><span class="sxs-lookup"><span data-stu-id="acdb1-193">Goals</span></span>

<span data-ttu-id="acdb1-194">El objetivo de este tutorial es mostrar las alternativas varios que tiene al implementar contenedores de Windows en las máquinas virtuales de Azure que se basan en Windows Server 2016 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="acdb1-194">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="acdb1-195">Escenarios</span><span class="sxs-lookup"><span data-stu-id="acdb1-195">Scenarios</span></span>

<span data-ttu-id="acdb1-196">En este tutorial se tratan varios escenarios.</span><span class="sxs-lookup"><span data-stu-id="acdb1-196">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="acdb1-197">Escenario A: implementar en una VM de Azure desde un equipo de desarrollo a través de la conexión con el motor de Docker</span><span class="sxs-lookup"><span data-stu-id="acdb1-197">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker](./media/image5-4.png)

> <span data-ttu-id="acdb1-199">**Figura 5-4.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-199">**Figure 5-4.**</span></span> <span data-ttu-id="acdb1-200">Implementar en una VM de Azure desde un equipo de desarrollo a través de una conexión con el motor de Docker</span><span class="sxs-lookup"><span data-stu-id="acdb1-200">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="acdb1-201">Escenario B: implementar en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="acdb1-201">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Implementar en una máquina virtual de Azure a través de un registro de Docker](./media/image5-5.png)

> <span data-ttu-id="acdb1-203">**Figura 5-5.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-203">**Figure 5-5.**</span></span> <span data-ttu-id="acdb1-204">Implementar en una máquina virtual de Azure a través de un registro de Docker</span><span class="sxs-lookup"><span data-stu-id="acdb1-204">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="acdb1-205">Escenario C: implementar en una VM de Azure desde el elemento de configuración/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-205">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-6.png)

> <span data-ttu-id="acdb1-207">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="acdb1-207">**Figure 5-6.**</span></span> <span data-ttu-id="acdb1-208">Implementar en una VM de Azure de CI/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-208">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="acdb1-209">Máquinas virtuales de Azure para los contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="acdb1-209">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="acdb1-210">Máquinas virtuales de Azure para contenedores de Windows son máquinas virtuales basadas en Windows Server 2016, Windows 10 o versiones posteriores, ambos con el motor de Docker configurar.</span><span class="sxs-lookup"><span data-stu-id="acdb1-210">Azure VMs for Windows Containers are VMs based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="acdb1-211">En la mayoría de los casos, se utiliza Windows Server 2016 en las máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-211">In most cases, Windows Server 2016 is used in the Azure VMs.</span></span>

<span data-ttu-id="acdb1-212">Actualmente, Azure proporciona una máquina virtual denominada **Windows Server 2016 con contenedores**.</span><span class="sxs-lookup"><span data-stu-id="acdb1-212">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="acdb1-213">Puede usar esta máquina virtual para probar la nueva característica de contenedor de Windows Server, con Windows Server Core o Nano Server de Windows.</span><span class="sxs-lookup"><span data-stu-id="acdb1-213">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="acdb1-214">Imágenes del sistema operativo de contenedor se instalan y, a continuación, la máquina virtual está lista para su uso con Docker.</span><span class="sxs-lookup"><span data-stu-id="acdb1-214">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="acdb1-215">Ventajas</span><span class="sxs-lookup"><span data-stu-id="acdb1-215">Benefits</span></span>

<span data-ttu-id="acdb1-216">Aunque los contenedores de Windows se pueden implementar en local 2016 máquinas virtuales Windows Server, cuando se implementa en Azure, obtendrá una manera más fácil para empezar a trabajar con máquinas virtuales de contenedor de listos para usar Windows Server.</span><span class="sxs-lookup"><span data-stu-id="acdb1-216">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="acdb1-217">También obtendrá una ubicación en línea común que es accesible para evaluadores y escalabilidad automática a través de conjuntos de escalas de máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-217">You also get a common online location that’s accessible to testers, and automatic scalability through Azure virtual machine scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="acdb1-218">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acdb1-218">Next steps</span></span>

<span data-ttu-id="acdb1-219">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="acdb1-219">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="acdb1-220">Tutorial 4: Implementar las aplicaciones de Windows basada en contenedores en Kubernetes en el servicio de contenedor de Azure</span><span class="sxs-lookup"><span data-stu-id="acdb1-220">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="acdb1-221">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="acdb1-221">Technical walkthrough availability</span></span>

<span data-ttu-id="acdb1-222">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="acdb1-222">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a><span data-ttu-id="acdb1-223">Información general</span><span class="sxs-lookup"><span data-stu-id="acdb1-223">Overview</span></span>

<span data-ttu-id="acdb1-224">Una aplicación que se basa en los contenedores de Windows rápidamente necesite usan las plataformas, aleja el aún más de las máquinas virtuales IaaS.</span><span class="sxs-lookup"><span data-stu-id="acdb1-224">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="acdb1-225">Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones.</span><span class="sxs-lookup"><span data-stu-id="acdb1-225">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="acdb1-226">Puede lograr estos objetivos utilizando el orchestrator [Kubernetes](https://kubernetes.io/), disponible en [servicios de contenedor de Azure](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="acdb1-226">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="acdb1-227">Objetivos</span><span class="sxs-lookup"><span data-stu-id="acdb1-227">Goals</span></span>

<span data-ttu-id="acdb1-228">El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows para Kubernetes (también denominada *K8s*) en el servicio de contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-228">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="acdb1-229">Implementación a Kubernetes desde cero es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="acdb1-229">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="acdb1-230">Implementar un clúster de Kubernetes al servicio de contenedor de Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-230">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="acdb1-231">Implementar la aplicación y los recursos relacionados en el clúster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acdb1-231">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="acdb1-232">Escenarios</span><span class="sxs-lookup"><span data-stu-id="acdb1-232">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="acdb1-233">Escenario A: implementar directamente a un clúster de Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="acdb1-233">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo](./media/image5-7.png)

> <span data-ttu-id="acdb1-235">**Figura 5-7.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-235">**Figure 5-7.**</span></span> <span data-ttu-id="acdb1-236">Implementar directamente en un clúster Kubernetes desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="acdb1-236">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="acdb1-237">Escenario B: implementar en un clúster Kubernetes desde el elemento de configuración/CD canalizaciones en Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-237">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services](./media/image5-8.png)

> <span data-ttu-id="acdb1-239">**Figura 5-8.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-239">**Figure 5-8.**</span></span> <span data-ttu-id="acdb1-240">Implementar en un clúster de Kubernetes de canalizaciones de CI/CD en Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-240">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="acdb1-241">Ventajas</span><span class="sxs-lookup"><span data-stu-id="acdb1-241">Benefits</span></span>

<span data-ttu-id="acdb1-242">Hay muchas ventajas a la implementación en un clúster en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acdb1-242">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="acdb1-243">La mayor ventaja es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de nodos o máquinas virtuales en el clúster ( escalabilidad global del clúster).</span><span class="sxs-lookup"><span data-stu-id="acdb1-243">The biggest benefit is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="acdb1-244">Servicio de contenedor de Azure optimiza las tecnologías y herramientas de código abierto populares específicamente para Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-244">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="acdb1-245">Obtener una solución abierta que ofrece la portabilidad tanto para los contenedores de la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-245">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="acdb1-246">Seleccione el tamaño, el número de hosts, y el servicio de contenedor-herramientas de orchestrator controla todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="acdb1-246">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="acdb1-247">Con Kubernetes, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales, para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:</span><span class="sxs-lookup"><span data-stu-id="acdb1-247">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="acdb1-248">Aplicaciones basadas en varios contenedores</span><span class="sxs-lookup"><span data-stu-id="acdb1-248">Applications based on multiple containers</span></span>

- <span data-ttu-id="acdb1-249">La replicación de instancias de contenedor y ajuste automático de escala horizontal</span><span class="sxs-lookup"><span data-stu-id="acdb1-249">Replicating container instances and horizontal autoscaling</span></span>

- <span data-ttu-id="acdb1-250">Nomenclatura y detectar (por ejemplo, DNS interno)</span><span class="sxs-lookup"><span data-stu-id="acdb1-250">Naming and discovering (for example, internal DNS)</span></span>

- <span data-ttu-id="acdb1-251">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="acdb1-251">Balancing loads</span></span>

- <span data-ttu-id="acdb1-252">Actualizaciones graduales</span><span class="sxs-lookup"><span data-stu-id="acdb1-252">Rolling updates</span></span>

- <span data-ttu-id="acdb1-253">Distribuir secretos</span><span class="sxs-lookup"><span data-stu-id="acdb1-253">Distributing secrets</span></span>

- <span data-ttu-id="acdb1-254">Comprobaciones de estado de aplicación</span><span class="sxs-lookup"><span data-stu-id="acdb1-254">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="acdb1-255">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acdb1-255">Next steps</span></span>

<span data-ttu-id="acdb1-256">Explorar este contenido más detallada en el sitio wiki de GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="acdb1-256">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="acdb1-257">Tutorial 5: Implementar las aplicaciones de Windows basada en contenedores en Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="acdb1-257">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="acdb1-258">Disponibilidad de tutorial técnica</span><span class="sxs-lookup"><span data-stu-id="acdb1-258">Technical walkthrough availability</span></span>

<span data-ttu-id="acdb1-259">El tutorial técnico completo está disponible en el wiki de repositorio de GitHub de eShopModernizing:</span><span class="sxs-lookup"><span data-stu-id="acdb1-259">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a><span data-ttu-id="acdb1-260">Información general</span><span class="sxs-lookup"><span data-stu-id="acdb1-260">Overview</span></span>

<span data-ttu-id="acdb1-261">Una aplicación basada en los contenedores de Windows rápidamente debe usar plataformas, aleja el aún más de las máquinas virtuales IaaS.</span><span class="sxs-lookup"><span data-stu-id="acdb1-261">An application based on Windows Containers quickly needs to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="acdb1-262">Esto es necesario para lograr fácilmente alta escalabilidad y mejor automatizada escalabilidad y para una mejora considerable en automatizar las implementaciones y control de versiones.</span><span class="sxs-lookup"><span data-stu-id="acdb1-262">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="acdb1-263">Puede lograr estos objetivos con el orchestrator Azure Service Fabric, que está disponible en la nube de Azure, pero también disponible para su uso local, o incluso en una nube pública diferente.</span><span class="sxs-lookup"><span data-stu-id="acdb1-263">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="acdb1-264">Objetivos</span><span class="sxs-lookup"><span data-stu-id="acdb1-264">Goals</span></span>

<span data-ttu-id="acdb1-265">El objetivo de este tutorial es aprender a implementar una aplicación basada en el contenedor de Windows a un clúster de Service Fabric en Azure.</span><span class="sxs-lookup"><span data-stu-id="acdb1-265">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="acdb1-266">Implementación a Service Fabric desde cero es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="acdb1-266">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="acdb1-267">Implementar un clúster de Service Fabric en Azure (o en un entorno diferente).</span><span class="sxs-lookup"><span data-stu-id="acdb1-267">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="acdb1-268">Implementar la aplicación y los recursos relacionados en el clúster de Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="acdb1-268">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="acdb1-269">Escenarios</span><span class="sxs-lookup"><span data-stu-id="acdb1-269">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="acdb1-270">Escenario A: implementar directamente a un clúster de Service Fabric desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="acdb1-270">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo](./media/image5-9.png)

> <span data-ttu-id="acdb1-272">**Figura 5-9.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-272">**Figure 5-9.**</span></span> <span data-ttu-id="acdb1-273">Implementar directamente en un clúster de Service Fabric desde un entorno de desarrollo</span><span class="sxs-lookup"><span data-stu-id="acdb1-273">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="acdb1-274">Escenario B: implementar en un clúster de Service Fabric desde el elemento de configuración/CD canalizaciones en Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-274">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services](./media/image5-10.png)

> <span data-ttu-id="acdb1-276">**Figura 5-10.**</span><span class="sxs-lookup"><span data-stu-id="acdb1-276">**Figure 5-10.**</span></span> <span data-ttu-id="acdb1-277">Implementar en un clúster de Service Fabric de CI/CD canalizaciones en Visual Studio Team Services</span><span class="sxs-lookup"><span data-stu-id="acdb1-277">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="acdb1-278">Ventajas</span><span class="sxs-lookup"><span data-stu-id="acdb1-278">Benefits</span></span>

<span data-ttu-id="acdb1-279">Las ventajas de la implementación en un clúster de Service Fabric son similares a las ventajas de usar Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acdb1-279">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="acdb1-280">Sin embargo, no obstante, es que Service Fabric es un entorno de producción más maduro para aplicaciones de Windows en comparación con Kubernetes, que se encuentra en una fase beta para contenedores de Windows en Kubernetes versión 1.9 (diciembre de 2017).</span><span class="sxs-lookup"><span data-stu-id="acdb1-280">One difference, though, is that Service Fabric is a more mature production environment for Windows applications compared to Kubernetes, which is in a beta phase for Windows Containers in Kubernetes version 1.9 (December 2017).</span></span> <span data-ttu-id="acdb1-281">Kubernetes es un entorno más maduro para Linux.</span><span class="sxs-lookup"><span data-stu-id="acdb1-281">Kubernetes is a more mature environment for Linux.</span></span>

<span data-ttu-id="acdb1-282">La principal ventaja del uso de Azure Service Fabric es que se obtiene de un entorno para entornos de producción en el que puede escalar horizontalmente la aplicación en función del número de instancias de contenedor que desea utilizar (escalabilidad interna en los nodos existentes) y, en función del número de los nodos o máquinas virtuales del clúster (escalabilidad global del clúster).</span><span class="sxs-lookup"><span data-stu-id="acdb1-282">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="acdb1-283">Azure Service Fabric ofrece portabilidad de los contenedores y para la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-283">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="acdb1-284">Puede tener un tejido de servicio de clúster en Azure, o instalar localmente en su propio centro de datos.</span><span class="sxs-lookup"><span data-stu-id="acdb1-284">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="acdb1-285">Incluso puede instalar un clúster de Service Fabric en una nube diferente, como [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span><span class="sxs-lookup"><span data-stu-id="acdb1-285">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="acdb1-286">Con Service Fabric, los desarrolladores pueden progreso de pensar en máquinas físicas y virtuales para planear una infraestructura centrada en el contenedor que facilita las siguientes capacidades, entre otros:</span><span class="sxs-lookup"><span data-stu-id="acdb1-286">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

- <span data-ttu-id="acdb1-287">Aplicaciones basadas en varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="acdb1-287">Applications based on multiple containers.</span></span>

- <span data-ttu-id="acdb1-288">Replicación de instancias de contenedor y ajuste automático de escala horizontal.</span><span class="sxs-lookup"><span data-stu-id="acdb1-288">Replicating container instances and horizontal autoscaling.</span></span>

- <span data-ttu-id="acdb1-289">Nomenclatura y detectar (por ejemplo, DNS interno).</span><span class="sxs-lookup"><span data-stu-id="acdb1-289">Naming and discovering (for example, internal DNS).</span></span>

- <span data-ttu-id="acdb1-290">Equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="acdb1-290">Balancing loads.</span></span>

- <span data-ttu-id="acdb1-291">Actualizaciones graduales.</span><span class="sxs-lookup"><span data-stu-id="acdb1-291">Rolling updates.</span></span>

- <span data-ttu-id="acdb1-292">Distribuir secretos.</span><span class="sxs-lookup"><span data-stu-id="acdb1-292">Distributing secrets.</span></span>

- <span data-ttu-id="acdb1-293">Comprueba el estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acdb1-293">Application health checks.</span></span>

<span data-ttu-id="acdb1-294">Las siguientes capacidades son exclusivas de Service Fabric (en comparación con otras orchestrators):</span><span class="sxs-lookup"><span data-stu-id="acdb1-294">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

- <span data-ttu-id="acdb1-295">Capacidad de servicios con estado, a través del modelo de aplicación de servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="acdb1-295">Stateful services capability, through the Reliable Services application model.</span></span>

- <span data-ttu-id="acdb1-296">Patrón de actores a través del modelo de aplicación de Reliable Actors.</span><span class="sxs-lookup"><span data-stu-id="acdb1-296">Actors pattern, through the Reliable Actors application model.</span></span>

- <span data-ttu-id="acdb1-297">Implementar procesos descubierto, además de los contenedores de Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="acdb1-297">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

- <span data-ttu-id="acdb1-298">Advanced actualizaciones graduales y comprobaciones de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="acdb1-298">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="acdb1-299">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acdb1-299">Next steps</span></span>

<span data-ttu-id="acdb1-300">Explorar este contenido más detallada en el sitio wiki de GitHub:</span><span class="sxs-lookup"><span data-stu-id="acdb1-300">Explore this content more in-depth on the GitHub wiki:</span></span>

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
<span data-ttu-id="acdb1-301">[Anterior](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Siguiente](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="acdb1-301">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
