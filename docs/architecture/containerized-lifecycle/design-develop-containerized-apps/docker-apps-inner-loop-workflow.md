---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Obtenga información sobre el flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker.
ms.date: 01/06/2021
ms.openlocfilehash: 78c593890d56a6888d4c4ea6752497918222ebee
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970590"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="6eef4-103">Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="6eef4-104">Antes de desencadenar el flujo de trabajo de bucle exterior que comprende el ciclo completo de DevOps, todo comienza en la máquina de cada desarrollador, al codificar la propia aplicación, utilizar sus lenguajes o plataformas preferidos y probarla localmente (figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="6eef4-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="6eef4-105">Pero en todos los casos, tendrá un aspecto importante en común, con independencia del lenguaje, el marco o las plataformas que elija.</span><span class="sxs-lookup"><span data-stu-id="6eef4-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="6eef4-106">En este flujo de trabajo concreto, los contenedores de Docker siempre se desarrollan y se prueban en este entorno y no otro, pero en local.</span><span class="sxs-lookup"><span data-stu-id="6eef4-106">In this specific workflow, you're always developing and testing Docker containers in no other environments, but locally.</span></span>

![Diagrama que muestra el concepto de un entorno de desarrollo de bucle interno.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="6eef4-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-108">**Figure 4-21**.</span></span> <span data-ttu-id="6eef4-109">Contexto de desarrollo de bucle interno</span><span class="sxs-lookup"><span data-stu-id="6eef4-109">Inner-loop development context</span></span>

<span data-ttu-id="6eef4-110">El contenedor o la instancia de una imagen de Docker contiene estos componentes:</span><span class="sxs-lookup"><span data-stu-id="6eef4-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="6eef4-111">Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="6eef4-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="6eef4-112">Archivos agregados por el desarrollador (por ejemplo, binarios de aplicación)</span><span class="sxs-lookup"><span data-stu-id="6eef4-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="6eef4-113">Información de configuración (por ejemplo, configuración de entorno y dependencias)</span><span class="sxs-lookup"><span data-stu-id="6eef4-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="6eef4-114">Instrucciones sobre los procesos que debe ejecutar Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="6eef4-115">Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como proceso (lo que se describe en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="6eef4-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="6eef4-116">Tenga en cuenta que no se incluyen los pasos iniciales para configurar el entorno, ya que basta con hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="6eef4-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="6eef4-117">Compilación de una sola aplicación en un contenedor de Docker con Visual Studio Code y la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="6eef4-118">Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="6eef4-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="6eef4-119">La figura 4-22 muestra los pasos básicos que normalmente hay que llevar a cabo para compilar una aplicación de Docker, seguidos de una descripción detallada de cada paso.</span><span class="sxs-lookup"><span data-stu-id="6eef4-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Diagrama que muestra los siete pasos necesarios para crear una aplicación en contenedores.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="6eef4-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-121">**Figure 4-22**.</span></span> <span data-ttu-id="6eef4-122">Flujo de trabajo general del ciclo de vida de aplicaciones en contenedor con la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="6eef4-123">Paso 1: Inicio de la codificación en Visual Studio Code y creación de la instantánea inicial de la aplicación o el servicio</span><span class="sxs-lookup"><span data-stu-id="6eef4-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="6eef4-124">La forma de desarrollar una aplicación es similar a la forma en que se lleva a cabo sin Docker.</span><span class="sxs-lookup"><span data-stu-id="6eef4-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="6eef4-125">La diferencia es que durante el desarrollo, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker situados en el entorno local (como una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="6eef4-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="6eef4-126">**Configuración del entorno local**</span><span class="sxs-lookup"><span data-stu-id="6eef4-126">**Setting up your local environment**</span></span>

<span data-ttu-id="6eef4-127">Con las últimas versiones de Docker Desktop para Mac y Windows, desarrollar aplicaciones de Docker es más fácil que nunca y la configuración es sencilla.</span><span class="sxs-lookup"><span data-stu-id="6eef4-127">With the latest versions of Docker Desktop for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-128">Para obtener instrucciones sobre cómo configurar Docker Desktop para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-128">For instructions on setting up Docker Desktop for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
> <span data-ttu-id="6eef4-129">Para obtener instrucciones sobre cómo configurar Docker Desktop para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-129">For instructions on setting up Docker Desktop for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="6eef4-130">Además, necesitará un editor de código para que realmente pueda desarrollar su aplicación al tiempo que usa la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="6eef4-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="6eef4-131">Microsoft ofrece Visual Studio Code, que es un editor de código ligero compatible con Windows, Linux y macOS y que proporciona IntelliSense con [compatibilidad con numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y la mayoría de lenguajes modernos), [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="6eef4-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="6eef4-132">Este editor es muy adecuado para desarrolladores de macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="6eef4-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="6eef4-133">En Windows, también puede usar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6eef4-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-134">Para instrucciones sobre cómo instalar Visual Studio Code para Windows, Linux o macOS, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="6eef4-135">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="6eef4-136">Puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero el uso de Visual Studio Code con la extensión de Docker facilita la creación de archivos `Dockerfile` y `docker-compose.yml` en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6eef4-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="6eef4-137">También puede ejecutar tareas y scripts en el IDE de Visual Studio Code que ejecuten comandos de Docker con la CLI de Docker que se encuentra debajo.</span><span class="sxs-lookup"><span data-stu-id="6eef4-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="6eef4-138">La extensión de Docker para VS Code ofrece las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="6eef4-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="6eef4-139">Generación automática de archivos `Dockerfile` y `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="6eef4-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="6eef4-140">Sugerencias de mantenimiento del puntero y resaltado de sintaxis en archivos `docker-compose.yml` y `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="6eef4-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="6eef4-141">IntelliSense (finalizaciones) para archivos `Dockerfile` y `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="6eef4-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="6eef4-142">Linting (errores y advertencias) en archivos `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="6eef4-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="6eef4-143">Integración con la paleta de comandos (F1) para los comandos de Docker más comunes</span><span class="sxs-lookup"><span data-stu-id="6eef4-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="6eef4-144">Integración con el explorador para administrar imágenes y contenedores</span><span class="sxs-lookup"><span data-stu-id="6eef4-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="6eef4-145">Implementación de imágenes de DockerHub y de instancias de Azure Container Registry en Azure App Service</span><span class="sxs-lookup"><span data-stu-id="6eef4-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="6eef4-146">Para instalar la extensión de Docker, presione Ctrl+Mayús+P, escriba `ext install` y ejecute el comando Instalar extensión para que aparezca la lista de extensiones de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="6eef4-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="6eef4-147">A continuación, escriba **docker** para filtrar los resultados y luego seleccione la extensión de compatibilidad con Docker, tal y como se muestra en la figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="6eef4-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Vista de la extensión de Docker para VS Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="6eef4-149">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-149">**Figure 4-23**.</span></span> <span data-ttu-id="6eef4-150">Instalación de la extensión de Docker para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6eef4-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-nodejs-and-ruby"></a><span data-ttu-id="6eef4-151">Paso 2: Creación de un DockerFile relacionado con una imagen existente (entornos de desarrollo o sistemas operativos estándar como .NET, Node.js y Ruby)</span><span class="sxs-lookup"><span data-stu-id="6eef4-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET, Node.js, and Ruby)</span></span>

<span data-ttu-id="6eef4-152">Necesitará un `DockerFile` por imagen personalizada que quiera crear y por contenedor que quiera implementar.</span><span class="sxs-lookup"><span data-stu-id="6eef4-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="6eef4-153">Si la aplicación se compone de un único servicio personalizado, necesita un solo `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-153">If your app is made up of single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="6eef4-154">Pero si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará un `Dockerfile` por servicio.</span><span class="sxs-lookup"><span data-stu-id="6eef4-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="6eef4-155">El archivo `DockerFile` normalmente se coloca en la carpeta raíz de la aplicación o el servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o ese servicio.</span><span class="sxs-lookup"><span data-stu-id="6eef4-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="6eef4-156">Puede crear el elemento `DockerFile` y agregarlo al proyecto junto con el código (node.js, .NET, etc.) o, si no está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="6eef4-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-157">Puede usar la extensión de Docker como guía al usar los archivos `Dockerfile` y `docker-compose.yml` relacionados con los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="6eef4-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="6eef4-158">Con el tiempo, es probable que escriba este tipo de archivos sin esta herramienta, pero el uso de la extensión de Docker es un buen punto de partida que acelerará su curva de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6eef4-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="6eef4-159">En la figura 4-24 puede ver los pasos necesarios para agregar archivos de Docker a un proyecto con la extensión de Docker para VS Code:</span><span class="sxs-lookup"><span data-stu-id="6eef4-159">In Figure 4-24, you can see the steps to add the docker files to a project by using the Docker Extension for VS Code:</span></span>

1. <span data-ttu-id="6eef4-160">Abra la paleta de comandos, escriba "**docker**" y seleccione "**Add Docker Files to Workspace**" (Agregar archivos de Docker al área de trabajo).</span><span class="sxs-lookup"><span data-stu-id="6eef4-160">Open the command palette, type "**docker**" and select "**Add Docker Files to Workspace**".</span></span>
2. <span data-ttu-id="6eef4-161">Selección de la plataforma de aplicación (ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="6eef4-161">Select Application Platform (ASP.NET Core)</span></span>
3. <span data-ttu-id="6eef4-162">Selección del sistema operativo (Linux)</span><span class="sxs-lookup"><span data-stu-id="6eef4-162">Select Operating System (Linux)</span></span>
4. <span data-ttu-id="6eef4-163">Inclusión de archivos de Docker Compose opcionales</span><span class="sxs-lookup"><span data-stu-id="6eef4-163">Include optional Docker Compose files</span></span>
5. <span data-ttu-id="6eef4-164">Especificación de los puertos para publicar (80, 443)</span><span class="sxs-lookup"><span data-stu-id="6eef4-164">Enter ports to publish (80, 443)</span></span>
6. <span data-ttu-id="6eef4-165">Seleccionar el proyecto</span><span class="sxs-lookup"><span data-stu-id="6eef4-165">Select the project</span></span>

![Pasos para agregar archivos de Docker con la extensión de Docker](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="6eef4-167">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-167">**Figure 4-24**.</span></span> <span data-ttu-id="6eef4-168">Archivos de Docker agregados con el comando **Add Docker files to Workspace** (Agregar archivos de Docker al área de trabajo)</span><span class="sxs-lookup"><span data-stu-id="6eef4-168">Docker files added using the **Add Docker files to Workspace** command</span></span>

<span data-ttu-id="6eef4-169">Cuando agregue un documento DockerFile, especifique la imagen base de Docker que va a usar (como el uso de `FROM mcr.microsoft.com/dotnet/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="6eef4-169">When you add a DockerFile, you specify what base Docker image you'll be using (like using `FROM mcr.microsoft.com/dotnet/aspnet`).</span></span> <span data-ttu-id="6eef4-170">Normalmente, creará la imagen personalizada sobre una imagen base que obtendrá de cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como una [imagen para .NET](https://hub.docker.com/_/microsoft-dotnet/) o la correspondiente [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="6eef4-170">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET](https://hub.docker.com/_/microsoft-dotnet/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-171">Tiene que repetir este procedimiento para cada proyecto de la aplicación,</span><span class="sxs-lookup"><span data-stu-id="6eef4-171">You'll have to repeat this procedure for every project in your application.</span></span> <span data-ttu-id="6eef4-172">aunque la extensión le pide que sobrescriba el archivo de Docker Compose generado después de la primera vez.</span><span class="sxs-lookup"><span data-stu-id="6eef4-172">However, the extension will ask to overwrite the generated docker-compose file after the first time.</span></span> <span data-ttu-id="6eef4-173">Debe responder que no quiere sobrescribirlo, para que la extensión cree archivos independientes de Docker Compose que después pueda combinar manualmente, antes de ejecutar Docker Compose.</span><span class="sxs-lookup"><span data-stu-id="6eef4-173">You should reply to not overwrite it, so the extension creates separate docker-compose files, that you can then merge by hand, prior to running docker-compose.</span></span>

<span data-ttu-id="6eef4-174">**_Uso de una imagen oficial de Docker existente_**</span><span class="sxs-lookup"><span data-stu-id="6eef4-174">**_Use an existing official Docker image_**</span></span>

<span data-ttu-id="6eef4-175">El uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todas las máquinas (incluidas las de desarrollo, pruebas y producción).</span><span class="sxs-lookup"><span data-stu-id="6eef4-175">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="6eef4-176">Este es un DockerFile de ejemplo para un contenedor de .NET:</span><span class="sxs-lookup"><span data-stu-id="6eef4-176">The following is a sample DockerFile for a .NET container:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

<span data-ttu-id="6eef4-177">En este caso, la imagen se basa en la versión 5.0 de la imagen oficial de Docker para ASP.NET Core (multiarquitectura de Linux y Windows), según la línea `FROM mcr.microsoft.com/dotnet/aspnet:5.0`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-177">In this case, the image is based on version 5.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/aspnet:5.0`.</span></span> <span data-ttu-id="6eef4-178">(Para obtener más información sobre este tema, vea las páginas sobre la [imagen de Docker de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet/) y la [imagen de Docker de .NET](https://hub.docker.com/_/microsoft-dotnet/)).</span><span class="sxs-lookup"><span data-stu-id="6eef4-178">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-aspnet/) page and the [.NET Docker Image](https://hub.docker.com/_/microsoft-dotnet/) page).</span></span>

<span data-ttu-id="6eef4-179">En el Dockerfile, también puede indicar a Docker que escuche el puerto TCP que se va a usar en tiempo de ejecución (por ejemplo, el puerto 80 o 443).</span><span class="sxs-lookup"><span data-stu-id="6eef4-179">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80 or 443).</span></span>

<span data-ttu-id="6eef4-180">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use.</span><span class="sxs-lookup"><span data-stu-id="6eef4-180">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="6eef4-181">Por ejemplo, la línea `ENTRYPOINT` con `["dotnet", "WebMvcApplication.dll"]` indica a Docker que ejecute una aplicación de .NET.</span><span class="sxs-lookup"><span data-stu-id="6eef4-181">For instance, the `ENTRYPOINT` line with `["dotnet", "WebMvcApplication.dll"]` tells Docker to run a .NET application.</span></span> <span data-ttu-id="6eef4-182">Si usa el SDK y la CLI de .NET (`dotnet CLI`) para compilar y ejecutar la aplicación de .NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-182">If you're using the SDK and the .NET CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="6eef4-183">El punto clave aquí es que la línea ENTRYPOINT y otros valores varían según el lenguaje y la plataforma que se elijan para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6eef4-183">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-184">Para obtener más información sobre cómo crear imágenes de Docker para aplicaciones de .NET, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-184">For more information about building Docker images for .NET applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="6eef4-185">Para más información sobre cómo crear sus propias imágenes, vaya a <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-185">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="6eef4-186">**Uso de repositorios de imágenes multiarquitectura**</span><span class="sxs-lookup"><span data-stu-id="6eef4-186">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="6eef4-187">Un solo nombre de imagen en un repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="6eef4-187">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="6eef4-188">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="6eef4-188">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="6eef4-189">Por ejemplo, el repositorio [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/), disponible en el registro de Docker Hub, proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de imagen.</span><span class="sxs-lookup"><span data-stu-id="6eef4-189">For example, the [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="6eef4-190">Al extraer la imagen [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="6eef4-190">Pulling the [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="6eef4-191">**_Creación de la imagen base desde cero_**</span><span class="sxs-lookup"><span data-stu-id="6eef4-191">**_Create your base image from scratch_**</span></span>

<span data-ttu-id="6eef4-192">Puede crear su propia imagen de base de Docker desde cero, tal y como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="6eef4-192">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="6eef4-193">Probablemente este escenario no sea el más adecuado para usuarios que acaban de iniciarse en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6eef4-193">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="6eef4-194">Paso 3: Creación de imágenes personalizadas de Docker insertando su servicio en ellas</span><span class="sxs-lookup"><span data-stu-id="6eef4-194">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="6eef4-195">Por cada servicio personalizado que incluya su aplicación, deberá crear una imagen relacionada.</span><span class="sxs-lookup"><span data-stu-id="6eef4-195">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="6eef4-196">Si la aplicación consta de un único servicio o aplicación web, solo necesitará una imagen.</span><span class="sxs-lookup"><span data-stu-id="6eef4-196">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="6eef4-197">Si se tiene en cuenta el "flujo de trabajo de bucle exterior de DevOps", las imágenes se crearán mediante un proceso de compilación automatizado cada vez que el código fuente se inserte en un repositorio de Git (integración continua), por lo que las imágenes se crearán en ese entorno global a partir de su código fuente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-197">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="6eef4-198">Pero antes de contemplar la posibilidad de ir a esa ruta de bucle externo, tiene que asegurarse de que la aplicación de Docker funciona correctamente para que no inserte código que pudiera no funcionar correctamente en el sistema de control de código fuente (Git, etc.).</span><span class="sxs-lookup"><span data-stu-id="6eef4-198">But before you consider going to that outer-loop route, you need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="6eef4-199">Por lo tanto, cada desarrollador debe realizar en primer lugar todo el proceso de bucle interno para probarlo localmente y continuar desarrollando hasta que quiera insertar una característica completa o cambiarla al sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-199">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="6eef4-200">Para crear una imagen en el entorno local y usar el Dockerfile, puede emplear el comando build de Docker, como se muestra en la figura 4-25, porque ya etiqueta la imagen automáticamente y compila las imágenes para todos los servicios de la aplicación con un comando simple.</span><span class="sxs-lookup"><span data-stu-id="6eef4-200">To create an image in your local environment and using the DockerFile, you can use the docker build command, as shown in Figure 4-25, because it already tags the image for you and builds the images for all services in the application with a simple command.</span></span>

![Captura de pantalla que muestra la salida de la consola del comando build de Docker Compose.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="6eef4-202">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-202">**Figure 4-25**.</span></span> <span data-ttu-id="6eef4-203">Ejecución de la compilación de Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-203">Running docker build</span></span>

<span data-ttu-id="6eef4-204">Si lo prefiere, en lugar de ejecutar directamente `docker build` desde la carpeta del proyecto, puede generar primero una carpeta implementable con las bibliotecas.NET necesarias mediante la ejecución del comando `dotnet publish` y la posterior ejecución de `docker build`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-204">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="6eef4-205">En este ejemplo se crea una imagen de Docker de nombre `webapi:latest` (`:latest` es una etiqueta, como una versión específica).</span><span class="sxs-lookup"><span data-stu-id="6eef4-205">This example creates a Docker image with the name `webapi:latest` (`:latest` is a tag, like a specific version).</span></span> <span data-ttu-id="6eef4-206">Puede seguir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta con varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="6eef4-206">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span> <span data-ttu-id="6eef4-207">Pero en la siguiente sección va a ver que es más fácil hacerlo mediante `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-207">However, we'll see in the next section that it's easier to do this using `docker-compose`.</span></span>

<span data-ttu-id="6eef4-208">Puede encontrar las imágenes existentes en el repositorio local (la máquina de desarrollo) mediante el comando `docker images`, como se muestra en la figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="6eef4-208">You can find the existing images in your local repository (your development machine) by using the `docker images` command, as illustrated in Figure 4-26.</span></span>

![Salida de consola del comando docker images, que muestra las imágenes existentes en la consola.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="6eef4-210">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-210">**Figure 4-26**.</span></span> <span data-ttu-id="6eef4-211">Visualización de imágenes existentes con docker images</span><span class="sxs-lookup"><span data-stu-id="6eef4-211">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="6eef4-212">Paso 4: Definición de los servicios en docker-compose.yml al compilar una aplicación de Docker compuesta de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="6eef4-212">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="6eef4-213">Con el archivo `docker-compose.yml`, puede definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con los comandos de implementación que se explican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-213">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="6eef4-214">Cree ese archivo en la carpeta principal o raíz de su solución; debe tener un contenido similar al que se muestra en este archivo `docker-compose.yml`:</span><span class="sxs-lookup"><span data-stu-id="6eef4-214">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

<span data-ttu-id="6eef4-215">En este caso concreto, este archivo define tres servicios: el servicio API web (el servicio personalizado), una aplicación web y el servicio Redis (un popular servicio de caché).</span><span class="sxs-lookup"><span data-stu-id="6eef4-215">In this particular case, this file defines three services: the web API service (your custom service), a web application, and the Redis service (a popular cache service).</span></span> <span data-ttu-id="6eef4-216">Cada servicio se implementa como un contenedor, por lo que debe usar una imagen de Docker concreta para cada uno.</span><span class="sxs-lookup"><span data-stu-id="6eef4-216">Each service will be deployed as a container, so you need to use a concrete Docker image for each.</span></span> <span data-ttu-id="6eef4-217">En el caso de esta aplicación concreta:</span><span class="sxs-lookup"><span data-stu-id="6eef4-217">For this particular application:</span></span>

- <span data-ttu-id="6eef4-218">El servicio API web se compila a partir del Dockerfile del directorio `src/WebApi/Dockerfile`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-218">The web API service is built from the DockerFile in the `src/WebApi/Dockerfile` directory.</span></span>

- <span data-ttu-id="6eef4-219">El puerto de host 51080 se reenvía al puerto 80 expuesto en el contenedor `webapi`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-219">The host port 51080 is forwarded to the exposed port 80 on the `webapi` container.</span></span>

- <span data-ttu-id="6eef4-220">El servicio API web depende del servicio Redis</span><span class="sxs-lookup"><span data-stu-id="6eef4-220">The web API service depends on the Redis service</span></span>

- <span data-ttu-id="6eef4-221">La aplicación web accede al servicio API web mediante la dirección interna: `http://webapi`.</span><span class="sxs-lookup"><span data-stu-id="6eef4-221">The web application accesses the web API service using the internal address: `http://webapi`.</span></span>

- <span data-ttu-id="6eef4-222">El servicio Redis usa la [imagen pública más reciente de Redis](https://hub.docker.com/_/redis/) extraída del registro de Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="6eef4-222">The Redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="6eef4-223">[Redis](https://redis.io/) es un popular sistema de caché para aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="6eef4-223">[Redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="6eef4-224">Paso 5: Compilación y ejecución de la aplicación de Docker</span><span class="sxs-lookup"><span data-stu-id="6eef4-224">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="6eef4-225">Si la aplicación tiene un solo contenedor, para ejecutarla tan solo tiene que implementarla en el host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="6eef4-225">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="6eef4-226">Aunque si la aplicación se compone de varios servicios también tendrá que _componerla_.</span><span class="sxs-lookup"><span data-stu-id="6eef4-226">However, if your app is made up of multiple services, you need to _compose it_, too.</span></span> <span data-ttu-id="6eef4-227">Veamos las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="6eef4-227">Let's see the different options.</span></span>

<span data-ttu-id="6eef4-228">**_Opción A: Ejecución de un único contenedor o servicio_**</span><span class="sxs-lookup"><span data-stu-id="6eef4-228">**_Option A: Run a single container or service_**</span></span>

<span data-ttu-id="6eef4-229">Puede ejecutar la imagen de Docker mediante el comando docker run, tal y como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="6eef4-229">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 50080:80 webapp:latest
```

<span data-ttu-id="6eef4-230">En el caso de esta implementación en particular, las solicitudes enviadas al puerto 50080 en el host se van a redirigir al puerto interno 80.</span><span class="sxs-lookup"><span data-stu-id="6eef4-230">For this particular deployment, we'll be redirecting requests sent to port 50080 on the host to the internal port 80.</span></span>

<span data-ttu-id="6eef4-231">**_Opción B: Redacción y ejecución de una aplicación de varios contenedores_**</span><span class="sxs-lookup"><span data-stu-id="6eef4-231">**_Option B: Compose and run a multiple-container application_**</span></span>

<span data-ttu-id="6eef4-232">En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios.</span><span class="sxs-lookup"><span data-stu-id="6eef4-232">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="6eef4-233">En estos casos, puede ejecutar el comando `docker-compose up` (figura 4-27), que va a usar el archivo docker-compose.yml creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-233">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you created previously.</span></span> <span data-ttu-id="6eef4-234">Al ejecutar este comando se compilan todas las imágenes personalizadas y se implementa la aplicación compuesta con todos sus contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="6eef4-234">Running this command builds all custom images and deploys the composed application with all of its related containers.</span></span>

![Salida de consola del comando docker-compose up.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="6eef4-236">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-236">**Figure 4-27**.</span></span> <span data-ttu-id="6eef4-237">Resultados de la ejecución del comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="6eef4-237">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="6eef4-238">Después de ejecutar `docker-compose up`, se implementa la aplicación y sus contenedores relacionados en el host de Docker, tal y como se muestra en la figura 4-28, en la representación de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="6eef4-238">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Máquina virtual que ejecuta una aplicación de varios contenedores.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="6eef4-240">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-240">**Figure 4-28**.</span></span> <span data-ttu-id="6eef4-241">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="6eef4-241">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="6eef4-242">Paso 6: Prueba de la aplicación de Docker (localmente, en la máquina virtual de CD local)</span><span class="sxs-lookup"><span data-stu-id="6eef4-242">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="6eef4-243">Este paso varía en función de lo que haga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6eef4-243">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="6eef4-244">En "Hola mundo", una API web sencilla de .NET que se implementa como contenedor o servicio único, solo tiene que acceder al servicio facilitando el puerto TCP especificado en el DockerFile.</span><span class="sxs-lookup"><span data-stu-id="6eef4-244">In a simple .NET Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="6eef4-245">En el host de Docker, abra un explorador y navegue a ese sitio; debe ver la aplicación o el servicio en ejecución, tal y como se muestra en la figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="6eef4-245">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Vista de explorador de la respuesta de localhost/API/valores.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="6eef4-247">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-247">**Figure 4-29**.</span></span> <span data-ttu-id="6eef4-248">Prueba de la aplicación de Docker en local mediante el explorador</span><span class="sxs-lookup"><span data-stu-id="6eef4-248">Testing your Docker application locally by using the browser</span></span>

<span data-ttu-id="6eef4-249">Observe que usa el puerto 50080, pero internamente se redirige al puerto 80, porque así es como se han implementado con `docker compose`, como se ha explicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-249">Note that it's using port 50080, but internally it's being redirected to port 80, because that's how it was deployed with `docker compose`, as explained earlier.</span></span>

<span data-ttu-id="6eef4-250">Puede probar con el explorador si usa CURL desde el terminal, como se muestra en la figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="6eef4-250">You can test this by using the browser using CURL from the terminal, as depicted in Figure 4-30.</span></span>

![Resultado de CURL obtenido de http://localhost:51080/WeatherForecast](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="6eef4-252">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="6eef4-252">**Figure 4-30**.</span></span> <span data-ttu-id="6eef4-253">Prueba de una aplicación de Docker en local mediante CURL</span><span class="sxs-lookup"><span data-stu-id="6eef4-253">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="6eef4-254">**Depuración de un contenedor que se ejecuta en Docker**</span><span class="sxs-lookup"><span data-stu-id="6eef4-254">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="6eef4-255">Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como, por ejemplo, contenedores de .NET.</span><span class="sxs-lookup"><span data-stu-id="6eef4-255">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET containers.</span></span>

<span data-ttu-id="6eef4-256">También puede depurar contenedores de .NET o .NET Framework en Docker cuando se usa Visual Studio para Windows o Mac, tal y como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6eef4-256">You also can debug .NET or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="6eef4-257">Para más información sobre la depuración de contenedores de Docker de Node.js, consulte <https://blog.docker.com/2016/07/live-debugging-docker/> y <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span><span class="sxs-lookup"><span data-stu-id="6eef4-257">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="6eef4-258">[Anterior](docker-apps-development-environment.md)
> [Siguiente](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="6eef4-258">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
