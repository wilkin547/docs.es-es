---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Flujo de trabajo de desarrollo para aplicaciones de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: b7115530c44321dc2a10be3996c14429591b611f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864831"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="d08be-103">Flujo de trabajo de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="d08be-104">El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde este programa la aplicación mediante su lenguaje preferido y la prueba en local.</span><span class="sxs-lookup"><span data-stu-id="d08be-104">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="d08be-105">Independientemente del lenguaje, el marco de trabajo y la plataforma que elija el desarrollador, con este flujo de trabajo, siempre desarrolla y prueba contenedores de Docker, aunque lo hace en local.</span><span class="sxs-lookup"><span data-stu-id="d08be-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="d08be-106">Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d08be-106">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="d08be-107">Una selección de sistema operativo (por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="d08be-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="d08be-108">Archivos agregados por el desarrollador (binarios de aplicación, etc.).</span><span class="sxs-lookup"><span data-stu-id="d08be-108">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="d08be-109">Información de configuración (configuración de entorno y dependencias).</span><span class="sxs-lookup"><span data-stu-id="d08be-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="d08be-110">Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="d08be-111">En esta sección se explica el flujo de trabajo de desarrollo de *bucle interno* para aplicaciones basadas en contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="d08be-112">El flujo de trabajo de bucle interno significa que no se tiene en cuenta el flujo de trabajo general de DevOps y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="d08be-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="d08be-113">Los pasos iniciales para configurar el entorno no se incluyen, ya que se realizan solo una vez.</span><span class="sxs-lookup"><span data-stu-id="d08be-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="d08be-114">Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="d08be-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="d08be-115">Estos son los pasos básicos que normalmente se realizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="d08be-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="d08be-116">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="d08be-116">**Figure 5-1.**</span></span> <span data-ttu-id="d08be-117">Flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-117">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="d08be-118">En esta guía se detalla el proceso completo y se explica cada paso importante centrándose en un entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d08be-118">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="d08be-119">Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, Visual Studio Code más la CLI de Docker en macOS o Windows), es necesario conocer cada paso, generalmente más detalladamente que si se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d08be-119">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="d08be-120">Para más información sobre cómo trabajar en un entorno de CLI, vea el libro electrónico [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Ciclo de vida de aplicaciones en contenedor de Docker con plataformas y herramientas de Microsoft)](https://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="d08be-120">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="d08be-121">Cuando se usa Visual Studio 2015 o Visual Studio 2017, muchos de esos pasos se controlan automáticamente, lo cual mejora considerablemente la productividad.</span><span class="sxs-lookup"><span data-stu-id="d08be-121">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="d08be-122">Esto es así especialmente con Visual Studio 2017 y cuando el destino son aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-122">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="d08be-123">Por ejemplo, con un solo clic, Visual Studio agrega el Dockerfile y el archivo docker-compose.yml a los proyectos con la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d08be-123">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="d08be-124">Al ejecutar la aplicación en Visual Studio, compila la imagen de Docker y ejecuta la aplicación de varios contenedores directamente en Docker; incluso permite depurar varios contenedores al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d08be-124">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="d08be-125">Estas características aumentan la velocidad de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d08be-125">These features will boost your development speed.</span></span>

<span data-ttu-id="d08be-126">Pero que Visual Studio realice esos pasos automáticamente no significa que no sea necesario saber lo que ocurre en segundo plano con Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-126">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="d08be-127">Por lo tanto, en la guía siguiente se detalla cada paso.</span><span class="sxs-lookup"><span data-stu-id="d08be-127">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="d08be-128">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="d08be-128">Step 1.</span></span> <span data-ttu-id="d08be-129">Empezar a programar y crear la aplicación inicial o la base de referencia del servicio</span><span class="sxs-lookup"><span data-stu-id="d08be-129">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="d08be-130">El desarrollo de una aplicación de Docker es similar al desarrollo de una aplicación sin Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-130">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="d08be-131">La diferencia es que al desarrollar para Docker, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="d08be-131">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="d08be-132">El contenedor puede ser un contenedor de Linux o de Windows.</span><span class="sxs-lookup"><span data-stu-id="d08be-132">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="d08be-133">Configurar el entorno local con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-133">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="d08be-134">Para empezar, asegúrese de que tiene instalado [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows, como se explica en estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d08be-134">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="d08be-135">Get started with Docker CE for Windows (Introducción a Docker CE para Windows)</span><span class="sxs-lookup"><span data-stu-id="d08be-135">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="d08be-136">Además, necesita tener Visual Studio 2017 instalado.</span><span class="sxs-lookup"><span data-stu-id="d08be-136">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="d08be-137">Se prefiere a Visual Studio 2015 con el complemento Visual Studio Tools para Docker, ya que Visual Studio 2017 tiene más compatibilidad con Docker, por ejemplo, compatibilidad con la depuración de contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-137">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="d08be-138">Visual Studio 2017 incluye las herramientas para Docker si ha seleccionado la carga de trabajo **.NET Core y Docker** durante la instalación, como se muestra en la figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="d08be-138">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="d08be-139">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="d08be-139">**Figure 5-2**.</span></span> <span data-ttu-id="d08be-140">Selección de la carga de trabajo **.NET Core y Docker** durante la instalación de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="d08be-141">Puede empezar a programar la aplicación en .NET sin formato (normalmente en .NET Core si va a usar contenedores) incluso antes de habilitar Docker en la aplicación e implementar y probar en Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="d08be-142">Pero se recomienda empezar a trabajar en Docker tan pronto como sea posible, ya que es el entorno real y se pueden detectar los problemas a la mayor brevedad.</span><span class="sxs-lookup"><span data-stu-id="d08be-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="d08be-143">Se recomienda encarecidamente porque Visual Studio facilita tanto el trabajo con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de varios contenedores desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d08be-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-144">Additional resources</span></span>

-   <span data-ttu-id="d08be-145">**Get started with Docker CE for Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/) (Introducción a Docker CE para Windows)</span><span class="sxs-lookup"><span data-stu-id="d08be-145">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="d08be-146">**Visual Studio 2017**
    [*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="d08be-146">**Visual Studio 2017**
[*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="d08be-147">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="d08be-147">Step 2.</span></span> <span data-ttu-id="d08be-148">Crear un Dockerfile relacionado con una imagen base existente de .NET</span><span class="sxs-lookup"><span data-stu-id="d08be-148">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="d08be-149">Necesita un Dockerfile para cada imagen personalizada que quiera compilar; también necesita un Dockerfile para cada contenedor que se vaya a implementar, tanto si se implementa automáticamente desde Visual Studio como manualmente mediante la CLI de Docker (comandos docker run y docker-compose).</span><span class="sxs-lookup"><span data-stu-id="d08be-149">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="d08be-150">Si la aplicación contiene un único servicio personalizado, necesita un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d08be-150">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="d08be-151">Si la aplicación contiene varios servicios (como en una arquitectura de microservicios), necesita un Dockerfile para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="d08be-151">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="d08be-152">El Dockerfile se coloca en la carpeta raíz de la aplicación o el servicio.</span><span class="sxs-lookup"><span data-stu-id="d08be-152">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="d08be-153">Contiene los comandos que indican a Docker cómo configurar y ejecutar la aplicación o el servicio en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d08be-153">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="d08be-154">Puede crear un Dockerfile de forma manual en el código y agregarlo al proyecto junto con las dependencias de .NET.</span><span class="sxs-lookup"><span data-stu-id="d08be-154">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="d08be-155">Con Visual Studio y sus herramientas para Docker, esta tarea solo exige unos clics.</span><span class="sxs-lookup"><span data-stu-id="d08be-155">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="d08be-156">Al crear un nuevo proyecto en Visual Studio 2017, hay una opción denominada **Enable Container (Docker) Support** (Habilitar compatibilidad con contenedor (Docker)), como se muestra en la figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="d08be-156">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="d08be-157">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="d08be-157">**Figure 5-3**.</span></span> <span data-ttu-id="d08be-158">Habilitación de la compatibilidad con Docker al crear un nuevo proyecto en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-158">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="d08be-159">También puede habilitar la compatibilidad con Docker en un proyecto nuevo o existente si hace clic con el botón derecho en el archivo de proyecto en Visual Studio y selecciona la opción **Add-Docker Project Support** (Agregar-Compatibilidad con proyectos de Docker), como se muestra en la figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="d08be-159">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="d08be-160">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="d08be-160">**Figure 5-4**.</span></span> <span data-ttu-id="d08be-161">Habilitación de la compatibilidad con Docker en un proyecto existente de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-161">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="d08be-162">Esta acción en un proyecto (como una aplicación web ASP.NET o un servicio de Web API), agrega un Dockerfile al proyecto con la configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="d08be-162">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="d08be-163">También agrega un archivo docker-compose.yml para toda la solución.</span><span class="sxs-lookup"><span data-stu-id="d08be-163">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="d08be-164">En las siguientes secciones se describe la información incluida en cada uno de esos archivos.</span><span class="sxs-lookup"><span data-stu-id="d08be-164">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="d08be-165">Visual Studio puede hacer este trabajo automáticamente, aunque resulta útil entender qué contiene un Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d08be-165">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="d08be-166">Opción A: crear un proyecto mediante una imagen de Docker de .NET oficial existente</span><span class="sxs-lookup"><span data-stu-id="d08be-166">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="d08be-167">Normalmente se compila una imagen personalizada para el contenedor sobre una imagen base que se puede obtener de un repositorio oficial en el registro [Docker Hub](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="d08be-167">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="d08be-168">Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d08be-168">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="d08be-169">El Dockerfile usa una imagen de aspnetcore existente.</span><span class="sxs-lookup"><span data-stu-id="d08be-169">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="d08be-170">Anteriormente se ha explicado qué imágenes y repositorios de Docker se pueden usar según el marco de trabajo y el sistema operativo elegidos.</span><span class="sxs-lookup"><span data-stu-id="d08be-170">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="d08be-171">Por ejemplo, si quiere usar ASP.NET Core (Linux o Windows), la imagen que se debe usar es microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="d08be-171">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="d08be-172">Por lo tanto, debe especificar qué imagen base de Docker va a usar para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="d08be-172">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="d08be-173">Para ello hay que agregar FROM microsoft/aspnetcore:2.0 al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="d08be-173">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="d08be-174">Visual Studio lo hace de forma automática, pero si va a actualizar la versión, actualice este valor.</span><span class="sxs-lookup"><span data-stu-id="d08be-174">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="d08be-175">El uso de un repositorio de imágenes de .NET oficial de Docker Hub con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todos los equipos (incluido el desarrollo, las pruebas y la producción).</span><span class="sxs-lookup"><span data-stu-id="d08be-175">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="d08be-176">En el ejemplo siguiente se muestra un Dockerfile de ejemplo para un contenedor de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d08be-176">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="d08be-177">En este caso, el contenedor se basa en la versión 2.0 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="d08be-177">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="d08be-178">Es el valor `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="d08be-178">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="d08be-179">(Para más información sobre esta imagen base, vea las páginas [Imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) e [Imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/)). En el Dockerfile, también debe indicar a Docker que escuche en el puerto TCP que se vaya a usar en tiempo de ejecución (en este caso, el puerto 80, como se ha configurado con el valor EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="d08be-179">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="d08be-180">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco de trabajo que use.</span><span class="sxs-lookup"><span data-stu-id="d08be-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="d08be-181">Por ejemplo, la línea ENTRYPOINT con \["dotnet", "MySingleContainerWebApp.dll"\] indica a Docker que ejecute una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d08be-181">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="d08be-182">Si usa el SDK y la CLI de .NET Core (dotnet CLI) para compilar y ejecutar la aplicación de .NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="d08be-182">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="d08be-183">La conclusión es que la línea ENTRYPOINT y otros valores pueden variar según el lenguaje y la plataforma que se elijan para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d08be-183">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-184">Additional resources</span></span>

-   <span data-ttu-id="d08be-185">**Creación de imágenes de Docker para aplicaciones de .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="d08be-185">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span></span>

-   <span data-ttu-id="d08be-186">**Compile su propia imagen**.</span><span class="sxs-lookup"><span data-stu-id="d08be-186">**Build your own image**.</span></span> <span data-ttu-id="d08be-187">En la documentación oficial de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-187">In the official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="d08be-188">Uso de repositorios de imágenes multiarquitectura</span><span class="sxs-lookup"><span data-stu-id="d08be-188">Using multi-arch image repositories</span></span>

<span data-ttu-id="d08be-189">Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="d08be-189">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="d08be-190">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="d08be-190">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="d08be-191">Por ejemplo, el repositorio [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) disponible en el registro Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de repositorio.</span><span class="sxs-lookup"><span data-stu-id="d08be-191">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="d08be-192">Si especifica una etiqueta, se toma como destino una plataforma explícita, como en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d08be-192">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="d08be-193">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="d08be-193">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="d08be-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="d08be-194">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="d08be-195">Pero, y esto es nuevo desde mediados de 2017, si especifica el mismo nombre de imagen, incluso con la misma etiqueta, las nuevas imágenes multiarquitectura (por ejemplo, la imagen de aspnetcore compatible con multiarquitectura) usan la versión de Linux o Windows según el sistema operativo de host de Docker que se vaya a implementar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d08be-195">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="d08be-196">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="d08be-196">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="d08be-197">De esta forma, al extraer una imagen de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="d08be-197">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="d08be-198">Opción B: crear la imagen base desde cero</span><span class="sxs-lookup"><span data-stu-id="d08be-198">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="d08be-199">Puede crear su propia imagen base de Docker desde cero.</span><span class="sxs-lookup"><span data-stu-id="d08be-199">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="d08be-200">Este escenario no se recomienda para usuarios que se están iniciando en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d08be-200">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-201">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-201">Additional resources</span></span>

-   <span data-ttu-id="d08be-202">**Multi-arch .NET Core images (Imágenes de .NET Core multiarquitectura)**.</span><span class="sxs-lookup"><span data-stu-id="d08be-202">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="d08be-203">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="d08be-203">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="d08be-204">**Create a base image (Crear una imagen base)**.</span><span class="sxs-lookup"><span data-stu-id="d08be-204">**Create a base image**.</span></span> <span data-ttu-id="d08be-205">Documentación oficial de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-205">Official Docker documentation.</span></span>
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="d08be-206">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="d08be-206">Step 3.</span></span> <span data-ttu-id="d08be-207">Crear las imágenes de Docker personalizadas e insertar la aplicación o el servicio en ellas</span><span class="sxs-lookup"><span data-stu-id="d08be-207">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="d08be-208">Debe crear una imagen relacionada para cada servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d08be-208">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="d08be-209">Si la aplicación está formada por un único servicio o aplicación web, solo necesita una imagen.</span><span class="sxs-lookup"><span data-stu-id="d08be-209">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="d08be-210">Tenga en cuenta que las imágenes de Docker se compilan automáticamente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d08be-210">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="d08be-211">Los pasos siguientes solo son necesarios para el flujo de trabajo de editor/CLI y se explican para aclarar lo que sucede en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d08be-211">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="d08be-212">Como desarrollador, debe desarrollar y probar en local hasta que inserte una característica o cambio completados en el sistema de control de código fuente (por ejemplo, en GitHub).</span><span class="sxs-lookup"><span data-stu-id="d08be-212">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="d08be-213">Esto significa que tiene que crear las imágenes de Docker e implementar contenedores en un host de Docker local (máquina virtual de Windows o Linux) y ejecutar, probar y depurar en esos contenedores locales.</span><span class="sxs-lookup"><span data-stu-id="d08be-213">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="d08be-214">Para crear una imagen personalizada en el entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando docker build, como se muestra en la figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="d08be-214">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="d08be-215">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="d08be-215">**Figure 5-5**.</span></span> <span data-ttu-id="d08be-216">Creación de una imagen personalizada de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-216">Creating a custom Docker image</span></span>

<span data-ttu-id="d08be-217">De forma opcional, en lugar de ejecutar directamente la compilación de Docker desde la carpeta del proyecto, primero puede generar una carpeta que se pueda implementar con las bibliotecas de .NET y los binarios necesarios al ejecutar dotnet publish y, luego, usar el comando docker build.</span><span class="sxs-lookup"><span data-stu-id="d08be-217">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="d08be-218">Esto creará una imagen de Docker con el nombre cesardl/netcore-webapi-microservice-docker:first.</span><span class="sxs-lookup"><span data-stu-id="d08be-218">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="d08be-219">En este caso, :first es una etiqueta que representa una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="d08be-219">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="d08be-220">Puede repetir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta.</span><span class="sxs-lookup"><span data-stu-id="d08be-220">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="d08be-221">Cuando una aplicación se compone de varios contenedores (es decir, es una aplicación de varios contenedores), también puede usar el comando docker-compose up --build para compilar todas las imágenes relacionadas con un solo comando al usar los metadatos expuestos en los archivos relacionados docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="d08be-221">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="d08be-222">Puede encontrar las imágenes existentes en el repositorio local mediante el comando docker images, como se muestra en la figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="d08be-222">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="d08be-223">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="d08be-223">**Figure 5-6.**</span></span> <span data-ttu-id="d08be-224">Visualización de imágenes existentes mediante el comando docker images</span><span class="sxs-lookup"><span data-stu-id="d08be-224">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="d08be-225">Creación de imágenes de Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-225">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="d08be-226">Cuando se usa Visual Studio para crear un proyecto con compatibilidad con Docker, no se crea una imagen de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="d08be-226">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="d08be-227">Por el contrario, la imagen se crea automáticamente al presionar F5 y ejecutar el servicio o la aplicación a los que se ha aplicado Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-227">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="d08be-228">Este paso es automático en Visual Studio y el usuario no lo ve, pero es importante conocer lo que ocurre en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d08be-228">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="d08be-229">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="d08be-229">Step 4.</span></span> <span data-ttu-id="d08be-230">Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="d08be-230">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="d08be-231">El archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) permite definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con comandos de implementación.</span><span class="sxs-lookup"><span data-stu-id="d08be-231">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="d08be-232">Para usar un archivo docker-compose.yml, debe crear el archivo en la carpeta de solución principal o raíz, con contenido similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d08be-232">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

<span data-ttu-id="d08be-233">Tenga en cuenta que este archivo docker-compose.yml es una versión simplificada y combinada.</span><span class="sxs-lookup"><span data-stu-id="d08be-233">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="d08be-234">Contiene datos de configuración estáticos para cada contenedor (como el nombre de la imagen personalizada), que siempre se aplican, junto con información de configuración que puede depender del entorno de implementación, como la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="d08be-234">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="d08be-235">En secciones posteriores aprenderá a dividir la configuración de docker-compose.yml en varios archivos docker-compose y a sustituir los valores según el entorno y el tipo de ejecución (depuración o versión).</span><span class="sxs-lookup"><span data-stu-id="d08be-235">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="d08be-236">El ejemplo de archivo docker-compose.yml define cuatro servicios: el servicio webmvc (una aplicación web), dos microservicios (catalog.api y ordering.api) y un contenedor de fuente de datos, sql.data, según el servidor de SQL Server para Linux que se ejecute como contenedor.</span><span class="sxs-lookup"><span data-stu-id="d08be-236">The docker-compose.yml file example defines four services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="d08be-237">Cada servicio se implementa como un contenedor, por lo que se necesita una imagen de Docker para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="d08be-237">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="d08be-238">El archivo docker-compose.yml especifica no solo qué contenedores se van a usar, sino cómo se configuran individualmente.</span><span class="sxs-lookup"><span data-stu-id="d08be-238">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="d08be-239">Por ejemplo, la definición del contenedor webmvc en el archivo .yml:</span><span class="sxs-lookup"><span data-stu-id="d08be-239">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="d08be-240">Usa una imagen precompilada eshop/web:latest.</span><span class="sxs-lookup"><span data-stu-id="d08be-240">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="d08be-241">Pero también puede configurar la imagen de modo que se compile como parte de la ejecución de docker-compose con una configuración adicional basada en una compilación: sección del archivo docker-compose.</span><span class="sxs-lookup"><span data-stu-id="d08be-241">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="d08be-242">Inicializa dos variables de entorno (CatalogUrl y OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="d08be-242">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="d08be-243">Reenvía el puerto 80 expuesto en el contenedor al puerto 80 externo del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="d08be-243">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="d08be-244">Vincula la aplicación web al catálogo y el servicio de orden con el valor depends\_on.</span><span class="sxs-lookup"><span data-stu-id="d08be-244">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="d08be-245">Esto hace que el servicio espere hasta que se inician los servicios.</span><span class="sxs-lookup"><span data-stu-id="d08be-245">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="d08be-246">Se volverá a hablar del archivo docker-compose.yml en una sección posterior, cuando se trate la implementación de microservicios y aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-246">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="d08be-247">Trabajo con docker-compose.yml en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-247">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="d08be-248">Cuando se agrega compatibilidad con soluciones de Docker a un proyecto de servicio en una solución de Visual Studio, como se muestra en la figura 5-7, Visual Studio agrega un Dockerfile al proyecto y una sección de servicio (proyecto) en la solución con los archivos docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="d08be-248">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="d08be-249">Es una forma sencilla de empezar a crear la solución de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-249">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="d08be-250">Luego puede abrir los archivos docker-compose.yml y actualizarlos con otras características.</span><span class="sxs-lookup"><span data-stu-id="d08be-250">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="d08be-251">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="d08be-251">**Figure 5-7**.</span></span> <span data-ttu-id="d08be-252">Adición de compatibilidad con Docker en Visual Studio 2017 al hacer clic con el botón derecho en un proyecto de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d08be-252">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="d08be-253">Al agregar compatibilidad con Docker en Visual Studio no solo se agrega el Dockerfile al proyecto, sino que se agrega la información de configuración a varios archivos docker-compose.yml globales establecidos en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="d08be-253">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="d08be-254">Después de agregar compatibilidad con Docker a la solución en Visual Studio, también se ve un nuevo nodo (en el archivo de proyecto docker-compose.dcproj) en el Explorador de soluciones que contiene los archivos docker-compose.yml agregados, como se muestra en la figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="d08be-254">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="d08be-255">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="d08be-255">**Figure 5-8**.</span></span> <span data-ttu-id="d08be-256">Nodo de árbol **docker-compose** agregado en el Explorador de soluciones de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-256">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="d08be-257">Puede implementar una aplicación de varios contenedores con un único archivo docker-compose.yml mediante el comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="d08be-257">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="d08be-258">Pero Visual Studio agrega un grupo de ellos para que pueda sustituir valores en función del entorno (desarrollo frente a producción) y el tipo de ejecución (versión frente a depuración).</span><span class="sxs-lookup"><span data-stu-id="d08be-258">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="d08be-259">Esta capacidad se explica en secciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d08be-259">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="d08be-260">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="d08be-260">Step 5.</span></span> <span data-ttu-id="d08be-261">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="d08be-261">Build and run your Docker application</span></span>

<span data-ttu-id="d08be-262">Si la aplicación solo tiene un contenedor, puede ejecutarla mediante su implementación en el host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="d08be-262">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="d08be-263">Pero si la aplicación contiene varios servicios, se puede implementar como una aplicación compuesta, ya sea mediante un solo comando de la CLI (docker-compose up) o con Visual Studio, que usará ese comando en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d08be-263">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="d08be-264">Echemos un vistazo a las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="d08be-264">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="d08be-265">Opción A: ejecución de un solo contenedor con la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-265">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="d08be-266">Puede ejecutar un contenedor de Docker mediante el comando docker run, como se muestra en la figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="d08be-266">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="d08be-267">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="d08be-267">**Figure 5-9**.</span></span> <span data-ttu-id="d08be-268">Ejecución de un contenedor de Docker mediante el comando docker run</span><span class="sxs-lookup"><span data-stu-id="d08be-268">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="d08be-269">En este caso, el comando enlaza el puerto interno 5000 del contenedor con el puerto 80 del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="d08be-269">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="d08be-270">Esto significa que el host escucha en el puerto 80 y reenvía al puerto 5000 del contenedor.</span><span class="sxs-lookup"><span data-stu-id="d08be-270">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="d08be-271">Opción B: ejecución de una aplicación de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="d08be-271">Option B: Running a multi-container application</span></span>

<span data-ttu-id="d08be-272">En la mayoría de los escenarios de empresa, una aplicación de Docker se compone de varios servicios, lo que significa que hay que ejecutar una aplicación de varios contenedores, como se muestra en la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="d08be-272">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="d08be-273">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="d08be-273">**Figure 5-10**.</span></span> <span data-ttu-id="d08be-274">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="d08be-274">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="d08be-275">Ejecución de una aplicación de varios contenedores con la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-275">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="d08be-276">Para ejecutar una aplicación de varios contenedores con la CLI de Docker, puede ejecutar el comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="d08be-276">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="d08be-277">Este comando usa el archivo docker-compose.yml que hay en el nivel de solución para implementar una aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-277">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="d08be-278">La figura 5-11 muestra los resultados de la ejecución del comando desde el directorio principal del proyecto, que contiene el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="d08be-278">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="d08be-279">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="d08be-279">**Figure 5-11**.</span></span> <span data-ttu-id="d08be-280">Resultados del ejemplo al ejecutar el comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="d08be-280">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="d08be-281">Después de la ejecución del comando docker-compose up, la aplicación y sus contenedores relacionados se implementan en el host de Docker, como se muestra en la representación de la máquina virtual de la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="d08be-281">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="d08be-282">Ejecución y depuración de una aplicación de varios contenedores con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-282">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="d08be-283">La ejecución de una aplicación de varios contenedores mediante Visual Studio 2017 no puede ser más sencilla.</span><span class="sxs-lookup"><span data-stu-id="d08be-283">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="d08be-284">No solo se puede ejecutar la aplicación de varios contenedores, sino que es posible depurar todos sus contenedores directamente desde Visual Studio al establecer puntos de interrupción regulares.</span><span class="sxs-lookup"><span data-stu-id="d08be-284">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="d08be-285">Como se ha mencionado antes, cada vez que se agrega compatibilidad con soluciones de Docker a un proyecto de una solución, ese proyecto se configura en el archivo global (nivel de solución) docker-compose.yml, lo que permite ejecutar o depurar la solución completa al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d08be-285">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="d08be-286">Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad con soluciones de Docker y realiza todos los pasos internos automáticamente (dotnet publish, docker build, etc.).</span><span class="sxs-lookup"><span data-stu-id="d08be-286">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="d08be-287">Lo importante aquí es que, como se muestra en la figura 5-12, en Visual Studio 2017 hay un comando adicional de **Docker** para la acción de la tecla F5.</span><span class="sxs-lookup"><span data-stu-id="d08be-287">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="d08be-288">Esta opción permite ejecutar o depurar una aplicación de varios contenedores mediante la ejecución de todos los contenedores definidos en los archivos docker-compose.yml en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="d08be-288">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="d08be-289">La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada uno en un proyecto diferente (contenedor) y, durante la depuración desde Visual Studio, detenerse en los puntos de interrupción definidos en los distintos proyectos y en ejecución en contenedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="d08be-289">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="d08be-290">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="d08be-290">**Figure 5-12**.</span></span> <span data-ttu-id="d08be-291">Ejecución de aplicaciones de varios contenedores en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-291">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-292">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-292">Additional resources</span></span>

-   <span data-ttu-id="d08be-293">**Implementación de un contenedor ASP.NET en un host remoto de Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="d08be-293">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="d08be-294">Nota sobre las pruebas y la implementación con orquestadores</span><span class="sxs-lookup"><span data-stu-id="d08be-294">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="d08be-295">Los comandos docker-compose up y docker run (o la ejecución y depuración de los contenedores en Visual Studio) son adecuados para probar contenedores en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d08be-295">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="d08be-296">Pero no debería usar este enfoque si el destino son clústeres y orquestadores de Docker como Docker Swarm, Mesosphere DC/OS o Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="d08be-296">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="d08be-297">Si está usando un clúster como [modo Docker Swarm](https://docs.docker.com/engine/swarm/) (disponible en Docker CE para Windows y Mac a partir de la versión 1.12), debe implementar y probar con otros comandos, como [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) para servicios únicos.</span><span class="sxs-lookup"><span data-stu-id="d08be-297">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="d08be-298">Si va a implementar una aplicación formada por varios contenedores, use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) y [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) para implementar la aplicación compuesta como una *pila*.</span><span class="sxs-lookup"><span data-stu-id="d08be-298">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="d08be-299">Para más información, vea la entrada de blog [Introducing Experimental Distributed Application Bundles (Introducción a los lotes de aplicaciones experimentales distribuidos)](https://blog.docker.com/2016/06/docker-app-bundle/) en la documentación de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-299">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="d08be-300">en el sitio de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-300">on the Docker site.</span></span>

<span data-ttu-id="d08be-301">En [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) se usarían además comandos y scripts de implementación diferentes.</span><span class="sxs-lookup"><span data-stu-id="d08be-301">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="d08be-302">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="d08be-302">Step 6.</span></span> <span data-ttu-id="d08be-303">Probar la aplicación de Docker con el host local de Docker</span><span class="sxs-lookup"><span data-stu-id="d08be-303">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="d08be-304">Este paso varía en función de lo que haga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d08be-304">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="d08be-305">En una aplicación web de .NET Core sencilla implementada como un único contenedor o servicio, puede acceder al servicio si abre un explorador en el host de Docker y va a ese sitio, como se muestra en la figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="d08be-305">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="d08be-306">(Si la configuración del Dockerfile asigna el contenedor a un puerto del host distinto al 80, incluya el puerto del host en la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="d08be-306">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="d08be-307">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="d08be-307">**Figure 5-13**.</span></span> <span data-ttu-id="d08be-308">Ejemplo de prueba de la aplicación de Docker en local mediante localhost</span><span class="sxs-lookup"><span data-stu-id="d08be-308">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="d08be-309">Si localhost no apunta a la IP del host de Docker (de forma predeterminada, al usar Docker CE, debería hacerlo), para ir al servicio, use la dirección IP de la tarjeta de red del equipo.</span><span class="sxs-lookup"><span data-stu-id="d08be-309">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="d08be-310">Tenga en cuenta que esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se está analizando.</span><span class="sxs-lookup"><span data-stu-id="d08be-310">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="d08be-311">Pero, internamente, las solicitudes se redirigen al puerto 5000, porque así es como se ha implementado con el comando docker run, como se ha explicado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d08be-311">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="d08be-312">También puede probar la aplicación con la CURL del terminal, como se muestra en la figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="d08be-312">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="d08be-313">En una instalación de Docker en Windows, el valor predeterminado de la IP del host de Docker es siempre 10.0.75.1, además de la dirección IP real del equipo.</span><span class="sxs-lookup"><span data-stu-id="d08be-313">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="d08be-314">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="d08be-314">**Figure 5-14**.</span></span> <span data-ttu-id="d08be-315">Ejemplo de prueba de la aplicación de Docker en local mediante CURL</span><span class="sxs-lookup"><span data-stu-id="d08be-315">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="d08be-316">Prueba y depuración de contenedores con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="d08be-316">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="d08be-317">Al ejecutar y depurar los contenedores con Visual Studio 2017, puede depurar la aplicación de .NET prácticamente de la misma manera que como lo haría al ejecutar sin contenedores.</span><span class="sxs-lookup"><span data-stu-id="d08be-317">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="d08be-318">Pruebas y depuración sin Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-318">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="d08be-319">Si está desarrollando con el enfoque de editor/CLI, la depuración de contenedores es más difícil y se prefiere hacer mediante la generación de seguimientos.</span><span class="sxs-lookup"><span data-stu-id="d08be-319">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-320">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-320">Additional resources</span></span>

-   <span data-ttu-id="d08be-321">**Depuración de aplicaciones en un contenedor de Docker local**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="d08be-321">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="d08be-322">**Steve Lasker. Compilar, depurar e implementar aplicaciones ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="d08be-322">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="d08be-323">Video.</span><span class="sxs-lookup"><span data-stu-id="d08be-323">Video.</span></span>
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="d08be-324">Flujo de trabajo simplificado al desarrollar contenedores con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-324">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="d08be-325">En la práctica, el flujo de trabajo cuando se usa Visual Studio es mucho más sencillo que si se usa el enfoque de editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="d08be-325">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="d08be-326">La mayoría de los pasos que necesita Docker relacionados con el Dockerfile y los archivos docker-compose.yml están ocultos o se han simplificado con Visual Studio, como se muestra en la figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="d08be-326">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="d08be-327">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="d08be-327">**Figure 5-15**.</span></span> <span data-ttu-id="d08be-328">Flujo de trabajo simplificado al desarrollar con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d08be-328">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="d08be-329">Además, debe realizar el paso 2 (agregar compatibilidad con Docker a los proyectos) una sola vez.</span><span class="sxs-lookup"><span data-stu-id="d08be-329">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="d08be-330">Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habituales cuando se usa .NET para cualquier otro desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d08be-330">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="d08be-331">Debe saber qué está sucediendo en segundo plano (el proceso de compilación de imágenes, qué imágenes base usa, la implementación de contenedores, etc.) y, a veces, también debe editar el Dockerfile o el archivo docker-compose.yml para personalizar comportamientos.</span><span class="sxs-lookup"><span data-stu-id="d08be-331">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="d08be-332">Pero con Visual Studio se simplifica enormemente la mayor parte del trabajo, lo que mejora mucho la productividad.</span><span class="sxs-lookup"><span data-stu-id="d08be-332">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d08be-333">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-333">Additional resources</span></span>

-   <span data-ttu-id="d08be-334">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111) (Desarrollo de Docker de .NET con Visual Studio 2017, de Steve Lasker)</span><span class="sxs-lookup"><span data-stu-id="d08be-334">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="d08be-335">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/) (Colocación de una aplicación de .NET Core en un contenedor con las nuevas Herramientas de Docker para Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="d08be-335">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="d08be-336">Uso de comandos de PowerShell en un Dockerfile para configurar contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="d08be-336">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="d08be-337">Los [contenedores de Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) permiten convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="d08be-337">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="d08be-338">Para usar contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d08be-338">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="d08be-339">En este caso se usa una imagen base de Windows Server Core (el valor FROM) y se instala IIS con un comando de PowerShell (el valor RUN).</span><span class="sxs-lookup"><span data-stu-id="d08be-339">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="d08be-340">Del mismo modo, también se pueden usar comandos de PowerShell para configurar otros componentes como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows.</span><span class="sxs-lookup"><span data-stu-id="d08be-340">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="d08be-341">Por ejemplo, el siguiente comando en un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="d08be-341">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="d08be-342">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d08be-342">Additional resources</span></span>

-   <span data-ttu-id="d08be-343">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="d08be-343">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="d08be-344">Example Powershell commands to run from dockerfiles to include Windows features (Comandos de PowerShell de ejemplo para ejecutar desde Dockerfiles a fin de incluir características de Windows).</span><span class="sxs-lookup"><span data-stu-id="d08be-344">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="d08be-345">[Anterior](index.md)
[Siguiente](../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="d08be-345">[Previous](index.md)
[Next](../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
