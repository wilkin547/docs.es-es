---
title: 'Introducción a las imágenes de Docker: .NET Core'
description: Obtenga información sobre cómo usar las imágenes de Docker de .NET Core publicadas desde el registro de Docker. También aprenderá cómo extraer imágenes y crear sus propias imágenes.
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 34ff6ce7d990412fa0ac4896d1e2e39b307681f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145837"
---
# <a name="learn-about-docker-images-for-net-core"></a><span data-ttu-id="65be0-104">Obtener información sobre imágenes de Docker para .NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-104">Learn about Docker images for .NET Core</span></span>

<span data-ttu-id="65be0-105">Este tutorial se centra en cómo usar .NET Core en Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="65be0-106">En primer lugar se analizan las distintas imágenes de Docker que ofrece y mantiene Microsoft, además de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="65be0-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="65be0-107">Luego se aprende a compilar una aplicación de ASP.NET Core y a aplicarle Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="65be0-108">Este tutorial ayuda a:</span><span class="sxs-lookup"><span data-stu-id="65be0-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="65be0-109">Obtener información sobre las imágenes de Microsoft .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="65be0-110">Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="65be0-111">Ejecutar la aplicación de ejemplo de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="65be0-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="65be0-112">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="65be0-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="65be0-113">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="65be0-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="65be0-114">Optimizaciones de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-114">Docker Image Optimizations</span></span>

<span data-ttu-id="65be0-115">Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="65be0-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="65be0-116">Imágenes usadas para desarrollar aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="65be0-117">Imágenes usadas para crear aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="65be0-118">Imágenes usadas para ejecutar aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="65be0-119">¿Por qué tres imágenes?</span><span class="sxs-lookup"><span data-stu-id="65be0-119">Why three images?</span></span>
<span data-ttu-id="65be0-120">Al desarrollar, compilar y ejecutar aplicaciones en contenedor, hay prioridades diferentes.</span><span class="sxs-lookup"><span data-stu-id="65be0-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="65be0-121">**Desarrollo:** la prioridad se centra en la iteración rápida de los cambios y en la posibilidad de depurarlos.</span><span class="sxs-lookup"><span data-stu-id="65be0-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="65be0-122">El tamaño de la imagen no es tan importante; lo que importa es si se pueden hacer cambios en el código y verlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="65be0-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="65be0-123">**Compilación:** esta imagen contiene todo lo necesario para compilar la aplicación, lo que incluye el compilador y las demás dependencias para optimizar los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="65be0-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="65be0-124">La imagen de compilación se usa para crear los recursos que se colocan en una imagen de producción.</span><span class="sxs-lookup"><span data-stu-id="65be0-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="65be0-125">La imagen de compilación se usaría para la integración continua, o en un entorno de compilación.</span><span class="sxs-lookup"><span data-stu-id="65be0-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="65be0-126">Este enfoque permite a un agente de compilación compilar y generar la aplicación (con todas las dependencias necesarias) en una instancia de imagen de compilación.</span><span class="sxs-lookup"><span data-stu-id="65be0-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="65be0-127">El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="65be0-128">**Producción:** velocidad a la que puede implementar e iniciar la imagen.</span><span class="sxs-lookup"><span data-stu-id="65be0-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="65be0-129">Esta imagen es pequeña, así que el rendimiento de red desde el Registro de Docker hasta los hosts de Docker está optimizado.</span><span class="sxs-lookup"><span data-stu-id="65be0-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="65be0-130">El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="65be0-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="65be0-131">En el modelo de Docker no se necesita compilación de código dinámico.</span><span class="sxs-lookup"><span data-stu-id="65be0-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="65be0-132">El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65be0-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="65be0-133">Por ejemplo, la salida `dotnet publish` contiene:</span><span class="sxs-lookup"><span data-stu-id="65be0-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="65be0-134">los archivos binarios compilados</span><span class="sxs-lookup"><span data-stu-id="65be0-134">the compiled binaries</span></span>
    * <span data-ttu-id="65be0-135">archivos .js y .css</span><span class="sxs-lookup"><span data-stu-id="65be0-135">.js and .css files</span></span>


<span data-ttu-id="65be0-136">La razón para incluir la salida del comando `dotnet publish` en la imagen de producción es mantener su tamaño al mínimo.</span><span class="sxs-lookup"><span data-stu-id="65be0-136">The reason to include the `dotnet publish` command output in your production image is to keep its size to a minimum.</span></span>

<span data-ttu-id="65be0-137">Algunas imágenes de .NET Core comparten capas entre diferentes etiquetas, de modo que la descarga de la última etiqueta es un proceso relativamente ligero.</span><span class="sxs-lookup"><span data-stu-id="65be0-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="65be0-138">Si ya tiene una versión anterior en el equipo, esta arquitectura reduce el espacio en disco necesario.</span><span class="sxs-lookup"><span data-stu-id="65be0-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="65be0-139">Cuando varias aplicaciones usan imágenes comunes en el mismo equipo, la memoria se comparte entre las imágenes comunes.</span><span class="sxs-lookup"><span data-stu-id="65be0-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="65be0-140">Las imágenes deben ser las mismas para poder compartirse.</span><span class="sxs-lookup"><span data-stu-id="65be0-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="65be0-141">Variantes de imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-141">Docker image variations</span></span>

<span data-ttu-id="65be0-142">Para lograr los objetivos anteriores, en [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) se proporcionan variantes de imágenes.</span><span class="sxs-lookup"><span data-stu-id="65be0-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="65be0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`): esta imagen contiene el SDK de .NET Core, que incluye .NET Core y las herramientas de línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="65be0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="65be0-144">Esta imagen se asigna al **escenario de desarrollo**.</span><span class="sxs-lookup"><span data-stu-id="65be0-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="65be0-145">Esta imagen se usa para el desarrollo local, la depuración y las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="65be0-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="65be0-146">Esta imagen también puede usarse en sus escenarios de **compilación**.</span><span class="sxs-lookup"><span data-stu-id="65be0-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="65be0-147">Al usar `microsoft/dotnet:sdk` siempre se obtiene la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="65be0-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="65be0-148">Si no está seguro de sus necesidades, se recomienda usar la imagen `microsoft/dotnet:<version>-sdk`.</span><span class="sxs-lookup"><span data-stu-id="65be0-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="65be0-149">Como imagen "de facto", se ha diseñado para usarse como contenedor desechable (monte el código fuente e inicie el contenedor para iniciar la aplicación) y como imagen base para compilar otras imágenes.</span><span class="sxs-lookup"><span data-stu-id="65be0-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="65be0-150">`microsoft/dotnet:<version>-runtime`: esta imagen contiene .NET Core (runtime y bibliotecas) y está optimizada para ejecutar aplicaciones de .NET Core en **producción**.</span><span class="sxs-lookup"><span data-stu-id="65be0-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="65be0-151">Imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="65be0-151">Alternative images</span></span>

<span data-ttu-id="65be0-152">Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:</span><span class="sxs-lookup"><span data-stu-id="65be0-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="65be0-153">`microsoft/dotnet:<version>-runtime-deps`: la imagen de **dependencias en tiempo de ejecución** contiene el sistema operativo con todas las dependencias nativas que necesita .NET Core.</span><span class="sxs-lookup"><span data-stu-id="65be0-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="65be0-154">Esta imagen es para [aplicaciones autocontenidas](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="65be0-154">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="65be0-155">Versiones más recientes de cada variante:</span><span class="sxs-lookup"><span data-stu-id="65be0-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="65be0-156">`microsoft/dotnet` o `microsoft/dotnet:latest` (alias para la imagen del SDK)</span><span class="sxs-lookup"><span data-stu-id="65be0-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="65be0-157">Ejemplos para examinar</span><span class="sxs-lookup"><span data-stu-id="65be0-157">Samples to explore</span></span>

* <span data-ttu-id="65be0-158">[En este ejemplo de Docker de ASP.NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) se muestra un patrón de prácticas recomendadas para compilar imágenes de Docker para aplicaciones de ASP.NET Core para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="65be0-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="65be0-159">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="65be0-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="65be0-160">En este ejemplo de Docker de .NET Core se muestra un patrón de prácticas recomendadas para [compilar imágenes de Docker para aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span><span class="sxs-lookup"><span data-stu-id="65be0-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span></span>

## <a name="forward-the-request-scheme-and-original-ip-address"></a><span data-ttu-id="65be0-161">Reenvío de un esquema de solicitud y una dirección IP original</span><span class="sxs-lookup"><span data-stu-id="65be0-161">Forward the request scheme and original IP address</span></span>

<span data-ttu-id="65be0-162">Los servidores proxy, los equilibradores de carga y otros dispositivos de red con frecuencia ocultan información sobre una solicitud antes de que llegue a la aplicación en contenedor:</span><span class="sxs-lookup"><span data-stu-id="65be0-162">Proxy servers, load balancers, and other network appliances often obscure information about a request before it reaches the containerized app:</span></span>

* <span data-ttu-id="65be0-163">Cuando las solicitudes HTTPS se redirigen mediante proxy a través de HTTP, el esquema original (HTTPS) se pierde y se debe reenviar en un encabezado.</span><span class="sxs-lookup"><span data-stu-id="65be0-163">When HTTPS requests are proxied over HTTP, the original scheme (HTTPS) is lost and must be forwarded in a header.</span></span>
* <span data-ttu-id="65be0-164">Como una aplicación recibe una solicitud del proxy y no desde su verdadero origen en Internet o la red corporativa, la dirección IP del cliente original también se debe reenviar en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="65be0-164">Because an app receives a request from the proxy and not its true source on the Internet or corporate network, the original client IP address must also be forwarded in a header.</span></span>

<span data-ttu-id="65be0-165">Esta información puede ser importante en el procesamiento de las solicitudes, por ejemplo, en los redireccionamientos, la autenticación, la generación de vínculos, la evaluación de directivas y la geolocalización del cliente.</span><span class="sxs-lookup"><span data-stu-id="65be0-165">This information may be important in request processing, for example in redirects, authentication, link generation, policy evaluation, and client geolocation.</span></span>

<span data-ttu-id="65be0-166">Para reenviar el esquema y la dirección IP original a una aplicación de ASP.NET Core en contenedores, use el middleware Forwarded Headers.</span><span class="sxs-lookup"><span data-stu-id="65be0-166">To forward the scheme and original IP address to a containerized ASP.NET Core app, use Forwarded Headers Middleware.</span></span> <span data-ttu-id="65be0-167">Para más información, vea [Configurar ASP.NET Core para trabajar con servidores proxy y equilibradores de carga](/aspnet/core/host-and-deploy/proxy-load-balancer).</span><span class="sxs-lookup"><span data-stu-id="65be0-167">For more information, see [Configure ASP.NET Core to work with proxy servers and load balancers](/aspnet/core/host-and-deploy/proxy-load-balancer).</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="65be0-168">Primera aplicación de ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-168">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="65be0-169">En este tutorial se usa una aplicación de ejemplo de ASP.NET Core Docker para la aplicación a la que se va a aplicar Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-169">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="65be0-170">En esta aplicación de ejemplo de ASP.NET Core Docker se muestra un patrón de procedimientos recomendados para compilar imágenes de Docker para aplicaciones de ASP.NET Core para producción.</span><span class="sxs-lookup"><span data-stu-id="65be0-170">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="65be0-171">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="65be0-171">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="65be0-172">El Dockerfile de ejemplo crea una imagen de Docker de aplicación de ASP.NET Core basada en la imagen base de Docker de runtime de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="65be0-172">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="65be0-173">Usa la [característica de compilación de varias fases de Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) para:</span><span class="sxs-lookup"><span data-stu-id="65be0-173">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="65be0-174">compilar el ejemplo en un contenedor en función de la **mayor** imagen base de Docker de compilación de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-174">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="65be0-175">copiar el resultado de la compilación final en una imagen de Docker en función de la **menor** imagen base de Docker de runtime de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65be0-175">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="65be0-176">La imagen de compilación contiene las herramientas necesarias para compilar aplicaciones, mientras que la imagen de runtime no.</span><span class="sxs-lookup"><span data-stu-id="65be0-176">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="65be0-177">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="65be0-177">Prerequisites</span></span>

<span data-ttu-id="65be0-178">Para compilar y ejecutar, instale los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="65be0-178">To build and run, install the following items:</span></span>

#### <a name="net-core-21-sdk"></a><span data-ttu-id="65be0-179">SDK de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="65be0-179">.NET Core 2.1 SDK</span></span>

* <span data-ttu-id="65be0-180">Instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="65be0-180">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="65be0-181">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="65be0-181">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="65be0-182">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="65be0-182">Need to install a code editor?</span></span> <span data-ttu-id="65be0-183">Pruebe [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="65be0-183">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="65be0-184">Instalación del cliente Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-184">Installing Docker Client</span></span>

<span data-ttu-id="65be0-185">Instale la versión [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-185">Install [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="65be0-186">El cliente Docker se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="65be0-186">The Docker client can be installed in:</span></span>

* <span data-ttu-id="65be0-187">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="65be0-187">Linux distributions</span></span>

   * [<span data-ttu-id="65be0-188">CentOS</span><span class="sxs-lookup"><span data-stu-id="65be0-188">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="65be0-189">Debian</span><span class="sxs-lookup"><span data-stu-id="65be0-189">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="65be0-190">Fedora</span><span class="sxs-lookup"><span data-stu-id="65be0-190">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="65be0-191">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="65be0-191">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="65be0-192">macOS</span><span class="sxs-lookup"><span data-stu-id="65be0-192">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="65be0-193">[Windows](https://docs.docker.com/docker-for-windows/install/).</span><span class="sxs-lookup"><span data-stu-id="65be0-193">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="65be0-194">Instalación de Git para el repositorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="65be0-194">Installing Git for sample repository</span></span>

* <span data-ttu-id="65be0-195">Instale [git](https://git-scm.com/download) si quiere clonar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="65be0-195">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="65be0-196">Obtención de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="65be0-196">Getting the sample application</span></span>

<span data-ttu-id="65be0-197">La manera más sencilla de obtener el ejemplo es clonar el [repositorio de .NET Core Docker](https://github.com/dotnet/dotnet-docker) con git, mediante las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="65be0-197">The easiest way to get the sample is by cloning the [.NET Core Docker repository](https://github.com/dotnet/dotnet-docker) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker
```

<span data-ttu-id="65be0-198">También puede descargar el repositorio (es pequeño) como un archivo zip desde el repositorio de .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-198">You can also download the repository (it is small) as a zip from the .NET Core Docker repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="65be0-199">Ejecutar la aplicación de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="65be0-199">Run the ASP.NET app locally</span></span>

<span data-ttu-id="65be0-200">Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.</span><span class="sxs-lookup"><span data-stu-id="65be0-200">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="65be0-201">Puede compilar y ejecutar la aplicación en local con el SDK de .NET Core 2.1 mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="65be0-201">You can build and run the application locally with the .NET Core 2.1 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

<span data-ttu-id="65be0-202">Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="65be0-202">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="65be0-203">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="65be0-203">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="65be0-204">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Linux mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="65be0-204">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="65be0-205">El argumento `docker run` "-p" asigna el puerto 5000 del equipo local al puerto 80 del contenedor (el formato de asignación de puerto es `host:container`).</span><span class="sxs-lookup"><span data-stu-id="65be0-205">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="65be0-206">Para más información, vea la referencia [docker run](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65be0-206">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="65be0-207">Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="65be0-207">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="65be0-208">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="65be0-208">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="65be0-209">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Windows mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="65be0-209">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="65be0-210">Si usa contenedores de Windows, debe ir a la **dirección IP del contenedor** (en lugar de `http://localhost`) en el explorador directamente.</span><span class="sxs-lookup"><span data-stu-id="65be0-210">You must navigate to the **container IP address** (as opposed to `http://localhost`) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="65be0-211">Puede obtener la dirección IP del contenedor con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="65be0-211">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="65be0-212">Abra otro símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="65be0-212">Open up another command prompt.</span></span>
* <span data-ttu-id="65be0-213">Ejecute `docker ps` para ver los contenedores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="65be0-213">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="65be0-214">El contenedor "aspnetcore_sample" debería estar ahí.</span><span class="sxs-lookup"><span data-stu-id="65be0-214">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="65be0-215">Ejecute `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="65be0-215">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="65be0-216">Copie la dirección IP del contenedor y péguela en el explorador (por ejemplo, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="65be0-216">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="65be0-217">La ejecución de Docker admite la identificación de contenedores con nombre o hash.</span><span class="sxs-lookup"><span data-stu-id="65be0-217">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="65be0-218">En el ejemplo se usa el nombre (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="65be0-218">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="65be0-219">Vea el siguiente ejemplo de cómo obtener la dirección IP de un contenedor de Windows en ejecución.</span><span class="sxs-lookup"><span data-stu-id="65be0-219">See the following example of how to get the IP address of a running Windows container.</span></span>

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

> [!NOTE]
> <span data-ttu-id="65be0-220">La ejecución de Docker ejecuta un comando nuevo en un contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="65be0-220">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="65be0-221">Para más información, vea la referencia [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65be0-221">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="65be0-222">Puede crear una aplicación lista para implementarse en producción localmente mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="65be0-222">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> <span data-ttu-id="65be0-223">El argumento de versión -c compila la aplicación en modo de versión (el valor predeterminado es el modo de depuración).</span><span class="sxs-lookup"><span data-stu-id="65be0-223">The -c Release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="65be0-224">Para más información, vea la referencia [dotnet run](../tools/dotnet-run.md) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="65be0-224">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="65be0-225">Puede ejecutar la aplicación en **Windows** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="65be0-225">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="65be0-226">Puede ejecutar la aplicación en **Linux** o **macOS** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="65be0-226">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="65be0-227">Imágenes de Docker usadas en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="65be0-227">Docker Images used in this sample</span></span>

<span data-ttu-id="65be0-228">En el dockerfile de este ejemplo se usan las siguientes imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="65be0-228">The following Docker images are used in this sample's dockerfile.</span></span>

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

<span data-ttu-id="65be0-229">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="65be0-229">Congratulations!</span></span> <span data-ttu-id="65be0-230">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="65be0-230">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="65be0-231">Obtener información sobre las imágenes de Microsoft .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-231">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="65be0-232">Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker</span><span class="sxs-lookup"><span data-stu-id="65be0-232">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="65be0-233">Ejecutar la aplicación de ejemplo de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="65be0-233">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="65be0-234">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="65be0-234">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="65be0-235">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="65be0-235">Built and ran the sample with Docker for Windows containers</span></span>

<span data-ttu-id="65be0-236">**Pasos siguientes**</span><span class="sxs-lookup"><span data-stu-id="65be0-236">**Next Steps**</span></span>

<span data-ttu-id="65be0-237">Estos son algunos de los pasos que puede realizar a continuación:</span><span class="sxs-lookup"><span data-stu-id="65be0-237">Here are some next steps you can take:</span></span>

* <span data-ttu-id="65be0-238">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)</span><span class="sxs-lookup"><span data-stu-id="65be0-238">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="65be0-239">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="65be0-239">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* [<span data-ttu-id="65be0-240">Depuración con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="65be0-240">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* <span data-ttu-id="65be0-241">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Información práctica sobre Visual Studio para Mac, contenedores y código sin servidor en la nube)</span><span class="sxs-lookup"><span data-stu-id="65be0-241">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)</span></span>
* <span data-ttu-id="65be0-242">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Introducción a Docker y Visual Studio para Mac Lab)</span><span class="sxs-lookup"><span data-stu-id="65be0-242">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!NOTE]
> <span data-ttu-id="65be0-243">Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="65be0-243">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
