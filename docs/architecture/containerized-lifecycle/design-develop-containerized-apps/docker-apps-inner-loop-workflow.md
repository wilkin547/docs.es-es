---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Conozca el flujo de trabajo de "bucle interno" del desarrollo de aplicaciones de Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 3d2fc889d22dbf02acccfbf9231ad98fca224cff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936812"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="1760e-103">Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="1760e-104">Antes de desencadenar el flujo de trabajo de bucle exterior que comprende el ciclo completo de DevOps, todo comienza en la máquina de cada desarrollador, al codificar la propia aplicación, utilizar sus lenguajes o plataformas preferidos y probarla localmente (figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="1760e-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="1760e-105">Pero en todos los casos, tendrá un aspecto importante en común, con independencia del lenguaje, el marco o las plataformas que elija.</span><span class="sxs-lookup"><span data-stu-id="1760e-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="1760e-106">En este flujo de trabajo concreto, siempre desarrolla y prueba contenedores de Docker, pero localmente.</span><span class="sxs-lookup"><span data-stu-id="1760e-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Diagrama que muestra el concepto de un entorno de desarrollo de bucle interno.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="1760e-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="1760e-108">**Figure 4-21**.</span></span> <span data-ttu-id="1760e-109">Contexto de desarrollo de bucle interno</span><span class="sxs-lookup"><span data-stu-id="1760e-109">Inner-loop development context</span></span>

<span data-ttu-id="1760e-110">El contenedor o la instancia de una imagen de Docker contiene estos componentes:</span><span class="sxs-lookup"><span data-stu-id="1760e-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="1760e-111">Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="1760e-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="1760e-112">Archivos agregados por el desarrollador (por ejemplo, binarios de aplicación)</span><span class="sxs-lookup"><span data-stu-id="1760e-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="1760e-113">Información de configuración (por ejemplo, configuración de entorno y dependencias)</span><span class="sxs-lookup"><span data-stu-id="1760e-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="1760e-114">Instrucciones sobre los procesos que debe ejecutar Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="1760e-115">Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como proceso (lo que se describe en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="1760e-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="1760e-116">Tenga en cuenta que no se incluyen los pasos iniciales para configurar el entorno, ya que basta con hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="1760e-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="1760e-117">Compilación de una sola aplicación en un contenedor de Docker con Visual Studio Code y la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="1760e-118">Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="1760e-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="1760e-119">La figura 4-22 muestra los pasos básicos que normalmente hay que llevar a cabo para compilar una aplicación de Docker, seguidos de una descripción detallada de cada paso.</span><span class="sxs-lookup"><span data-stu-id="1760e-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Diagrama que muestra los siete pasos necesarios para crear una aplicación en contenedores.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="1760e-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="1760e-121">**Figure 4-22**.</span></span> <span data-ttu-id="1760e-122">Flujo de trabajo general del ciclo de vida de aplicaciones en contenedor con la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="1760e-123">Paso 1: Inicio de la codificación en Visual Studio Code y creación de la instantánea inicial de la aplicación o el servicio</span><span class="sxs-lookup"><span data-stu-id="1760e-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="1760e-124">La forma de desarrollar una aplicación es similar a la forma en que se lleva a cabo sin Docker.</span><span class="sxs-lookup"><span data-stu-id="1760e-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="1760e-125">La diferencia es que durante el desarrollo, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker situados en el entorno local (como una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="1760e-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="1760e-126">**Configuración del entorno local**</span><span class="sxs-lookup"><span data-stu-id="1760e-126">**Setting up your local environment**</span></span>

<span data-ttu-id="1760e-127">Con las últimas versiones de Docker para Mac y Windows, desarrollar aplicaciones de Docker es más fácil que nunca y la configuración es sencilla.</span><span class="sxs-lookup"><span data-stu-id="1760e-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="1760e-128">Para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="1760e-128">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="1760e-129">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="1760e-129">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="1760e-130">Además, necesitará un editor de código para que realmente pueda desarrollar su aplicación al tiempo que usa la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="1760e-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="1760e-131">Microsoft ofrece Visual Studio Code, que es un editor de código ligero compatible con Windows, Linux y macOS y que proporciona IntelliSense con [compatibilidad con numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y la mayoría de lenguajes modernos), [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="1760e-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="1760e-132">Este editor es muy adecuado para desarrolladores de macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="1760e-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="1760e-133">En Windows, también puede usar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1760e-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="1760e-134">Para instrucciones sobre cómo instalar Visual Studio Code para Windows, Linux o macOS, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="1760e-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="1760e-135">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="1760e-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="1760e-136">Puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero el uso de Visual Studio Code con la extensión de Docker facilita la creación de archivos `Dockerfile` y `docker-compose.yml` en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1760e-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="1760e-137">También puede ejecutar tareas y scripts en el IDE de Visual Studio Code que ejecuten comandos de Docker con la CLI de Docker que se encuentra debajo.</span><span class="sxs-lookup"><span data-stu-id="1760e-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="1760e-138">La extensión de Docker para VS Code ofrece las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="1760e-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="1760e-139">Generación automática de archivos `Dockerfile` y `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="1760e-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="1760e-140">Sugerencias de mantenimiento del puntero y resaltado de sintaxis en archivos `docker-compose.yml` y `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="1760e-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="1760e-141">IntelliSense (finalizaciones) para archivos `Dockerfile` y `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="1760e-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="1760e-142">Linting (errores y advertencias) en archivos `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="1760e-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="1760e-143">Integración con la paleta de comandos (F1) para los comandos de Docker más comunes</span><span class="sxs-lookup"><span data-stu-id="1760e-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="1760e-144">Integración con el explorador para administrar imágenes y contenedores</span><span class="sxs-lookup"><span data-stu-id="1760e-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="1760e-145">Implementación de imágenes de DockerHub y de instancias de Azure Container Registry en Azure App Service</span><span class="sxs-lookup"><span data-stu-id="1760e-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="1760e-146">Para instalar la extensión de Docker, presione Ctrl+Mayús+P, escriba `ext install` y ejecute el comando Instalar extensión para que aparezca la lista de extensiones de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="1760e-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="1760e-147">A continuación, escriba **docker** para filtrar los resultados y luego seleccione la extensión de compatibilidad con Docker, tal y como se muestra en la figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="1760e-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Vista de la extensión de Docker para VS Code.](./media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="1760e-149">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="1760e-149">**Figure 4-23**.</span></span> <span data-ttu-id="1760e-150">Instalación de la extensión de Docker para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="1760e-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="1760e-151">Paso 2: Creación de un DockerFile relacionado con una imagen existente (entornos de desarrollo o sistemas operativos estándar como Ruby, Node.js y .NET Core)</span><span class="sxs-lookup"><span data-stu-id="1760e-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="1760e-152">Necesitará un `DockerFile` por imagen personalizada que quiera crear y por contenedor que quiera implementar.</span><span class="sxs-lookup"><span data-stu-id="1760e-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="1760e-153">Si la aplicación se compone de un único servicio personalizado, necesitará un solo `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="1760e-153">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="1760e-154">Pero si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará un `Dockerfile` por servicio.</span><span class="sxs-lookup"><span data-stu-id="1760e-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="1760e-155">El archivo `DockerFile` normalmente se coloca en la carpeta raíz de la aplicación o el servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o ese servicio.</span><span class="sxs-lookup"><span data-stu-id="1760e-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="1760e-156">Puede crear el `DockerFile` y agregarlo al proyecto junto con el código (node.js, .NET Core, etc.) o, si no está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="1760e-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="1760e-157">Puede usar la extensión de Docker como guía al usar los archivos `Dockerfile` y `docker-compose.yml` relacionados con los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="1760e-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="1760e-158">Con el tiempo, es probable que escriba este tipo de archivos sin esta herramienta, pero el uso de la extensión de Docker es un buen punto de partida que acelerará su curva de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="1760e-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="1760e-159">En la figura 4-24, puede ver cómo se agrega un archivo docker-compose mediante la extensión de Docker para VS Code.</span><span class="sxs-lookup"><span data-stu-id="1760e-159">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Vista de consola de la extensión de Docker para VS Code.](./media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="1760e-161">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="1760e-161">**Figure 4-24**.</span></span> <span data-ttu-id="1760e-162">Archivos de Docker que se agregan con el **comando Add Docker files to Workspace** (Agregar archivos de Docker al área de trabajo)</span><span class="sxs-lookup"><span data-stu-id="1760e-162">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="1760e-163">Cuando agregue un DockerFile, especifique la imagen base de Docker que va a usar (como el uso de `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="1760e-163">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="1760e-164">Normalmente, creará la imagen personalizada sobre una imagen base que obtendrá de cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como una [imagen para .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) o la correspondiente [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="1760e-164">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="1760e-165">***Uso de una imagen oficial de Docker existente***</span><span class="sxs-lookup"><span data-stu-id="1760e-165">***Use an existing official Docker image***</span></span>

<span data-ttu-id="1760e-166">El uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todas las máquinas (incluidas las de desarrollo, pruebas y producción).</span><span class="sxs-lookup"><span data-stu-id="1760e-166">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="1760e-167">Este es un DockerFile de ejemplo para un contenedor de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="1760e-167">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="1760e-168">En este caso, la imagen se basa en la versión 2.2 de la imagen oficial de Docker para ASP.NET Core (multiarquitectura de Linux y Windows), según la línea `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="1760e-168">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="1760e-169">(Para obtener más información sobre este tema, vea las páginas [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) [Imagen de Docker de ASP.NET Core] y [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) [Imagen de Docker de .NET Core]).</span><span class="sxs-lookup"><span data-stu-id="1760e-169">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="1760e-170">En el DockerFile, también puede indicar a Docker que escuche el puerto TCP que se va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).</span><span class="sxs-lookup"><span data-stu-id="1760e-170">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="1760e-171">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use.</span><span class="sxs-lookup"><span data-stu-id="1760e-171">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="1760e-172">Por ejemplo, la línea `ENTRYPOINT` con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker que ejecute una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1760e-172">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="1760e-173">Si usa el SDK y la CLI de .NET Core (`dotnet CLI`) para compilar y ejecutar la aplicación .NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="1760e-173">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="1760e-174">El punto clave aquí es que la línea ENTRYPOINT y otros valores varían según el lenguaje y la plataforma que se elijan para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1760e-174">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="1760e-175">Para más información sobre cómo crear imágenes de Docker para aplicaciones .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="1760e-175">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="1760e-176">Para más información sobre cómo crear sus propias imágenes, vaya a <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="1760e-176">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="1760e-177">**Uso de repositorios de imágenes multiarquitectura**</span><span class="sxs-lookup"><span data-stu-id="1760e-177">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="1760e-178">Un solo nombre de imagen en un repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="1760e-178">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="1760e-179">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="1760e-179">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="1760e-180">Por ejemplo, el repositorio [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) disponible en el registro de Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de imagen.</span><span class="sxs-lookup"><span data-stu-id="1760e-180">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="1760e-181">Al extraer la imagen [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="1760e-181">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="1760e-182">***Creación de la imagen base desde cero***</span><span class="sxs-lookup"><span data-stu-id="1760e-182">***Create your base image from scratch***</span></span>

<span data-ttu-id="1760e-183">Puede crear su propia imagen de base de Docker desde cero, tal y como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="1760e-183">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="1760e-184">Probablemente este escenario no sea el más adecuado para usuarios que acaban de iniciarse en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1760e-184">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="1760e-185">Paso 3: Creación de imágenes personalizadas de Docker insertando su servicio en ellas</span><span class="sxs-lookup"><span data-stu-id="1760e-185">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="1760e-186">Por cada servicio personalizado que incluya su aplicación, deberá crear una imagen relacionada.</span><span class="sxs-lookup"><span data-stu-id="1760e-186">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="1760e-187">Si la aplicación consta de un único servicio o aplicación web, solo necesitará una imagen.</span><span class="sxs-lookup"><span data-stu-id="1760e-187">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="1760e-188">Si se tiene en cuenta el "flujo de trabajo de bucle exterior de DevOps", las imágenes se crearán mediante un proceso de compilación automatizado cada vez que el código fuente se inserte en un repositorio de Git (integración continua), por lo que las imágenes se crearán en ese entorno global a partir de su código fuente.</span><span class="sxs-lookup"><span data-stu-id="1760e-188">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="1760e-189">Pero antes de contemplar la posibilidad de ir a esa ruta de bucle externo, hemos de asegurarnos de que la aplicación Docker funciona correctamente para que no inserte código que podría no funcionar correctamente en el sistema de control de código fuente (Git, etcétera).</span><span class="sxs-lookup"><span data-stu-id="1760e-189">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="1760e-190">Por lo tanto, cada desarrollador debe realizar en primer lugar todo el proceso de bucle interno para probarlo localmente y continuar desarrollando hasta que quiera insertar una característica completa o cambiarla al sistema de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1760e-190">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="1760e-191">Para crear una imagen en su entorno local y con el DockerFile, puede usar el comando de compilación de Docker, tal y como se muestra en la figura 4-25 (también puede ejecutar `docker-compose up --build` para aplicaciones compuestas por varios contenedores y servicios).</span><span class="sxs-lookup"><span data-stu-id="1760e-191">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Captura de pantalla que muestra la salida de la consola del comando de compilación de Docker.](./media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="1760e-193">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="1760e-193">**Figure 4-25**.</span></span> <span data-ttu-id="1760e-194">Ejecución de la compilación de Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-194">Running docker build</span></span>

<span data-ttu-id="1760e-195">Si lo prefiere, en lugar de ejecutar directamente `docker build` desde la carpeta del proyecto, puede generar primero una carpeta implementable con las bibliotecas.NET necesarias mediante la ejecución del comando `dotnet publish` y la posterior ejecución de `docker build`.</span><span class="sxs-lookup"><span data-stu-id="1760e-195">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="1760e-196">En este ejemplo se crea una imagen de Docker de nombre `cesardl/netcore-webapi-microservice-docker:first` (`:first` es una etiqueta, como una versión específica).</span><span class="sxs-lookup"><span data-stu-id="1760e-196">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="1760e-197">Puede seguir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta con varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="1760e-197">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="1760e-198">Puede encontrar las imágenes existentes en el repositorio local (la máquina de desarrollo) mediante el comando docker images, tal y como se muestra en la figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="1760e-198">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Salida de consola del comando docker images, que muestra las imágenes existentes en la consola.](./media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="1760e-200">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="1760e-200">**Figure 4-26**.</span></span> <span data-ttu-id="1760e-201">Visualización de imágenes existentes con docker images</span><span class="sxs-lookup"><span data-stu-id="1760e-201">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="1760e-202">Paso 4: Definición de los servicios en docker-compose.yml al compilar una aplicación de Docker compuesta de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="1760e-202">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="1760e-203">Con el archivo `docker-compose.yml`, puede definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con los comandos de implementación que se explican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="1760e-203">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="1760e-204">Cree ese archivo en la carpeta principal o raíz de su solución; debe tener un contenido similar al que se muestra en este archivo `docker-compose.yml`:</span><span class="sxs-lookup"><span data-stu-id="1760e-204">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="1760e-205">En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio Redis (un popular servicio de cache).</span><span class="sxs-lookup"><span data-stu-id="1760e-205">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="1760e-206">Cada servicio se implementa como contenedor, por lo que se necesita una imagen de Docker concreta para cada uno.</span><span class="sxs-lookup"><span data-stu-id="1760e-206">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="1760e-207">Para este servicio web en particular, la imagen debe llevar a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1760e-207">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="1760e-208">Compilación desde el archivo DockerFile en el directorio actual</span><span class="sxs-lookup"><span data-stu-id="1760e-208">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="1760e-209">Reenvío del puerto 80 expuesto en el contenedor al puerto 81 de la máquina host</span><span class="sxs-lookup"><span data-stu-id="1760e-209">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="1760e-210">Montaje del directorio del proyecto en el host en /code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen</span><span class="sxs-lookup"><span data-stu-id="1760e-210">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="1760e-211">Vinculación del servicio web al servicio Redis</span><span class="sxs-lookup"><span data-stu-id="1760e-211">Link the web service to the redis service</span></span>

<span data-ttu-id="1760e-212">El servicio Redis usa la [imagen pública más reciente de Redis](https://hub.docker.com/_/redis/) extraída del registro de Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="1760e-212">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="1760e-213">[redis](https://redis.io/) es un popular sistema de caché para aplicaciones del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="1760e-213">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="1760e-214">Paso 5: Compilación y ejecución de la aplicación de Docker</span><span class="sxs-lookup"><span data-stu-id="1760e-214">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="1760e-215">Si la aplicación tiene un solo contenedor, para ejecutarla tan solo tiene que implementarla en el host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="1760e-215">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="1760e-216">Aunque si la aplicación se compone de varios servicios también tendrá que *componerla*.</span><span class="sxs-lookup"><span data-stu-id="1760e-216">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="1760e-217">Veamos las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="1760e-217">Let's see the different options.</span></span>

<span data-ttu-id="1760e-218">***Opción A: Ejecución de un único contenedor o servicio***</span><span class="sxs-lookup"><span data-stu-id="1760e-218">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="1760e-219">Puede ejecutar la imagen de Docker mediante el comando docker run, tal y como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="1760e-219">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="1760e-220">En el caso de esta implementación en particular, las solicitudes enviadas al puerto 80 se redirigirán al puerto interno 5000.</span><span class="sxs-lookup"><span data-stu-id="1760e-220">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="1760e-221">Ahora la aplicación escucha en el puerto 80 externo en el nivel de host.</span><span class="sxs-lookup"><span data-stu-id="1760e-221">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="1760e-222">***Opción B: Redacción y ejecución de una aplicación de varios contenedores***</span><span class="sxs-lookup"><span data-stu-id="1760e-222">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="1760e-223">En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios.</span><span class="sxs-lookup"><span data-stu-id="1760e-223">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="1760e-224">En estos casos, puede ejecutar el comando `docker-compose up` (figura 4-27), que utilizará el archivo docker-compose.yml que haya creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1760e-224">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="1760e-225">La ejecución de este comando implementa una aplicación compuesta con todos sus contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="1760e-225">Running this command deploys a composed application with all of its related containers.</span></span>

![Salida de consola del comando docker-compose up.](./media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="1760e-227">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="1760e-227">**Figure 4-27**.</span></span> <span data-ttu-id="1760e-228">Resultados de la ejecución del comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="1760e-228">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="1760e-229">Después de ejecutar `docker-compose up`, se implementa la aplicación y sus contenedores relacionados en el host de Docker, tal y como se muestra en la figura 4-28, en la representación de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="1760e-229">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Máquina virtual que ejecuta una aplicación de varios contenedores.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="1760e-231">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="1760e-231">**Figure 4-28**.</span></span> <span data-ttu-id="1760e-232">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="1760e-232">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="1760e-233">Paso 6: Prueba de la aplicación de Docker (localmente, en la máquina virtual de CD local)</span><span class="sxs-lookup"><span data-stu-id="1760e-233">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="1760e-234">Este paso varía en función de lo que haga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1760e-234">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="1760e-235">En "Hola mundo", una API web sencilla de .NET Core que se implementa como contenedor o servicio único, solo tiene que acceder al servicio facilitando el puerto TCP especificado en el DockerFile.</span><span class="sxs-lookup"><span data-stu-id="1760e-235">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="1760e-236">Si localhost no está activado, para navegar al servicio, busque la dirección IP de la máquina mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="1760e-236">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="1760e-237">En el host de Docker, abra un explorador y navegue a ese sitio; debe ver la aplicación o el servicio en ejecución, tal y como se muestra en la figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="1760e-237">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Vista de explorador de la respuesta de localhost/API/valores.](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="1760e-239">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="1760e-239">**Figure 4-29**.</span></span> <span data-ttu-id="1760e-240">Prueba de la aplicación de Docker en local con localhost</span><span class="sxs-lookup"><span data-stu-id="1760e-240">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="1760e-241">Tenga en cuenta que utiliza el puerto 80, pero internamente se redirige al puerto 5000, porque así es cómo se implementó con `docker run`, tal y como se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1760e-241">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="1760e-242">Puede realizar esta prueba con CURL desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="1760e-242">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="1760e-243">En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, tal y como se muestra en la figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="1760e-243">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Salida de consola de la obtención de http://10.0.75.1/API/values con CURL](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="1760e-245">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="1760e-245">**Figure 4-30**.</span></span> <span data-ttu-id="1760e-246">Prueba de una aplicación de Docker en local mediante CURL</span><span class="sxs-lookup"><span data-stu-id="1760e-246">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="1760e-247">**Depuración de un contenedor que se ejecuta en Docker**</span><span class="sxs-lookup"><span data-stu-id="1760e-247">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="1760e-248">Visual Studio Code admite la depuración de Docker si utiliza Node.js y otras plataformas como, por ejemplo, contenedores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1760e-248">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="1760e-249">También puede depurar contenedores de .NET Core o .NET Framework en Docker cuando se usa Visual Studio para Windows o Mac, tal y como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="1760e-249">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="1760e-250">Para más información sobre la depuración de contenedores de Docker de Node.js, consulte <https://blog.docker.com/2016/07/live-debugging-docker/> y <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span><span class="sxs-lookup"><span data-stu-id="1760e-250">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1760e-251">[Anterior](docker-apps-development-environment.md)
>[Siguiente](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="1760e-251">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
