---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Comprenda los detalles del flujo de trabajo para desarrollar aplicaciones basadas en Docker. Comience paso a paso, profundice en algunos detalles para optimizar Dockerfiles y termine con el flujo de trabajo simplificado disponible cuando se usa Visual Studio.
ms.date: 01/30/2020
ms.openlocfilehash: 421b1aaf3965bd3aa80c6e09da963404d2a46c09
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359080"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="e0bb9-104">Flujo de trabajo de desarrollo para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="e0bb9-105">El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde se programa la aplicación con el lenguaje preferido y se prueba en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="e0bb9-106">Con este flujo de trabajo, no importa el lenguaje, el marco ni la plataforma que se elija, ya que siempre se desarrollan y se prueban contenedores de Docker en local.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="e0bb9-107">Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="e0bb9-108">Una selección de sistema operativo, por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="e0bb9-109">Archivos agregados durante el desarrollo, por ejemplo, archivos binarios de código fuente y aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="e0bb9-110">Información de configuración, como configuración de entorno y dependencias.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="e0bb9-111">Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="e0bb9-112">En esta sección se explica el flujo de trabajo de desarrollo de *bucle interno* para aplicaciones basadas en contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="e0bb9-113">Flujo de trabajo de bucle interno significa que no se tiene en cuenta el flujo de trabajo general de DevOps, que puede incluir hasta implementación en producción, y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-113">The inner-loop workflow means it's not considering the broader DevOps workflow, which can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="e0bb9-114">Los pasos iniciales para configurar el entorno no se incluyen, ya que se realizan solo una vez.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="e0bb9-115">Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="e0bb9-116">Estos son los pasos básicos que normalmente se realizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagrama que muestra los 7 pasos necesarios para crear una aplicación en contenedor.":::
<span data-ttu-id="e0bb9-118">Proceso de desarrollo de aplicaciones de Docker: 1. Programar la aplicación, 2. Escribir Dockerfiles, 3. Crear imágenes definidas en Dockerfiles, 4. (Opcional) Crear servicios en el archivo docker-compose.yml, 5. Ejecutar contenedor o aplicación docker-compose, 6. Probar la aplicación o los microservicios, 7. Insertar en el repositorio y repetir.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-118">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="e0bb9-119">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-119">**Figure 5-1.**</span></span> <span data-ttu-id="e0bb9-120">Flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-120">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="e0bb9-121">En esta sección se detalla el proceso completo y se explica cada paso importante centrándose en un entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-121">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="e0bb9-122">Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, Visual Studio Code más la CLI de Docker en macOS o Windows), es necesario conocer cada paso, generalmente más detalladamente que si se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-122">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="e0bb9-123">Para obtener más información sobre cómo trabajar en un entorno de CLI, vea el libro electrónico [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo de vida de las aplicaciones en contenedor de Docker con plataformas y herramientas de Microsoft).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-123">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="e0bb9-124">Al usar Visual Studio 2019, muchos de esos pasos se controlan de forma automática, lo que mejora considerablemente la productividad.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-124">When you're using Visual Studio 2019, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="e0bb9-125">Esto es así especialmente con Visual Studio 2019 y cuando el destino son aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-125">This is especially true when you're using Visual Studio 2019 and targeting multi-container applications.</span></span> <span data-ttu-id="e0bb9-126">Por ejemplo, con un solo clic, Visual Studio agrega `Dockerfile` y el archivo `docker-compose.yml` a los proyectos con la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-126">For instance, with just one mouse click, Visual Studio adds the `Dockerfile` and `docker-compose.yml` file to your projects with the configuration for your application.</span></span> <span data-ttu-id="e0bb9-127">Al ejecutar la aplicación en Visual Studio, compila la imagen de Docker y ejecuta la aplicación de varios contenedores directamente en Docker; incluso permite depurar varios contenedores al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-127">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="e0bb9-128">Estas características aumentan la velocidad de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-128">These features will boost your development speed.</span></span>

<span data-ttu-id="e0bb9-129">Pero que Visual Studio realice esos pasos automáticamente no significa que no sea necesario saber lo que ocurre en segundo plano con Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-129">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="e0bb9-130">Por lo tanto, la guía siguiente detalla cada paso.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-130">Therefore, the following guidance details every step.</span></span>

![Imagen del paso 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="e0bb9-132">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-132">Step 1.</span></span> <span data-ttu-id="e0bb9-133">Empezar a programar y crear la aplicación inicial o la base de referencia del servicio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-133">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="e0bb9-134">El desarrollo de una aplicación de Docker es similar al desarrollo de una aplicación sin Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-134">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="e0bb9-135">La diferencia es que al desarrollar para Docker, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker en el entorno local (una instalación de máquina virtual de Linux realizada por Docker o directamente Windows si se usan contenedores de Windows).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-135">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="e0bb9-136">Configurar el entorno local con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-136">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="e0bb9-137">Para empezar, asegúrese de que tiene instalado [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) para Windows, como se explica en estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-137">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="e0bb9-138">Get started with Docker CE for Windows (Introducción a Docker CE para Windows)</span><span class="sxs-lookup"><span data-stu-id="e0bb9-138">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="e0bb9-139">Además, se necesita Visual Studio 2019 16.4 o posterior con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada, como se muestra en la figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-139">In addition, you need Visual Studio 2019 version 16.4 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Captura de pantalla de la selección de desarrollo multiplataforma de .NET Core.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

<span data-ttu-id="e0bb9-141">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-141">**Figure 5-2**.</span></span> <span data-ttu-id="e0bb9-142">Selección de la carga de trabajo **Desarrollo multiplataforma de .NET Core** durante la instalación de Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-142">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2019 setup</span></span>

<span data-ttu-id="e0bb9-143">Puede empezar a programar la aplicación en .NET sin formato (normalmente en .NET Core si va a usar contenedores) incluso antes de habilitar Docker en la aplicación e implementar y probar en Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-143">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="e0bb9-144">Pero se recomienda empezar a trabajar en Docker tan pronto como sea posible, ya que es el entorno real y se pueden detectar los problemas a la mayor brevedad.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-144">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="e0bb9-145">Se recomienda encarecidamente porque Visual Studio facilita tanto el trabajo con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de varios contenedores desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-145">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-146">Additional resources</span></span>

- <span data-ttu-id="e0bb9-147">**Get started with Docker CE for Windows** (Introducción a Docker CE para Windows) </span><span class="sxs-lookup"><span data-stu-id="e0bb9-147">**Get started with Docker CE for Windows** </span></span>\
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="e0bb9-148">**Visual Studio 2019** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-148">**Visual Studio 2019** </span></span>\
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

![Imagen del paso 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="e0bb9-150">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-150">Step 2.</span></span> <span data-ttu-id="e0bb9-151">Crear un Dockerfile relacionado con una imagen base existente de .NET</span><span class="sxs-lookup"><span data-stu-id="e0bb9-151">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="e0bb9-152">Necesita un Dockerfile para cada imagen personalizada que quiera compilar; también necesita un Dockerfile para cada contenedor que se vaya a implementar, tanto si se implementa automáticamente desde Visual Studio como manualmente mediante la CLI de Docker (comandos docker run y docker-compose).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-152">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="e0bb9-153">Si la aplicación contiene un único servicio personalizado, necesita un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-153">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="e0bb9-154">Si la aplicación contiene varios servicios (como en una arquitectura de microservicios), necesita un Dockerfile para cada servicio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-154">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="e0bb9-155">El Dockerfile se coloca en la carpeta raíz de la aplicación o el servicio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-155">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="e0bb9-156">Contiene los comandos que indican a Docker cómo configurar y ejecutar la aplicación o el servicio en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-156">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="e0bb9-157">Puede crear un Dockerfile de forma manual en el código y agregarlo al proyecto junto con las dependencias de .NET.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-157">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="e0bb9-158">Con Visual Studio y sus herramientas para Docker, esta tarea solo exige unos clics.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-158">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="e0bb9-159">Al crear un proyecto en Visual Studio 2019, hay una opción denominada **Habilitar compatibilidad con Docker**, como se muestra en la figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-159">When you create a new project in Visual Studio 2019, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Captura de pantalla que muestra la casilla Enable Docker Support (Habilitar compatibilidad con Docker).](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

<span data-ttu-id="e0bb9-161">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-161">**Figure 5-3**.</span></span> <span data-ttu-id="e0bb9-162">Habilitación de la compatibilidad con Docker al crear un nuevo proyecto de ASP.NET Core en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-162">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2019</span></span>

<span data-ttu-id="e0bb9-163">También puede habilitar la compatibilidad con Docker en un proyecto de aplicación web de ASP.NET Core existente haciendo clic con el botón derecho en el proyecto, en el **Explorador de soluciones**, y seleccionando **Agregar** > **Compatibilidad con Docker...** , como se muestra en la figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-163">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support...**, as shown in Figure 5-4.</span></span>

![Captura de pantalla que muestra la opción Docker Support (Compatibilidad con Docker) en el menú Add (Agregar).](./media/docker-app-development-workflow/add-docker-support-option.png)

<span data-ttu-id="e0bb9-165">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-165">**Figure 5-4**.</span></span> <span data-ttu-id="e0bb9-166">Habilitación de la compatibilidad con Docker en un proyecto existente de Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-166">Enabling Docker support in an existing Visual Studio 2019 project</span></span>

<span data-ttu-id="e0bb9-167">Esta acción agrega un *Dockerfile* al proyecto con la configuración necesaria y solo está disponible en los proyectos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-167">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="e0bb9-168">De forma similar, Visual Studio también puede agregar un archivo `docker-compose.yml` para toda la solución con la opción **Agregar > Compatibilidad con el orquestador de contenedores...** . En el paso 4 se examina esta opción más detalladamente.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-168">In a similar fashion, Visual Studio can also add a `docker-compose.yml` file for the whole solution with the option **Add > Container Orchestrator Support...**. In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="e0bb9-169">Uso de una imagen de Docker de .NET oficial existente</span><span class="sxs-lookup"><span data-stu-id="e0bb9-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="e0bb9-170">Normalmente se compila una imagen personalizada para el contenedor además de una imagen base que se obtiene de un repositorio oficial como el registro [Docker Hub](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="e0bb9-171">Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="e0bb9-172">El Dockerfile usa una imagen `dotnet/core/aspnet` existente.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-172">Your Dockerfile will use an existing `dotnet/core/aspnet` image.</span></span>

<span data-ttu-id="e0bb9-173">Anteriormente se ha explicado qué imágenes y repositorios de Docker se pueden usar según el marco de trabajo y el sistema operativo elegidos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="e0bb9-174">Por ejemplo, si quiere usar ASP.NET Core (Linux o Windows), la imagen que se debe usar es `mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="e0bb9-175">Por lo tanto, debe especificar qué imagen base de Docker va a usar para el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="e0bb9-176">Se hace mediante la incorporación de `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-176">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` to your Dockerfile.</span></span> <span data-ttu-id="e0bb9-177">Visual Studio lo hace de forma automática, pero si va a actualizar la versión, actualice este valor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="e0bb9-178">El uso de un repositorio de imágenes de .NET oficial de Docker Hub con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todos los equipos (incluido el desarrollo, las pruebas y la producción).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="e0bb9-179">En el ejemplo siguiente se muestra un Dockerfile de ejemplo para un contenedor de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="e0bb9-180">En este caso, la imagen se basa en la versión 3.1 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-180">In this case, the image is based on version 3.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="e0bb9-181">Es el valor `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-181">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="e0bb9-182">[Para obtener más información sobre esta imagen base, consulte la página [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) (Imagen de Docker de .NET Core)]. En el Dockerfile, también debe indicar a Docker que escuche en el puerto TCP que se vaya a usar en tiempo de ejecución (en este caso, el puerto 80, como se ha configurado con el valor EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="e0bb9-183">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="e0bb9-184">Por ejemplo, la línea ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker que ejecute una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="e0bb9-185">Si usa el SDK y la CLI de .NET Core (dotnet CLI) para compilar y ejecutar la aplicación .NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="e0bb9-186">La conclusión es que la línea ENTRYPOINT y otros valores pueden variar según el lenguaje y la plataforma que se elijan para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-187">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-187">Additional resources</span></span>

- <span data-ttu-id="e0bb9-188">**Compilación de imágenes de Docker para aplicaciones .NET Core** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-188">**Building Docker Images for .NET Core Applications** </span></span>\
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- <span data-ttu-id="e0bb9-189">**Compile su propia imagen**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-189">**Build your own image**.</span></span> <span data-ttu-id="e0bb9-190">En la documentación oficial de Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-190">In the official Docker documentation.</span></span>\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="e0bb9-191">**Mantenerse actualizado con imágenes de contenedor de .NET** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-191">**Staying up-to-date with .NET Container Images** </span></span>\
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="e0bb9-192">**Uso conjunto de .NET y Docket: actualización de DockerCon de 2018** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-192">**Using .NET and Docker Together - DockerCon 2018 Update** </span></span>\
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="e0bb9-193">Uso de repositorios de imágenes multiarquitectura</span><span class="sxs-lookup"><span data-stu-id="e0bb9-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="e0bb9-194">Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="e0bb9-195">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="e0bb9-196">Por ejemplo, el repositorio [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) disponible en el registro Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de repositorio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-196">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="e0bb9-197">Si especifica una etiqueta, se toma como destino una plataforma explícita, como en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim` \
  <span data-ttu-id="e0bb9-198">Destino: solo entorno de ejecución .NET Core 3.1 en Linux</span><span class="sxs-lookup"><span data-stu-id="e0bb9-198">Targets: .NET Core 3.1 runtime-only on Linux</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1909` \
  <span data-ttu-id="e0bb9-199">Destino: solo entorno de ejecución .NET Core 3.1 en Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="e0bb9-199">Targets: .NET Core 3.1 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="e0bb9-200">Pero, si se especifica el mismo nombre de imagen, incluso con la misma etiqueta, las imágenes multiarquitectura (como la imagen `aspnet`) usan la versión de Linux o Windows según el sistema operativo del host de Docker que se vaya a implementar, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnet` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1` \
  <span data-ttu-id="e0bb9-201">Arquitectura múltiple: solo entorno de ejecución .NET Core 3.1 en Linux o Windows Nano Server según el sistema operativo del host de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-201">Multi-arch: .NET Core 3.1 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="e0bb9-202">De esta forma, al extraer una imagen de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="e0bb9-203">Compilaciones de varias fases en Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e0bb9-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="e0bb9-204">El Dockerfile es similar a un script por lotes.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="e0bb9-205">Es similar a lo que haría si tuviera que configurar el equipo desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="e0bb9-206">Comienza con una imagen base que configura el contexto inicial, es como el sistema de archivos de inicio, que se coloca sobre el sistema operativo del host.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="e0bb9-207">No es un sistema operativo, pero se puede considerar como "el" sistema operativo dentro del contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-207">It's not an OS, but you can think of it like "the" OS inside the container.</span></span>

<span data-ttu-id="e0bb9-208">La ejecución de cada línea de comandos crea una nueva capa en el sistema de archivos con los cambios de la anterior, por lo que, cuando se combinan, generan el sistema de archivos resultante.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="e0bb9-209">Dado que cada nueva capa "descansa" sobre la anterior y el tamaño de la imagen resultante aumenta con cada comando, las imágenes pueden llegar a tener un gran tamaño si tienen que incluir, por ejemplo, el SDK necesario para compilar y publicar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="e0bb9-210">Aquí es donde las compilaciones de varias fases entran en escena (a partir de Docker 17.05 y posterior) para hacer su magia.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="e0bb9-211">La idea central es que puede separar el proceso de ejecución del Dockerfile en fases, donde una fase es una imagen inicial seguida de uno o más comandos, y la última fase determina el tamaño final de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="e0bb9-212">En resumen, las compilaciones de varias fases permiten dividir la creación en "fases" distintas y, luego, ensamblar la imagen final al tomar solo los directorios pertinentes de las fases intermedias.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="e0bb9-213">La estrategia general para usar esta característica es:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="e0bb9-214">Usar una imagen base de SDK (no importa su tamaño), con todo lo necesario para compilar y publicar la aplicación en una carpeta</span><span class="sxs-lookup"><span data-stu-id="e0bb9-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="e0bb9-215">Usar una imagen base pequeña de solo el entorno de ejecución y copiar la carpeta de publicación de la fase anterior para generar una pequeña imagen final.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="e0bb9-216">Probablemente la mejor manera de comprender las fases es analizar un archivo Dockerfile en detalle, línea a línea, así que vamos a comenzar con el Dockerfile inicial creado por Visual Studio al agregar compatibilidad con Docker a un proyecto y, luego, realizaremos algunas optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="e0bb9-217">El Dockerfile inicial podría ser algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
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
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="e0bb9-218">Y estos son los detalles, línea a línea:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-218">And these are the details, line by line:</span></span>

- <span data-ttu-id="e0bb9-219">**Línea 1:** Comience una fase con una imagen base "pequeña" de solo el entorno de ejecución, denomínela **base** para referencia.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-219">**Line #1:** Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>

- <span data-ttu-id="e0bb9-220">**Línea 2:** Cree el directorio **/app** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-220">**Line #2:** Create the **/app** directory in the image.</span></span>

- <span data-ttu-id="e0bb9-221">**Línea 3:** Exponga el puerto **80**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-221">**Line #3:** Expose port **80**.</span></span>

- <span data-ttu-id="e0bb9-222">**Línea 5:** Comience una nueva fase con una imagen "grande" para compilar y publicar.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-222">**Line #5:** Begin a new stage with the "large" image for building/publishing.</span></span> <span data-ttu-id="e0bb9-223">Denomínela **build** como referencia.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-223">Call it **build** for reference.</span></span>

- <span data-ttu-id="e0bb9-224">**Línea 6:** Cree un directorio **/src** en la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-224">**Line #6:** Create directory **/src** in the image.</span></span>

- <span data-ttu-id="e0bb9-225">**Línea 7:** Hasta la línea 16, copie los archivos del proyecto **.csproj** a los que se hace referencia para poder restaurar los paquetes más adelante.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-225">**Line #7:** Up to line 16, copy referenced **.csproj** project files to be able to restore packages later.</span></span>

- <span data-ttu-id="e0bb9-226">**Línea 17:** Restaure los paquetes del proyecto **Catalog.API** y los proyectos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-226">**Line #17:** Restore packages for the **Catalog.API** project and the referenced projects.</span></span>

- <span data-ttu-id="e0bb9-227">**Línea 18:** Copie **todo el árbol de directorio de la solución** (excepto los archivos o directorios incluidos en el archivo **.dockerignore**) en el directorio **/src** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-227">**Line #18:** Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) to the **/src** directory in the image.</span></span>

- <span data-ttu-id="e0bb9-228">**Línea 19:** Cambie la carpeta actual al proyecto **Catalog.API**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-228">**Line #19:** Change the current folder to the **Catalog.API** project.</span></span>

- <span data-ttu-id="e0bb9-229">**Línea 20:** Compile el proyecto (y otras dependencias del proyecto) y use como salida el directorio **/app** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-229">**Line #20:** Build the project (and other project dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="e0bb9-230">**Línea 22:** Comience una nueva fase a partir de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-230">**Line #22:** Begin a new stage continuing from the build.</span></span> <span data-ttu-id="e0bb9-231">Denomínela **publish** como referencia.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-231">Call it **publish** for reference.</span></span>

- <span data-ttu-id="e0bb9-232">**Línea 23:** Publique el proyecto (y las dependencias) y use como salida el directorio **/app** de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-232">**Line #23:** Publish the project (and dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="e0bb9-233">**Línea 25:** Comience una nueva fase a partir de **base** y denomínela **final**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-233">**Line #25:** Begin a new stage continuing from **base** and call it **final**.</span></span>

- <span data-ttu-id="e0bb9-234">**Línea 26:** Cambie el directorio actual a **/app**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-234">**Line #26:** Change the current directory to **/app**.</span></span>

- <span data-ttu-id="e0bb9-235">**Línea 27:** Copie el directorio **/app** de la fase **publish** en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-235">**Line #27:** Copy the **/app** directory from stage **publish** to the current directory.</span></span>

- <span data-ttu-id="e0bb9-236">**Línea 28:** Defina el comando que se va a ejecutar cuando se inicie el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-236">**Line #28:** Define the command to run when the container is started.</span></span>

<span data-ttu-id="e0bb9-237">Ahora vamos a examinar algunas optimizaciones para mejorar el rendimiento del proceso completo, lo que, en el caso de eShopOnContainers, significa aproximadamente 22 minutos o más para compilar la solución completa en contenedores de Linux.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-237">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="e0bb9-238">Puede aprovechar la característica de caché de capas de Docker, que es bastante sencilla: si la imagen base y los comandos son los mismos que algunos ejecutados previamente, puede usar la capa resultante sin necesidad de ejecutar los comandos, con lo que se ahorra algo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-238">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="e0bb9-239">Así, vamos a centrarnos en la fase **build**, las líneas 5 y 6 son prácticamente iguales, pero las líneas 7-17 son diferentes para cada servicio de eShopOnContainers, así que se tienen que ejecutar cada vez, pero si ha cambiado las líneas 7-16 a:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-239">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```Dockerfile
COPY . .
```

<span data-ttu-id="e0bb9-240">Luego, sería igual para cada servicio, se copiaría la solución completa y se crearía una capa más grande pero:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-240">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1. <span data-ttu-id="e0bb9-241">El proceso de copia solo se ejecutaría la primera vez (y al recompilar si se modifica un archivo) y se usaría la memoria caché para todos los demás servicios y</span><span class="sxs-lookup"><span data-stu-id="e0bb9-241">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2. <span data-ttu-id="e0bb9-242">Puesto que la imagen más grande se produce en una fase intermedia, no afecta al tamaño final de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-242">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="e0bb9-243">La siguiente optimización importante implica al comando `restore` ejecutado en la línea 17, que también es diferente para cada servicio de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-243">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="e0bb9-244">Si cambia esa línea a:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-244">If you change that line to just:</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="e0bb9-245">Restauraría los paquetes de toda la solución, pero, de nuevo, lo haría una sola vez, en lugar de las 15 veces con la estrategia actual.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-245">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="e0bb9-246">Pero `dotnet restore` únicamente se ejecuta si hay un solo archivo de proyecto o solución en la carpeta, así que lograrlo es un poco más complicado y la forma de solucionarlo, sin entrar en demasiados detalles, es esta:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-246">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1. <span data-ttu-id="e0bb9-247">Agregue las líneas siguientes a **.dockerignore**:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-247">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="e0bb9-248">`*.sln`, para omitir todos los archivos de solución del árbol de la carpeta principal</span><span class="sxs-lookup"><span data-stu-id="e0bb9-248">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="e0bb9-249">`!eShopOnContainers-ServicesAndWebApps.sln`, para incluir solo este archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-249">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2. <span data-ttu-id="e0bb9-250">Incluya el argumento `/ignoreprojectextensions:.dcproj` en `dotnet restore`, de modo que también omita el proyecto docker-compose y solo restaure los paquetes de la solución eShopOnContainers-ServicesAndWebApps.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-250">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="e0bb9-251">Para la optimización final, resulta que la línea 20 es redundante, ya que la línea 23 también compila la aplicación y viene, básicamente, justo después de la línea 20, así que ahí tenemos otro comando que usa mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-251">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="e0bb9-252">El archivo resultante es entonces:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-252">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -o /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="e0bb9-253">Creación de la imagen base desde cero</span><span class="sxs-lookup"><span data-stu-id="e0bb9-253">Creating your base image from scratch</span></span>

<span data-ttu-id="e0bb9-254">Puede crear su propia imagen base de Docker desde cero.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-254">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="e0bb9-255">Este escenario no se recomienda para usuarios que se están iniciando en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-255">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-256">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-256">Additional resources</span></span>

- <span data-ttu-id="e0bb9-257">**Multi-arch .NET Core images** (Imágenes de .NET Core multiarquitectura).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-257">**Multi-arch .NET Core images**.</span></span>\
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="e0bb9-258">**Create a base image (Crear una imagen base)** .</span><span class="sxs-lookup"><span data-stu-id="e0bb9-258">**Create a base image**.</span></span> <span data-ttu-id="e0bb9-259">Documentación oficial de Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-259">Official Docker documentation.</span></span>\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Imagen del paso 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="e0bb9-261">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-261">Step 3.</span></span> <span data-ttu-id="e0bb9-262">Crear las imágenes de Docker personalizadas e insertar la aplicación o el servicio en ellas</span><span class="sxs-lookup"><span data-stu-id="e0bb9-262">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="e0bb9-263">Debe crear una imagen relacionada para cada servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-263">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="e0bb9-264">Si la aplicación está formada por un único servicio o aplicación web, solo necesita una imagen.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-264">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="e0bb9-265">Tenga en cuenta que las imágenes de Docker se compilan automáticamente en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-265">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="e0bb9-266">Los pasos siguientes solo son necesarios para el flujo de trabajo de editor/CLI y se explican para aclarar lo que sucede en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-266">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="e0bb9-267">Como desarrollador, debe desarrollar y probar en local hasta que inserte una característica o cambio completados en el sistema de control de código fuente (por ejemplo, en GitHub).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-267">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="e0bb9-268">Esto significa que tiene que crear las imágenes de Docker e implementar contenedores en un host de Docker local (máquina virtual de Windows o Linux) y ejecutar, probar y depurar en esos contenedores locales.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-268">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="e0bb9-269">Para crear una imagen personalizada en el entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando docker build, como se muestra en la figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-269">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Captura de pantalla que muestra la salida de la consola del comando de compilación de Docker.](./media/docker-app-development-workflow/run-docker-build-command.png)

<span data-ttu-id="e0bb9-271">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-271">**Figure 5-5**.</span></span> <span data-ttu-id="e0bb9-272">Creación de una imagen personalizada de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-272">Creating a custom Docker image</span></span>

<span data-ttu-id="e0bb9-273">De forma opcional, en lugar de ejecutar directamente docker build desde la carpeta del proyecto, primero puede generar una carpeta que se pueda implementar con las bibliotecas de .NET y los binarios necesarios mediante la ejecución de `dotnet publish` y, luego, usar el comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-273">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="e0bb9-274">Esto crea una imagen de Docker con el nombre `cesardl/netcore-webapi-microservice-docker:first`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-274">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="e0bb9-275">En este caso, :first es una etiqueta que representa una versión determinada.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-275">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="e0bb9-276">Puede repetir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-276">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="e0bb9-277">Cuando una aplicación se compone de varios contenedores (es decir, es una aplicación de varios contenedores), también puede usar el comando `docker-compose up --build` para compilar todas las imágenes relacionadas con un solo comando al usar los metadatos expuestos en los archivos relacionados docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-277">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="e0bb9-278">Puede encontrar las imágenes existentes en el repositorio local mediante el comando docker images, como se muestra en la figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-278">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Salida de consola del comando docker images, que muestra las imágenes existentes en la consola.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="e0bb9-280">**Figura 5-6**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-280">**Figure 5-6.**</span></span> <span data-ttu-id="e0bb9-281">Visualización de imágenes existentes mediante el comando docker images</span><span class="sxs-lookup"><span data-stu-id="e0bb9-281">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="e0bb9-282">Creación de imágenes de Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-282">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="e0bb9-283">Cuando se usa Visual Studio para crear un proyecto con compatibilidad con Docker, no se crea una imagen de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-283">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="e0bb9-284">La imagen se crea automáticamente al presionar **F5** (o **Ctrl-F5**) para ejecutar el servicio o la aplicación a los que se ha aplicado Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-284">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="e0bb9-285">Este paso es automático en Visual Studio y no lo verá, pero es importante saber lo que ocurre en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-285">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Imagen del paso 4 opcional.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="e0bb9-287">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-287">Step 4.</span></span> <span data-ttu-id="e0bb9-288">Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="e0bb9-288">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="e0bb9-289">El archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) permite definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con comandos de implementación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-289">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="e0bb9-290">También configura sus relaciones de dependencia y la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-290">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="e0bb9-291">Para usar un archivo docker-compose.yml, debe crear el archivo en la carpeta de solución principal o raíz, con contenido similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-291">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
    ports:
      - "80:80"
    depends_on:
      - catalog-api
      - ordering-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sqldata

  sqldata:
    image: mcr.microsoft.com/mssql/server:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="e0bb9-292">Este archivo docker-compose.yml es una versión simplificada y combinada.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-292">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="e0bb9-293">Contiene datos de configuración estáticos para cada contenedor (como el nombre de la imagen personalizada), que siempre son necesarios, junto con información de configuración que puede depender del entorno de implementación, como la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-293">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="e0bb9-294">En secciones posteriores se enseña a dividir la configuración de docker-compose.yml en varios archivos docker-compose y a reemplazar los valores según el entorno y el tipo de ejecución (depuración o versión).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-294">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="e0bb9-295">El ejemplo de archivo docker-compose.yml define cuatro servicios: el servicio `webmvc` (una aplicación web), dos microservicios (`ordering-api` y `basket-api`) y un contenedor de fuente de datos, `sqldata`, según el servidor de SQL Server para Linux que se ejecute como contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-295">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering-api` and `basket-api`), and one data source container, `sqldata`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="e0bb9-296">Cada servicio se implementa como un contenedor, por lo que se necesita una imagen de Docker para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-296">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="e0bb9-297">El archivo docker-compose.yml especifica no solo qué contenedores se van a usar, sino cómo se configuran individualmente.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-297">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="e0bb9-298">Por ejemplo, la definición del contenedor `webmvc` en el archivo .yml:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-298">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="e0bb9-299">Usa una imagen `eshop/web:latest` precompilada.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-299">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="e0bb9-300">Pero también puede configurar la imagen de modo que se compile como parte de la ejecución de docker-compose con una configuración adicional basada en una compilación: sección del archivo docker-compose.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-300">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="e0bb9-301">Inicializa dos variables de entorno (CatalogUrl y OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-301">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="e0bb9-302">Reenvía el puerto 80 expuesto en el contenedor al puerto 80 externo del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-302">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="e0bb9-303">Vincula la aplicación web al catálogo y el servicio de orden con el valor depends_on.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-303">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="e0bb9-304">Esto hace que el servicio espere hasta que se inician los servicios.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-304">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="e0bb9-305">Se volverá a hablar del archivo docker-compose.yml en una sección posterior, cuando se trate la implementación de microservicios y aplicaciones de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-305">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2019"></a><span data-ttu-id="e0bb9-306">Trabajo con docker-compose.yml en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-306">Working with docker-compose.yml in Visual Studio 2019</span></span>

<span data-ttu-id="e0bb9-307">Además de agregar un Dockerfile a un proyecto, como se ha mencionado antes, Visual Studio 2017 (a partir de la versión 15.8 en adelante) puede agregar compatibilidad de orquestador con Docker Compose a una solución.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-307">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from version 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="e0bb9-308">Cuando se agrega compatibilidad de orquestador de contenedores, como se muestra en la figura 5-7, por primera vez, Visual Studio crea el Dockerfile para el proyecto y un nuevo proyecto (sección servicio) en la solución con varios archivos `docker-compose*.yml` globales y, luego, agrega el proyecto a esos archivos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-308">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="e0bb9-309">Luego puede abrir los archivos docker-compose.yml y actualizarlos con otras características.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-309">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="e0bb9-310">Tiene que repetir esta operación para cada proyecto que quiera incluir en el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-310">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="e0bb9-311">En el momento de redactar este artículo, Visual Studio admite los orquestadores **Docker Compose** y **Kubernetes/Helm**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-311">At the time of this writing, Visual Studio supports **Docker Compose** and **Kubernetes/Helm** orchestrators.</span></span>

![Captura de pantalla que muestra la opción Container Orchestrator Support (Compatibilidad con orquestador de contenedores) en el menú contextual del proyecto.](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

<span data-ttu-id="e0bb9-313">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-313">**Figure 5-7**.</span></span> <span data-ttu-id="e0bb9-314">Adición de compatibilidad con Docker en Visual Studio 2019 al hacer clic con el botón derecho en un proyecto de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0bb9-314">Adding Docker support in Visual Studio 2019 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="e0bb9-315">Después de agregar compatibilidad de orquestador a la solución en Visual Studio, también se ve un nuevo nodo (en el archivo de proyecto `docker-compose.dcproj`) en el Explorador de soluciones que contiene los archivos docker-compose.yml agregados, como se muestra en la figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-315">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Captura de pantalla del nodo docker-compose en el Explorador de soluciones.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

<span data-ttu-id="e0bb9-317">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-317">**Figure 5-8**.</span></span> <span data-ttu-id="e0bb9-318">Nodo de árbol **docker-compose** agregado en el Explorador de soluciones de Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-318">The **docker-compose** tree node added in Visual Studio 2019 Solution Explorer</span></span>

<span data-ttu-id="e0bb9-319">Puede implementar una aplicación de varios contenedores con un único archivo docker-compose.yml mediante el comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-319">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="e0bb9-320">Pero Visual Studio agrega un grupo de ellos para que pueda reemplazar valores en función del entorno (desarrollo o producción) y el tipo de ejecución (versión o depuración).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-320">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="e0bb9-321">Esta capacidad se explica en secciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-321">This capability will be explained in later sections.</span></span>

![Imagen del paso 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="e0bb9-323">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-323">Step 5.</span></span> <span data-ttu-id="e0bb9-324">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="e0bb9-324">Build and run your Docker application</span></span>

<span data-ttu-id="e0bb9-325">Si la aplicación solo tiene un contenedor, puede ejecutarla mediante su implementación en el host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-325">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="e0bb9-326">Sin embargo, si la aplicación contiene varios servicios, se puede implementar como aplicación compuesta, ya sea mediante un solo comando de la CLI `docker-compose up)` o con Visual Studio, que usará ese comando en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-326">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (`docker-compose up)`, or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="e0bb9-327">Echemos un vistazo a las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-327">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="e0bb9-328">Opción A: Ejecución de una aplicación de un solo contenedor</span><span class="sxs-lookup"><span data-stu-id="e0bb9-328">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="e0bb9-329">Uso de la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-329">Using Docker CLI</span></span>

<span data-ttu-id="e0bb9-330">Puede ejecutar un contenedor de Docker mediante el comando `docker run`, como se muestra en la figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-330">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="e0bb9-331">El comando anterior crea una nueva instancia de contenedor a partir de la imagen especificada cada vez que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-331">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="e0bb9-332">Puede usar el parámetro `--name` para asignar un nombre al contenedor y, luego, usar `docker start {name}` (o el identificador del contenedor o el nombre automático) para ejecutar una instancia de contenedor existente.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-332">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container ID or automatic name) to run an existing container instance.</span></span>

![Captura de pantalla de la ejecución de un contenedor de Docker mediante el comando docker run.](./media/docker-app-development-workflow/use-docker-run-command.png)

<span data-ttu-id="e0bb9-334">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-334">**Figure 5-9**.</span></span> <span data-ttu-id="e0bb9-335">Ejecución de un contenedor de Docker mediante el comando docker run</span><span class="sxs-lookup"><span data-stu-id="e0bb9-335">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="e0bb9-336">En este caso, el comando enlaza el puerto interno 5000 del contenedor con el puerto 80 del equipo de host.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-336">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="e0bb9-337">Esto significa que el host escucha en el puerto 80 y reenvía al puerto 5000 del contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-337">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="e0bb9-338">El hash que se muestra es el identificador del contenedor y además se le ha asignado un nombre legible aleatorio si no se ha usado la opción `--name`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-338">The hash shown is the container ID and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="e0bb9-339">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-339">Using Visual Studio</span></span>

<span data-ttu-id="e0bb9-340">Si no ha agregado compatibilidad de orquestador de contenedores, también puede ejecutar una aplicación de un solo contenedor si presiona **Ctrl-F5** y además puede usar **F5** para depurar la aplicación del contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-340">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="e0bb9-341">El contenedor se ejecuta localmente mediante docker run.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-341">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="e0bb9-342">Opción B: Ejecución de una aplicación de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="e0bb9-342">Option B: Running a multi-container application</span></span>

<span data-ttu-id="e0bb9-343">En la mayoría de los escenarios de empresa, una aplicación de Docker se compone de varios servicios, lo que significa que hay que ejecutar una aplicación de varios contenedores, como se muestra en la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-343">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Máquina virtual con varios contenedores de Docker](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="e0bb9-345">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-345">**Figure 5-10**.</span></span> <span data-ttu-id="e0bb9-346">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="e0bb9-346">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="e0bb9-347">Uso de la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-347">Using Docker CLI</span></span>

<span data-ttu-id="e0bb9-348">Para ejecutar una aplicación de varios contenedores con la CLI de Docker, use el comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-348">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="e0bb9-349">Este comando usa el archivo **docker-compose.yml** que hay en el nivel de solución para implementar una aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-349">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="e0bb9-350">La figura 5-11 muestra los resultados de la ejecución del comando desde el directorio principal de la solución, que contiene el archivo docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-350">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Vista de pantalla de la ejecución del comando docker-compose up](./media/docker-app-development-workflow/results-docker-compose-up.png)

<span data-ttu-id="e0bb9-352">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-352">**Figure 5-11**.</span></span> <span data-ttu-id="e0bb9-353">Resultados del ejemplo al ejecutar el comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="e0bb9-353">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="e0bb9-354">Después de la ejecución del comando docker-compose up, la aplicación y sus contenedores relacionados se implementan en el host de Docker, como se muestra en la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-354">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="e0bb9-355">Uso de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-355">Using Visual Studio</span></span>

<span data-ttu-id="e0bb9-356">La ejecución de una aplicación de varios contenedores mediante Visual Studio 2019 no puede ser más sencilla.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-356">Running a multi-container application using Visual Studio 2019 can't get any simpler.</span></span> <span data-ttu-id="e0bb9-357">Simplemente presione **Ctrl-F5** para ejecutar o **F5** para depurar, como de costumbre, con lo que se configura el proyecto **docker-compose** como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-357">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="e0bb9-358">Visual Studio controla toda la configuración necesaria, por lo que puede crear puntos de interrupción como de costumbre y depurar lo que finalmente se convierte en procesos independientes que se ejecutan en "servidores remotos", con el depurador ya adjuntado, con facilidad.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-358">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", with the debugger already attached, just like that.</span></span>

<span data-ttu-id="e0bb9-359">Como se ha mencionado antes, cada vez que se agrega compatibilidad con soluciones de Docker a un proyecto de una solución, ese proyecto se configura en el archivo global (nivel de solución) docker-compose.yml, lo que permite ejecutar o depurar la solución completa al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-359">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="e0bb9-360">Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad con soluciones de Docker y realiza todos los pasos internos automáticamente (dotnet publish, docker build, etc.).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-360">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="e0bb9-361">Si quiere echar un vistazo al trabajo monótono, vea el archivo:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-361">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="e0bb9-362">Lo importante aquí es que, como se muestra en la figura 5-12, en Visual Studio 2019 hay un comando adicional de **Docker** para la acción de la tecla F5.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-362">The important point here is that, as shown in Figure 5-12, in Visual Studio 2019 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="e0bb9-363">Esta opción permite ejecutar o depurar una aplicación de varios contenedores mediante la ejecución de todos los contenedores definidos en los archivos docker-compose.yml en el nivel de solución.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-363">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="e0bb9-364">La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada uno en un proyecto diferente (contenedor) y, durante la depuración desde Visual Studio, detenerse en los puntos de interrupción definidos en los distintos proyectos y en ejecución en contenedores diferentes.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-364">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Captura de pantalla de la barra de herramientas de depuración de Visual Studio ejecutando un proyecto docker-compose.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

<span data-ttu-id="e0bb9-366">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-366">**Figure 5-12**.</span></span> <span data-ttu-id="e0bb9-367">Ejecución de aplicaciones de varios contenedores en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-367">Running multi-container apps in Visual Studio 2019</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-368">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-368">Additional resources</span></span>

- <span data-ttu-id="e0bb9-369">**Implementación de un contenedor de ASP.NET en un host remoto de Docker** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-369">**Deploy an ASP.NET container to a remote Docker host** </span></span>\
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="e0bb9-370">Nota sobre las pruebas y la implementación con orquestadores</span><span class="sxs-lookup"><span data-stu-id="e0bb9-370">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="e0bb9-371">Los comandos docker-compose up y docker run (o la ejecución y depuración de los contenedores en Visual Studio) son adecuados para probar contenedores en el entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-371">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="e0bb9-372">Sin embargo, no debe usar este enfoque para implementaciones de producción donde se deba tener como destino orquestadores como [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-372">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="e0bb9-373">Si usa Kubernetes, tiene que usar [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) para organizar los contenedores y los [servicios](https://kubernetes.io/docs/concepts/services-networking/service/) para conectarlos en red.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-373">If you're using Kubernetes, you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="e0bb9-374">También se usan [implementaciones](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) organizar la creación y la modificación de pods.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-374">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![Imagen del paso 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="e0bb9-376">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-376">Step 6.</span></span> <span data-ttu-id="e0bb9-377">Probar la aplicación de Docker con el host local de Docker</span><span class="sxs-lookup"><span data-stu-id="e0bb9-377">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="e0bb9-378">Este paso varía en función de lo que haga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-378">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="e0bb9-379">En una aplicación web de .NET Core sencilla implementada como un único contenedor o servicio, puede acceder al servicio si abre un explorador en el host de Docker y va a ese sitio, como se muestra en la figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-379">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="e0bb9-380">(Si la configuración del Dockerfile asigna el contenedor a un puerto del host distinto al 80, incluya el puerto del host en la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-380">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Captura de pantalla de la respuesta de localhost/API/valores.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="e0bb9-382">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-382">**Figure 5-13**.</span></span> <span data-ttu-id="e0bb9-383">Ejemplo de prueba de la aplicación de Docker en local mediante localhost</span><span class="sxs-lookup"><span data-stu-id="e0bb9-383">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="e0bb9-384">Si localhost no apunta a la IP del host de Docker (de forma predeterminada, al usar Docker CE, debería hacerlo), para ir al servicio, use la dirección IP de la tarjeta de red del equipo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-384">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="e0bb9-385">Tenga en cuenta que esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se está analizando.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-385">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="e0bb9-386">Pero, internamente, las solicitudes se redirigen al puerto 5000, porque así es como se ha implementado con el comando docker run, como se ha explicado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-386">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="e0bb9-387">También puede probar la aplicación con la CURL del terminal, como se muestra en la figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-387">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="e0bb9-388">En una instalación de Docker en Windows, el valor predeterminado de la IP del host de Docker es siempre 10.0.75.1, además de la dirección IP real del equipo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-388">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Salida de consola de la obtención de http://10.0.75.1/API/values con CURL.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="e0bb9-390">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-390">**Figure 5-14**.</span></span> <span data-ttu-id="e0bb9-391">Ejemplo de prueba de la aplicación de Docker en local mediante CURL</span><span class="sxs-lookup"><span data-stu-id="e0bb9-391">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2019"></a><span data-ttu-id="e0bb9-392">Prueba y depuración de contenedores con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e0bb9-392">Testing and debugging containers with Visual Studio 2019</span></span>

<span data-ttu-id="e0bb9-393">Al ejecutar y depurar contenedores con Visual Studio 2019, puede depurar la aplicación de .NET prácticamente de la misma manera que como lo haría al realizar la ejecución sin contenedores.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-393">When running and debugging the containers with Visual Studio 2019, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="e0bb9-394">Pruebas y depuración sin Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-394">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="e0bb9-395">Si su desarrollo se basa en el enfoque de editor/CLI, la depuración de contenedores es más difícil y es probable que prefiera hacerlo mediante la generación de seguimientos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-395">If you're developing using the editor/CLI approach, debugging containers is more difficult and you'll probably want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-396">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-396">Additional resources</span></span>

- <span data-ttu-id="e0bb9-397">**Depuración de aplicaciones en un contenedor de Docker local** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-397">**Debugging apps in a local Docker container** </span></span>\
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="e0bb9-398">**Steve Lasker. Compilar, depurar e implementar aplicaciones ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="e0bb9-398">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="e0bb9-399">Video.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-399">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="e0bb9-400">Flujo de trabajo simplificado al desarrollar contenedores con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-400">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="e0bb9-401">En la práctica, el flujo de trabajo cuando se usa Visual Studio es mucho más sencillo que si se usa el enfoque de editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-401">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="e0bb9-402">La mayoría de los pasos que necesita Docker relacionados con el Dockerfile y los archivos docker-compose.yml están ocultos o se han simplificado con Visual Studio, como se muestra en la figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-402">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagrama que muestra los cinco pasos simplificados necesarios para crear una aplicación.":::
<span data-ttu-id="e0bb9-404">Proceso de desarrollo de aplicaciones de Docker: 1. Programar la aplicación, 2. Escribir Dockerfiles, 3. Crear imágenes definidas en Dockerfiles, 4. (Opcional) Crear servicios en el archivo docker-compose.yml, 5. Ejecutar contenedor o aplicación docker-compose, 6. Probar la aplicación o los microservicios, 7. Insertar en el repositorio y repetir.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-404">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="e0bb9-405">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-405">**Figure 5-15**.</span></span> <span data-ttu-id="e0bb9-406">Flujo de trabajo simplificado al desarrollar con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0bb9-406">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="e0bb9-407">Además, debe realizar el paso 2 (agregar compatibilidad con Docker a los proyectos) una sola vez.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-407">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="e0bb9-408">Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habituales cuando se usa .NET para cualquier otro desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-408">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="e0bb9-409">Debe saber qué está sucediendo en segundo plano (el proceso de compilación de imágenes, qué imágenes base usa, la implementación de contenedores, etc.) y, a veces, también debe editar el Dockerfile o el archivo docker-compose.yml para personalizar comportamientos.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-409">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="e0bb9-410">Pero con Visual Studio se simplifica enormemente la mayor parte del trabajo, lo que mejora mucho la productividad.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-410">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-411">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-411">Additional resources</span></span>

- <span data-ttu-id="e0bb9-412">**Desarrollo de Docker de .NET con Visual Studio 2017, de Steve Lasker** </span><span class="sxs-lookup"><span data-stu-id="e0bb9-412">**Steve Lasker. .NET Docker Development with Visual Studio (2017)** </span></span>\
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="e0bb9-413">Uso de comandos de PowerShell en un Dockerfile para configurar contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="e0bb9-413">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="e0bb9-414">Los [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) permiten convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-414">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="e0bb9-415">Para usar contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-415">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM mcr.microsoft.com/windows/servercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="e0bb9-416">En este caso se usa una imagen base de Windows Server Core (el valor FROM) y se instala IIS con un comando de PowerShell (el valor RUN).</span><span class="sxs-lookup"><span data-stu-id="e0bb9-416">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="e0bb9-417">Del mismo modo, también se pueden usar comandos de PowerShell para configurar otros componentes como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-417">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="e0bb9-418">Por ejemplo, el siguiente comando en un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="e0bb9-418">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="e0bb9-419">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0bb9-419">Additional resources</span></span>

- <span data-ttu-id="e0bb9-420">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="e0bb9-420">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="e0bb9-421">Comandos de PowerShell de ejemplo para ejecutar desde Dockerfiles a fin de incluir características de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0bb9-421">Example PowerShell commands to run from dockerfiles to include Windows features.</span></span>\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="e0bb9-422">[Anterior](index.md)
>[Siguiente](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="e0bb9-422">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
