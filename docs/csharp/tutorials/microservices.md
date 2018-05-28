---
title: 'Microservicios hospedados en Docker: C#'
description: Aprenda a crear microservicios de ASP.NET Core que se ejecutan en contenedores de Docker.
ms.date: 02/03/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 7428051c1d9a29ba98ca1f28288b3c50ea36ae1a
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2018
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="aa5e9-103">Microservicios alojados en Docker</span><span class="sxs-lookup"><span data-stu-id="aa5e9-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="aa5e9-104">En este tutorial se describen las tareas necesarias para compilar e implementar un microservicio de ASP.NET Core en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="aa5e9-105">Durante el transcurso de este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="aa5e9-106">Generar una aplicación de ASP.NET Core mediante Yeoman</span><span class="sxs-lookup"><span data-stu-id="aa5e9-106">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="aa5e9-107">Crear un entorno de desarrollo de Docker</span><span class="sxs-lookup"><span data-stu-id="aa5e9-107">How to create a development Docker environment</span></span>
* <span data-ttu-id="aa5e9-108">Crear una imagen de Docker basada en una imagen existente</span><span class="sxs-lookup"><span data-stu-id="aa5e9-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="aa5e9-109">Implementar su servicio en un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="aa5e9-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="aa5e9-110">Por el camino, también verá algunas características del lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="aa5e9-111">Cómo convertir objetos de C# en cargas de JSON</span><span class="sxs-lookup"><span data-stu-id="aa5e9-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="aa5e9-112">Cómo compilar objetos de transferencia de datos inmutables</span><span class="sxs-lookup"><span data-stu-id="aa5e9-112">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="aa5e9-113">Cómo procesar solicitudes HTTP entrantes y generar la respuesta HTTP</span><span class="sxs-lookup"><span data-stu-id="aa5e9-113">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="aa5e9-114">Cómo trabajar con tipos de valor que aceptan valores null</span><span class="sxs-lookup"><span data-stu-id="aa5e9-114">How to work with nullable value types</span></span>

<span data-ttu-id="aa5e9-115">Puede [ver o descargar la aplicación de ejemplo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) para este tema.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="aa5e9-116">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="aa5e9-117">¿Por qué Docker?</span><span class="sxs-lookup"><span data-stu-id="aa5e9-117">Why Docker?</span></span>

<span data-ttu-id="aa5e9-118">Docker facilita la creación de imágenes de máquina estándar para hospedar los servicios de un centro de datos o en la nube pública.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="aa5e9-119">Docker le permite configurar la imagen y replicarla según sea necesario para escalar la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="aa5e9-120">Todo el código de este tutorial funciona en cualquier entorno .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="aa5e9-121">Las tareas adicionales para una instalación de Docker funcionarán para una aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="aa5e9-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aa5e9-122">Prerequisites</span></span>
<span data-ttu-id="aa5e9-123">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-123">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="aa5e9-124">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="aa5e9-125">Puede ejecutar esta aplicación en Windows, Ubuntu Linux, macOS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-125">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="aa5e9-126">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="aa5e9-127">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="aa5e9-128">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="aa5e9-129">También deberá instalar el motor de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="aa5e9-130">Consulte la [página de instalación de Docker](http://www.docker.com/products/docker) para obtener instrucciones para su plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="aa5e9-131">Docker puede instalarse en muchas distribuciones de Linux, macOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="aa5e9-132">La página mencionada anteriormente contiene secciones para cada una de las instalaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-132">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="aa5e9-133">La instalación de la mayoría de componentes se realiza mediante un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-133">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="aa5e9-134">Si tiene instalado el administrador de paquetes de node.js `npm`, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-134">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="aa5e9-135">Si no, instale el archivo de NodeJs más reciente desde [nodejs.org](https://nodejs.org), que instalará el administrador de paquetes de npm.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-135">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="aa5e9-136">En este punto, deberá instalar una serie de herramientas de línea de comandos compatibles con el desarrollo de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-136">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="aa5e9-137">Las plantillas de línea de comandos usan Yeoman, Bower, Grunt y Gulp.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-137">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="aa5e9-138">Si las tiene instaladas, genial, si no, escriba lo siguiente en su shell favorito:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-138">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="aa5e9-139">La opción `-g` indica que es una instalación global y esas herramientas están disponibles en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-139">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="aa5e9-140">(En una instalación local el ámbito del paquete es un único proyecto).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-140">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="aa5e9-141">Cuando haya instalado las herramientas básicas, debe instalar los generadores de plantillas ASP.NET de Yeoman:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-141">Once you've installed those core tools, you need to install the yeoman ASP.NET template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="aa5e9-142">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="aa5e9-142">Create the Application</span></span>

<span data-ttu-id="aa5e9-143">Ahora que ha instalado todas las herramientas, cree una nueva aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-143">Now that you've installed all the tools, create a new ASP.NET Core application.</span></span> <span data-ttu-id="aa5e9-144">Para usar el generador de línea de comandos, ejecute el siguiente comando de Yeoman en su shell favorito:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-144">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="aa5e9-145">Este comando le pide que seleccione el tipo de aplicación que desea crear.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-145">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="aa5e9-146">Para este microservicio, desea la aplicación web más sencilla y ligera posible, así que seleccione "Empty Web Application" (Aplicación web vacía).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-146">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="aa5e9-147">La plantilla le solicita un nombre.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-147">The template will prompt you for a name.</span></span> <span data-ttu-id="aa5e9-148">Seleccione "WeatherMicroservice".</span><span class="sxs-lookup"><span data-stu-id="aa5e9-148">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="aa5e9-149">La plantilla crea ocho archivos:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-149">The template creates eight files for you:</span></span>

* <span data-ttu-id="aa5e9-150">Un archivo .gitignore, personalizado para aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-150">A .gitignore, customized for ASP.NET Core applications.</span></span>
* <span data-ttu-id="aa5e9-151">Un archivo Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-151">A Startup.cs file.</span></span> <span data-ttu-id="aa5e9-152">Este archivo contiene la base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-152">This contains the basis of the application.</span></span>
* <span data-ttu-id="aa5e9-153">Un archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-153">A Program.cs file.</span></span> <span data-ttu-id="aa5e9-154">Este archivo contiene el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-154">This contains the entry point of the application.</span></span>
* <span data-ttu-id="aa5e9-155">Un archivo WeatherMicroservice.csproj.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-155">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="aa5e9-156">Este es el archivo de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-156">This is the build file for the application.</span></span>
* <span data-ttu-id="aa5e9-157">Un archivo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-157">A Dockerfile.</span></span> <span data-ttu-id="aa5e9-158">Este script crea una imagen de Docker para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-158">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="aa5e9-159">Un archivo README.md.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-159">A README.md.</span></span> <span data-ttu-id="aa5e9-160">Este archivo contiene vínculos a otros recursos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-160">This contains links to other ASP.NET Core resources.</span></span>
* <span data-ttu-id="aa5e9-161">Un archivo web.config.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-161">A web.config file.</span></span> <span data-ttu-id="aa5e9-162">Este archivo contiene información de configuración básica.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-162">This contains basic configuration information.</span></span>
* <span data-ttu-id="aa5e9-163">Un archivo runtimeconfig.template.json.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-163">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="aa5e9-164">Este archivo contiene la configuración de depuración usada por los IDE.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-164">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="aa5e9-165">Ahora puede ejecutar la aplicación generada por la plantilla.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-165">Now you can run the template generated application.</span></span> <span data-ttu-id="aa5e9-166">Para ello se usa una serie de herramientas desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-166">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="aa5e9-167">El comando `dotnet` ejecuta las herramientas necesarias para el desarrollo de .NET.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-167">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="aa5e9-168">Cada verbo ejecuta un comando diferente.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-168">Each verb executes a different command</span></span>

<span data-ttu-id="aa5e9-169">El primer paso consiste en restaurar todas las dependencias:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-169">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="aa5e9-170">La restauración de Dotnet emplea el Administrador de paquetes NuGet para instalar todos los paquetes necesarios en el directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-170">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="aa5e9-171">También genera un archivo project.json.lock.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-171">It also generates a project.json.lock file.</span></span> <span data-ttu-id="aa5e9-172">Este archivo contiene información sobre cada paquete al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-172">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="aa5e9-173">Después de restaurar todas las dependencias, compile la aplicación:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-173">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="aa5e9-174">Una vez compilada, ejecútela desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-174">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="aa5e9-175">La configuración predeterminada escucha a `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-175">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="aa5e9-176">Abra un explorador y vaya a esa página. Verá un "¡Hola a todos!".</span><span class="sxs-lookup"><span data-stu-id="aa5e9-176">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="aa5e9-177">.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-177">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="aa5e9-178">Anatomía de una aplicación de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aa5e9-178">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="aa5e9-179">Ahora que ha creado la aplicación, echemos un vistazo a cómo se implementa esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-179">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="aa5e9-180">Dos de los archivos generados son especialmente interesantes en este momento: project.json y Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-180">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="aa5e9-181">Project.JSON contiene información sobre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-181">Project.json contains information about the project.</span></span> <span data-ttu-id="aa5e9-182">Los dos nodos con los que trabaja a menudo son "dependencias" y "marcos".</span><span class="sxs-lookup"><span data-stu-id="aa5e9-182">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="aa5e9-183">El nodo de dependencias muestra todos los paquetes que son necesarios para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-183">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="aa5e9-184">En este momento, este es un nodo pequeño, que solo necesita paquetes que se ejecutan en el servidor web.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-184">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="aa5e9-185">El nodo "marcos" especifica las versiones y configuraciones de .NET Framework que ejecutarán esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-185">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="aa5e9-186">La aplicación se implementa en Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-186">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="aa5e9-187">Este archivo contiene la clase de inicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-187">This file contains the startup class.</span></span>

<span data-ttu-id="aa5e9-188">La infraestructura de ASP.NET Core llama a los dos métodos para configurar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-188">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="aa5e9-189">El método `ConfigureServices` describe los servicios que son necesarios para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-189">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="aa5e9-190">Va a crear un microservicio de Lean, así que no es necesario configurar ninguna dependencia.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-190">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="aa5e9-191">El método `Configure` configura los controladores para las solicitudes HTTP entrantes.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-191">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="aa5e9-192">La plantilla genera un controlador sencillo que responde a cualquier solicitud con el texto "¡Hola a todos!".</span><span class="sxs-lookup"><span data-stu-id="aa5e9-192">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="aa5e9-193">Creación de un microservicio</span><span class="sxs-lookup"><span data-stu-id="aa5e9-193">Build a microservice</span></span>

<span data-ttu-id="aa5e9-194">El servicio que va a crear proporcionará informes meteorológicos desde cualquier lugar del mundo.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-194">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="aa5e9-195">En una aplicación de producción, se llamaría a algún servicio para recuperar datos meteorológicos.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-195">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="aa5e9-196">Para nuestro ejemplo, vamos a generar un pronóstico meteorológico aleatorio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-196">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="aa5e9-197">Hay una serie de tareas que debe realizar para implementar nuestro servicio de información meteorológica aleatorio:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-197">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="aa5e9-198">Analizar la solicitud entrante para leer la latitud y la longitud.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-198">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="aa5e9-199">Generar algunos datos de pronóstico aleatorios.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-199">Generate some random forecast data.</span></span>
* <span data-ttu-id="aa5e9-200">Convertir estos datos de pronóstico aleatorios de objetos de C# a paquetes JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-200">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="aa5e9-201">Establecer el encabezado de respuesta para indicar que el servicio devuelve JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-201">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="aa5e9-202">Escribir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-202">Write the response.</span></span>

<span data-ttu-id="aa5e9-203">Las secciones siguientes le guiarán en cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-203">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="aa5e9-204">Análisis de la cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="aa5e9-204">Parsing the Query String.</span></span>

<span data-ttu-id="aa5e9-205">Para comenzar, analizará la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-205">You'll begin by parsing the query string.</span></span> <span data-ttu-id="aa5e9-206">El servicio acepta argumentos "lat" y "long" en la cadena de consulta en este formato:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-206">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="aa5e9-207">Todos los cambios que debe realzar se encuentran en la expresión lambda definida como el argumento para `app.Run` en la clase de inicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-207">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="aa5e9-208">El argumento en la expresión lambda es el elemento `HttpContext` para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-208">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="aa5e9-209">Una de sus propiedades es el objeto `Request`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-209">One of its properties is the `Request` object.</span></span> <span data-ttu-id="aa5e9-210">El objeto `Request` tiene una propiedad `Query` que contiene un diccionario de todos los valores en la cadena de consulta de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-210">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="aa5e9-211">La primera adición consiste en encontrar los valores de latitud y longitud:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-211">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="aa5e9-212">Los valores del diccionario de consulta son de tipo `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-212">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="aa5e9-213">Ese tipo puede contener una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-213">That type can contain a collection of strings.</span></span> <span data-ttu-id="aa5e9-214">Para el servicio de información meteorológica, cada valor es una única cadena.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-214">For your weather service, each value is a single string.</span></span> <span data-ttu-id="aa5e9-215">Es por eso que existe la llamada a `FirstOrDefault()` en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-215">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="aa5e9-216">A continuación, debe convertir las cadenas en valores dobles.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-216">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="aa5e9-217">El método que va a usar para convertir la cadena en un doble es `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-217">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="aa5e9-218">Este método aprovecha parámetros de salida de C# para indicar si la cadena de entrada se puede convertir en un doble.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-218">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="aa5e9-219">Si la cadena representa un valor doble válido, el método devuelve true y el argumento `result` contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-219">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="aa5e9-220">Si la cadena no representa un valor doble válido, el método devuelve false.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-220">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="aa5e9-221">Puede adaptar dicha API con el uso de un *método de extensión* que devuelve un *valor doble que acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-221">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="aa5e9-222">Un *tipo de valor que acepta valores NULL* es un tipo que representa algún tipo de valor y también puede contener un valor que falta o un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-222">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="aa5e9-223">Un tipo que acepta valores NULL se representa mediante la anexión del carácter `?` a la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-223">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="aa5e9-224">Los métodos de extensión son métodos que se definen como métodos estáticos, pero al agregar el modificador `this` en el primer parámetro, se pueden llamar como si fueran miembros de esa clase.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-224">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="aa5e9-225">Los métodos de extensión solo se pueden definir en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-225">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="aa5e9-226">Esta es la definición de la clase que contiene el método de extensión para el análisis:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-226">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="aa5e9-227">La expresión `default(double?)` devuelve el valor predeterminado del tipo `double?`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-227">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="aa5e9-228">Este valor predeterminado es el valor NULL (o que falta).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-228">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="aa5e9-229">Puede usar este método de extensión para convertir los argumentos de cadena de consulta en el tipo doble:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-229">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="aa5e9-230">Para probar fácilmente el código de análisis, actualice la respuesta para incluir los valores de los argumentos:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-230">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="aa5e9-231">En este punto, puede ejecutar la aplicación web y ver si su código de análisis está funcionando.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-231">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="aa5e9-232">Agregue valores a la solicitud web en un explorador y verá los resultados actualizados.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-232">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="aa5e9-233">Creación de un pronóstico meteorológico aleatorio</span><span class="sxs-lookup"><span data-stu-id="aa5e9-233">Build a random weather forecast</span></span>

<span data-ttu-id="aa5e9-234">La siguiente tarea consiste en crear un pronóstico meteorológico aleatorio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-234">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="aa5e9-235">Comencemos con un contenedor de datos que contiene los valores que desea para un pronóstico meteorológico:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-235">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="aa5e9-236">A continuación, cree un constructor que establezca esos valores de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-236">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="aa5e9-237">Este constructor usa los valores de la latitud y la longitud para inicializar el generador de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-237">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="aa5e9-238">Esto significa que el pronóstico para la misma ubicación es el mismo.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-238">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="aa5e9-239">Si cambia los argumentos para la latitud y la longitud, obtendrá un pronóstico diferente (ya que comienza con un valor de inicialización diferente).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-239">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="aa5e9-240">Ahora puede generar el pronóstico de cinco días en el método de respuesta:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-240">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="aa5e9-241">Compile la respuesta JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-241">Build the JSON response.</span></span>

<span data-ttu-id="aa5e9-242">La tarea final de código en el servidor es convertir la matriz WeatherReport en un paquete JSON y devolverlo al cliente.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-242">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="aa5e9-243">Comencemos creando el paquete JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-243">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="aa5e9-244">Agregará el serializador NewtonSoft de JSON a la lista de dependencias.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-244">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="aa5e9-245">Puede hacerlo mediante la CLI de `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-245">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="aa5e9-246">A continuación, puede usar la clase `JsonConvert` para escribir el objeto en una cadena:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-246">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="aa5e9-247">El código anterior convierte el objeto de pronóstico (una lista de objetos `WeatherForecast`) en un paquete JSON.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-247">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="aa5e9-248">Después de haber construido el paquete de respuesta, establezca el tipo de contenido en `application/json` y escriba la cadena.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-248">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="aa5e9-249">Ahora, la aplicación se ejecuta y devuelve los pronósticos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-249">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="aa5e9-250">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="aa5e9-250">Build a Docker image</span></span>

<span data-ttu-id="aa5e9-251">La tarea final es ejecutar la aplicación en Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-251">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="aa5e9-252">Vamos a crear un contenedor de Docker que ejecute una imagen de Docker que representa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-252">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="aa5e9-253">Una ***imagen de Docker*** es un archivo que define el entorno de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-253">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="aa5e9-254">Un ***contenedor de Docker*** representa una instancia en ejecución de una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-254">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="aa5e9-255">Por analogía, puede considerar la *imagen de Docker* como una *clase*y el *contenedor de Docker* como un objeto o una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-255">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="aa5e9-256">El Dockerfile creado por la plantilla de ASP.NET sirve para nuestros propósitos.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-256">The Dockerfile created by the ASP.NET template will serve for our purposes.</span></span> <span data-ttu-id="aa5e9-257">Repasemos su contenido.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-257">Let's go over its contents.</span></span>

<span data-ttu-id="aa5e9-258">La primera línea especifica la imagen de origen:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-258">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="aa5e9-259">Docker le permite configurar una imagen de máquina basada en una plantilla de origen.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-259">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="aa5e9-260">Esto significa que no tiene que suministrar todos los parámetros de máquina cuando se inicia, solo tiene que proporcionar los cambios.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-260">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="aa5e9-261">Aquí los cambios van a ser incluir nuestra aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-261">The changes here will be to include our application.</span></span>

<span data-ttu-id="aa5e9-262">En este primer ejemplo, usaremos la versión `1.1-sdk-msbuild` de la imagen de dotnet.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-262">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="aa5e9-263">Esta es la manera más fácil de crear un entorno de trabajo de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-263">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="aa5e9-264">Esta imagen incluye el tiempo de ejecución de dotnet core y el SDK de dotnet.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-264">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="aa5e9-265">Como resultado, es más fácil comenzar a trabajar y realizar la compilación, pero la imagen que se crea es más grande.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-265">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="aa5e9-266">Las siguientes cinco líneas instalan y compilan su aplicación:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-266">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroService.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="aa5e9-267">El archivo de proyecto se copia desde el directorio actual en la máquina virtual de Docker y se restauran todos los paquetes.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-267">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="aa5e9-268">El uso de la CLI de dotnet significa que la imagen de Docker debe incluir el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-268">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="aa5e9-269">Luego, se copia el resto de la aplicación y el comando de publicación de dotnet compila y empaqueta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-269">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="aa5e9-270">La última línea del archivo ejecuta la aplicación:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-270">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroService.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="aa5e9-271">Se hace referencia a este puerto configurado en el argumento `--server.urls` para `dotnet` en la última línea del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-271">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="aa5e9-272">El comando `ENTRYPOINT` informa a Docker de qué opciones de comando y de línea de comandos inician el servicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-272">The `ENTRYPOINT` command informs Docker what command and command-line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="aa5e9-273">Compilación y ejecución de la imagen en un contenedor</span><span class="sxs-lookup"><span data-stu-id="aa5e9-273">Building and running the image in a container.</span></span>

<span data-ttu-id="aa5e9-274">Vamos a compilar una imagen y ejecutar el servicio dentro de un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-274">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="aa5e9-275">No desea copiar todos los archivos de su directorio local en la imagen.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-275">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="aa5e9-276">En su lugar, va a compilar la aplicación en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-276">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="aa5e9-277">Creará un archivo `.dockerignore` para especificar los directorios que no se copian en la imagen.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-277">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="aa5e9-278">No desea copiar ninguno de los recursos de compilación.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-278">You don't want any of the build assets copied.</span></span> <span data-ttu-id="aa5e9-279">Especifique los directorios de compilación y publicación en el archivo `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-279">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="aa5e9-280">Compile la imagen mediante el comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-280">You build the image using the `docker build` command.</span></span> <span data-ttu-id="aa5e9-281">Ejecute el siguiente comando desde el directorio que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-281">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="aa5e9-282">Este comando compila la imagen de contenedor en función de toda la información del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-282">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="aa5e9-283">El argumento `-t` proporciona una etiqueta, o nombre, para esta imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-283">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="aa5e9-284">En la línea de comandos anterior, la etiqueta usada para el contenedor de Docker es `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-284">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="aa5e9-285">Cuando termina este comando, tendrá un contenedor listo para ejecutar el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-285">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="aa5e9-286">Ejecute el siguiente comando para iniciar el contenedor y el servicio:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-286">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="aa5e9-287">La opción `-d` implica ejecutar el contenedor desasociado del terminal actual.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-287">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="aa5e9-288">Esto significa que no verá la salida del comando en el terminal.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-288">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="aa5e9-289">La opción `-p` indica la asignación de puertos entre el servicio y el host.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-289">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="aa5e9-290">Aquí dice que cualquier solicitud entrante en el puerto 80 se debe reenviar al puerto 5000 en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-290">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="aa5e9-291">El uso de 5000 coincide con el puerto en el que escucha su servicio desde los argumentos de línea de comandos especificados en el Dockerfile anterior.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-291">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="aa5e9-292">El argumento `--name` nombra el contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-292">The `--name` argument names your running container.</span></span> <span data-ttu-id="aa5e9-293">Es un nombre adecuado que puede usar para trabajar con ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-293">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="aa5e9-294">Para ver si la imagen se ejecuta, compruebe el comando:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-294">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="aa5e9-295">Si el contenedor se está ejecutando, verá una línea que lo indica en los procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-295">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="aa5e9-296">(Puede que sea la única).</span><span class="sxs-lookup"><span data-stu-id="aa5e9-296">(It may be the only one).</span></span>

<span data-ttu-id="aa5e9-297">Para probar el servicio, abra un explorador y vaya a localhost, luego especifique la latitud y la longitud:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-297">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="aa5e9-298">Asociación de un contenedor en ejecución</span><span class="sxs-lookup"><span data-stu-id="aa5e9-298">Attaching to a running container</span></span>

<span data-ttu-id="aa5e9-299">Cuando ejecutó su servicio en una ventana de comandos, ha podido ver información de diagnóstico impresa para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-299">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="aa5e9-300">Cuando el contenedor se ejecuta en modo de desconexión, no puede ver esa información.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-300">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="aa5e9-301">El comando attach de Docker le permite conectarse a un contenedor en ejecución para ver la información de registro.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-301">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="aa5e9-302">Ejecute este comando desde una ventana de comandos:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-302">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="aa5e9-303">El argumento `--sig-proxy=false` significa que los comandos `Ctrl-C` no se envían al proceso del contenedor, sino que detienen el comando `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-303">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="aa5e9-304">El argumento final es el nombre asignado al contenedor en el comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-304">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="aa5e9-305">También puede usar el Id. de contenedor asignado a Docker para hacer referencia a cualquier contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-305">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="aa5e9-306">Si no especifica un nombre para su contenedor en `docker run`, debe usar el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-306">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="aa5e9-307">Abra un explorador y vaya a su servicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-307">Open a browser and navigate to your service.</span></span> <span data-ttu-id="aa5e9-308">Verá los mensajes de diagnóstico en las ventanas de comandos desde el contenedor en ejecución conectado.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-308">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="aa5e9-309">Presione `Ctrl-C` para detener el proceso de conexión.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-309">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="aa5e9-310">Cuando haya terminado de trabajar con el contenedor, puede detenerlo:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-310">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="aa5e9-311">El contenedor y la imagen siguen estando disponibles para que los reinicie.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-311">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="aa5e9-312">Si desea quitar el contenedor de la máquina, use este comando:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-312">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="aa5e9-313">Si desea quitar imágenes no usadas de la máquina, utilice este comando:</span><span class="sxs-lookup"><span data-stu-id="aa5e9-313">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="aa5e9-314">Conclusión</span><span class="sxs-lookup"><span data-stu-id="aa5e9-314">Conclusion</span></span> 

<span data-ttu-id="aa5e9-315">En este tutorial, ha compilado un microservicio de ASP.NET Core y ha agregado unas cuantas características sencillas.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-315">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="aa5e9-316">Ha compilado una imagen de un contenedor de Docker para ese servicio y ha ejecutado ese contenedor en el equipo.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-316">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="aa5e9-317">Ha conectado una ventana de terminal al servicio y ha visto los mensajes de diagnóstico de su servicio.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-317">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="aa5e9-318">Por el camino, ha visto varias características del lenguaje C# en acción.</span><span class="sxs-lookup"><span data-stu-id="aa5e9-318">Along the way, you saw several features of the C# language in action.</span></span>
