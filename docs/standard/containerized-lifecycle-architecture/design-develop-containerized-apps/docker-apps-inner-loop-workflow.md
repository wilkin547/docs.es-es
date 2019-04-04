---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Obtenga información sobre el flujo de trabajo de "bucle interno" para el desarrollo de aplicaciones de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920914"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="3c759-103">Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker</span><span class="sxs-lookup"><span data-stu-id="3c759-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="3c759-104">Antes de desencadenar el flujo de trabajo del bucle exterior que abarca el DevOps completa del ciclo, todo comienza en el equipo de cada desarrollador, codificación de la propia aplicación, con sus lenguajes preferidos o plataformas y probarlo localmente (figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="3c759-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="3c759-105">Pero en todos los casos, tendrá un aspecto importante en común, con independencia de qué lenguaje, marco o plataformas elija.</span><span class="sxs-lookup"><span data-stu-id="3c759-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="3c759-106">En este flujo de trabajo específico, siempre desarrolla y prueba contenedores de Docker, pero localmente.</span><span class="sxs-lookup"><span data-stu-id="3c759-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Paso 1: código, ejecución y depuración](./media/image18.png)

<span data-ttu-id="3c759-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="3c759-108">**Figure 4-21**.</span></span> <span data-ttu-id="3c759-109">Contexto de desarrollo de bucle interno</span><span class="sxs-lookup"><span data-stu-id="3c759-109">Inner-loop development context</span></span>

<span data-ttu-id="3c759-110">El contenedor o la instancia de una imagen de Docker contiene estos componentes:</span><span class="sxs-lookup"><span data-stu-id="3c759-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="3c759-111">Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="3c759-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="3c759-112">Archivos agregados por el desarrollador (por ejemplo, archivos binarios de aplicación)</span><span class="sxs-lookup"><span data-stu-id="3c759-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="3c759-113">Configuración (por ejemplo, configuración del entorno y dependencias)</span><span class="sxs-lookup"><span data-stu-id="3c759-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="3c759-114">Instrucciones para los procesos que ejecutar docker</span><span class="sxs-lookup"><span data-stu-id="3c759-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="3c759-115">Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como el proceso (descrito en la sección siguiente).</span><span class="sxs-lookup"><span data-stu-id="3c759-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="3c759-116">Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluyen, ya que basta con hacerlo una vez.</span><span class="sxs-lookup"><span data-stu-id="3c759-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="3c759-117">Creación de una sola aplicación en un contenedor de Docker con Visual Studio Code y CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="3c759-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="3c759-118">Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).</span><span class="sxs-lookup"><span data-stu-id="3c759-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="3c759-119">Figura 4-22 muestra los pasos básicos que normalmente se necesitan para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.</span><span class="sxs-lookup"><span data-stu-id="3c759-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Información general del flujo de trabajo: Paso 1: código, paso 2: escribir Dockerfiles, paso 3: creación de imágenes definidas con Dockerfiles, paso 4: definir los servicios con el archivo docker-Compose, paso 5: ejecutar contenedores o aplicaciones compuestas, paso 6: prueba de aplicaciones, paso 7: de inserción para que comience el bucle exterior (canalizaciones de CI/CD) o continuar de veloping.](./media/image19.png)

<span data-ttu-id="3c759-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="3c759-121">**Figure 4-22**.</span></span> <span data-ttu-id="3c759-122">Flujo de trabajo de alto nivel para el ciclo de vida de aplicaciones de Docker en contenedor mediante la CLI de Docker</span><span class="sxs-lookup"><span data-stu-id="3c759-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="3c759-123">Paso 1: Empezar a programar en Visual Studio Code y crear la instantánea inicial de aplicación/servicio</span><span class="sxs-lookup"><span data-stu-id="3c759-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="3c759-124">La manera de desarrollar la aplicación es similar a la manera de que hacerlo sin Docker.</span><span class="sxs-lookup"><span data-stu-id="3c759-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="3c759-125">La diferencia es que durante el desarrollo, es implementar y probar su aplicación o servicios que se ejecutan dentro de contenedores de Docker que se colocan en su entorno local (por ejemplo, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="3c759-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

**<span data-ttu-id="3c759-126">Configurar el entorno local</span><span class="sxs-lookup"><span data-stu-id="3c759-126">Setting up your local environment</span></span>**

<span data-ttu-id="3c759-127">Con las últimas versiones de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.</span><span class="sxs-lookup"><span data-stu-id="3c759-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [! INFORMACIÓN]
>
> <span data-ttu-id="3c759-129">Para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="3c759-130">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="3c759-131">Además, necesitará un editor de código para que realmente puede desarrollar su aplicación a la vez mediante la CLI de Docker.</span><span class="sxs-lookup"><span data-stu-id="3c759-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="3c759-132">Microsoft proporciona código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [soporte para numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y más lenguajes modernos) [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="3c759-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="3c759-133">Este editor es una opción ideal para desarrolladores de Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="3c759-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="3c759-134">En Windows, también se puede usar la aplicación completa de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3c759-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [! INFORMACIÓN]
>
> <span data-ttu-id="3c759-136">Para obtener instrucciones sobre cómo instalar Visual Studio código para Windows, Mac o Linux, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="3c759-137">Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="3c759-138">También puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero con Visual Studio Code con la extensión Docker facilita la tarea al autor `Dockerfile` y `docker-compose.yml` archivos en el área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c759-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="3c759-139">También puede ejecutar las tareas y las secuencias de comandos del IDE de Visual Studio código para ejecutar comandos de Docker mediante la CLI de Docker debajo.</span><span class="sxs-lookup"><span data-stu-id="3c759-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="3c759-140">La extensión Docker para VS Code proporciona las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="3c759-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="3c759-141">Automática `Dockerfile` y `docker-compose.yml` generación de archivos</span><span class="sxs-lookup"><span data-stu-id="3c759-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="3c759-142">Sugerencias de sintaxis resaltado y mantenga el puntero para `docker-compose.yml` y `Dockerfile` archivos</span><span class="sxs-lookup"><span data-stu-id="3c759-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="3c759-143">IntelliSense (finalización) para `Dockerfile` y `docker-compose.yml` archivos</span><span class="sxs-lookup"><span data-stu-id="3c759-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="3c759-144">Detección de errores (errores y advertencias) para `Dockerfile` archivos</span><span class="sxs-lookup"><span data-stu-id="3c759-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="3c759-145">Integración de paleta (F1) para los comandos más comunes de Docker de comando</span><span class="sxs-lookup"><span data-stu-id="3c759-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="3c759-146">Integración del explorador para administrar imágenes y contenedores</span><span class="sxs-lookup"><span data-stu-id="3c759-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="3c759-147">Implementar imágenes de docker hub y Azure Container Registry en Azure App Service</span><span class="sxs-lookup"><span data-stu-id="3c759-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="3c759-148">Para instalar la extensión de Docker, presione Ctrl + Mayús + P, escriba `ext install`, y, a continuación, ejecute el comando de la extensión de instalación para que aparezca la lista de extensiones de Marketplace.</span><span class="sxs-lookup"><span data-stu-id="3c759-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="3c759-149">A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione la extensión de la compatibilidad con Docker, como se muestra en la figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="3c759-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Vista de la extensión Docker para VS Code.](./media/image20.png)

<span data-ttu-id="3c759-151">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="3c759-151">**Figure 4-23**.</span></span> <span data-ttu-id="3c759-152">Instalar la extensión de Docker en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3c759-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="3c759-153">Paso 2: Crear un DockerFile relacionado con una imagen existente (sin formato del sistema operativo o entornos de desarrollo como Ruby, Node.js y .NET Core)</span><span class="sxs-lookup"><span data-stu-id="3c759-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="3c759-154">Necesitará un `DockerFile` por una imagen personalizada que se crea y por contenedor para implementarse.</span><span class="sxs-lookup"><span data-stu-id="3c759-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="3c759-155">Si la aplicación se compone de un único servicio personalizado, necesitará una sola `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="3c759-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="3c759-156">Pero si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará una `Dockerfile` por servicio.</span><span class="sxs-lookup"><span data-stu-id="3c759-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="3c759-157">El `DockerFile` normalmente se coloca en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o servicio.</span><span class="sxs-lookup"><span data-stu-id="3c759-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="3c759-158">Puede crear su `DockerFile` y agréguelo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="3c759-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="3c759-159">Puede usar la extensión Docker para guiar al usar el `Dockerfile` y `docker-compose.yml` los archivos relacionados con los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="3c759-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="3c759-160">Finalmente, probablemente deberá escribir estos tipos de archivos sin esta herramienta, pero con la extensión de Docker es un buen punto de partida que acelerará la curva de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="3c759-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="3c759-161">En la figura 4-24, puede ver cómo docker-compose se agrega el archivo mediante la extensión Docker para VS Code.</span><span class="sxs-lookup"><span data-stu-id="3c759-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Vista de la consola de la extensión Docker para VS Code.](./media/image24.png)

<span data-ttu-id="3c759-163">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="3c759-163">**Figure 4-24**.</span></span> <span data-ttu-id="3c759-164">Archivos de docker que se agregan utilizando la **archivos de Docker de agregar al comando del área de trabajo**</span><span class="sxs-lookup"><span data-stu-id="3c759-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="3c759-165">Cuando se agrega un DockerFile, especificar qué imagen de Docker básica que va a usar (como el uso de `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="3c759-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="3c759-166">Normalmente, compilará la imagen personalizada sobre una imagen base que se obtiene desde cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como un [imágenes para .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) o la [para Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="3c759-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

***<span data-ttu-id="3c759-167">Use una imagen de Docker oficial existente</span><span class="sxs-lookup"><span data-stu-id="3c759-167">Use an existing official Docker image</span></span>***

<span data-ttu-id="3c759-168">Uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).</span><span class="sxs-lookup"><span data-stu-id="3c759-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="3c759-169">Este es un DockerFile de ejemplo para un contenedor de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="3c759-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="3c759-170">En este caso, la imagen se basa en la versión 2.1 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows), según la línea `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span><span class="sxs-lookup"><span data-stu-id="3c759-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span></span> <span data-ttu-id="3c759-171">(Para obtener más información acerca de este tema, consulte el [imagen de Docker de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) página y el [imagen de Docker de .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) página).</span><span class="sxs-lookup"><span data-stu-id="3c759-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="3c759-172">En el DockerFile, también puede indicar a Docker para escuchar el puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).</span><span class="sxs-lookup"><span data-stu-id="3c759-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="3c759-173">Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use.</span><span class="sxs-lookup"><span data-stu-id="3c759-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="3c759-174">Por ejemplo, el `ENTRYPOINT` línea con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker para ejecutar una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3c759-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="3c759-175">Si está usando el SDK y la CLI de .NET Core (`dotnet CLI`) para compilar y ejecutar la aplicación. NET, este valor sería diferente.</span><span class="sxs-lookup"><span data-stu-id="3c759-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="3c759-176">El punto clave aquí es que la línea ENTRYPOINT y otros valores de configuración dependen del lenguaje y plataforma que elija para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c759-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [! INFORMACIÓN]
>
> <span data-ttu-id="3c759-178">Para obtener más información sobre la creación de imágenes de Docker para aplicaciones .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="3c759-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="3c759-179">Para más información acerca de cómo crear sus propias imágenes, vaya a <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

**<span data-ttu-id="3c759-180">Usar repositorios de imágenes multiarquitectura</span><span class="sxs-lookup"><span data-stu-id="3c759-180">Use multi-arch image repositories</span></span>**

<span data-ttu-id="3c759-181">Un nombre de imagen única en un repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c759-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="3c759-182">Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows).</span><span class="sxs-lookup"><span data-stu-id="3c759-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="3c759-183">Por ejemplo, el [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repositorio disponible en el registro de Docker Hub proporciona compatibilidad para Linux y Windows Nano Server mediante el mismo nombre de imagen.</span><span class="sxs-lookup"><span data-stu-id="3c759-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="3c759-184">Extrayendo el [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) imagen desde un host de Windows extrae la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extrae la variante de Linux.</span><span class="sxs-lookup"><span data-stu-id="3c759-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

***<span data-ttu-id="3c759-185">Crear su imagen base desde cero</span><span class="sxs-lookup"><span data-stu-id="3c759-185">Create your base image from scratch</span></span>***

<span data-ttu-id="3c759-186">Puede crear su propia imagen de base de Docker desde cero como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker.</span><span class="sxs-lookup"><span data-stu-id="3c759-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="3c759-187">Este escenario es probablemente no lo mejor para usted si está empezando con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="3c759-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="3c759-188">Paso 3: Crear las imágenes de Docker personalizadas insertar su servicio en él</span><span class="sxs-lookup"><span data-stu-id="3c759-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="3c759-189">Para cada servicio personalizado que consta de la aplicación, deberá crear una imagen relacionada.</span><span class="sxs-lookup"><span data-stu-id="3c759-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="3c759-190">Si la aplicación se compone de un único servicio o aplicación web, necesitará una imagen de única.</span><span class="sxs-lookup"><span data-stu-id="3c759-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="3c759-191">Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso de compilación automatizada siempre que inserte el código fuente en un repositorio de Git (integración continua), por lo que las imágenes se crearán en el entorno global de su código fuente.</span><span class="sxs-lookup"><span data-stu-id="3c759-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="3c759-192">Pero antes de que se considere la posibilidad de ir a esa ruta de bucle externo, es necesario asegurarse de que la aplicación de Docker realmente funciona correctamente para que no inserción código que podría no funcionar correctamente en el sistema de control de código fuente (Git, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="3c759-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="3c759-193">Por lo tanto, cada desarrollador en primer lugar debe hacer todo el proceso de bucle interno para probar localmente y continuar desarrollando hasta que desean insertar una característica completa o cambio en el sistema de control de origen.</span><span class="sxs-lookup"><span data-stu-id="3c759-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="3c759-194">Para crear una imagen en su entorno local y mediante el DockerFile, puede usar el comando docker build, como se muestra en la figura 4-25 (también puede ejecutar `docker-compose up --build` para aplicaciones compuestas por varios contenedores y servicios).</span><span class="sxs-lookup"><span data-stu-id="3c759-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Salida de la consola de la compilación de docker-Compose, que muestra el progreso de descarga de imágenes.](./media/image25.png)

<span data-ttu-id="3c759-196">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="3c759-196">**Figure 4-25**.</span></span> <span data-ttu-id="3c759-197">Ejecuta la compilación de docker</span><span class="sxs-lookup"><span data-stu-id="3c759-197">Running docker build</span></span>

<span data-ttu-id="3c759-198">Opcionalmente, en lugar de ejecutar directamente `docker build` desde la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET que sea necesarias, mediante la ejecución `dotnet publish` comando y, a continuación, ejecute `docker build`.</span><span class="sxs-lookup"><span data-stu-id="3c759-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="3c759-199">Este ejemplo crea una imagen de Docker con el nombre `cesardl/netcore-webapi-microservice-docker:first` (`:first` es una etiqueta, como una versión específica).</span><span class="sxs-lookup"><span data-stu-id="3c759-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="3c759-200">Puede realizar este paso para cada imagen personalizada, deberá crear la aplicación de Docker compuesta con varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="3c759-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="3c759-201">Puede encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) utilizando el docker de comando de imágenes, como se muestra en la figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="3c759-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Salida de imágenes de docker de comando, que muestra las imágenes existentes en la consola.](./media/image26.png)

<span data-ttu-id="3c759-203">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="3c759-203">**Figure 4-26**.</span></span> <span data-ttu-id="3c759-204">Visualización de imágenes existente con imágenes de docker</span><span class="sxs-lookup"><span data-stu-id="3c759-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="3c759-205">Paso 4: Definir los servicios en docker-compose.yml al compilar una aplicación compuesta de Docker con varios servicios</span><span class="sxs-lookup"><span data-stu-id="3c759-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="3c759-206">Con el `docker-compose.yml` archivo, puede definir un conjunto de servicios relacionados para implementarse como una aplicación compuesta con los comandos de implementación se explica en la sección paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c759-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="3c759-207">Creación de ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener contenido similar al que se muestra en este `docker-compose.yml` archivo:</span><span class="sxs-lookup"><span data-stu-id="3c759-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="3c759-208">En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio redis (un servicio de caché popular).</span><span class="sxs-lookup"><span data-stu-id="3c759-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="3c759-209">Cada servicio se implementará como un contenedor, por lo que necesitamos utilizar una imagen de Docker concreta para cada uno.</span><span class="sxs-lookup"><span data-stu-id="3c759-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="3c759-210">Para este servicio web en particular, la imagen debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c759-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="3c759-211">Compilar desde el archivo DockerFile en el directorio actual</span><span class="sxs-lookup"><span data-stu-id="3c759-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="3c759-212">Reenviar el puerto 80 expuesto en el contenedor al puerto 81 en el equipo host</span><span class="sxs-lookup"><span data-stu-id="3c759-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="3c759-213">Montar el directorio del proyecto en el host a/Code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen</span><span class="sxs-lookup"><span data-stu-id="3c759-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="3c759-214">Vincular el servicio web para el servicio redis</span><span class="sxs-lookup"><span data-stu-id="3c759-214">Link the web service to the redis service</span></span>

<span data-ttu-id="3c759-215">El servicio redis usa el [imagen más reciente de redis pública](https://hub.docker.com/_/redis/) extrae del registro de Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="3c759-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="3c759-216">[Redis](https://redis.io/) es un sistema de caché populares para aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="3c759-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="3c759-217">Paso 5: Compilar y ejecutar la aplicación de Docker</span><span class="sxs-lookup"><span data-stu-id="3c759-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="3c759-218">Si la aplicación tiene solo un único contenedor, solo deberá ejecutarla mediante su implementación en el Host de Docker (máquina virtual o servidor físico).</span><span class="sxs-lookup"><span data-stu-id="3c759-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="3c759-219">Sin embargo, si la aplicación se compone de varios servicios, deberá *componerla*, demasiado.</span><span class="sxs-lookup"><span data-stu-id="3c759-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="3c759-220">Vamos a ver las distintas opciones.</span><span class="sxs-lookup"><span data-stu-id="3c759-220">Let's see the different options.</span></span>

***<span data-ttu-id="3c759-221">Opción A: Ejecutar un único contenedor o servicio</span><span class="sxs-lookup"><span data-stu-id="3c759-221">Option A: Run a single container or service</span></span>***

<span data-ttu-id="3c759-222">Puede ejecutar la imagen de Docker mediante el comando docker run, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="3c759-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="3c759-223">Para esta implementación concreta, se deberá redirigir las solicitudes enviadas al puerto 80 al puerto interno 5000.</span><span class="sxs-lookup"><span data-stu-id="3c759-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="3c759-224">Ahora la aplicación está escuchando en el puerto 80 en el nivel de host externo.</span><span class="sxs-lookup"><span data-stu-id="3c759-224">Now the application is listening on the external port 80 at the host level.</span></span>

***<span data-ttu-id="3c759-225">Opción B: Redactar y ejecutar una aplicación de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="3c759-225">Option B: Compose and run a multiple-container application</span></span>***

<span data-ttu-id="3c759-226">En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios.</span><span class="sxs-lookup"><span data-stu-id="3c759-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="3c759-227">En estos casos, puede ejecutar el `docker-compose up` comando (figura 4-27), que utilizará el archivo docker-compose.yml que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3c759-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="3c759-228">Ejecutar este comando implementa una aplicación compuesta con todos sus contenedores relacionados.</span><span class="sxs-lookup"><span data-stu-id="3c759-228">Running this command deploys a composed application with all of its related containers.</span></span>

![Salida de la consola el-comando docker compose up.](./media/image27.png)

<span data-ttu-id="3c759-230">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="3c759-230">**Figure 4-27**.</span></span> <span data-ttu-id="3c759-231">Resultados de ejecutar el comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="3c759-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="3c759-232">Después de ejecutar `docker-compose up`, implementar la aplicación y sus contenedores relacionados en el Host de Docker, como se muestra en la figura 4-28, en la representación de la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="3c759-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Máquina virtual que ejecuta aplicaciones de varios contenedores.](./media/image28.png)

<span data-ttu-id="3c759-234">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="3c759-234">**Figure 4-28**.</span></span> <span data-ttu-id="3c759-235">Máquina virtual con contenedores de Docker implementados</span><span class="sxs-lookup"><span data-stu-id="3c759-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="3c759-236">Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual local de CD)</span><span class="sxs-lookup"><span data-stu-id="3c759-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="3c759-237">Este paso variarán dependiendo de lo que hace la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c759-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="3c759-238">En un núcleo .NET simple "Hello World" implementar como un único contenedor o el servicio de Web API, solo sería necesario acceder al servicio proporcionando el puerto TCP especificado en el archivo DockerFile.</span><span class="sxs-lookup"><span data-stu-id="3c759-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="3c759-239">Si localhost no está activado, para navegar a su servicio, busque la dirección IP para la máquina mediante este comando:</span><span class="sxs-lookup"><span data-stu-id="3c759-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="3c759-240">En el host de Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio que se está ejecutando, como se muestra en la figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="3c759-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Vista del explorador de la respuesta de localhost/API/values.](./media/image29.png)

<span data-ttu-id="3c759-242">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="3c759-242">**Figure 4-29**.</span></span> <span data-ttu-id="3c759-243">Probar la aplicación de Docker local mediante localhost</span><span class="sxs-lookup"><span data-stu-id="3c759-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="3c759-244">Tenga en cuenta que está utilizando el puerto 80, pero internamente se redirige al puerto 5000, ya que es cómo se implementó con `docker run`, tal y como se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3c759-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="3c759-245">Puede probar esto con CURL desde el terminal.</span><span class="sxs-lookup"><span data-stu-id="3c759-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="3c759-246">En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="3c759-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Salida de la introducción de la consola la http://10.0.75.1/API/values con curl](./media/image30.png)

<span data-ttu-id="3c759-248">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="3c759-248">**Figure 4-30**.</span></span> <span data-ttu-id="3c759-249">Probar una aplicación de Docker localmente mediante CURL</span><span class="sxs-lookup"><span data-stu-id="3c759-249">Testing a Docker application locally by using CURL</span></span>

**<span data-ttu-id="3c759-250">Depuración de un contenedor que se ejecutan en Docker</span><span class="sxs-lookup"><span data-stu-id="3c759-250">Debugging a container running on Docker</span></span>**

<span data-ttu-id="3c759-251">Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como contenedores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3c759-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="3c759-252">También se pueden depurar contenedores .NET Core o .NET Framework en Docker cuando se usa Visual Studio para Windows o Mac, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c759-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [! INFORMACIÓN]
>
> <span data-ttu-id="3c759-254">Para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span><span class="sxs-lookup"><span data-stu-id="3c759-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3c759-255">[Anterior](docker-apps-development-environment.md)
>[Siguiente](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="3c759-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
