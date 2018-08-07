---
title: Creación de imágenes de Docker de .NET Core
description: Descripción de las imágenes de Docker y .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e48a263334ebb93a5d281032336aeb4073d8467c
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2018
ms.locfileid: "34827344"
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="639b6-103">Creación de imágenes de Docker para aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="639b6-104">Este tutorial se centra en cómo usar .NET Core en Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="639b6-105">En primer lugar se analizan las distintas imágenes de Docker que ofrece y mantiene Microsoft, además de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="639b6-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="639b6-106">Luego se aprende a compilar una aplicación de ASP.NET Core y a aplicarle Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="639b6-107">Este tutorial ayuda a:</span><span class="sxs-lookup"><span data-stu-id="639b6-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="639b6-108">Obtener información sobre las imágenes de Microsoft .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="639b6-109">Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="639b6-110">Ejecutar la aplicación de ejemplo de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="639b6-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="639b6-111">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="639b6-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="639b6-112">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="639b6-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="639b6-113">Optimizaciones de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-113">Docker Image Optimizations</span></span>

<span data-ttu-id="639b6-114">Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="639b6-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="639b6-115">Imágenes usadas para desarrollar aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="639b6-116">Imágenes usadas para crear aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="639b6-117">Imágenes usadas para ejecutar aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="639b6-118">¿Por qué tres imágenes?</span><span class="sxs-lookup"><span data-stu-id="639b6-118">Why three images?</span></span>
<span data-ttu-id="639b6-119">Al desarrollar, compilar y ejecutar aplicaciones en contenedor, hay prioridades diferentes.</span><span class="sxs-lookup"><span data-stu-id="639b6-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="639b6-120">**Desarrollo:** la prioridad se centra en la iteración rápida de los cambios y en la posibilidad de depurarlos.</span><span class="sxs-lookup"><span data-stu-id="639b6-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="639b6-121">El tamaño de la imagen no es tan importante; lo que importa es si se pueden hacer cambios en el código y verlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="639b6-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="639b6-122">**Compilación:** esta imagen contiene todo lo necesario para compilar la aplicación, lo que incluye el compilador y las demás dependencias para optimizar los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="639b6-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="639b6-123">La imagen de compilación se usa para crear los recursos que se colocan en una imagen de producción.</span><span class="sxs-lookup"><span data-stu-id="639b6-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="639b6-124">La imagen de compilación se usaría para la integración continua, o en un entorno de compilación.</span><span class="sxs-lookup"><span data-stu-id="639b6-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="639b6-125">Este enfoque permite a un agente de compilación compilar y generar la aplicación (con todas las dependencias necesarias) en una instancia de imagen de compilación.</span><span class="sxs-lookup"><span data-stu-id="639b6-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="639b6-126">El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="639b6-127">**Producción:** velocidad a la que puede implementar e iniciar la imagen.</span><span class="sxs-lookup"><span data-stu-id="639b6-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="639b6-128">Esta imagen es pequeña, así que el rendimiento de red desde el Registro de Docker hasta los hosts de Docker está optimizado.</span><span class="sxs-lookup"><span data-stu-id="639b6-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="639b6-129">El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="639b6-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="639b6-130">En el modelo de Docker no se necesita compilación de código dinámico.</span><span class="sxs-lookup"><span data-stu-id="639b6-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="639b6-131">El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="639b6-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="639b6-132">Por ejemplo, la salida `dotnet publish` contiene:</span><span class="sxs-lookup"><span data-stu-id="639b6-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="639b6-133">los archivos binarios compilados</span><span class="sxs-lookup"><span data-stu-id="639b6-133">the compiled binaries</span></span>
    * <span data-ttu-id="639b6-134">archivos .js y .css</span><span class="sxs-lookup"><span data-stu-id="639b6-134">.js and .css files</span></span>


<span data-ttu-id="639b6-135">La razón para incluir la salida del comando `dotnet publish` en la imagen de producción es mantener su tamaño al mínimo.</span><span class="sxs-lookup"><span data-stu-id="639b6-135">The reason to include the `dotnet publish` command output in your production image is to keep its size to a minimum.</span></span>

<span data-ttu-id="639b6-136">Algunas imágenes de .NET Core comparten capas entre diferentes etiquetas, de modo que la descarga de la última etiqueta es un proceso relativamente ligero.</span><span class="sxs-lookup"><span data-stu-id="639b6-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="639b6-137">Si ya tiene una versión anterior en el equipo, esta arquitectura reduce el espacio en disco necesario.</span><span class="sxs-lookup"><span data-stu-id="639b6-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="639b6-138">Cuando varias aplicaciones usan imágenes comunes en el mismo equipo, la memoria se comparte entre las imágenes comunes.</span><span class="sxs-lookup"><span data-stu-id="639b6-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="639b6-139">Las imágenes deben ser las mismas para poder compartirse.</span><span class="sxs-lookup"><span data-stu-id="639b6-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="639b6-140">Variantes de imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-140">Docker image variations</span></span>

<span data-ttu-id="639b6-141">Para lograr los objetivos anteriores, en [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) se proporcionan variantes de imágenes.</span><span class="sxs-lookup"><span data-stu-id="639b6-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="639b6-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`): esta imagen contiene el SDK de .NET Core, que incluye .NET Core y las herramientas de línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="639b6-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.1-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="639b6-143">Esta imagen se asigna al **escenario de desarrollo**.</span><span class="sxs-lookup"><span data-stu-id="639b6-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="639b6-144">Esta imagen se usa para el desarrollo local, la depuración y las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="639b6-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="639b6-145">Esta imagen también puede usarse en sus escenarios de **compilación**.</span><span class="sxs-lookup"><span data-stu-id="639b6-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="639b6-146">Al usar `microsoft/dotnet:sdk` siempre se obtiene la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="639b6-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="639b6-147">Si no está seguro de sus necesidades, se recomienda usar la imagen `microsoft/dotnet:<version>-sdk`.</span><span class="sxs-lookup"><span data-stu-id="639b6-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="639b6-148">Como imagen "de facto", se ha diseñado para usarse como contenedor desechable (monte el código fuente e inicie el contenedor para iniciar la aplicación) y como imagen base para compilar otras imágenes.</span><span class="sxs-lookup"><span data-stu-id="639b6-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="639b6-149">`microsoft/dotnet:<version>-runtime`: esta imagen contiene .NET Core (runtime y bibliotecas) y está optimizada para ejecutar aplicaciones de .NET Core en **producción**.</span><span class="sxs-lookup"><span data-stu-id="639b6-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="639b6-150">Imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="639b6-150">Alternative images</span></span>

<span data-ttu-id="639b6-151">Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:</span><span class="sxs-lookup"><span data-stu-id="639b6-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="639b6-152">`microsoft/dotnet:<version>-runtime-deps`: la imagen de **dependencias en tiempo de ejecución** contiene el sistema operativo con todas las dependencias nativas que necesita .NET Core.</span><span class="sxs-lookup"><span data-stu-id="639b6-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="639b6-153">Esta imagen es para [aplicaciones autocontenidas](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="639b6-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="639b6-154">Versiones más recientes de cada variante:</span><span class="sxs-lookup"><span data-stu-id="639b6-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="639b6-155">`microsoft/dotnet` o `microsoft/dotnet:latest` (alias para la imagen del SDK)</span><span class="sxs-lookup"><span data-stu-id="639b6-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="639b6-156">Ejemplos para examinar</span><span class="sxs-lookup"><span data-stu-id="639b6-156">Samples to explore</span></span>

* <span data-ttu-id="639b6-157">[En este ejemplo de Docker de ASP.NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) se muestra un patrón de prácticas recomendadas para compilar imágenes de Docker para aplicaciones de ASP.NET Core para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="639b6-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker/tree/master/samples/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="639b6-158">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="639b6-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="639b6-159">En este ejemplo de Docker de .NET Core se muestra un patrón de prácticas recomendadas para [compilar imágenes de Docker para aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span><span class="sxs-lookup"><span data-stu-id="639b6-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker/tree/master/samples/dotnetapp)</span></span>

## <a name="forward-the-request-scheme-and-original-ip-address"></a><span data-ttu-id="639b6-160">Reenvío de un esquema de solicitud y una dirección IP original</span><span class="sxs-lookup"><span data-stu-id="639b6-160">Forward the request scheme and original IP address</span></span>

<span data-ttu-id="639b6-161">Los servidores proxy, los equilibradores de carga y otros dispositivos de red con frecuencia ocultan información sobre una solicitud antes de que llegue a la aplicación en contenedor:</span><span class="sxs-lookup"><span data-stu-id="639b6-161">Proxy servers, load balancers, and other network appliances often obscure information about a request before it reaches the containerized app:</span></span>

* <span data-ttu-id="639b6-162">Cuando las solicitudes HTTPS se redirigen mediante proxy a través de HTTP, el esquema original (HTTPS) se pierde y se debe reenviar en un encabezado.</span><span class="sxs-lookup"><span data-stu-id="639b6-162">When HTTPS requests are proxied over HTTP, the original scheme (HTTPS) is lost and must be forwarded in a header.</span></span>
* <span data-ttu-id="639b6-163">Como una aplicación recibe una solicitud del proxy y no desde su verdadero origen en Internet o la red corporativa, la dirección IP del cliente original también se debe reenviar en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="639b6-163">Because an app receives a request from the proxy and not its true source on the Internet or corporate network, the original client IP address must also be forwarded in a header.</span></span>

<span data-ttu-id="639b6-164">Esta información puede ser importante en el procesamiento de las solicitudes, por ejemplo, en los redireccionamientos, la autenticación, la generación de vínculos, la evaluación de directivas y la geolocalización del cliente.</span><span class="sxs-lookup"><span data-stu-id="639b6-164">This information may be important in request processing, for example in redirects, authentication, link generation, policy evaluation, and client geolocation.</span></span>

<span data-ttu-id="639b6-165">Para reenviar el esquema y la dirección IP original a una aplicación de ASP.NET Core en contenedores, use el middleware Forwarded Headers.</span><span class="sxs-lookup"><span data-stu-id="639b6-165">To forward the scheme and original IP address to a containerized ASP.NET Core app, use Forwarded Headers Middleware.</span></span> <span data-ttu-id="639b6-166">Para más información, vea [Configurar ASP.NET Core para trabajar con servidores proxy y equilibradores de carga](/aspnet/core/host-and-deploy/proxy-load-balancer).</span><span class="sxs-lookup"><span data-stu-id="639b6-166">For more information, see [Configure ASP.NET Core to work with proxy servers and load balancers](/aspnet/core/host-and-deploy/proxy-load-balancer).</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="639b6-167">Primera aplicación de ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-167">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="639b6-168">En este tutorial se usa una aplicación de ejemplo de ASP.NET Core Docker para la aplicación a la que se va a aplicar Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-168">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="639b6-169">En esta aplicación de ejemplo de ASP.NET Core Docker se muestra un patrón de procedimientos recomendados para compilar imágenes de Docker para aplicaciones de ASP.NET Core para producción.</span><span class="sxs-lookup"><span data-stu-id="639b6-169">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="639b6-170">El ejemplo funciona con contenedores de Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="639b6-170">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="639b6-171">El Dockerfile de ejemplo crea una imagen de Docker de aplicación de ASP.NET Core basada en la imagen base de Docker de runtime de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="639b6-171">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="639b6-172">Usa la [característica de compilación de varias fases de Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) para:</span><span class="sxs-lookup"><span data-stu-id="639b6-172">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="639b6-173">compilar el ejemplo en un contenedor en función de la **mayor** imagen base de Docker de compilación de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-173">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="639b6-174">copiar el resultado de la compilación final en una imagen de Docker en función de la **menor** imagen base de Docker de runtime de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="639b6-174">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="639b6-175">La imagen de compilación contiene las herramientas necesarias para compilar aplicaciones, mientras que la imagen de runtime no.</span><span class="sxs-lookup"><span data-stu-id="639b6-175">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="639b6-176">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="639b6-176">Prerequisites</span></span>

<span data-ttu-id="639b6-177">Para compilar y ejecutar, instale los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="639b6-177">To build and run, install the following items:</span></span>

#### <a name="net-core-21-sdk"></a><span data-ttu-id="639b6-178">SDK de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="639b6-178">.NET Core 2.1 SDK</span></span>

* <span data-ttu-id="639b6-179">Instale el [SDK de .NET Core 2.1](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="639b6-179">Install [.NET Core SDK 2.1](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="639b6-180">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="639b6-180">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="639b6-181">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="639b6-181">Need to install a code editor?</span></span> <span data-ttu-id="639b6-182">Pruebe [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="639b6-182">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="639b6-183">Instalación del cliente Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-183">Installing Docker Client</span></span>

<span data-ttu-id="639b6-184">Instale la versión [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) o posterior del cliente Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-184">Install [Docker 18.03](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="639b6-185">El cliente Docker se puede instalar en:</span><span class="sxs-lookup"><span data-stu-id="639b6-185">The Docker client can be installed in:</span></span>

* <span data-ttu-id="639b6-186">Distribuciones de Linux</span><span class="sxs-lookup"><span data-stu-id="639b6-186">Linux distributions</span></span>

   * [<span data-ttu-id="639b6-187">CentOS</span><span class="sxs-lookup"><span data-stu-id="639b6-187">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="639b6-188">Debian</span><span class="sxs-lookup"><span data-stu-id="639b6-188">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="639b6-189">Fedora</span><span class="sxs-lookup"><span data-stu-id="639b6-189">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="639b6-190">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="639b6-190">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="639b6-191">macOS</span><span class="sxs-lookup"><span data-stu-id="639b6-191">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="639b6-192">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="639b6-192">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="639b6-193">Instalación de Git para el repositorio de ejemplo</span><span class="sxs-lookup"><span data-stu-id="639b6-193">Installing Git for sample repository</span></span>

* <span data-ttu-id="639b6-194">Instale [git](https://git-scm.com/download) si quiere clonar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="639b6-194">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="639b6-195">Obtención de la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="639b6-195">Getting the sample application</span></span>

<span data-ttu-id="639b6-196">La manera más sencilla de obtener el ejemplo es clonar el [repositorio de .NET Core Docker](https://github.com/dotnet/dotnet-docker) con git, mediante las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="639b6-196">The easiest way to get the sample is by cloning the [.NET Core Docker repository](https://github.com/dotnet/dotnet-docker) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker
```

<span data-ttu-id="639b6-197">También puede descargar el repositorio (es pequeño) como un archivo zip desde el repositorio de .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-197">You can also download the repository (it is small) as a zip from the .NET Core Docker repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="639b6-198">Ejecutar la aplicación de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="639b6-198">Run the ASP.NET app locally</span></span>

<span data-ttu-id="639b6-199">Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.</span><span class="sxs-lookup"><span data-stu-id="639b6-199">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="639b6-200">Puede compilar y ejecutar la aplicación en local con el SDK de .NET Core 2.1 mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="639b6-200">You can build and run the application locally with the .NET Core 2.1 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located
cd aspnetapp // project scope

dotnet run
```

<span data-ttu-id="639b6-201">Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="639b6-201">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="639b6-202">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="639b6-202">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="639b6-203">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Linux mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="639b6-203">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="639b6-204">El argumento `docker run` "-p" asigna el puerto 5000 del equipo local al puerto 80 del contenedor (el formato de asignación de puerto es `host:container`).</span><span class="sxs-lookup"><span data-stu-id="639b6-204">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="639b6-205">Para más información, vea la referencia [docker run](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="639b6-205">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="639b6-206">Una vez iniciada la aplicación, visite **http://localhost:5000** en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="639b6-206">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="639b6-207">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="639b6-207">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="639b6-208">Puede compilar y ejecutar el ejemplo en Docker con contenedores de Windows mediante los comandos siguientes (las instrucciones presuponen la raíz del repositorio):</span><span class="sxs-lookup"><span data-stu-id="639b6-208">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd dotnet-docker
cd samples
cd aspnetapp // solution scope where the dockerfile is located

docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="639b6-209">Si usa contenedores de Windows, debe ir a la **dirección IP del contenedor** (en lugar de http://localhost)) en el explorador directamente.</span><span class="sxs-lookup"><span data-stu-id="639b6-209">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="639b6-210">Puede obtener la dirección IP del contenedor con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="639b6-210">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="639b6-211">Abra otro símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="639b6-211">Open up another command prompt.</span></span>
* <span data-ttu-id="639b6-212">Ejecute `docker ps` para ver los contenedores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="639b6-212">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="639b6-213">El contenedor "aspnetcore_sample" debería estar ahí.</span><span class="sxs-lookup"><span data-stu-id="639b6-213">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="639b6-214">Ejecute `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="639b6-214">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="639b6-215">Copie la dirección IP del contenedor y péguela en el explorador (por ejemplo, 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="639b6-215">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="639b6-216">La ejecución de Docker admite la identificación de contenedores con nombre o hash.</span><span class="sxs-lookup"><span data-stu-id="639b6-216">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="639b6-217">En el ejemplo se usa el nombre (aspnetcore_sample).</span><span class="sxs-lookup"><span data-stu-id="639b6-217">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="639b6-218">Vea el siguiente ejemplo de cómo obtener la dirección IP de un contenedor de Windows en ejecución.</span><span class="sxs-lookup"><span data-stu-id="639b6-218">See the following example of how to get the IP address of a running Windows container.</span></span>

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
> <span data-ttu-id="639b6-219">La ejecución de Docker ejecuta un comando nuevo en un contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="639b6-219">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="639b6-220">Para más información, vea la referencia [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="639b6-220">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="639b6-221">Puede crear una aplicación lista para implementarse en producción localmente mediante el comando [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="639b6-221">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c Release -o published
```

> [!NOTE]
> <span data-ttu-id="639b6-222">El argumento de versión -c compila la aplicación en modo de versión (el valor predeterminado es el modo de depuración).</span><span class="sxs-lookup"><span data-stu-id="639b6-222">The -c Release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="639b6-223">Para más información, vea la referencia [dotnet run](../tools/dotnet-run.md) en los parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="639b6-223">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="639b6-224">Puede ejecutar la aplicación en **Windows** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="639b6-224">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="639b6-225">Puede ejecutar la aplicación en **Linux** o **macOS** mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="639b6-225">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="639b6-226">Imágenes de Docker usadas en este ejemplo</span><span class="sxs-lookup"><span data-stu-id="639b6-226">Docker Images used in this sample</span></span>

<span data-ttu-id="639b6-227">En el dockerfile de este ejemplo se usan las siguientes imágenes de Docker.</span><span class="sxs-lookup"><span data-stu-id="639b6-227">The following Docker images are used in this sample's dockerfile.</span></span>

* `microsoft/dotnet:2.1-sdk`
* `microsoft/dotnet:2.1-aspnetcore-runtime`

<span data-ttu-id="639b6-228">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="639b6-228">Congratulations!</span></span> <span data-ttu-id="639b6-229">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="639b6-229">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="639b6-230">Obtener información sobre las imágenes de Microsoft .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-230">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="639b6-231">Obtener una aplicación de ejemplo de ASP.NET Core para aplicarle Docker</span><span class="sxs-lookup"><span data-stu-id="639b6-231">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="639b6-232">Ejecutar la aplicación de ejemplo de ASP.NET en local</span><span class="sxs-lookup"><span data-stu-id="639b6-232">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="639b6-233">Compilar y ejecutar el ejemplo con contenedores de Docker para Linux</span><span class="sxs-lookup"><span data-stu-id="639b6-233">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="639b6-234">Compilar y ejecutar el ejemplo con contenedores de Docker para Windows</span><span class="sxs-lookup"><span data-stu-id="639b6-234">Built and ran the sample with Docker for Windows containers</span></span>

<span data-ttu-id="639b6-235">**Pasos siguientes**</span><span class="sxs-lookup"><span data-stu-id="639b6-235">**Next Steps**</span></span>

<span data-ttu-id="639b6-236">Estos son algunos de los pasos que puede realizar a continuación:</span><span class="sxs-lookup"><span data-stu-id="639b6-236">Here are some next steps you can take:</span></span>

* <span data-ttu-id="639b6-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)</span><span class="sxs-lookup"><span data-stu-id="639b6-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="639b6-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="639b6-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>
* [<span data-ttu-id="639b6-239">Depuración con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="639b6-239">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* <span data-ttu-id="639b6-240">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Información práctica sobre Visual Studio para Mac, contenedores y código sin servidor en la nube)</span><span class="sxs-lookup"><span data-stu-id="639b6-240">[Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)</span></span>
* <span data-ttu-id="639b6-241">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Introducción a Docker y Visual Studio para Mac Lab)</span><span class="sxs-lookup"><span data-stu-id="639b6-241">[Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)</span></span>

> [!NOTE]
> <span data-ttu-id="639b6-242">Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="639b6-242">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
