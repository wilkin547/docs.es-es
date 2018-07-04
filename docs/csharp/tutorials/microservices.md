---
title: 'Microservicios hospedados en Docker: C#'
description: Aprenda a crear microservicios de ASP.NET Core que se ejecutan en contenedores de Docker.
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 1f4b38243beb1210b1374bd701fac66b2fa72cc5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106355"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="49756-103">Microservicios alojados en Docker</span><span class="sxs-lookup"><span data-stu-id="49756-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="49756-104">En este tutorial se describen las tareas necesarias para compilar e implementar un microservicio de ASP.NET Core en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="49756-105">Durante el transcurso de este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="49756-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="49756-106">Generar una aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="49756-107">Crear un entorno de desarrollo de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="49756-108">Crear una imagen de Docker basada en una imagen existente</span><span class="sxs-lookup"><span data-stu-id="49756-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="49756-109">Implementar su servicio en un contenedor de Docker</span><span class="sxs-lookup"><span data-stu-id="49756-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="49756-110">Por el camino, también verá algunas características del lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="49756-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="49756-111">Cómo convertir objetos de C# en cargas de JSON</span><span class="sxs-lookup"><span data-stu-id="49756-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="49756-112">Cómo compilar objetos de transferencia de datos inmutables.</span><span class="sxs-lookup"><span data-stu-id="49756-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="49756-113">Cómo procesar solicitudes HTTP entrantes y generar la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="49756-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="49756-114">Cómo trabajar con tipos de valor que aceptan valores null.</span><span class="sxs-lookup"><span data-stu-id="49756-114">How to work with nullable value types.</span></span>

<span data-ttu-id="49756-115">Puede [ver o descargar la aplicación de ejemplo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) para este tema.</span><span class="sxs-lookup"><span data-stu-id="49756-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="49756-116">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="49756-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="49756-117">¿Por qué Docker?</span><span class="sxs-lookup"><span data-stu-id="49756-117">Why Docker?</span></span>

<span data-ttu-id="49756-118">Docker facilita la creación de imágenes de máquina estándar para hospedar los servicios de un centro de datos o en la nube pública.</span><span class="sxs-lookup"><span data-stu-id="49756-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="49756-119">Docker le permite configurar la imagen y replicarla según sea necesario para escalar la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="49756-120">Todo el código de este tutorial funciona en cualquier entorno .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="49756-121">Las tareas adicionales para una instalación de Docker funcionarán para una aplicación de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="49756-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="49756-122">Prerequisites</span></span>

<span data-ttu-id="49756-123">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="49756-124">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="49756-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="49756-125">Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="49756-126">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="49756-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="49756-127">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="49756-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="49756-128">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="49756-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="49756-129">También deberá instalar el motor de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="49756-130">Consulte la [página de instalación de Docker](http://www.docker.com/products/docker) para obtener instrucciones para su plataforma.</span><span class="sxs-lookup"><span data-stu-id="49756-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="49756-131">Docker puede instalarse en muchas distribuciones de Linux, macOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="49756-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="49756-132">La página mencionada anteriormente contiene secciones para cada una de las instalaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="49756-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="49756-133">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="49756-133">Create the Application</span></span>

<span data-ttu-id="49756-134">Ahora que ha instalado las herramientas, cree una aplicación ASP.NET Core en un directorio denominado "WeatherMicroservice"mediante la ejecución del comando siguiente en el shell que prefiera:</span><span class="sxs-lookup"><span data-stu-id="49756-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="49756-135">El comando `dotnet` ejecuta las herramientas necesarias para el desarrollo de .NET.</span><span class="sxs-lookup"><span data-stu-id="49756-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="49756-136">Cada verbo ejecuta un comando diferente.</span><span class="sxs-lookup"><span data-stu-id="49756-136">Each verb executes a different command.</span></span>

<span data-ttu-id="49756-137">El comando `dotnet new` se usa para crear proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="49756-138">La opción `-o WeatherMicroservice` después del comando `dotnet new` se usa para asignar la ubicación para crear la aplicación ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="49756-139">Para este microservicio, queremos la aplicación web más sencilla y más ligera posible, por lo que usamos la plantilla "ASP.NET Core vacío", especificando su nombre corto, `web`.</span><span class="sxs-lookup"><span data-stu-id="49756-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="49756-140">La plantilla crea cuatro archivos:</span><span class="sxs-lookup"><span data-stu-id="49756-140">The template creates four files for you:</span></span>

* <span data-ttu-id="49756-141">Un archivo Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="49756-141">A Startup.cs file.</span></span> <span data-ttu-id="49756-142">Este archivo contiene la base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="49756-143">Un archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="49756-143">A Program.cs file.</span></span> <span data-ttu-id="49756-144">Este archivo contiene el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="49756-145">Un archivo WeatherMicroservice.csproj.</span><span class="sxs-lookup"><span data-stu-id="49756-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="49756-146">Este es el archivo de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-146">This is the build file for the application.</span></span>
* <span data-ttu-id="49756-147">Un archivo Properties/launchSettings.json.</span><span class="sxs-lookup"><span data-stu-id="49756-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="49756-148">Este archivo contiene la configuración de depuración usada por los IDE.</span><span class="sxs-lookup"><span data-stu-id="49756-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="49756-149">Ahora puede ejecutar la aplicación generada por la plantilla:</span><span class="sxs-lookup"><span data-stu-id="49756-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="49756-150">Este comando restaurará en primer lugar las dependencias necesarias para compilar la aplicación y, después, creará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="49756-151">La configuración predeterminada escucha a `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="49756-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="49756-152">Abra un explorador y vaya a esa página. Verá un "¡Hola a todos!".</span><span class="sxs-lookup"><span data-stu-id="49756-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="49756-153">.</span><span class="sxs-lookup"><span data-stu-id="49756-153">message.</span></span>

<span data-ttu-id="49756-154">Cuando haya terminado, puede cerrar la aplicación presionando <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="49756-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="49756-155">Anatomía de una aplicación de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49756-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="49756-156">Ahora que ha creado la aplicación, echemos un vistazo a cómo se implementa esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="49756-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="49756-157">Dos de los archivos generados son especialmente interesantes en este momento: WeatherMicroservice.csproj y Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="49756-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="49756-158">El archivo .csproj contiene información sobre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="49756-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="49756-159">Los dos nodos que son más interesantes son `<TargetFramework>` y `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="49756-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="49756-160">El nodo `<TargetFramework>` especifica la versión de .NET que ejecutará esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="49756-161">Cada nodo `<PackageReference>` se usa para especificar un paquete necesario para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="49756-162">La aplicación se implementa en Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="49756-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="49756-163">Este archivo contiene la clase de inicio.</span><span class="sxs-lookup"><span data-stu-id="49756-163">This file contains the startup class.</span></span>

<span data-ttu-id="49756-164">La infraestructura de ASP.NET Core llama a los dos métodos para configurar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="49756-165">El método `ConfigureServices` describe los servicios que son necesarios para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="49756-166">Va a crear un microservicio de Lean, así que no es necesario configurar ninguna dependencia.</span><span class="sxs-lookup"><span data-stu-id="49756-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="49756-167">El método `Configure` configura los controladores para las solicitudes HTTP entrantes.</span><span class="sxs-lookup"><span data-stu-id="49756-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="49756-168">La plantilla genera un controlador sencillo que responde a cualquier solicitud con el texto "¡Hola a todos!".</span><span class="sxs-lookup"><span data-stu-id="49756-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="49756-169">Creación de un microservicio</span><span class="sxs-lookup"><span data-stu-id="49756-169">Build a microservice</span></span>

<span data-ttu-id="49756-170">El servicio que va a crear proporcionará informes meteorológicos desde cualquier lugar del mundo.</span><span class="sxs-lookup"><span data-stu-id="49756-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="49756-171">En una aplicación de producción, se llamaría a algún servicio para recuperar datos meteorológicos.</span><span class="sxs-lookup"><span data-stu-id="49756-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="49756-172">Para nuestro ejemplo, vamos a generar un pronóstico meteorológico aleatorio.</span><span class="sxs-lookup"><span data-stu-id="49756-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="49756-173">Hay una serie de tareas que debe realizar para implementar nuestro servicio de información meteorológica aleatorio:</span><span class="sxs-lookup"><span data-stu-id="49756-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="49756-174">Analizar la solicitud entrante para leer la latitud y la longitud.</span><span class="sxs-lookup"><span data-stu-id="49756-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="49756-175">Generar algunos datos de pronóstico aleatorios.</span><span class="sxs-lookup"><span data-stu-id="49756-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="49756-176">Convertir estos datos de pronóstico aleatorios de objetos de C# a paquetes JSON.</span><span class="sxs-lookup"><span data-stu-id="49756-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="49756-177">Establecer el encabezado de respuesta para indicar que el servicio devuelve JSON.</span><span class="sxs-lookup"><span data-stu-id="49756-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="49756-178">Escribir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="49756-178">Write the response.</span></span>

<span data-ttu-id="49756-179">Las secciones siguientes le guiarán en cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="49756-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="49756-180">Análisis de la cadena de consulta</span><span class="sxs-lookup"><span data-stu-id="49756-180">Parsing the Query String</span></span>

<span data-ttu-id="49756-181">Para comenzar, analizará la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="49756-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="49756-182">El servicio acepta argumentos "lat" y "long" en la cadena de consulta en este formato:</span><span class="sxs-lookup"><span data-stu-id="49756-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="49756-183">Todos los cambios que debe realzar se encuentran en la expresión lambda definida como el argumento para `app.Run` en la clase de inicio.</span><span class="sxs-lookup"><span data-stu-id="49756-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="49756-184">El argumento en la expresión lambda es el elemento `HttpContext` para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="49756-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="49756-185">Una de sus propiedades es el objeto `Request`.</span><span class="sxs-lookup"><span data-stu-id="49756-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="49756-186">El objeto `Request` tiene una propiedad `Query` que contiene un diccionario de todos los valores en la cadena de consulta de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="49756-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="49756-187">La primera adición consiste en encontrar los valores de latitud y longitud:</span><span class="sxs-lookup"><span data-stu-id="49756-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="49756-188">Los valores del diccionario de `Query` son de tipo `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="49756-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="49756-189">Ese tipo puede contener una colección de cadenas.</span><span class="sxs-lookup"><span data-stu-id="49756-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="49756-190">Para el servicio de información meteorológica, cada valor es una única cadena.</span><span class="sxs-lookup"><span data-stu-id="49756-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="49756-191">Es por eso que existe la llamada a `FirstOrDefault()` en el código anterior.</span><span class="sxs-lookup"><span data-stu-id="49756-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="49756-192">A continuación, debe convertir las cadenas en valores dobles.</span><span class="sxs-lookup"><span data-stu-id="49756-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="49756-193">El método que va a usar para convertir la cadena en un doble es `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="49756-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="49756-194">Este método aprovecha parámetros de salida de C# para indicar si la cadena de entrada se puede convertir en un doble.</span><span class="sxs-lookup"><span data-stu-id="49756-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="49756-195">Si la cadena representa un valor doble válido, el método devuelve true y el argumento `result` contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="49756-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="49756-196">Si la cadena no representa un valor doble válido, el método devuelve false.</span><span class="sxs-lookup"><span data-stu-id="49756-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="49756-197">Puede adaptar dicha API con el uso de un *método de extensión* que devuelve un *valor doble que acepta valores NULL*.</span><span class="sxs-lookup"><span data-stu-id="49756-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="49756-198">Un *tipo de valor que acepta valores NULL* es un tipo que representa algún tipo de valor y también puede contener un valor que falta o un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="49756-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="49756-199">Un tipo que acepta valores NULL se representa mediante la anexión del carácter `?` a la declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="49756-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="49756-200">Los métodos de extensión son métodos que se definen como métodos estáticos, pero al agregar el modificador `this` en el primer parámetro, se pueden llamar como si fueran miembros de esa clase.</span><span class="sxs-lookup"><span data-stu-id="49756-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="49756-201">Los métodos de extensión solo se pueden definir en clases estáticas.</span><span class="sxs-lookup"><span data-stu-id="49756-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="49756-202">Esta es la definición de la clase que contiene el método de extensión para el análisis:</span><span class="sxs-lookup"><span data-stu-id="49756-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="49756-203">Antes de llamar al método de extensión, cambie la referencia cultural actual a invariable:</span><span class="sxs-lookup"><span data-stu-id="49756-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="49756-204">Esto garantiza que la aplicación analiza los números de la misma forma en cualquier servidor, independientemente de su referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49756-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="49756-205">Ahora puede usar el método de extensión para convertir los argumentos de cadena de consulta en el tipo doble:</span><span class="sxs-lookup"><span data-stu-id="49756-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="49756-206">Para probar fácilmente el código de análisis, actualice la respuesta para incluir los valores de los argumentos:</span><span class="sxs-lookup"><span data-stu-id="49756-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="49756-207">En este punto, puede ejecutar la aplicación web y ver si su código de análisis está funcionando.</span><span class="sxs-lookup"><span data-stu-id="49756-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="49756-208">Agregue valores a la solicitud web en un explorador y verá los resultados actualizados.</span><span class="sxs-lookup"><span data-stu-id="49756-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="49756-209">Creación de un pronóstico meteorológico aleatorio</span><span class="sxs-lookup"><span data-stu-id="49756-209">Build a random weather forecast</span></span>

<span data-ttu-id="49756-210">La siguiente tarea consiste en crear un pronóstico meteorológico aleatorio.</span><span class="sxs-lookup"><span data-stu-id="49756-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="49756-211">Comencemos con un contenedor de datos que contiene los valores que desea para un pronóstico meteorológico:</span><span class="sxs-lookup"><span data-stu-id="49756-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="49756-212">A continuación, cree un constructor que establezca esos valores de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="49756-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="49756-213">Este constructor usa los valores de la latitud y la longitud para inicializar el generador de números `Random`.</span><span class="sxs-lookup"><span data-stu-id="49756-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="49756-214">Esto significa que el pronóstico para la misma ubicación es el mismo.</span><span class="sxs-lookup"><span data-stu-id="49756-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="49756-215">Si cambia los argumentos para la latitud y la longitud, obtendrá un pronóstico diferente (ya que comienza con un valor de inicialización diferente).</span><span class="sxs-lookup"><span data-stu-id="49756-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="49756-216">Ahora puede generar el pronóstico de cinco días en el método de respuesta:</span><span class="sxs-lookup"><span data-stu-id="49756-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="49756-217">Compilar la respuesta JSON</span><span class="sxs-lookup"><span data-stu-id="49756-217">Build the JSON response</span></span>

<span data-ttu-id="49756-218">La tarea final de código en el servidor es convertir la lista `WeatherReport` en un documento JSON y devolverla al cliente.</span><span class="sxs-lookup"><span data-stu-id="49756-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="49756-219">Comencemos creando el documento JSON.</span><span class="sxs-lookup"><span data-stu-id="49756-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="49756-220">Agregará el serializador Newtonsoft de JSON a la lista de dependencias.</span><span class="sxs-lookup"><span data-stu-id="49756-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="49756-221">Puede hacerlo mediante el comando `dotnet` siguiente:</span><span class="sxs-lookup"><span data-stu-id="49756-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="49756-222">A continuación, puede usar la clase `JsonConvert` para escribir el objeto en una cadena:</span><span class="sxs-lookup"><span data-stu-id="49756-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="49756-223">El código anterior convierte el objeto de pronóstico (una lista de objetos `WeatherForecast`) en un documento JSON.</span><span class="sxs-lookup"><span data-stu-id="49756-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="49756-224">Después de haber construido el documento de respuesta, establezca el tipo de contenido en `application/json` y escriba la cadena.</span><span class="sxs-lookup"><span data-stu-id="49756-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="49756-225">Ahora, la aplicación se ejecuta y devuelve los pronósticos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="49756-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="49756-226">Creación de una imagen de Docker</span><span class="sxs-lookup"><span data-stu-id="49756-226">Build a Docker image</span></span>

<span data-ttu-id="49756-227">La tarea final es ejecutar la aplicación en Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="49756-228">Vamos a crear un contenedor de Docker que ejecute una imagen de Docker que representa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="49756-229">Una ***imagen de Docker*** es un archivo que define el entorno de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="49756-230">Un ***contenedor de Docker*** representa una instancia en ejecución de una imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="49756-231">Por analogía, puede considerar la *imagen de Docker* como una *clase*y el *contenedor de Docker* como un objeto o una instancia de esa clase.</span><span class="sxs-lookup"><span data-stu-id="49756-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="49756-232">El Dockerfile siguiente servirá para nuestros propósitos:</span><span class="sxs-lookup"><span data-stu-id="49756-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="49756-233">Repasemos su contenido.</span><span class="sxs-lookup"><span data-stu-id="49756-233">Let's go over its contents.</span></span>

<span data-ttu-id="49756-234">La primera línea especifica la imagen de origen que se usa para generar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="49756-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="49756-235">Docker le permite configurar una imagen de máquina basada en una plantilla de origen.</span><span class="sxs-lookup"><span data-stu-id="49756-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="49756-236">Esto significa que no tiene que suministrar todos los parámetros de máquina cuando se inicia, solo tiene que proporcionar los cambios.</span><span class="sxs-lookup"><span data-stu-id="49756-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="49756-237">Aquí los cambios van a ser incluir nuestra aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="49756-238">En este ejemplo, usaremos la versión `2.1-sdk` de la imagen de `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="49756-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="49756-239">Esta es la manera más fácil de crear un entorno de trabajo de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="49756-240">Esta imagen incluye el tiempo de ejecución de .NET Core y el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="49756-241">Esto hace que resulte más fácil empezar a trabajar y compilar, pero también crea una imagen mayor, por lo que usaremos esta imagen para crear la aplicación y otra imagen para ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="49756-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="49756-242">Las siguientes líneas instalan y compilan la aplicación:</span><span class="sxs-lookup"><span data-stu-id="49756-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="49756-243">El archivo de proyecto se copia desde el directorio actual en la máquina virtual de Docker y se restauran todos los paquetes.</span><span class="sxs-lookup"><span data-stu-id="49756-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="49756-244">El uso de la CLI de dotnet significa que la imagen de Docker debe incluir el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="49756-245">Luego, se copia el resto de la aplicación y el comando `dotnet
publish` compila y empaqueta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49756-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="49756-246">Por último, se crea una segunda imagen de Docker que ejecuta la aplicación:</span><span class="sxs-lookup"><span data-stu-id="49756-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="49756-247">Esta imagen usa la versión `2.1-aspnetcore-runtime` de la imagen de `dotnet`, que contiene todos los elementos necesarios para ejecutar aplicaciones de ASP.NET Core, pero no incluye el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="49756-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="49756-248">Esto significa que esta imagen no se puede usar para crear aplicaciones de .NET Core, pero también hace que la imagen final sea menor.</span><span class="sxs-lookup"><span data-stu-id="49756-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="49756-249">Para solucionar este problema, copiamos la aplicación integrada desde la primera imagen en la segunda.</span><span class="sxs-lookup"><span data-stu-id="49756-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="49756-250">El comando `ENTRYPOINT` informa a Docker qué comando inicia el servicio.</span><span class="sxs-lookup"><span data-stu-id="49756-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="49756-251">Compilación y ejecución de la imagen en un contenedor</span><span class="sxs-lookup"><span data-stu-id="49756-251">Building and running the image in a container</span></span>

<span data-ttu-id="49756-252">Vamos a compilar una imagen y ejecutar el servicio dentro de un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="49756-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="49756-253">No desea copiar todos los archivos de su directorio local en la imagen.</span><span class="sxs-lookup"><span data-stu-id="49756-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="49756-254">En su lugar, va a compilar la aplicación en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="49756-255">Creará un archivo `.dockerignore` para especificar los directorios que no se copian en la imagen.</span><span class="sxs-lookup"><span data-stu-id="49756-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="49756-256">No desea copiar ninguno de los recursos de compilación.</span><span class="sxs-lookup"><span data-stu-id="49756-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="49756-257">Especifique los directorios de compilación y publicación en el archivo `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="49756-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="49756-258">Compile la imagen mediante el comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="49756-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="49756-259">Ejecute el siguiente comando desde el directorio que contiene el código.</span><span class="sxs-lookup"><span data-stu-id="49756-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="49756-260">Este comando compila la imagen de contenedor en función de toda la información del Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="49756-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="49756-261">El argumento `-t` proporciona una etiqueta, o nombre, para esta imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="49756-262">En la línea de comandos anterior, la etiqueta usada para el contenedor de Docker es `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="49756-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="49756-263">Cuando termina este comando, tendrá un contenedor listo para ejecutar el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="49756-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="49756-264">Ejecute el siguiente comando para iniciar el contenedor y el servicio:</span><span class="sxs-lookup"><span data-stu-id="49756-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="49756-265">La opción `-d` implica ejecutar el contenedor desasociado del terminal actual.</span><span class="sxs-lookup"><span data-stu-id="49756-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="49756-266">Esto significa que no verá la salida del comando en el terminal.</span><span class="sxs-lookup"><span data-stu-id="49756-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="49756-267">La opción `-p` indica la asignación de puertos entre el servicio y el host.</span><span class="sxs-lookup"><span data-stu-id="49756-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="49756-268">Aquí dice que cualquier solicitud entrante en el puerto 80 se debe reenviar al puerto 80 en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="49756-269">El uso de 80 coincide con el puerto en el que está escuchando el servicio, que es el puerto predeterminado para las aplicaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="49756-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="49756-270">El argumento `--name` nombra el contenedor en ejecución.</span><span class="sxs-lookup"><span data-stu-id="49756-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="49756-271">Es un nombre adecuado que puede usar para trabajar con ese contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="49756-272">Para ver si la imagen se ejecuta, compruebe el comando:</span><span class="sxs-lookup"><span data-stu-id="49756-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="49756-273">Si el contenedor se está ejecutando, verá una línea que lo indica en los procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="49756-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="49756-274">(Puede que sea la única).</span><span class="sxs-lookup"><span data-stu-id="49756-274">(It may be the only one.)</span></span>

<span data-ttu-id="49756-275">Para probar el servicio, abra un explorador y vaya a localhost, luego especifique la latitud y la longitud:</span><span class="sxs-lookup"><span data-stu-id="49756-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="49756-276">Asociación de un contenedor en ejecución</span><span class="sxs-lookup"><span data-stu-id="49756-276">Attaching to a running container</span></span>

<span data-ttu-id="49756-277">Cuando ejecutó el servicio en una ventana de comandos, pudo ver información de diagnóstico impresa para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="49756-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="49756-278">Cuando el contenedor se ejecuta en modo de desconexión, no puede ver esa información.</span><span class="sxs-lookup"><span data-stu-id="49756-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="49756-279">El comando attach de Docker le permite conectarse a un contenedor en ejecución para ver la información de registro.</span><span class="sxs-lookup"><span data-stu-id="49756-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="49756-280">Ejecute este comando desde una ventana de comandos:</span><span class="sxs-lookup"><span data-stu-id="49756-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="49756-281">El argumento `--sig-proxy=false` significa que los comandos <kbd>Ctrl</kbd>+<kbd>C</kbd> no se envían al proceso del contenedor, sino que detienen el comando `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="49756-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="49756-282">El argumento final es el nombre asignado al contenedor en el comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="49756-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="49756-283">También puede usar el Id. de contenedor asignado a Docker para hacer referencia a cualquier contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="49756-284">Si no especifica un nombre para el contenedor en `docker run`, debe usar el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="49756-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="49756-285">Abra un explorador y vaya a su servicio.</span><span class="sxs-lookup"><span data-stu-id="49756-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="49756-286">Verá los mensajes de diagnóstico en las ventanas de comandos desde el contenedor en ejecución conectado.</span><span class="sxs-lookup"><span data-stu-id="49756-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="49756-287">Presione <kbd>Ctrl</kbd>+<kbd>C</kbd> para detener el proceso de conexión.</span><span class="sxs-lookup"><span data-stu-id="49756-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="49756-288">Cuando haya terminado de trabajar con el contenedor, puede detenerlo:</span><span class="sxs-lookup"><span data-stu-id="49756-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="49756-289">El contenedor y la imagen siguen estando disponibles para que los reinicie.</span><span class="sxs-lookup"><span data-stu-id="49756-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="49756-290">Si desea quitar el contenedor de la máquina, use este comando:</span><span class="sxs-lookup"><span data-stu-id="49756-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="49756-291">Si desea quitar imágenes no usadas de la máquina, utilice este comando:</span><span class="sxs-lookup"><span data-stu-id="49756-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="49756-292">Conclusión</span><span class="sxs-lookup"><span data-stu-id="49756-292">Conclusion</span></span> 

<span data-ttu-id="49756-293">En este tutorial, ha compilado un microservicio de ASP.NET Core y ha agregado unas cuantas características sencillas.</span><span class="sxs-lookup"><span data-stu-id="49756-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="49756-294">Ha compilado una imagen de un contenedor de Docker para ese servicio y ha ejecutado ese contenedor en el equipo.</span><span class="sxs-lookup"><span data-stu-id="49756-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="49756-295">Ha conectado una ventana de terminal al servicio y ha visto los mensajes de diagnóstico de su servicio.</span><span class="sxs-lookup"><span data-stu-id="49756-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="49756-296">Por el camino, ha visto varias características del lenguaje C# en acción.</span><span class="sxs-lookup"><span data-stu-id="49756-296">Along the way, you saw several features of the C# language in action.</span></span>
