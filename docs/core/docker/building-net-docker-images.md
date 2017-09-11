---
title: "Creación de imágenes de Docker de .NET Core"
description: "Descripción de las imágenes de Docker y .NET Core"
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: es-es
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="a4703-104">Creación de imágenes de Docker para aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4703-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="a4703-105">En estos momentos, estamos actualizando para .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="a4703-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="a4703-106">Las instrucciones siguientes están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="a4703-106">The instructions below are out of date.</span></span> <span data-ttu-id="a4703-107">Lamentamos las molestias.</span><span class="sxs-lookup"><span data-stu-id="a4703-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="a4703-108">Para ver una descripción de cómo usar .NET Core y Docker juntos, primero debemos conocer las diferentes imágenes de Docker que se ofrecen y cuándo es mejor usar cada una.</span><span class="sxs-lookup"><span data-stu-id="a4703-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="a4703-109">Aquí examinaremos las variantes ofrecidas, compilaremos una API web ASP.NET Core, usaremos las herramientas de Yeoman Docker para crear un contenedor depurable y echaremos un vistazo a cómo Visual Studio Code puede ayudar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a4703-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="a4703-110">Optimizaciones de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="a4703-110">Docker Image Optimizations</span></span>

<span data-ttu-id="a4703-111">Al crear imágenes de Docker para desarrolladores, nos centramos en tres escenarios principales:</span><span class="sxs-lookup"><span data-stu-id="a4703-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="a4703-112">Imágenes usadas para desarrollar aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4703-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="a4703-113">Imágenes usadas para crear aplicaciones .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4703-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="a4703-114">Imágenes usadas para ejecutar aplicaciones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a4703-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="a4703-115">¿Por qué tres imágenes?</span><span class="sxs-lookup"><span data-stu-id="a4703-115">Why three images?</span></span>
<span data-ttu-id="a4703-116">Al desarrollar, compilar y ejecutar aplicaciones en contenedor, tenemos prioridades diferentes.</span><span class="sxs-lookup"><span data-stu-id="a4703-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="a4703-117">**Desarrollo:** la rapidez con que se pueden iterar los cambios y la posibilidad de depurar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a4703-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="a4703-118">El tamaño de la imagen no es tan importante, sino que pueda hacer cambios en el código y verlos rápidamente.</span><span class="sxs-lookup"><span data-stu-id="a4703-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="a4703-119">Algunas de las herramientas, como [yo docker](https://aka.ms/yodocker), disponibles para usarlas en Visual Studio Code emplean esta imagen durante la fase de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a4703-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="a4703-120">**Compilación:** lo que es necesario para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="a4703-121">Esto incluye el compilador y cualquier otra dependencia para optimizar los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="a4703-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="a4703-122">Esta imagen no es la imagen que se implementa, sino más bien una imagen que se utiliza para compilar el contenido que se coloca en una imagen de producción.</span><span class="sxs-lookup"><span data-stu-id="a4703-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="a4703-123">Esta imagen se usaría de la integración continua o el entorno de compilación.</span><span class="sxs-lookup"><span data-stu-id="a4703-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="a4703-124">Por ejemplo, en lugar de instalar todas las dependencias directamente en un agente de compilación, el agente de compilación crearía una instancia de una imagen de compilación para compilar la aplicación con todas las dependencias necesarias para compilar la aplicación contenida en la imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="a4703-125">El agente de compilación solo necesita saber cómo ejecutar la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="a4703-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="a4703-126">**Producción:** la rapidez con que puede implementar e iniciar la imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="a4703-127">Esta imagen es pequeña, por lo que puede desplazarse rápidamente a través de la red desde el Registro a los hosts de Docker.</span><span class="sxs-lookup"><span data-stu-id="a4703-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="a4703-128">El contenido está listo para ejecutar, lo que permite el tiempo más rápido desde la ejecución de Docker hasta el procesamiento de los resultados.</span><span class="sxs-lookup"><span data-stu-id="a4703-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="a4703-129">En el modelo de Docker inmutable, no hay ninguna necesidad de compilación dinámica del código.</span><span class="sxs-lookup"><span data-stu-id="a4703-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="a4703-130">El contenido que se coloca en esta imagen estaría limitado a los archivos binarios y al contenido necesario para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="a4703-131">Por ejemplo, el resultado publicado mediante `dotnet publish` que contiene los archivos binarios compilados, imágenes y archivos .js y .css.</span><span class="sxs-lookup"><span data-stu-id="a4703-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="a4703-132">Con el tiempo, verá imágenes que contienen paquetes anteriores a la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="a4703-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="a4703-133">Aunque hay varias versiones de la imagen de .NET Core, comparten una o varias capas.</span><span class="sxs-lookup"><span data-stu-id="a4703-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="a4703-134">La cantidad de espacio en disco necesario para almacenar o la diferencia para extraer del Registro es mucho menor que la totalidad porque todas las imágenes comparten la misma capa base y posiblemente otras.</span><span class="sxs-lookup"><span data-stu-id="a4703-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="a4703-135">Variantes de imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="a4703-135">Docker image variations</span></span>

<span data-ttu-id="a4703-136">Para lograr los objetivos anteriores, proporcionamos variantes de imágenes en [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="a4703-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="a4703-137">`microsoft/dotnet:<version>-sdk`: esta es **microsoft/dotnet:1.0.0-preview2-sdk**. Esta imagen contiene el SDK de .NET Core que incluye .NET Core y las herramientas de línea de comandos (CLI).</span><span class="sxs-lookup"><span data-stu-id="a4703-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="a4703-138">Esta imagen se asigna al **escenario de desarrollo**.</span><span class="sxs-lookup"><span data-stu-id="a4703-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="a4703-139">Esta imagen se usaría para el desarrollo, la depuración y las pruebas unitarias locales.</span><span class="sxs-lookup"><span data-stu-id="a4703-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="a4703-140">Por ejemplo, todo el desarrollo realizado antes de proteger el código.</span><span class="sxs-lookup"><span data-stu-id="a4703-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="a4703-141">Esta imagen también puede usarse en sus escenarios de **compilación**.</span><span class="sxs-lookup"><span data-stu-id="a4703-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="a4703-142">`microsoft/dotnet:<version>-core` : esta es **microsoft/dotnet:1.0.0-core**, que ejecuta aplicaciones [.NET Core portátiles](../deploying/index.md) y está optimizada para ejecutar la aplicación en **producción**.</span><span class="sxs-lookup"><span data-stu-id="a4703-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="a4703-143">No contiene el SDK y tiene como fin tomar la salida optimizada de `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="a4703-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="a4703-144">El tiempo de ejecución portátil es ideal para escenarios de contenedor de Docker dado que la ejecución de varios contenedores se beneficia de las capas de imágenes compartidas.</span><span class="sxs-lookup"><span data-stu-id="a4703-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="a4703-145">Imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="a4703-145">Alternative images</span></span>

<span data-ttu-id="a4703-146">Además de los escenarios optimizados de desarrollo, compilación y producción, proporcionamos imágenes adicionales:</span><span class="sxs-lookup"><span data-stu-id="a4703-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="a4703-147">`microsoft/dotnet:<version>-onbuild`: esta es **microsoft/dotnet:1.0.0-preview2-onbuild**, que contiene desencadenadores [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild).</span><span class="sxs-lookup"><span data-stu-id="a4703-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="a4703-148">La compilación [COPIA](https://docs.docker.com/engine/reference/builder/#/copy) la aplicación, ejecuta `dotnet restore` y crea una instrucción [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` para ejecutar la aplicación cuando se ejecuta la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="a4703-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="a4703-149">Aunque no es una imagen optimizada para producción, algunos pueden encontrarla útil para copiar simplemente su código fuente en una imagen y ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="a4703-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="a4703-150">`microsoft/dotnet:<version>-core-deps`: esta es **microsoft/dotnet:1.0.0-core-deps**. Si desea ejecutar aplicaciones autocontenidas, use esta imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="a4703-151">Contiene el sistema operativo con todas las dependencias nativas necesarias en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4703-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="a4703-152">Esta imagen también puede usarse como base para sus propias compilaciones CoreFX o CoreCLR personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a4703-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="a4703-153">Aunque la variante **onbuild** está optimizada para colocar simplemente el código en una imagen y ejecutarlo, esta imagen está optimizada para tener solo las dependencias del sistema operativo necesarias para ejecutar aplicaciones .NET Core que tienen empaquetado el entorno de tiempo de ejecución .NET con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="a4703-154">Generalmente, esta imagen no está optimizada para ejecutar varios contenedores .NET Core en el mismo host, según cada imagen incluye el tiempo de ejecución de .NET Core dentro de la aplicación y no se beneficiará de las capas de imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="a4703-155">Versiones más recientes de cada variante:</span><span class="sxs-lookup"><span data-stu-id="a4703-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="a4703-156">`microsoft/dotnet` o `microsoft/dotnet:latest` (incluye el SDK)</span><span class="sxs-lookup"><span data-stu-id="a4703-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="a4703-157">Esta es una lista de las imágenes después de `docker pull <imagename>` en una máquina de desarrollo para mostrar los distintos tamaños.</span><span class="sxs-lookup"><span data-stu-id="a4703-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="a4703-158">Observe que la variante de desarrollo/compilación `microsoft/dotnet:1.0.0-preview2-sdk` es más grande dado que contiene el SDK para desarrollar y compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="a4703-159">La variante de producción, `microsoft/dotnet:core` es menor, ya que solo contiene el entorno de tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4703-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="a4703-160">La imagen mínima que se puede usar en Linux, `core-deps`, es bastante más pequeña, sin embargo, la aplicación deberá hacer una copia privada del entorno de tiempo de ejecución de .NET con ella.</span><span class="sxs-lookup"><span data-stu-id="a4703-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="a4703-161">Como los contenedores ya son barreras de aislamiento privadas, perderá esa optimización al ejecutar varios contenedores basados en dotnet.</span><span class="sxs-lookup"><span data-stu-id="a4703-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="a4703-162">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a4703-162">Prerequisites</span></span>

<span data-ttu-id="a4703-163">Para la compilación y ejecución, necesita tener instaladas algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="a4703-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="a4703-164">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a4703-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="a4703-165">[Docker](https://www.docker.com/products/docker) para ejecutar sus contenedores de Docker localmente.</span><span class="sxs-lookup"><span data-stu-id="a4703-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="a4703-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="a4703-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="a4703-167">[Generador de Yeoman para ASP.NET](https://github.com/omnisharp/generator-aspnet) para crear la aplicación de API web.</span><span class="sxs-lookup"><span data-stu-id="a4703-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="a4703-168">[Generador de Yeoman para Docker](http://aka.ms/yodocker) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4703-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="a4703-169">Instale los generadores de Yeoman para ASP.NET Core y Docker mediante npm.</span><span class="sxs-lookup"><span data-stu-id="a4703-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="a4703-170">En este ejemplo se usará [Visual Studio Code](http://code.visualstudio.com) en el editor.</span><span class="sxs-lookup"><span data-stu-id="a4703-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="a4703-171">Creación de la aplicación de API web</span><span class="sxs-lookup"><span data-stu-id="a4703-171">Creating the Web API application</span></span>

<span data-ttu-id="a4703-172">Como punto de referencia, antes de que meter la aplicación en un contenedor, ejecútela localmente.</span><span class="sxs-lookup"><span data-stu-id="a4703-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="a4703-173">La aplicación finalizada se encuentra en el [repositorio dotnet/docs en GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="a4703-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="a4703-174">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a4703-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a4703-175">Cree un directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-175">Create a directory for your application.</span></span>

<span data-ttu-id="a4703-176">Abra un comando o una sesión de terminal en ese directorio y use el generador de ASP.NET Yeoman escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4703-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="a4703-177">Seleccione **Web API Application** (Aplicación API web) y escriba **api**.</span><span class="sxs-lookup"><span data-stu-id="a4703-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="a4703-178">Después de aplicar la técnica scaffolding a la aplicación, cambie al directorio `/api` y restaure las dependencias de NuGet mediante `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="a4703-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="a4703-179">Pruebe la aplicación con `dotnet run` y vaya a **http://localhost:5000/api/values**.</span><span class="sxs-lookup"><span data-stu-id="a4703-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="a4703-180">Use `Ctrl+C` para detener la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4703-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="a4703-181">Adición de compatibilidad con Docker</span><span class="sxs-lookup"><span data-stu-id="a4703-181">Adding Docker support</span></span>

<span data-ttu-id="a4703-182">Para agregar compatibilidad con Docker al proyecto es necesario usar el generador Yeoman de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4703-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="a4703-183">Actualmente se admiten proyectos .NET Core, Node.js y Go mediante la creación de un Dockerfile y scripts que ayudan a compilar y ejecutar proyectos dentro de contenedores.</span><span class="sxs-lookup"><span data-stu-id="a4703-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="a4703-184">También se agregan archivos específicos de Visual Studio Code (launch.json, tasks.json) para la depuración del editor y la compatibilidad con la paleta de comandos.</span><span class="sxs-lookup"><span data-stu-id="a4703-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="a4703-185">Seleccione `.NET Core` como tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4703-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="a4703-186">`rtm` para la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4703-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="a4703-187">`Y` el proyecto usa un servidor web.</span><span class="sxs-lookup"><span data-stu-id="a4703-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="a4703-188">`5000` es el puerto en el que escucha la aplicación de API web (http://localhost:5000).</span><span class="sxs-lookup"><span data-stu-id="a4703-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="a4703-189">`api` para el nombre de imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-189">`api` for the image name</span></span>
- <span data-ttu-id="a4703-190">`api` para el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4703-190">`api` for the service name</span></span>
- <span data-ttu-id="a4703-191">`api` para el proyecto de redacción.</span><span class="sxs-lookup"><span data-stu-id="a4703-191">`api` for the compose project</span></span> 
- <span data-ttu-id="a4703-192">`Y` para sobrescribir el Dockerfile actual.</span><span class="sxs-lookup"><span data-stu-id="a4703-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="a4703-193">Cuando finalice el generador, los siguientes archivos se agregan al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4703-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="a4703-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="a4703-194">.vscode/launch.json</span></span>
- <span data-ttu-id="a4703-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="a4703-195">Dockerfile.debug</span></span>
- <span data-ttu-id="a4703-196">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="a4703-196">Dockerfile</span></span>
- <span data-ttu-id="a4703-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="a4703-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="a4703-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="a4703-198">docker-compose.yml</span></span>
- <span data-ttu-id="a4703-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="a4703-199">dockerTask.ps1</span></span>
- <span data-ttu-id="a4703-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="a4703-200">dockerTask.sh</span></span>
- <span data-ttu-id="a4703-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="a4703-201">.vscode/tasks.json</span></span>

<span data-ttu-id="a4703-202">El generador crea dos Dockerfiles.</span><span class="sxs-lookup"><span data-stu-id="a4703-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="a4703-203">**Dockerfile.debug**: este archivo se basa en la imagen **microsoft/dotnet:1.0.0-preview2-sdk** que, si advierte por la lista de variantes de imágenes, incluye el SDK, la CLI y .NET Core y será la imagen usada para el desarrollo y la depuración (F5).</span><span class="sxs-lookup"><span data-stu-id="a4703-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="a4703-204">Al incluir todos estos componentes se produce una imagen más grande con un tamaño aproximado de 540 MB.</span><span class="sxs-lookup"><span data-stu-id="a4703-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="a4703-205">**Dockerfile**: esta imagen es la imagen de lanzamiento basada en **microsoft/dotnet:1.0.0-core** y se debe usar en producción.</span><span class="sxs-lookup"><span data-stu-id="a4703-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="a4703-206">Cuando se compila esta imagen es de 253 MB aproximadamente.</span><span class="sxs-lookup"><span data-stu-id="a4703-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="a4703-207">Creación de las imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="a4703-207">Creating the Docker images</span></span>
<span data-ttu-id="a4703-208">Mediante el script `dockerTask.sh` o `dockerTask.ps1`, podemos compilar o componer la imagen y el contenedor para la aplicación de **api** en un entorno específico.</span><span class="sxs-lookup"><span data-stu-id="a4703-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="a4703-209">Compile la imagen **debug** mediante la ejecución del comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4703-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="a4703-210">La imagen compilará la aplicación ASP.NET, ejecutará `dotnet restore`, agregará el depurador a la imagen, establecerá un `ENTRYPOINT` y, finalmente, copiará la aplicación en la imagen.</span><span class="sxs-lookup"><span data-stu-id="a4703-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="a4703-211">El resultado es una imagen de Docker llamada *api* con una `TAG` de *debug*.</span><span class="sxs-lookup"><span data-stu-id="a4703-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="a4703-212">Vea las imágenes en la máquina mediante `docker images`.</span><span class="sxs-lookup"><span data-stu-id="a4703-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="a4703-213">Otra manera de generar la imagen y ejecutar la aplicación dentro del contenedor de Docker es abrir la aplicación en Visual Studio Code y usar las herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="a4703-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="a4703-214">Seleccione el icono de depuración en la barra de vistas del lado izquierdo de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="a4703-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![icono de depuración de vscode](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="a4703-216">A continuación, toque el icono de reproducción o F5 para generar la imagen e iniciar la aplicación dentro del contenedor.</span><span class="sxs-lookup"><span data-stu-id="a4703-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="a4703-217">Se iniciará la API web mediante el explorador web predeterminado en http://localhost:5000.</span><span class="sxs-lookup"><span data-stu-id="a4703-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![Depuración con las herramientas de Docker de VSCode](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="a4703-219">Puede establecer puntos de interrupción en la aplicación, ejecutar paso a paso, etc. como si la aplicación se ejecutara localmente en la máquina de desarrollo en lugar de en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a4703-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="a4703-220">La ventaja de depurar dentro del contenedor es que es la misma imagen que se implementaría en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="a4703-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="a4703-221">La creación de la imagen de lanzamiento o de producción requiere la ejecución del comando desde el terminal pasando el nombre del entorno `release`.</span><span class="sxs-lookup"><span data-stu-id="a4703-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="a4703-222">El comando crea la imagen basándose en la imagen base **microsoft/dotnet:core** más pequeña, [EXPONE](https://docs.docker.com/engine/reference/builder/#/expose) el puerto 5000, establece el [PUNTO DE ENTRADA](https://docs.docker.com/engine/reference/builder/#/entrypoint) para `dotnet api.dll` y lo copia en el directorio `/app`.</span><span class="sxs-lookup"><span data-stu-id="a4703-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="a4703-223">No hay ningún depurador, SDK o `dotnet restore` que dé lugar a una imagen mucho más pequeña.</span><span class="sxs-lookup"><span data-stu-id="a4703-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="a4703-224">La imagen se denomina **api** con una `TAG` de **latest**.</span><span class="sxs-lookup"><span data-stu-id="a4703-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="a4703-225">Resumen</span><span class="sxs-lookup"><span data-stu-id="a4703-225">Summary</span></span>

<span data-ttu-id="a4703-226">Mediante el generador de Docker para agregar los archivos necesarios a nuestra aplicación de API web se facilita el proceso para crear las versiones de desarrollo y producción de las imágenes.</span><span class="sxs-lookup"><span data-stu-id="a4703-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="a4703-227">Las herramientas son multiplataforma. Proporcionan también un script de PowerShell para lograr los mismos resultados en la integración de Windows y Visual Studio Code y ofrecen depuración paso a paso de la aplicación dentro del contenedor.</span><span class="sxs-lookup"><span data-stu-id="a4703-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="a4703-228">Si comprende las variantes de imagen y los escenarios de destino, puede optimizar el proceso de desarrollo de bucle interior y conseguir imágenes optimizadas para implementaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="a4703-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



