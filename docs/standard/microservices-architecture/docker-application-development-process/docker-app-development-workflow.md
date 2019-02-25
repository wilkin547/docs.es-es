---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Comprenda los detalles del flujo de trabajo para desarrollar aplicaciones basadas en Docker. Comience paso a paso, profundice en algunos detalles para optimizar Dockerfiles y termine con el flujo de trabajo simplificado disponible cuando se usa Visual Studio.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: c34d49307408520afc6223a43d1c347dd6cffb97
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584309"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="7b93d-104">Flujo de trabajo de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="7b93d-105">El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde se programa la aplicación con el lenguaje preferido y se prueba en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="7b93d-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="7b93d-106">Con este flujo de trabajo, no importa el lenguaje, el marco ni la plataforma que se elija, ya que siempre se desarrollan y se prueban contenedores de Docker en local.</span><span class="sxs-lookup"><span data-stu-id="7b93d-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="7b93d-107">Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="7b93d-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="7b93d-108">Una selección de sistema operativo, por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="7b93d-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="7b93d-109">Archivos agregados durante el desarrollo, por ejemplo, archivos binarios de código fuente y aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="7b93d-110">Información de configuración, como configuración de entorno y dependencias.</span><span class="sxs-lookup"><span data-stu-id="7b93d-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="7b93d-111">Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="7b93d-112">En esta sección se explica el flujo de trabajo de desarrollo de *bucle interno* para aplicaciones basadas en contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="7b93d-113">Flujo de trabajo de bucle interno significa que no se tiene en cuenta el flujo de trabajo general de DevOps, que puede incluir hasta implementación en producción, y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="7b93d-113">The inner-loop workflow means it's not considering the broader DevOps workflow, that can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="7b93d-114">Los pasos iniciales para configurar el entorno no se incluyen, ya que se realizan solo una vez.</span><span class="sxs-lookup"><span data-stu-id="7b93d-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="7b93d-115">Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="7b93d-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="7b93d-116">Estos son los pasos básicos que normalmente se realizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="7b93d-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![<span data-ttu-id="7b93d-117">Proceso de desarrollo de aplicaciones de Docker: 1. Programar la aplicación, 2. Escribir Dockerfiles, 3. Crear imágenes definidas en Dockerfiles, 4. (Opcional) Crear servicios en el archivo docker-compose.yml, 5. Ejecutar contenedor o aplicación docker-compose, 6. Probar la aplicación o los microservicios, 7. Insertar en el repositorio y repetir.</span><span class="sxs-lookup"><span data-stu-id="7b93d-117">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span> ](./media/image1.png)

<span data-ttu-id="7b93d-118">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-118">**Figure 5-1.**</span></span> <span data-ttu-id="7b93d-119">Flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-119">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="7b93d-120">En esta sección se detalla el proceso completo y se explica cada paso importante centrándose en un entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-120">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="7b93d-121">Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, Visual Studio Code más la CLI de Docker en macOS o Windows), es necesario conocer cada paso, generalmente más detalladamente que si se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-121">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="7b93d-122">Para obtener más información sobre cómo trabajar en un entorno de CLI, vea el libro electrónico [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo de vida de las aplicaciones en contenedor de Docker con plataformas y herramientas de Microsoft).</span><span class="sxs-lookup"><span data-stu-id="7b93d-122">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="7b93d-123">Cuando se usa Visual Studio 2017, muchos de esos pasos se controlan de forma automática, lo que mejora considerablemente la productividad.</span><span class="sxs-lookup"><span data-stu-id="7b93d-123">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="7b93d-124">Esto es así especialmente con Visual Studio 2017 y cuando el destino son aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="7b93d-124">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="7b93d-125">Por ejemplo, con un solo clic, Visual Studio agrega el Dockerfile y el archivo docker-compose.yml a los proyectos con la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-125">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="7b93d-126">Al ejecutar la aplicación en Visual Studio, compila la imagen de Docker y ejecuta la aplicación de varios contenedores directamente en Docker; incluso permite depurar varios contenedores al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-126">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="7b93d-127">Estas características aumentan la velocidad de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-127">These features will boost your development speed.</span></span>

<span data-ttu-id="7b93d-128">Pero que Visual Studio realice esos pasos automáticamente no significa que no sea necesario saber lo que ocurre en segundo plano con Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-128">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="7b93d-129">Por lo tanto, la guía siguiente detalla cada paso.</span><span class="sxs-lookup"><span data-stu-id="7b93d-129">Therefore, the following guidance details every step.</span></span>

![1. Programar la aplicación](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="7b93d-131">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="7b93d-131">Step 1.</span></span> <span data-ttu-id="7b93d-132">Empezar a programar y crear la aplicación inicial o la base de referencia del servicio</span><span class="sxs-lookup"><span data-stu-id="7b93d-132">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="7b93d-133">El desarrollo de una aplicación de Docker es similar al desarrollo de una aplicación sin Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-133">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="7b93d-134">La diferencia es que al desarrollar para Docker, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker en el entorno local (una instalación de máquina virtual de Linux realizada por Docker o directamente Windows si se usan contenedores de Windows).</span><span class="sxs-lookup"><span data-stu-id="7b93d-134">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="7b93d-135">Configurar el entorno local con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="7b93d-136">Para empezar, asegúrese de que tiene instalado [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) para Windows, como se explica en estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="7b93d-136">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="7b93d-137">Get started with Docker CE for Windows (Introducción a Docker CE para Windows)</span><span class="sxs-lookup"><span data-stu-id="7b93d-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="7b93d-138">Además, se necesita Visual Studio 2017 versión 15.7 o posterior con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada, como se muestra en la figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="7b93d-138">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Selección de carga de trabajo de desarrollo multiplataforma de .NET Core durante la instalación de Visual Studio.](./media/image3.png)

<span data-ttu-id="7b93d-140">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-140">**Figure 5-2**.</span></span> <span data-ttu-id="7b93d-141">Selección de la carga de trabajo **Desarrollo multiplataforma de .NET Core** durante la instalación de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-141">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="7b93d-142">Puede empezar a programar la aplicación en .NET sin formato (normalmente en .NET Core si va a usar contenedores) incluso antes de habilitar Docker en la aplicación e implementar y probar en Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-142">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="7b93d-143">Pero se recomienda empezar a trabajar en Docker tan pronto como sea posible, ya que es el entorno real y se pueden detectar los problemas a la mayor brevedad.</span><span class="sxs-lookup"><span data-stu-id="7b93d-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="7b93d-144">Se recomienda encarecidamente porque Visual Studio facilita tanto el trabajo con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de varios contenedores desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-145">Additional resources</span></span>

- <span data-ttu-id="7b93d-146">**Get started with Docker CE for Windows** \ (Introducción a Docker CE para Windows)</span><span class="sxs-lookup"><span data-stu-id="7b93d-146">**Get started with Docker CE for Windows** \\</span></span>
  [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="7b93d-147">**Visual Studio 2017** \\</span><span class="sxs-lookup"><span data-stu-id="7b93d-147">**Visual Studio 2017** \\</span></span>
  [*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![2. Escribir Dockerfiles](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="7b93d-149">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="7b93d-149">Step 2.</span></span> <span data-ttu-id="7b93d-150">Crear un Dockerfile relacionado con una imagen base existente de .NET</span><span class="sxs-lookup"><span data-stu-id="7b93d-150">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="7b93d-151">Necesita un Dockerfile para cada imagen personalizada que quiera compilar; también necesita un Dockerfile para cada contenedor que se vaya a implementar, tanto si se implementa automáticamente desde Visual Studio como manualmente mediante la CLI de Docker (comandos docker run y docker-compose).</span><span class="sxs-lookup"><span data-stu-id="7b93d-151">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="7b93d-152">Si la aplicación contiene un único servicio personalizado, necesita un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="7b93d-152">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="7b93d-153">Si la aplicación contiene varios servicios (como en una arquitectura de microservicios), necesita un Dockerfile para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-153">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="7b93d-154">El Dockerfile se coloca en la carpeta raíz de la aplicación o el servicio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-154">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="7b93d-155">Contiene los comandos que indican a Docker cómo configurar y ejecutar la aplicación o el servicio en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-155">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="7b93d-156">Puede crear un Dockerfile de forma manual en el código y agregarlo al proyecto junto con las dependencias de .NET.</span><span class="sxs-lookup"><span data-stu-id="7b93d-156">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="7b93d-157">Con Visual Studio y sus herramientas para Docker, esta tarea solo exige unos clics.</span><span class="sxs-lookup"><span data-stu-id="7b93d-157">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="7b93d-158">Al crear un nuevo proyecto en Visual Studio 2017, hay una opción denominada **Enable Container (Docker) Support** (Habilitar compatibilidad con contenedor (Docker)), como se muestra en la figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="7b93d-158">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![Activación de la casilla de compatibilidad con Docker al crear un nuevo proyecto de ASP.NET Core en Visual Studio 2017](./media/image5.png)

<span data-ttu-id="7b93d-160">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-160">**Figure 5-3**.</span></span> <span data-ttu-id="7b93d-161">Activación de la compatibilidad con Docker al crear un nuevo proyecto de ASP.NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-161">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="7b93d-162">También puede habilitar la compatibilidad con Docker en un proyecto de aplicación web de ASP.NET Core existente si hace clic con el botón derecho en el proyecto en el **Explorador de soluciones** y selecciona **Agregar** > **Compatibilidad con Docker**, como se muestra en la figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="7b93d-162">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Opción de menú Agregar compatibilidad con Docker en Visual Studio](./media/image6.png)

<span data-ttu-id="7b93d-164">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-164">**Figure 5-4**.</span></span> <span data-ttu-id="7b93d-165">Habilitación de la compatibilidad con Docker en un proyecto existente de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-165">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="7b93d-166">Esta acción agrega un *Dockerfile* al proyecto con la configuración necesaria y solo está disponible en los proyectos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b93d-166">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="7b93d-167">De forma similar, Visual Studio también puede agregar un archivo docker-compose.yml para toda la solución con la opción **Agregar > Container Orchestrator Support** (Compatibilidad con el orquestador de contenedores).</span><span class="sxs-lookup"><span data-stu-id="7b93d-167">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="7b93d-168">En el paso 4 se examina esta opción más detalladamente.</span><span class="sxs-lookup"><span data-stu-id="7b93d-168">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="7b93d-169">Uso de una imagen de Docker de .NET oficial existente</span><span class="sxs-lookup"><span data-stu-id="7b93d-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="7b93d-170">Normalmente se compila una imagen personalizada para el contenedor además de una imagen base que se obtiene de un repositorio oficial como el registro [Docker Hub](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="7b93d-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="7b93d-171">Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="7b93d-172">El Dockerfile usa una imagen `aspnetcore` existente.</span><span class="sxs-lookup"><span data-stu-id="7b93d-172">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="7b93d-173">Anteriormente se ha explicado qué imágenes y repositorios de Docker se pueden usar según el marco de trabajo y el sistema operativo elegidos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="7b93d-174">Por ejemplo, si quiere usar ASP.NET Core (Linux o Windows), la imagen que se debe usar es `microsoft/dotnet:2.2-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="7b93d-175">Por lo tanto, debe especificar qué imagen base de Docker va a usar para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="7b93d-176">Se hace mediante la incorporación de `FROM microsoft/dotnet:2.2-aspnetcore-runtime` al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="7b93d-176">You do that by adding `FROM microsoft/dotnet:2.2-aspnetcore-runtime` to your Dockerfile.</span></span> <span data-ttu-id="7b93d-177">Visual Studio lo hace de forma automática, pero si va a actualizar la versión, actualice este valor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="7b93d-178">El uso de un repositorio de imágenes de .NET oficial de Docker Hub con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todos los equipos (incluido el desarrollo, las pruebas y la producción).</span><span class="sxs-lookup"><span data-stu-id="7b93d-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="7b93d-179">En el ejemplo siguiente se muestra un Dockerfile de ejemplo para un contenedor de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b93d-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/dotnet:2.2-aspnetcore-runtime
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="7b93d-180">En este caso, la imagen se basa en la versión 2.2 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="7b93d-180">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="7b93d-181">Es el valor `FROM microsoft/dotnet:2.2-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-181">This is the setting `FROM microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="7b93d-182">[Para obtener más información sobre esta imagen base, consulte la página [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Imagen de Docker de .NET Core)]. En el Dockerfile, también debe indicar a Docker que escuche en el puerto TCP que se vaya a usar en tiempo de ejecución (en este caso, el puerto 80, como se ha configurado con el valor EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="7b93d-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="7b93d-183">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use.</span><span class="sxs-lookup"><span data-stu-id="7b93d-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="7b93d-184">Por ejemplo, la línea ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker que ejecute una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b93d-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="7b93d-185">Si usa el SDK y la CLI de .NET Core (dotnet CLI) para compilar y ejecutar la aplicación .NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="7b93d-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="7b93d-186">La conclusión es que la línea ENTRYPOINT y otros valores pueden variar según el lenguaje y la plataforma que se elijan para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-187">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-187">Additional resources</span></span>

- <span data-ttu-id="7b93d-188">**Compilación de imágenes de Docker para aplicaciones .NET Core** \\</span><span class="sxs-lookup"><span data-stu-id="7b93d-188">**Building Docker Images for .NET Core Applications** \\</span></span>
  [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="7b93d-189">**Compile su propia imagen**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-189">**Build your own image**.</span></span> <span data-ttu-id="7b93d-190">En la documentación oficial de Docker.\\</span><span class="sxs-lookup"><span data-stu-id="7b93d-190">In the official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

- <span data-ttu-id="7b93d-191">**Staying up-to-date with .NET Container Images** \ (Mantenerse actualizado con imágenes de contenedor de .NET)</span><span class="sxs-lookup"><span data-stu-id="7b93d-191">**Staying up-to-date with .NET Container Images** \\</span></span>
  [*https://blogs.msdn.microsoft.com/dotnet/2018/06/18/staying-up-to-date-with-net-container-images/*](https://blogs.msdn.microsoft.com/dotnet/2018/06/18/staying-up-to-date-with-net-container-images/)

- <span data-ttu-id="7b93d-192">**Uso conjunto de .NET y Docket: actualización de DockerCon de 2018** \\</span><span class="sxs-lookup"><span data-stu-id="7b93d-192">**Using .NET and Docker Together - DockerCon 2018 Update** \\</span></span>
  [*https://blogs.msdn.microsoft.com/dotnet/2018/06/13/using-net-and-docker-together-dockercon-2018-update/*](https://blogs.msdn.microsoft.com/dotnet/2018/06/13/using-net-and-docker-together-dockercon-2018-update/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="7b93d-193">Uso de repositorios de imágenes multiarquitectura</span><span class="sxs-lookup"><span data-stu-id="7b93d-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="7b93d-194">Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="7b93d-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="7b93d-195">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="7b93d-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="7b93d-196">Por ejemplo, el repositorio [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) disponible en el registro Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de repositorio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-196">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="7b93d-197">Si especifica una etiqueta, se toma como destino una plataforma explícita, como en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b93d-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="7b93d-198">Destinos: solo entorno de ejecución .NET Core 2.2 en Linux</span><span class="sxs-lookup"><span data-stu-id="7b93d-198">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="7b93d-199">Destinos: solo entorno de ejecución .NET Core 2.2 en Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="7b93d-199">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="7b93d-200">Pero, si se especifica el mismo nombre de imagen, incluso con la misma etiqueta, las imágenes multiarquitectura (como la imagen `aspnetcore`) usan la versión de Linux o Windows según el sistema operativo del host de Docker que se vaya a implementar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b93d-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="7b93d-201">Arquitectura múltiple: solo el entorno de ejecución .NET Core 2.2 en Linux o Windows Nano Server en función del sistema operativo del host de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-201">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="7b93d-202">De esta forma, al extraer una imagen de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="7b93d-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="7b93d-203">Compilaciones de varias fases en Dockerfile</span><span class="sxs-lookup"><span data-stu-id="7b93d-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="7b93d-204">El Dockerfile es similar a un script por lotes.</span><span class="sxs-lookup"><span data-stu-id="7b93d-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="7b93d-205">Es similar a lo que haría si tuviera que configurar el equipo desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="7b93d-206">Comienza con una imagen base que configura el contexto inicial, es como el sistema de archivos de inicio, que se coloca sobre el sistema operativo del host.</span><span class="sxs-lookup"><span data-stu-id="7b93d-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="7b93d-207">No es un sistema operativo, pero se puede considerar como "el" sistema operativo dentro del contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-207">It's not an OS, but you can think of if like "the" OS inside the container.</span></span>

<span data-ttu-id="7b93d-208">La ejecución de cada línea de comandos crea una nueva capa en el sistema de archivos con los cambios de la anterior, por lo que, cuando se combinan, generan el sistema de archivos resultante.</span><span class="sxs-lookup"><span data-stu-id="7b93d-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="7b93d-209">Dado que cada nueva capa "descansa" sobre la anterior y el tamaño de la imagen resultante aumenta con cada comando, las imágenes pueden llegar a tener un gran tamaño si tienen que incluir, por ejemplo, el SDK necesario para compilar y publicar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="7b93d-210">Aquí es donde las compilaciones de varias fases entran en escena (a partir de Docker 17.05 y posterior) para hacer su magia.</span><span class="sxs-lookup"><span data-stu-id="7b93d-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="7b93d-211">La idea central es que puede separar el proceso de ejecución del Dockerfile en fases, donde una fase es una imagen inicial seguida de uno o más comandos, y la última fase determina el tamaño final de la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="7b93d-212">En resumen, las compilaciones de varias fases permiten dividir la creación en "fases" distintas y, luego, ensamblar la imagen final al tomar solo los directorios pertinentes de las fases intermedias.</span><span class="sxs-lookup"><span data-stu-id="7b93d-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="7b93d-213">La estrategia general para usar esta característica es:</span><span class="sxs-lookup"><span data-stu-id="7b93d-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="7b93d-214">Usar una imagen base de SDK (no importa su tamaño), con todo lo necesario para compilar y publicar la aplicación en una carpeta</span><span class="sxs-lookup"><span data-stu-id="7b93d-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="7b93d-215">Usar una imagen base pequeña de solo el entorno de ejecución y copiar la carpeta de publicación de la fase anterior para generar una pequeña imagen final.</span><span class="sxs-lookup"><span data-stu-id="7b93d-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="7b93d-216">Probablemente la mejor manera de comprender las fases es analizar un archivo Dockerfile en detalle, línea a línea, así que vamos a comenzar con el Dockerfile inicial creado por Visual Studio al agregar compatibilidad con Docker a un proyecto y, luego, realizaremos algunas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="7b93d-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="7b93d-217">El Dockerfile inicial podría ser algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="7b93d-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks … 
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -0 /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="7b93d-218">Y estos son los detalles, línea a línea:</span><span class="sxs-lookup"><span data-stu-id="7b93d-218">And these are the details, line by line:</span></span>

1.  <span data-ttu-id="7b93d-219">Comience una fase con una imagen base "pequeña" de solo el entorno de ejecución, denomínela **base** para referencia.</span><span class="sxs-lookup"><span data-stu-id="7b93d-219">Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>
2.  <span data-ttu-id="7b93d-220">Cree un directorio **/app** en la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-220">Create **/app** directory in the image.</span></span>
3.  <span data-ttu-id="7b93d-221">Exponga el puerto **80**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-221">Expose port **80**.</span></span>
<!-- skip -->
5.  <span data-ttu-id="7b93d-222">Comience una nueva fase con una imagen "grande" para compilar y publicar, denomínela **build** para referencia.</span><span class="sxs-lookup"><span data-stu-id="7b93d-222">Begin a new stage with "large" image for building/publishing, call it **build** for reference.</span></span>
6.  <span data-ttu-id="7b93d-223">Cree un directorio **/src** en la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-223">Create directory **/src** in the image.</span></span>
7.  <span data-ttu-id="7b93d-224">Hasta la línea 16, copie los archivos **.csproj** de los proyectos a los que se hace referencia para poder restaurar los paquetes más adelante.</span><span class="sxs-lookup"><span data-stu-id="7b93d-224">Up to line 16, copy referenced projects **.csproj** files, to be able to restore packages later.</span></span>
<!-- skip -->
17. <span data-ttu-id="7b93d-225">Restaure los paquetes del proyecto **Catalog.API** y los proyectos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7b93d-225">Restore packages for the **Catalog.API** project and the referenced projects.</span></span>
18. <span data-ttu-id="7b93d-226">Copie **todo el árbol de directorio de la solución** (excepto los archivos o directorios incluidos en el archivo **.dockerignore**) del directorio **/src** en la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-226">Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) from to the **/src** directory in the image.</span></span>
19. <span data-ttu-id="7b93d-227">Cambie la carpeta actual al proyecto **Catalog.API**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-227">Change current folder to **Catalog.API** project.</span></span>
20. <span data-ttu-id="7b93d-228">Compile el proyecto (y otras dependencias del proyecto) y use como salida el directorio **/app** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-228">Build project (and other project dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
22. <span data-ttu-id="7b93d-229">Comience una nueva fase a partir de la compilación, denomínela **publish** para referencia.</span><span class="sxs-lookup"><span data-stu-id="7b93d-229">Begin a new stage continuing from build, call it **publish** for reference.</span></span>
23. <span data-ttu-id="7b93d-230">Publique el proyecto (y las dependencias) y use como salida el directorio **/app** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-230">Publish project (and dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
25. <span data-ttu-id="7b93d-231">Comience una nueva fase a partir de **base** y denomínela **final**</span><span class="sxs-lookup"><span data-stu-id="7b93d-231">Begin a new stage continuing from **base** and call it **final**</span></span>
26. <span data-ttu-id="7b93d-232">Cambie el directorio actual a **/app**</span><span class="sxs-lookup"><span data-stu-id="7b93d-232">Change current directory to **/app**</span></span>
27. <span data-ttu-id="7b93d-233">Copie el directorio **/app** de la fase **publish** en el directorio actual</span><span class="sxs-lookup"><span data-stu-id="7b93d-233">Copy the **/app** directory from stage **publish** to the current directory</span></span>
28. <span data-ttu-id="7b93d-234">Defina el comando que se va a ejecutar cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-234">Define the command to run when the container is started.</span></span>

<span data-ttu-id="7b93d-235">Ahora vamos a examinar algunas optimizaciones para mejorar el rendimiento del proceso completo, lo que, en el caso de eShopOnContainers, significa aproximadamente 22 minutos o más para compilar la solución completa en contenedores de Linux.</span><span class="sxs-lookup"><span data-stu-id="7b93d-235">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="7b93d-236">Puede aprovechar la característica de caché de capas de Docker, que es bastante sencilla: si la imagen base y los comandos son los mismos que algunos ejecutados previamente, puede usar la capa resultante sin necesidad de ejecutar los comandos, con lo que se ahorra algo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-236">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="7b93d-237">Así, vamos a centrarnos en la fase **build**, las líneas 5 y 6 son prácticamente iguales, pero las líneas 7-17 son diferentes para cada servicio de eShopOnContainers, así que se tienen que ejecutar cada vez, pero si ha cambiado las líneas 7-16 a:</span><span class="sxs-lookup"><span data-stu-id="7b93d-237">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```
COPY . .
```

<span data-ttu-id="7b93d-238">Luego, sería igual para cada servicio, se copiaría la solución completa y se crearía una capa más grande pero:</span><span class="sxs-lookup"><span data-stu-id="7b93d-238">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1) <span data-ttu-id="7b93d-239">El proceso de copia solo se ejecutaría la primera vez (y al recompilar si se modifica un archivo) y se usaría la memoria caché para todos los demás servicios y</span><span class="sxs-lookup"><span data-stu-id="7b93d-239">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2) <span data-ttu-id="7b93d-240">Puesto que la imagen más grande se produce en una fase intermedia, no afecta al tamaño final de la imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-240">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="7b93d-241">La siguiente optimización importante implica al comando `restore` ejecutado en la línea 17, que también es diferente para cada servicio de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="7b93d-241">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="7b93d-242">Si cambia esa línea a:</span><span class="sxs-lookup"><span data-stu-id="7b93d-242">If you change that line to just:</span></span>

```console
RUN dotnet restore
```

<span data-ttu-id="7b93d-243">Restauraría los paquetes de toda la solución, pero, de nuevo, lo haría una sola vez, en lugar de las 15 veces con la estrategia actual.</span><span class="sxs-lookup"><span data-stu-id="7b93d-243">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="7b93d-244">Pero `dotnet restore` únicamente se ejecuta si hay un solo archivo de proyecto o solución en la carpeta, así que lograrlo es un poco más complicado y la forma de solucionarlo, sin entrar en demasiados detalles, es esta:</span><span class="sxs-lookup"><span data-stu-id="7b93d-244">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1) <span data-ttu-id="7b93d-245">Agregue las líneas siguientes a **.dockerignore**:</span><span class="sxs-lookup"><span data-stu-id="7b93d-245">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="7b93d-246">`*.sln`, para omitir todos los archivos de solución del árbol de la carpeta principal</span><span class="sxs-lookup"><span data-stu-id="7b93d-246">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="7b93d-247">`!eShopOnContainers-ServicesAndWebApps.sln`, para incluir solo este archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="7b93d-247">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2) <span data-ttu-id="7b93d-248">Incluya el argumento `/ignoreprojectextensions:.dcproj` en `dotnet restore`, de modo que también omita el proyecto docker-compose y solo restaure los paquetes de la solución eShopOnContainers-ServicesAndWebApps.</span><span class="sxs-lookup"><span data-stu-id="7b93d-248">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="7b93d-249">Para la optimización final, resulta que la línea 20 es redundante, ya que la línea 23 también compila la aplicación y viene, básicamente, justo después de la línea 20, así que ahí tenemos otro comando que usa mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-249">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="7b93d-250">El archivo resultante es entonces:</span><span class="sxs-lookup"><span data-stu-id="7b93d-250">The resulting file is then:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="7b93d-251">Creación de la imagen base desde cero</span><span class="sxs-lookup"><span data-stu-id="7b93d-251">Creating your base image from scratch</span></span>

<span data-ttu-id="7b93d-252">Puede crear su propia imagen base de Docker desde cero.</span><span class="sxs-lookup"><span data-stu-id="7b93d-252">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="7b93d-253">Este escenario no se recomienda para usuarios que se están iniciando en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-253">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-254">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-254">Additional resources</span></span>

- <span data-ttu-id="7b93d-255">**Multi-arch .NET Core images** (Imágenes de .NET Core multiarquitectura).\\</span><span class="sxs-lookup"><span data-stu-id="7b93d-255">**Multi-arch .NET Core images**.\\</span></span>
  [*https://github.com/dotnet/announcements/issues/14*](https://github.com/dotnet/announcements/issues/14)

- <span data-ttu-id="7b93d-256">**Create a base image (Crear una imagen base)**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-256">**Create a base image**.</span></span> <span data-ttu-id="7b93d-257">Documentación oficial de Docker.\\</span><span class="sxs-lookup"><span data-stu-id="7b93d-257">Official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![3. Crear imágenes definidas en Dockerfiles](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="7b93d-259">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="7b93d-259">Step 3.</span></span> <span data-ttu-id="7b93d-260">Crear las imágenes de Docker personalizadas e insertar la aplicación o el servicio en ellas</span><span class="sxs-lookup"><span data-stu-id="7b93d-260">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="7b93d-261">Debe crear una imagen relacionada para cada servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-261">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="7b93d-262">Si la aplicación está formada por un único servicio o aplicación web, solo necesita una imagen.</span><span class="sxs-lookup"><span data-stu-id="7b93d-262">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="7b93d-263">Tenga en cuenta que las imágenes de Docker se compilan automáticamente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-263">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="7b93d-264">Los pasos siguientes solo son necesarios para el flujo de trabajo de editor/CLI y se explican para aclarar lo que sucede en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7b93d-264">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="7b93d-265">Como desarrollador, debe desarrollar y probar en local hasta que inserte una característica o cambio completados en el sistema de control de código fuente (por ejemplo, en GitHub).</span><span class="sxs-lookup"><span data-stu-id="7b93d-265">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="7b93d-266">Esto significa que tiene que crear las imágenes de Docker e implementar contenedores en un host de Docker local (máquina virtual de Windows o Linux) y ejecutar, probar y depurar en esos contenedores locales.</span><span class="sxs-lookup"><span data-stu-id="7b93d-266">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="7b93d-267">Para crear una imagen personalizada en el entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando docker build, como se muestra en la figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="7b93d-267">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Pantalla de progreso de la compilación de una imagen de Docker](./media/image8.png)

<span data-ttu-id="7b93d-269">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-269">**Figure 5-5**.</span></span> <span data-ttu-id="7b93d-270">Creación de una imagen personalizada de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-270">Creating a custom Docker image</span></span>

<span data-ttu-id="7b93d-271">De forma opcional, en lugar de ejecutar directamente docker build desde la carpeta del proyecto, primero puede generar una carpeta que se pueda implementar con las bibliotecas de .NET y los binarios necesarios mediante la ejecución de `dotnet publish` y, luego, usar el comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-271">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="7b93d-272">Esto crea una imagen de Docker con el nombre `cesardl/netcore-webapi-microservice-docker:first`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-272">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="7b93d-273">En este caso, :first es una etiqueta que representa una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="7b93d-273">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="7b93d-274">Puede repetir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta.</span><span class="sxs-lookup"><span data-stu-id="7b93d-274">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="7b93d-275">Cuando una aplicación se compone de varios contenedores (es decir, es una aplicación de varios contenedores), también puede usar el comando `docker-compose up --build` para compilar todas las imágenes relacionadas con un solo comando al usar los metadatos expuestos en los archivos relacionados docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="7b93d-275">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="7b93d-276">Puede encontrar las imágenes existentes en el repositorio local mediante el comando docker images, como se muestra en la figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="7b93d-276">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Vista de pantalla de lista de imágenes a partir del comando docker images](./media/image9.png)

<span data-ttu-id="7b93d-278">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-278">**Figure 5-6.**</span></span> <span data-ttu-id="7b93d-279">Visualización de imágenes existentes mediante el comando docker images</span><span class="sxs-lookup"><span data-stu-id="7b93d-279">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="7b93d-280">Creación de imágenes de Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-280">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="7b93d-281">Cuando se usa Visual Studio para crear un proyecto con compatibilidad con Docker, no se crea una imagen de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="7b93d-281">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="7b93d-282">La imagen se crea automáticamente al presionar **F5** (o **Ctrl-F5**) para ejecutar el servicio o la aplicación a los que se ha aplicado Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-282">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="7b93d-283">Este paso es automático en Visual Studio y no lo verá, pero es importante saber lo que ocurre en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7b93d-283">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![4. (Opcional) Crear servicios en el archivo docker-compose.yml](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="7b93d-285">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="7b93d-285">Step 4.</span></span> <span data-ttu-id="7b93d-286">Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="7b93d-286">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="7b93d-287">El archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) permite definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con comandos de implementación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-287">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="7b93d-288">También configura sus relaciones de dependencia y la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7b93d-288">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="7b93d-289">Para usar un archivo docker-compose.yml, debe crear el archivo en la carpeta de solución principal o raíz, con contenido similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b93d-289">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

<span data-ttu-id="7b93d-290">Este archivo docker-compose.yml es una versión simplificada y combinada.</span><span class="sxs-lookup"><span data-stu-id="7b93d-290">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="7b93d-291">Contiene datos de configuración estáticos para cada contenedor (como el nombre de la imagen personalizada), que siempre son necesarios, junto con información de configuración que puede depender del entorno de implementación, como la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="7b93d-291">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="7b93d-292">En secciones posteriores se enseña a dividir la configuración de docker-compose.yml en varios archivos docker-compose y a reemplazar los valores según el entorno y el tipo de ejecución (depuración o versión).</span><span class="sxs-lookup"><span data-stu-id="7b93d-292">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="7b93d-293">El ejemplo de archivo docker-compose.yml define cuatro servicios: el servicio `webmvc` (una aplicación web), dos microservicios (`ordering.api` y `basket.api`) y un contenedor de fuente de datos, `sql.data`, según el servidor de SQL Server para Linux que se ejecute como contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-293">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="7b93d-294">Cada servicio se implementa como un contenedor, por lo que se necesita una imagen de Docker para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-294">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="7b93d-295">El archivo docker-compose.yml especifica no solo qué contenedores se van a usar, sino cómo se configuran individualmente.</span><span class="sxs-lookup"><span data-stu-id="7b93d-295">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="7b93d-296">Por ejemplo, la definición del contenedor `webmvc` en el archivo .yml:</span><span class="sxs-lookup"><span data-stu-id="7b93d-296">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="7b93d-297">Usa una imagen `eshop/web:latest` precompilada.</span><span class="sxs-lookup"><span data-stu-id="7b93d-297">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="7b93d-298">Pero también puede configurar la imagen de modo que se compile como parte de la ejecución de docker-compose con una configuración adicional basada en una compilación: sección del archivo docker-compose.</span><span class="sxs-lookup"><span data-stu-id="7b93d-298">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="7b93d-299">Inicializa dos variables de entorno (CatalogUrl y OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="7b93d-299">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="7b93d-300">Reenvía el puerto 80 expuesto en el contenedor al puerto 80 externo del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="7b93d-300">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="7b93d-301">Vincula la aplicación web al catálogo y el servicio de orden con el valor depends_on.</span><span class="sxs-lookup"><span data-stu-id="7b93d-301">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="7b93d-302">Esto hace que el servicio espere hasta que se inician los servicios.</span><span class="sxs-lookup"><span data-stu-id="7b93d-302">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="7b93d-303">Se volverá a hablar del archivo docker-compose.yml en una sección posterior, cuando se trate la implementación de microservicios y aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="7b93d-303">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="7b93d-304">Trabajo con docker-compose.yml en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-304">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="7b93d-305">Además de agregar un Dockerfile a un proyecto, como se ha mencionado antes, Visual Studio 2017 (a partir de 15.8 en adelante) puede agregar compatibilidad de orquestador con Docker Compose a una solución.</span><span class="sxs-lookup"><span data-stu-id="7b93d-305">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="7b93d-306">Cuando se agrega compatibilidad de orquestador de contenedores, como se muestra en la figura 5-7, por primera vez, Visual Studio crea el Dockerfile para el proyecto y un nuevo proyecto (sección servicio) en la solución con varios archivos `docker-compose*.yml` globales y, luego, agrega el proyecto a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-306">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="7b93d-307">Luego puede abrir los archivos docker-compose.yml y actualizarlos con otras características.</span><span class="sxs-lookup"><span data-stu-id="7b93d-307">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="7b93d-308">Tiene que repetir esta operación para cada proyecto que quiera incluir en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="7b93d-308">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="7b93d-309">En el momento de redactar este artículo, Visual Studio es compatible con los orquestadores Docker Compose y Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="7b93d-309">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![Opción del menú contextual para agregar compatibilidad de orchestrator a un proyecto de ASP.NET Core](./media/image21.png)

<span data-ttu-id="7b93d-311">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-311">**Figure 5-7**.</span></span> <span data-ttu-id="7b93d-312">Adición de compatibilidad con Docker en Visual Studio 2017 al hacer clic con el botón derecho en un proyecto de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7b93d-312">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="7b93d-313">Después de agregar compatibilidad de orquestador a la solución en Visual Studio, también se ve un nuevo nodo (en el archivo de proyecto `docker-compose.dcproj`) en el Explorador de soluciones que contiene los archivos docker-compose.yml agregados, como se muestra en la figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="7b93d-313">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Nodo de docker-compose en el Explorador de soluciones](./media/image11.png)

<span data-ttu-id="7b93d-315">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-315">**Figure 5-8**.</span></span> <span data-ttu-id="7b93d-316">Nodo de árbol **docker-compose** agregado en el Explorador de soluciones de Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-316">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="7b93d-317">Puede implementar una aplicación de varios contenedores con un único archivo docker-compose.yml mediante el comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-317">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="7b93d-318">Pero Visual Studio agrega un grupo de ellos para que pueda reemplazar valores en función del entorno (desarrollo o producción) y el tipo de ejecución (versión o depuración).</span><span class="sxs-lookup"><span data-stu-id="7b93d-318">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="7b93d-319">Esta capacidad se explica en secciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7b93d-319">This capability will be explained in later sections.</span></span>

![5. Ejecutar contenedores o aplicación compuesta](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="7b93d-321">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="7b93d-321">Step 5.</span></span> <span data-ttu-id="7b93d-322">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7b93d-322">Build and run your Docker application</span></span>

<span data-ttu-id="7b93d-323">Si la aplicación solo tiene un contenedor, puede ejecutarla mediante su implementación en el host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="7b93d-323">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="7b93d-324">Pero si la aplicación contiene varios servicios, se puede implementar como una aplicación compuesta, ya sea mediante un solo comando de la CLI (docker-compose up) o con Visual Studio, que usará ese comando en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7b93d-324">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="7b93d-325">Echemos un vistazo a las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="7b93d-325">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="7b93d-326">Opción A: Ejecución de una aplicación de un solo contenedor</span><span class="sxs-lookup"><span data-stu-id="7b93d-326">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="7b93d-327">Uso de la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-327">Using Docker CLI</span></span>

<span data-ttu-id="7b93d-328">Puede ejecutar un contenedor de Docker mediante el comando `docker run`, como se muestra en la figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="7b93d-328">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="7b93d-329">El comando anterior crea una nueva instancia de contenedor a partir de la imagen especificada cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="7b93d-329">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="7b93d-330">Puede usar el parámetro `--name` para asignar un nombre al contenedor y, luego, usar `docker start {name}` (o el identificador del contenedor o el nombre automático) para ejecutar una instancia de contenedor existente.</span><span class="sxs-lookup"><span data-stu-id="7b93d-330">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![Vista de pantalla de ejecución de un contenedor de Docker mediante el comando docker run](./media/image13.png)

<span data-ttu-id="7b93d-332">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-332">**Figure 5-9**.</span></span> <span data-ttu-id="7b93d-333">Ejecución de un contenedor de Docker mediante el comando docker run</span><span class="sxs-lookup"><span data-stu-id="7b93d-333">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="7b93d-334">En este caso, el comando enlaza el puerto interno 5000 del contenedor con el puerto 80 del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="7b93d-334">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="7b93d-335">Esto significa que el host escucha en el puerto 80 y reenvía al puerto 5000 del contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-335">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="7b93d-336">El hash que se muestra es el identificador del contenedor y además se le ha asignado un nombre legible aleatorio si no se ha usado la opción `--name`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-336">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="7b93d-337">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-337">Using Visual Studio</span></span>

<span data-ttu-id="7b93d-338">Si no ha agregado compatibilidad de orquestador de contenedores, también puede ejecutar una aplicación de un solo contenedor si presiona **Ctrl-F5** y además puede usar **F5** para depurar la aplicación del contenedor.</span><span class="sxs-lookup"><span data-stu-id="7b93d-338">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="7b93d-339">El contenedor se ejecuta localmente mediante docker run.</span><span class="sxs-lookup"><span data-stu-id="7b93d-339">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="7b93d-340">Opción B: Ejecución de una aplicación de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="7b93d-340">Option B: Running a multi-container application</span></span>

<span data-ttu-id="7b93d-341">En la mayoría de los escenarios de empresa, una aplicación de Docker se compone de varios servicios, lo que significa que hay que ejecutar una aplicación de varios contenedores, como se muestra en la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="7b93d-341">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Máquina virtual con varios contenedores de Docker](./media/image14.png)

<span data-ttu-id="7b93d-343">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-343">**Figure 5-10**.</span></span> <span data-ttu-id="7b93d-344">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="7b93d-344">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="7b93d-345">Uso de la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-345">Using Docker CLI</span></span>

<span data-ttu-id="7b93d-346">Para ejecutar una aplicación de varios contenedores con la CLI de Docker, use el comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="7b93d-346">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="7b93d-347">Este comando usa el archivo **docker-compose.yml** que hay en el nivel de solución para implementar una aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="7b93d-347">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="7b93d-348">La figura 5-11 muestra los resultados de la ejecución del comando desde el directorio principal de la solución, que contiene el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="7b93d-348">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Vista de pantalla de la ejecución del comando docker-compose up](./media/image15.png)

<span data-ttu-id="7b93d-350">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-350">**Figure 5-11**.</span></span> <span data-ttu-id="7b93d-351">Resultados del ejemplo al ejecutar el comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="7b93d-351">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="7b93d-352">Después de la ejecución del comando docker-compose up, la aplicación y sus contenedores relacionados se implementan en el host de Docker, como se muestra en la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="7b93d-352">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="7b93d-353">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-353">Using Visual Studio</span></span>

<span data-ttu-id="7b93d-354">La ejecución de una aplicación de varios contenedores mediante Visual Studio 2017 no puede ser más sencilla.</span><span class="sxs-lookup"><span data-stu-id="7b93d-354">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="7b93d-355">Simplemente presione **Ctrl-F5** para ejecutar o **F5** para depurar, como de costumbre, con lo que se configura el proyecto **docker-compose** como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="7b93d-355">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="7b93d-356">Visual Studio controla toda la configuración necesaria, por lo que puede crear puntos de interrupción como de costumbre y depurar lo que finalmente se convierte en procesos independientes que se ejecutan en "servidores remotos", simplemente así.</span><span class="sxs-lookup"><span data-stu-id="7b93d-356">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="7b93d-357">Como se ha mencionado antes, cada vez que se agrega compatibilidad con soluciones de Docker a un proyecto de una solución, ese proyecto se configura en el archivo global (nivel de solución) docker-compose.yml, lo que permite ejecutar o depurar la solución completa al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-357">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="7b93d-358">Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad con soluciones de Docker y realiza todos los pasos internos automáticamente (dotnet publish, docker build, etc.).</span><span class="sxs-lookup"><span data-stu-id="7b93d-358">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="7b93d-359">Si quiere echar un vistazo al trabajo monótono, vea el archivo:</span><span class="sxs-lookup"><span data-stu-id="7b93d-359">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="7b93d-360">Lo importante aquí es que, como se muestra en la figura 5-12, en Visual Studio 2017 hay un comando adicional de **Docker** para la acción de la tecla F5.</span><span class="sxs-lookup"><span data-stu-id="7b93d-360">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="7b93d-361">Esta opción permite ejecutar o depurar una aplicación de varios contenedores mediante la ejecución de todos los contenedores definidos en los archivos docker-compose.yml en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="7b93d-361">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="7b93d-362">La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada uno en un proyecto diferente (contenedor) y, durante la depuración desde Visual Studio, detenerse en los puntos de interrupción definidos en los distintos proyectos y en ejecución en contenedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="7b93d-362">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Barra de herramientas de depuración de Visual Studio ejecutando el proyecto docker-compose](./media/image16.png)

<span data-ttu-id="7b93d-364">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-364">**Figure 5-12**.</span></span> <span data-ttu-id="7b93d-365">Ejecución de aplicaciones de varios contenedores en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-365">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-366">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-366">Additional resources</span></span>

- <span data-ttu-id="7b93d-367">**Implementación de un contenedor de ASP.NET en un host remoto de Docker** \\</span><span class="sxs-lookup"><span data-stu-id="7b93d-367">**Deploy an ASP.NET container to a remote Docker host** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="7b93d-368">Nota sobre las pruebas y la implementación con orquestadores</span><span class="sxs-lookup"><span data-stu-id="7b93d-368">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="7b93d-369">Los comandos docker-compose up y docker run (o la ejecución y depuración de los contenedores en Visual Studio) son adecuados para probar contenedores en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-369">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="7b93d-370">Sin embargo, no debe usar este enfoque para implementaciones de producción donde se deba tener como destino orquestadores como [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span><span class="sxs-lookup"><span data-stu-id="7b93d-370">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="7b93d-371">Si usa Kubernetes, tiene que usar [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) para organizar los contenedores y los [servicios](https://kubernetes.io/docs/concepts/services-networking/service/) para conectarlos en red.</span><span class="sxs-lookup"><span data-stu-id="7b93d-371">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="7b93d-372">También se usan [implementaciones](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) organizar la creación y la modificación de pods.</span><span class="sxs-lookup"><span data-stu-id="7b93d-372">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6. Probar la aplicación o los microservicios](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="7b93d-374">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="7b93d-374">Step 6.</span></span> <span data-ttu-id="7b93d-375">Probar la aplicación de Docker con el host local de Docker</span><span class="sxs-lookup"><span data-stu-id="7b93d-375">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="7b93d-376">Este paso varía en función de lo que haga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b93d-376">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="7b93d-377">En una aplicación web de .NET Core sencilla implementada como un único contenedor o servicio, puede acceder al servicio si abre un explorador en el host de Docker y va a ese sitio, como se muestra en la figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="7b93d-377">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="7b93d-378">(Si la configuración del Dockerfile asigna el contenedor a un puerto del host distinto al 80, incluya el puerto del host en la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="7b93d-378">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Vista de explorador de una respuesta del punto de conexión de la API](./media/image18.png)

<span data-ttu-id="7b93d-380">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-380">**Figure 5-13**.</span></span> <span data-ttu-id="7b93d-381">Ejemplo de prueba de la aplicación de Docker en local mediante localhost</span><span class="sxs-lookup"><span data-stu-id="7b93d-381">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="7b93d-382">Si localhost no apunta a la IP del host de Docker (de forma predeterminada, al usar Docker CE, debería hacerlo), para ir al servicio, use la dirección IP de la tarjeta de red del equipo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-382">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="7b93d-383">Tenga en cuenta que esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se está analizando.</span><span class="sxs-lookup"><span data-stu-id="7b93d-383">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="7b93d-384">Pero, internamente, las solicitudes se redirigen al puerto 5000, porque así es como se ha implementado con el comando docker run, como se ha explicado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="7b93d-384">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="7b93d-385">También puede probar la aplicación con la CURL del terminal, como se muestra en la figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="7b93d-385">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="7b93d-386">En una instalación de Docker en Windows, el valor predeterminado de la IP del host de Docker es siempre 10.0.75.1, además de la dirección IP real del equipo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-386">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Vista de pantalla de una respuesta del punto de conexión de la API con CURL](./media/image19.png)

<span data-ttu-id="7b93d-388">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-388">**Figure 5-14**.</span></span> <span data-ttu-id="7b93d-389">Ejemplo de prueba de la aplicación de Docker en local mediante CURL</span><span class="sxs-lookup"><span data-stu-id="7b93d-389">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="7b93d-390">Prueba y depuración de contenedores con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7b93d-390">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="7b93d-391">Al ejecutar y depurar los contenedores con Visual Studio 2017, puede depurar la aplicación de .NET prácticamente de la misma manera que como lo haría al ejecutar sin contenedores.</span><span class="sxs-lookup"><span data-stu-id="7b93d-391">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="7b93d-392">Pruebas y depuración sin Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-392">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="7b93d-393">Si está desarrollando con el enfoque de editor/CLI, la depuración de contenedores es más difícil y se prefiere hacer mediante la generación de seguimientos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-393">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-394">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-394">Additional resources</span></span>

- <span data-ttu-id="7b93d-395">**Depuración de aplicaciones en un contenedor de Docker local** \\</span><span class="sxs-lookup"><span data-stu-id="7b93d-395">**Debugging apps in a local Docker container** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="7b93d-396">**Steve Lasker. Compilar, depurar e implementar aplicaciones ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="7b93d-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="7b93d-397">Video.</span><span class="sxs-lookup"><span data-stu-id="7b93d-397">Video.</span></span> \
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="7b93d-398">Flujo de trabajo simplificado al desarrollar contenedores con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-398">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="7b93d-399">En la práctica, el flujo de trabajo cuando se usa Visual Studio es mucho más sencillo que si se usa el enfoque de editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="7b93d-399">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="7b93d-400">La mayoría de los pasos que necesita Docker relacionados con el Dockerfile y los archivos docker-compose.yml están ocultos o se han simplificado con Visual Studio, como se muestra en la figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="7b93d-400">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Flujo de trabajo simplificado de desarrollo de contenedores con Visual Studio: 1. Programar la aplicación, 2. Agregar compatibilidad de Docker a los proyectos (solo una vez), 3. Ejecutar contenedor o aplicación docker-compose, 4. Probar la aplicación o los microservicios, 5. Insertar en el repositorio y repetir.](./media/image20.png)

<span data-ttu-id="7b93d-402">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="7b93d-402">**Figure 5-15**.</span></span> <span data-ttu-id="7b93d-403">Flujo de trabajo simplificado al desarrollar con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b93d-403">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="7b93d-404">Además, debe realizar el paso 2 (agregar compatibilidad con Docker a los proyectos) una sola vez.</span><span class="sxs-lookup"><span data-stu-id="7b93d-404">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="7b93d-405">Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habituales cuando se usa .NET para cualquier otro desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7b93d-405">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="7b93d-406">Debe saber qué está sucediendo en segundo plano (el proceso de compilación de imágenes, qué imágenes base usa, la implementación de contenedores, etc.) y, a veces, también debe editar el Dockerfile o el archivo docker-compose.yml para personalizar comportamientos.</span><span class="sxs-lookup"><span data-stu-id="7b93d-406">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="7b93d-407">Pero con Visual Studio se simplifica enormemente la mayor parte del trabajo, lo que mejora mucho la productividad.</span><span class="sxs-lookup"><span data-stu-id="7b93d-407">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7b93d-408">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-408">Additional resources</span></span>

- <span data-ttu-id="7b93d-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \ (Desarrollo de Docker de .NET con Visual Studio 2017, de Steve Lasker)</span><span class="sxs-lookup"><span data-stu-id="7b93d-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \\</span></span>
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="7b93d-410">Uso de comandos de PowerShell en un Dockerfile para configurar contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="7b93d-410">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="7b93d-411">Los [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) permiten convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="7b93d-411">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="7b93d-412">Para usar contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b93d-412">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="7b93d-413">En este caso se usa una imagen base de Windows Server Core (el valor FROM) y se instala IIS con un comando de PowerShell (el valor RUN).</span><span class="sxs-lookup"><span data-stu-id="7b93d-413">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="7b93d-414">Del mismo modo, también se pueden usar comandos de PowerShell para configurar otros componentes como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows.</span><span class="sxs-lookup"><span data-stu-id="7b93d-414">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="7b93d-415">Por ejemplo, el siguiente comando en un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="7b93d-415">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="7b93d-416">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7b93d-416">Additional resources</span></span>

- <span data-ttu-id="7b93d-417">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="7b93d-417">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="7b93d-418">Comandos de PowerShell de ejemplo para ejecutar desde Dockerfiles a fin de incluir características de Windows.\\</span><span class="sxs-lookup"><span data-stu-id="7b93d-418">Example PowerShell commands to run from dockerfiles to include Windows features.\\</span></span>
  [*https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="7b93d-419">[Anterior](index.md)
>[Siguiente](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="7b93d-419">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
