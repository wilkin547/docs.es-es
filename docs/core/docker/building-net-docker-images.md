---
title: "Creación de imágenes de Docker de .NET Core"
description: "Descripción de las imágenes de Docker y .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="0a21e-104">Creación de imágenes de Docker para aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0a21e-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="0a21e-105">En este tutorial se centra en cómo usar .NET Core en Docker.</span><span class="sxs-lookup"><span data-stu-id="0a21e-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="0a21e-106">En primer lugar, exploramos las distintas imágenes de Docker ofrece y mantenido por Microsoft y casos de uso.</span><span class="sxs-lookup"><span data-stu-id="0a21e-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="0a21e-107">A continuación, se Aprenda a crear y dockerize una aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0a21e-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="0a21e-108">En el transcurso de este tutorial, aprenderá:</span><span class="sxs-lookup"><span data-stu-id="0a21e-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="0a21e-109">Obtenga información acerca de las imágenes de Docker de núcleo de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="0a21e-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="0a21e-110">Obtener un núcleo de ASP.NET de la aplicación de ejemplo para Dockerize</span><span class="sxs-lookup"><span data-stu-id="0a21e-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="0a21e-111">Ejecutar la aplicación de ejemplo ASP.NET localmente</span><span class="sxs-lookup"><span data-stu-id="0a21e-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="0a21e-112">Compilar y ejecutar el ejemplo con Docker para contenedores de Linux</span><span class="sxs-lookup"><span data-stu-id="0a21e-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="0a21e-113">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="0a21e-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="0a21e-114">Optimizaciones de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="0a21e-114">Docker Image Optimizations</span></span>

<span data-ttu-id="0a21e-115">Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="0a21e-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="0a21e-116">Imágenes usadas para desarrollar aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="0a21e-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="0a21e-117">Imágenes usadas para crear aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="0a21e-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="0a21e-118">Imágenes usadas para ejecutar aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0a21e-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="0a21e-119">¿Por qué tres imágenes?</span><span class="sxs-lookup"><span data-stu-id="0a21e-119">Why three images?</span></span>
<span data-ttu-id="0a21e-120">Al desarrollar, compilar y ejecutar aplicaciones en contenedores, se tengan diferentes prioridades.</span><span class="sxs-lookup"><span data-stu-id="0a21e-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="0a21e-121">**Desarrollo:** los enfoques de prioridad en iteración rápidamente cambios y la capacidad para depurar los cambios.</span><span class="sxs-lookup"><span data-stu-id="0a21e-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="0a21e-122">El tamaño de la imagen no es tan importante, en su lugar puede hacer cambios en el código y verlas rápidamente?</span><span class="sxs-lookup"><span data-stu-id="0a21e-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="0a21e-123">**La compilación:** esta imagen contiene todo lo necesario para compilar la aplicación, que incluye el compilador y las otras dependencias al optimizar los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="0a21e-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="0a21e-124">Usar la imagen de compilación para crear los activos que se colocan en una imagen de producción.</span><span class="sxs-lookup"><span data-stu-id="0a21e-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="0a21e-125">La imagen de la compilación se usaría para la integración continua, o en un entorno de compilación.</span><span class="sxs-lookup"><span data-stu-id="0a21e-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="0a21e-126">Este enfoque permite a un agente de compilación compilar y generar la aplicación (con todas las dependencias necesarias) en una instancia de la imagen de compilación.</span><span class="sxs-lookup"><span data-stu-id="0a21e-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="0a21e-127">El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="0a21e-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="0a21e-128">**Producción:** rapidez puede implementar e iniciar la imagen?</span><span class="sxs-lookup"><span data-stu-id="0a21e-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="0a21e-129">Esta imagen es pequeña, por lo que se optimiza el rendimiento de la red desde el registro de Docker para los hosts de Docker.</span><span class="sxs-lookup"><span data-stu-id="0a21e-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="0a21e-130">El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="0a21e-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="0a21e-131">Compilación de código dinámico no se necesita en el modelo de Docker.</span><span class="sxs-lookup"><span data-stu-id="0a21e-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="0a21e-132">El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0a21e-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="0a21e-133">Por ejemplo, el `dotnet publish` salida contiene:</span><span class="sxs-lookup"><span data-stu-id="0a21e-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="0a21e-134">los archivos binarios compilados</span><span class="sxs-lookup"><span data-stu-id="0a21e-134">the compiled binaries</span></span>
    * <span data-ttu-id="0a21e-135">archivos .js y .css</span><span class="sxs-lookup"><span data-stu-id="0a21e-135">.js and .css files</span></span>


<span data-ttu-id="0a21e-136">La razón para incluir el `dotnet publish` resultado del comando en la imagen de producción es mantener su ' tamaño al mínimo.</span><span class="sxs-lookup"><span data-stu-id="0a21e-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="0a21e-137">Algunas imágenes de .NET Core compartan capas entre diferentes etiquetas para descargar la última etiqueta es un proceso relativamente ligero.</span><span class="sxs-lookup"><span data-stu-id="0a21e-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="0a21e-138">Si ya tiene una versión anterior en su equipo, esta arquitectura reduce el espacio en disco necesario.</span><span class="sxs-lookup"><span data-stu-id="0a21e-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="0a21e-139">Cuando varias aplicaciones usan imágenes comunes en el mismo equipo, la memoria se comparte entre las imágenes comunes.</span><span class="sxs-lookup"><span data-stu-id="0a21e-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="0a21e-140">Las imágenes deben ser las mismas que se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="0a21e-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="0a21e-141">Variantes de imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="0a21e-141">Docker image variations</span></span>

<span data-ttu-id="0a21e-142">Para lograr los objetivos anteriores, proporcionamos variantes de imagen en [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="0a21e-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="0a21e-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Esta imagen contiene el núcleo de .NET SDK, que incluye el núcleo de .NET y herramientas de línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="0a21e-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="0a21e-144">Esta imagen se asigna al **escenario de desarrollo**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="0a21e-145">Usar esta imagen para el desarrollo local, depuración y pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="0a21e-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="0a21e-146">Esta imagen también puede usarse en sus escenarios de **compilación**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="0a21e-147">Usar `microsoft/dotnet:sdk` siempre obtendrá la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="0a21e-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="0a21e-148">Si no está seguro acerca de sus necesidades, desea utilizar la `microsoft/dotnet:<version>-sdk` imagen.</span><span class="sxs-lookup"><span data-stu-id="0a21e-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="0a21e-149">Como la imagen "de facto", se ha diseñado para utilizarse como throw contenedor alejada (montar el código fuente e iniciar el contenedor para iniciar la aplicación) y como la imagen base para generar otras imágenes de.</span><span class="sxs-lookup"><span data-stu-id="0a21e-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="0a21e-150">`microsoft/dotnet:<version>-runtime`: Esta imagen contiene el núcleo de .NET (en tiempo de ejecución y bibliotecas) y está optimizada para ejecutar aplicaciones de .NET Core **producción**.</span><span class="sxs-lookup"><span data-stu-id="0a21e-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="0a21e-151">Imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="0a21e-151">Alternative images</span></span>

<span data-ttu-id="0a21e-152">Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:</span><span class="sxs-lookup"><span data-stu-id="0a21e-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="0a21e-153">`microsoft/dotnet:<version>-runtime-deps`: La **en tiempo de ejecución depós** imagen contiene el sistema operativo con todas las dependencias nativo necesarios .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0a21e-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="0a21e-154">Esta imagen es para [aplicaciones independientes](https://docs.microsoft.com/dotnet/core/deploying/index).</span><span class="sxs-lookup"><span data-stu-id="0a21e-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="0a21e-155">Versiones más recientes de cada variante:</span><span class="sxs-lookup"><span data-stu-id="0a21e-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="0a21e-156">`microsoft/dotnet`o `microsoft/dotnet:latest` (alias para la imagen SDK)</span><span class="sxs-lookup"><span data-stu-id="0a21e-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="0a21e-157">Ejemplos para explorar</span><span class="sxs-lookup"><span data-stu-id="0a21e-157">Samples to explore</span></span>

* <span data-ttu-id="0a21e-158">[Este ejemplo de ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para ASP.NET Core aplicaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="0a21e-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="0a21e-159">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="0a21e-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="0a21e-160">Este ejemplo de .NET Core Docker muestra un patrón de prácticas recomendado para [crear imágenes de Docker para las aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="0a21e-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="0a21e-161">La primera aplicación de ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="0a21e-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="0a21e-162">Para este tutorial, permite usar una aplicación de ejemplo de ASP.NET Core Docker para la aplicación que deseamos dockerize.</span><span class="sxs-lookup"><span data-stu-id="0a21e-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="0a21e-163">Esta aplicación de ejemplo de ASP.NET Core Docker muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para ASP.NET Core aplicaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="0a21e-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="0a21e-164">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="0a21e-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="0a21e-165">El ejemplo Dockerfile crea una imagen de Docker de aplicación de ASP.NET Core basada fuera de la imagen de base de Docker en tiempo de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0a21e-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="0a21e-166">Usa el [varias fases de Docker generar la característica](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) para:</span><span class="sxs-lookup"><span data-stu-id="0a21e-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="0a21e-167">Genere el ejemplo en un contenedor en función de la **mayor** imagen base de Docker de compilación de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0a21e-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="0a21e-168">copia el resultado de compilación final en una imagen de Docker basada en la **menor** imagen base de tiempo de ejecución de ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="0a21e-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="0a21e-169">La imagen de la compilación contiene las herramientas necesarias para crear aplicaciones, mientras que la imagen en tiempo de ejecución no.</span><span class="sxs-lookup"><span data-stu-id="0a21e-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="0a21e-170">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0a21e-170">Prerequisites</span></span>

<span data-ttu-id="0a21e-171">Para compilar y ejecutar, instale los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="0a21e-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="0a21e-172">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="0a21e-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="0a21e-173">Instalar [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="0a21e-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="0a21e-174">Instale al editor de código favoritos, si no lo ha hecho ya.</span><span class="sxs-lookup"><span data-stu-id="0a21e-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="0a21e-175">¿Es necesario instalar a un editor de código?</span><span class="sxs-lookup"><span data-stu-id="0a21e-175">Need to install a code editor?</span></span> <span data-ttu-id="0a21e-176">Intente [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="0a21e-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="0a21e-177">Instalación de cliente de Docker</span><span class="sxs-lookup"><span data-stu-id="0a21e-177">Installing Docker Client</span></span>

<span data-ttu-id="0a21e-178">Instalar [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) u otra posterior del cliente.</span><span class="sxs-lookup"><span data-stu-id="0a21e-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="0a21e-179">El cliente se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="0a21e-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="0a21e-180">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="0a21e-180">Linux distributions</span></span>

   * [<span data-ttu-id="0a21e-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="0a21e-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="0a21e-182">Debian</span><span class="sxs-lookup"><span data-stu-id="0a21e-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="0a21e-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="0a21e-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="0a21e-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="0a21e-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="0a21e-185">macOS</span><span class="sxs-lookup"><span data-stu-id="0a21e-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="0a21e-186">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="0a21e-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="0a21e-187">Instalación de Git para el repositorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a21e-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="0a21e-188">Instalar [git](https://git-scm.com/download) si desea clonar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="0a21e-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="0a21e-189">Obtiene la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a21e-189">Getting the sample application</span></span>

<span data-ttu-id="0a21e-190">Es la manera más fácil de obtener el ejemplo mediante la clonación de la [repositorio de ejemplos](https://github.com/dotnet/dotnet-docker-samples) con git, mediante las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0a21e-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="0a21e-191">También puede descargar el repositorio (es pequeño) como un archivo zip del repositorio de ejemplos de .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="0a21e-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="0a21e-192">Ejecutar la aplicación ASP.NET localmente</span><span class="sxs-lookup"><span data-stu-id="0a21e-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="0a21e-193">Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.</span><span class="sxs-lookup"><span data-stu-id="0a21e-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="0a21e-194">Puede compilar y ejecutar la aplicación localmente con el SDK de .NET Core 2.0 utilizando los comandos siguientes (las instrucciones presupone la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="0a21e-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="0a21e-195">Tras iniciar la aplicación, visite **http://localhost: 5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="0a21e-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="0a21e-196">Compilar y ejecutar el ejemplo con Docker para contenedores de Linux</span><span class="sxs-lookup"><span data-stu-id="0a21e-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="0a21e-197">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Linux utilizando los comandos siguientes (las instrucciones presupone la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="0a21e-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="0a21e-198">El `docker run` '-p' argumento asignaciones de puerto 5000 en el equipo local al puerto 80 del contenedor (la forma de asignación de puerto es `host:container`).</span><span class="sxs-lookup"><span data-stu-id="0a21e-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="0a21e-199">Para obtener más información, consulte el [docker ejecutar](https://docs.docker.com/engine/reference/commandline/exec/) referencia en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0a21e-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="0a21e-200">Tras iniciar la aplicación, visite **http://localhost: 5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="0a21e-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="0a21e-201">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="0a21e-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="0a21e-202">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Windows mediante los comandos siguientes (las instrucciones presupone la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="0a21e-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="0a21e-203">Debe ir a la **dirección IP del contenedor** (en lugar de http://localhost) en el explorador directamente al utilizar los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="0a21e-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="0a21e-204">Puede obtener la dirección IP del contenedor con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a21e-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="0a21e-205">Abra el símbolo del otro.</span><span class="sxs-lookup"><span data-stu-id="0a21e-205">Open up another command prompt.</span></span>
* <span data-ttu-id="0a21e-206">Ejecute `docker ps` para ver los contenedores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a21e-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="0a21e-207">El contenedor "aspnetcore_sample" debería existir.</span><span class="sxs-lookup"><span data-stu-id="0a21e-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="0a21e-208">Ejecute `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="0a21e-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="0a21e-209">Copie la dirección IP del contenedor y pegue en el explorador (por ejemplo, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="0a21e-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="0a21e-210">Ejecución de docker es compatible con contenedores de identificación con nombre o hash.</span><span class="sxs-lookup"><span data-stu-id="0a21e-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="0a21e-211">En nuestro ejemplo, se utiliza el nombre (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="0a21e-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="0a21e-212">Vea el siguiente ejemplo de cómo obtener la dirección IP de un contenedor de Windows en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a21e-212">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> <span data-ttu-id="0a21e-213">Ejecución de docker ejecuta un comando nuevo en un contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a21e-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="0a21e-214">Para obtener más información, consulte el [referencia de docker exec](https://docs.docker.com/engine/reference/commandline/exec/) en parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0a21e-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="0a21e-215">Puede generar una aplicación que está lista para implementarse en producción localmente mediante el [publicar dotnet](../tools/dotnet-publish.md) comando.</span><span class="sxs-lookup"><span data-stu-id="0a21e-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="0a21e-216">El argumento de versión - c compila la aplicación en modo de lanzamiento (el valor predeterminado es el modo de depuración).</span><span class="sxs-lookup"><span data-stu-id="0a21e-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="0a21e-217">Para obtener más información, consulte el [referencia de run dotnet](../tools/dotnet-run.md) en parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0a21e-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="0a21e-218">Puede ejecutar la aplicación en **Windows** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0a21e-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="0a21e-219">Puede ejecutar la aplicación en **Linux** o **macOS** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="0a21e-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="0a21e-220">Imágenes de docker que se utilizan en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a21e-220">Docker Images used in this sample</span></span>

<span data-ttu-id="0a21e-221">Las siguientes imágenes de Docker se usan en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a21e-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="0a21e-222">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="0a21e-222">Congratulations!</span></span> <span data-ttu-id="0a21e-223">simplemente deberá:</span><span class="sxs-lookup"><span data-stu-id="0a21e-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="0a21e-224">Aprender acerca de las imágenes de Docker de núcleo de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="0a21e-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="0a21e-225">Tiene un núcleo de ASP.NET de aplicación de ejemplo para Dockerize</span><span class="sxs-lookup"><span data-stu-id="0a21e-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="0a21e-226">Se ejecutó la aplicación de ejemplo ASP.NET localmente</span><span class="sxs-lookup"><span data-stu-id="0a21e-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="0a21e-227">Compila y se ejecutó el ejemplo con Docker para contenedores de Linux</span><span class="sxs-lookup"><span data-stu-id="0a21e-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="0a21e-228">Compila y se ejecutó el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="0a21e-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="0a21e-229">**Pasos siguientes**</span><span class="sxs-lookup"><span data-stu-id="0a21e-229">**Next Steps**</span></span>

<span data-ttu-id="0a21e-230">Aquí le mostramos algunos procedimientos que puede realizar:</span><span class="sxs-lookup"><span data-stu-id="0a21e-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="0a21e-231">Trabajar con herramientas de Docker de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a21e-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="0a21e-232">Implementación de imágenes de Docker desde el registro de contenedor de Azure a las instancias de contenedor de Azure</span><span class="sxs-lookup"><span data-stu-id="0a21e-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="0a21e-233">Depuración con el código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a21e-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="0a21e-234">Obtener las manos con Visual Studio para Mac, contenedores y el código sin servidor en la nube</span><span class="sxs-lookup"><span data-stu-id="0a21e-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="0a21e-235">Introducción a Docker y Visual Studio para Mac laboratorio</span><span class="sxs-lookup"><span data-stu-id="0a21e-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="0a21e-236">Si no tiene una suscripción de Azure, [Regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para una cuenta gratuita de 30 días y get 200 dólares en créditos de Azure para probar cualquier combinación de los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="0a21e-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
