---
title: "Creación de un cliente de REST con .NET Core"
description: "Este tutorial le enseña varias características de .NET Core y el lenguaje C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 6b0f3acc3a6dbed4f44497d92d3c518ee5a5d2a7
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2018
---
# <a name="rest-client"></a><span data-ttu-id="7bb64-104">Cliente REST</span><span class="sxs-lookup"><span data-stu-id="7bb64-104">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="7bb64-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="7bb64-105">Introduction</span></span>
<span data-ttu-id="7bb64-106">Este tutorial le enseña varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="7bb64-107">Aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bb64-107">You’ll learn:</span></span>
*   <span data-ttu-id="7bb64-108">Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7bb64-108">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="7bb64-109">Información general de las características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-109">An overview of C# Language features.</span></span>
*   <span data-ttu-id="7bb64-110">Administración de dependencias con NuGet</span><span class="sxs-lookup"><span data-stu-id="7bb64-110">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="7bb64-111">Comunicaciones HTTP</span><span class="sxs-lookup"><span data-stu-id="7bb64-111">HTTP Communications</span></span>
*   <span data-ttu-id="7bb64-112">Procesamiento de información de JSON</span><span class="sxs-lookup"><span data-stu-id="7bb64-112">Processing JSON information</span></span>
*   <span data-ttu-id="7bb64-113">Administración de la configuración con atributos</span><span class="sxs-lookup"><span data-stu-id="7bb64-113">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="7bb64-114">Creará una aplicación que emite solicitudes HTTP a un servicio REST en GitHub.</span><span class="sxs-lookup"><span data-stu-id="7bb64-114">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="7bb64-115">Leerá información en formato JSON y convertirá ese paquete JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-115">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="7bb64-116">Por último, verá cómo trabajar con objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-116">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="7bb64-117">Hay muchas características en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7bb64-117">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="7bb64-118">Vamos a compilarlas una a una.</span><span class="sxs-lookup"><span data-stu-id="7bb64-118">Let’s build them one by one.</span></span>

<span data-ttu-id="7bb64-119">Si prefiere seguir el [ejemplo final](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) de este tema, puede descargarlo.</span><span class="sxs-lookup"><span data-stu-id="7bb64-119">If you prefer to follow along with the [final sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="7bb64-120">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="7bb64-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7bb64-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7bb64-121">Prerequisites</span></span>
<span data-ttu-id="7bb64-122">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bb64-122">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="7bb64-123">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="7bb64-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="7bb64-124">Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="7bb64-124">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="7bb64-125">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="7bb64-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="7bb64-126">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="7bb64-127">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="7bb64-127">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="7bb64-128">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="7bb64-128">Create the Application</span></span>
<span data-ttu-id="7bb64-129">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-129">The first step is to create a new application.</span></span> <span data-ttu-id="7bb64-130">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="7bb64-131">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7bb64-131">Make that the current directory.</span></span> <span data-ttu-id="7bb64-132">Escriba el comando `dotnet new console` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7bb64-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="7bb64-133">Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="7bb64-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="7bb64-134">Antes de comenzar a realizar modificaciones, vamos a recorrer los pasos para ejecutar la aplicación Hola a todos sencilla.</span><span class="sxs-lookup"><span data-stu-id="7bb64-134">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="7bb64-135">Después de crear la aplicación, escriba `dotnet restore` ([vea la nota](#dotnet-restore-note)) en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7bb64-135">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="7bb64-136">Este comando ejecuta el proceso de restauración de paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7bb64-136">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="7bb64-137">NuGet es un administrador de paquetes .NET.</span><span class="sxs-lookup"><span data-stu-id="7bb64-137">NuGet is a .NET package manager.</span></span> <span data-ttu-id="7bb64-138">Este comando permite descargar cualquiera de las dependencias que faltan para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-138">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="7bb64-139">Como se trata de un nuevo proyecto, ninguna de las dependencias está en su lugar, así que con la primera ejecución se descargará .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="7bb64-139">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="7bb64-140">Después de este paso inicial, solo deberá ejecutar `dotnet restore` ([vea la nota](#dotnet-restore-note)) al agregar nuevos paquetes dependientes, o actualizar las versiones de cualquiera de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="7bb64-140">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="7bb64-141">Después de restaurar los paquetes, ejecutará `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-141">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="7bb64-142">Esta acción ejecuta el motor de compilación y crea la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-142">This executes the build engine and creates your application.</span></span> <span data-ttu-id="7bb64-143">Por último, ejecute `dotnet run` para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-143">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="7bb64-144">Adición de nuevas dependencias</span><span class="sxs-lookup"><span data-stu-id="7bb64-144">Adding New Dependencies</span></span>
<span data-ttu-id="7bb64-145">Uno de los objetivos de diseño principales para .NET Core es reducir el tamaño de la instalación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7bb64-145">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="7bb64-146">El marco de trabajo de la aplicación .NET Core solo contiene los elementos más comunes del marco completo .NET.</span><span class="sxs-lookup"><span data-stu-id="7bb64-146">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="7bb64-147">Si una aplicación necesita bibliotecas adicionales para algunas de sus características, agregará esas dependencias al archivo de proyecto (\*.csproj) de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-147">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="7bb64-148">En nuestro ejemplo, deberá agregar el paquete `System.Runtime.Serialization.Json` para que su aplicación pueda procesar respuestas JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-148">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="7bb64-149">Abra el archivo de proyecto `csproj`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-149">Open your `csproj` project file.</span></span> <span data-ttu-id="7bb64-150">La primera línea del archivo debe aparecer como:</span><span class="sxs-lookup"><span data-stu-id="7bb64-150">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="7bb64-151">Agregue lo siguiente inmediatamente después de esta línea:</span><span class="sxs-lookup"><span data-stu-id="7bb64-151">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="7bb64-152">La mayoría de los editores de código proporcionarán la finalización de las distintas versiones de estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="7bb64-152">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="7bb64-153">Normalmente, querrá usar la versión más reciente de cualquier paquete que agregue.</span><span class="sxs-lookup"><span data-stu-id="7bb64-153">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="7bb64-154">Sin embargo, es importante asegurarse de que las versiones de todos los paquetes coincidan y que también coincida la versión del marco de trabajo de la aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7bb64-154">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="7bb64-155">Una vez realizados estos cambios, debe ejecutar de nuevo `dotnet restore` ([vea la nota](#dotnet-restore-note)) para que el paquete se instale en su sistema.</span><span class="sxs-lookup"><span data-stu-id="7bb64-155">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="7bb64-156">Realización de las solicitudes web</span><span class="sxs-lookup"><span data-stu-id="7bb64-156">Making Web Requests</span></span>
<span data-ttu-id="7bb64-157">Ahora está listo para comenzar a recuperar datos de la Web.</span><span class="sxs-lookup"><span data-stu-id="7bb64-157">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="7bb64-158">En esta aplicación, leerá información de la [API de GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="7bb64-158">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="7bb64-159">Vamos a leer información sobre los proyectos que aparecen en el paraguas [.NET Foundation](http://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="7bb64-159">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="7bb64-160">Para comenzar, realizará la solicitud a la API de GitHub para recuperar información sobre los proyectos.</span><span class="sxs-lookup"><span data-stu-id="7bb64-160">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="7bb64-161">El punto de conexión que se usará es: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="7bb64-161">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="7bb64-162">Quiere recuperar toda la información sobre estos proyectos, así que usará una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="7bb64-162">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="7bb64-163">El explorador también usa solicitudes HTTP GET, por lo que puede pegar esa dirección URL en él para ver la información que recibirá y procesará.</span><span class="sxs-lookup"><span data-stu-id="7bb64-163">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="7bb64-164">Usará la clase <xref:System.Net.Http.HttpClient> para realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="7bb64-164">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="7bb64-165">Al igual que las API de .NET modernas, <xref:System.Net.Http.HttpClient> admite solo métodos asincrónicos para sus API de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="7bb64-165">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="7bb64-166">Para empezar, cree un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="7bb64-166">Start by making an async method.</span></span> <span data-ttu-id="7bb64-167">Rellenará la implementación mientras compila la funcionalidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-167">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="7bb64-168">Para comenzar, abra el archivo `program.cs` en el directorio del proyecto y agregue el siguiente método a la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="7bb64-168">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="7bb64-169">Deberá agregar una instrucción `using` en la parte superior del método `Main` para que el compilador de C# reconozca el tipo <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="7bb64-169">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="7bb64-170">Si compila el proyecto en este momento, obtendrá una advertencia generada para este método, porque no contiene ningún operador `await` y se ejecutará de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7bb64-170">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="7bb64-171">Por ahora omítala; agregará los operadores `await` a medida que rellena el método.</span><span class="sxs-lookup"><span data-stu-id="7bb64-171">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="7bb64-172">A continuación, cambie el nombre del espacio de nombres definido en la instrucción `namespace` de su valor predeterminado de `ConsoleApp` a `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-172">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="7bb64-173">Más adelante definiremos una clase `repo` en este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7bb64-173">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="7bb64-174">A continuación, actualice el método `Main` para llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="7bb64-174">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="7bb64-175">El método `ProcessRepositories` devuelve una tarea. No debe salir del programa antes de que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="7bb64-175">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="7bb64-176">Por lo tanto, debe usar el método `Wait` para bloquear y esperar a que finalice la tarea:</span><span class="sxs-lookup"><span data-stu-id="7bb64-176">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
public static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="7bb64-177">Ahora, tiene un programa que no hace nada, pero lo hace de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7bb64-177">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="7bb64-178">Vamos a mejorarlo.</span><span class="sxs-lookup"><span data-stu-id="7bb64-178">Let's improve it.</span></span>

<span data-ttu-id="7bb64-179">Primero necesita un objeto capaz de recuperar datos de la Web; para ello, puede usar <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-179">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="7bb64-180">Este objeto administra la solicitud y las respuestas.</span><span class="sxs-lookup"><span data-stu-id="7bb64-180">This object handles the request and the responses.</span></span> <span data-ttu-id="7bb64-181">Cree una sola instancia de dicho tipo en la clase `Program` dentro del archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="7bb64-181">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="7bb64-182">Volvamos al método `ProcessRepositories` y rellene una primera versión de él:</span><span class="sxs-lookup"><span data-stu-id="7bb64-182">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="7bb64-183">También deberá agregar dos nuevas instrucciones using en la parte superior del archivo para compilar esto:</span><span class="sxs-lookup"><span data-stu-id="7bb64-183">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="7bb64-184">Esta primera versión realiza una solicitud web para leer la lista de todos los repositorios en la organización dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="7bb64-184">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="7bb64-185">(El id. de gitHub para .NET Foundation es "dotnet").</span><span class="sxs-lookup"><span data-stu-id="7bb64-185">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="7bb64-186">Las primeras líneas configuran el objeto <xref:System.Net.Http.HttpClient> para esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="7bb64-186">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="7bb64-187">En primer lugar, se configura para aceptar las respuestas JSON de GitHub.</span><span class="sxs-lookup"><span data-stu-id="7bb64-187">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="7bb64-188">Este formato es simplemente JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-188">This format is simply JSON.</span></span> <span data-ttu-id="7bb64-189">La siguiente línea agrega un encabezado de agente de usuario a todas las solicitudes desde este objeto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-189">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="7bb64-190">Estos dos encabezados se comprueban mediante el código de servidor de GitHub y son necesarios para recuperar información de GitHub.</span><span class="sxs-lookup"><span data-stu-id="7bb64-190">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="7bb64-191">Después de haber configurado el objeto <xref:System.Net.Http.HttpClient>, realizará una solicitud web y recuperará la respuesta.</span><span class="sxs-lookup"><span data-stu-id="7bb64-191">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="7bb64-192">En esta primera versión, usa el método de conveniencia <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-192">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="7bb64-193">Este método de conveniencia inicia una tarea que realiza la solicitud web y, a continuación, cuando la solicitud se devuelve, lee la secuencia de respuesta y extrae el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7bb64-193">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="7bb64-194">El cuerpo de la respuesta se devuelve como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-194">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="7bb64-195">La cadena está disponible cuando finaliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="7bb64-195">The string is available when the task completes.</span></span> 

<span data-ttu-id="7bb64-196">Las dos últimas líneas de este método esperan a la tarea y, luego, imprimen la respuesta en la consola.</span><span class="sxs-lookup"><span data-stu-id="7bb64-196">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="7bb64-197">Compile la aplicación y ejecútela.</span><span class="sxs-lookup"><span data-stu-id="7bb64-197">Build the app, and run it.</span></span> <span data-ttu-id="7bb64-198">La advertencia de compilación desaparece ahora, porque `ProcessRepositories` contiene ahora un operador `await`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-198">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="7bb64-199">Verá una pantalla larga de texto con formato de JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-199">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="7bb64-200">Procesamiento del resultado JSON</span><span class="sxs-lookup"><span data-stu-id="7bb64-200">Processing the JSON Result</span></span>

<span data-ttu-id="7bb64-201">Llegados a este punto, ha escrito el código para recuperar una respuesta de un servidor web y mostrar el texto contiene esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="7bb64-201">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="7bb64-202">A continuación, vamos a convertir esa respuesta JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-202">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="7bb64-203">El serializador JSON convierte datos JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-203">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="7bb64-204">La primera tarea consiste en definir un tipo de clase de C# para que contenga la información que se usa de esta respuesta.</span><span class="sxs-lookup"><span data-stu-id="7bb64-204">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="7bb64-205">Vamos a crear esto lentamente, así que comience con un tipo simple de C# que contiene el nombre del repositorio:</span><span class="sxs-lookup"><span data-stu-id="7bb64-205">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="7bb64-206">Coloque el código anterior en un archivo nuevo llamado "repo.cs".</span><span class="sxs-lookup"><span data-stu-id="7bb64-206">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="7bb64-207">Esta versión de la clase representa la ruta de acceso más sencilla de procesar datos JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-207">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="7bb64-208">El nombre de clase y el nombre de miembro coinciden con los nombres usados en el paquete JSON, en lugar de las siguientes convenciones de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-208">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="7bb64-209">Más adelante proporcionará algunos atributos de configuración para corregir esto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-209">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="7bb64-210">Esta clase demuestra otra característica importante de la serialización y deserialización JSON: no todos los campos del paquete JSON forman parte de esta clase.</span><span class="sxs-lookup"><span data-stu-id="7bb64-210">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="7bb64-211">El serializador JSON pasará por alto la información que no esté incluida en el tipo de clase que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7bb64-211">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="7bb64-212">Esta característica facilita la creación de tipos que funcionan con solo un subconjunto de los campos del paquete JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-212">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="7bb64-213">Ahora que ha creado el tipo, vamos a deserializarlo.</span><span class="sxs-lookup"><span data-stu-id="7bb64-213">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="7bb64-214">Deberá crear un objeto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-214">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="7bb64-215">Este objeto debe conocer el tipo CLR esperado para que el paquete JSON se recupere.</span><span class="sxs-lookup"><span data-stu-id="7bb64-215">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="7bb64-216">El paquete de GitHub contiene una secuencia de repositorios, por lo que un tipo `List<repo>` es el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-216">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="7bb64-217">Agregue la línea siguiente al método `ProcessRepositories`:</span><span class="sxs-lookup"><span data-stu-id="7bb64-217">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="7bb64-218">Va a usar dos nuevos espacios de nombres, por lo que también deberá agregarlos:</span><span class="sxs-lookup"><span data-stu-id="7bb64-218">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="7bb64-219">A continuación, usará el serializador para convertir JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-219">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="7bb64-220">Reemplace la llamada a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> en su método `ProcessRepositories` por las dos líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7bb64-220">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="7bb64-221">Tenga en cuenta que ahora usa <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> en lugar de <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-221">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="7bb64-222">El serializador usa una secuencia en lugar de una cadena como su origen.</span><span class="sxs-lookup"><span data-stu-id="7bb64-222">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="7bb64-223">Vamos a explicar algunas características del lenguaje C# que se usan en la segunda línea anterior.</span><span class="sxs-lookup"><span data-stu-id="7bb64-223">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="7bb64-224">El argumento para <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> es una expresión `await`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-224">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="7bb64-225">Las expresiones Await pueden aparecer prácticamente en cualquier parte del código, aunque hasta ahora, únicamente las ha visto como parte de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-225">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="7bb64-226">En segundo lugar, el operador `as` convierte el tipo de tiempo de compilación `object` a `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-226">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="7bb64-227">La declaración de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declara que devuelve un objeto de tipo <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-227">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7bb64-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> devolverá el tipo especificado al construirlo (`List<repo>` en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="7bb64-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="7bb64-229">Si la conversión no se realiza correctamente, el operador `as` se evalúa como `null`, en lugar de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="7bb64-229">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="7bb64-230">Casi ha terminado con esta sección.</span><span class="sxs-lookup"><span data-stu-id="7bb64-230">You're almost done with this section.</span></span> <span data-ttu-id="7bb64-231">Ahora que ha convertido el código JSON a objetos de C#, vamos a mostrar el nombre de cada repositorio.</span><span class="sxs-lookup"><span data-stu-id="7bb64-231">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="7bb64-232">Reemplace las líneas donde pone:</span><span class="sxs-lookup"><span data-stu-id="7bb64-232">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="7bb64-233">por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bb64-233">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="7bb64-234">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7bb64-234">Compile and run the application.</span></span> <span data-ttu-id="7bb64-235">Se imprimirán los nombres de los repositorios que forman parte de .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="7bb64-235">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="7bb64-236">Control de la serialización</span><span class="sxs-lookup"><span data-stu-id="7bb64-236">Controlling Serialization</span></span>

<span data-ttu-id="7bb64-237">Antes de agregar más características, vamos a abordar el tipo `repo` y hacer que siga convenciones de C# más estándar.</span><span class="sxs-lookup"><span data-stu-id="7bb64-237">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="7bb64-238">Para ello, anotará el tipo `repo` con *atributos* que controlan cómo funciona el serializador de JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-238">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="7bb64-239">En su caso, usará estos atributos para definir una asignación entre los nombres de claves JSON y los nombres de miembros y clases de C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-239">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="7bb64-240">Los dos atributos usados son el atributo `DataContract` y el atributo `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-240">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="7bb64-241">Por convención, todas las clases de atributo acaban en el sufijo `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-241">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="7bb64-242">Sin embargo, no es necesario usar ese sufijo cuando aplique un atributo.</span><span class="sxs-lookup"><span data-stu-id="7bb64-242">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="7bb64-243">Los atributos `DataContract` y `DataMember` están en una biblioteca diferente, por lo que deberá agregar esa biblioteca a su archivo de proyecto de C# como una dependencia.</span><span class="sxs-lookup"><span data-stu-id="7bb64-243">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="7bb64-244">Agregue la siguiente línea a la sección `<ItemGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="7bb64-244">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="7bb64-245">Después de guardar el archivo, ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para recuperar este paquete.</span><span class="sxs-lookup"><span data-stu-id="7bb64-245">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="7bb64-246">A continuación, abra el archivo `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-246">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="7bb64-247">Vamos a cambiar el nombre por Pascal Case y a deletrear totalmente el nombre `Repository`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-247">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="7bb64-248">Queremos asignar nodos "repo" de JSON a este tipo, así que deberá instalar el atributo `DataContract` en la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="7bb64-248">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="7bb64-249">Establecerá la propiedad `Name` del atributo en el nombre de los nodos JSON que se asignan a este tipo:</span><span class="sxs-lookup"><span data-stu-id="7bb64-249">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="7bb64-250"><xref:System.Runtime.Serialization.DataContractAttribute> es miembro del espacio de nombres <xref:System.Runtime.Serialization>, así que deberá agregar la instrucción `using` adecuada al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="7bb64-250">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="7bb64-251">Ha cambiado el nombre de la clase `repo` por `Repository`, así que deberá hacer el mismo cambio en Program.cs (algunos editores pueden admitir una refactorización de cambio de nombre que realizará este cambio automáticamente):</span><span class="sxs-lookup"><span data-stu-id="7bb64-251">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="7bb64-252">A continuación, vamos a realizar el mismo cambio con el campo `name` mediante la clase <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-252">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="7bb64-253">Realice los siguientes cambios en la declaración del campo `name` en repo.cs:</span><span class="sxs-lookup"><span data-stu-id="7bb64-253">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="7bb64-254">Este cambio significa que debe cambiar el código que escribe el nombre de cada repositorio en program.cs:</span><span class="sxs-lookup"><span data-stu-id="7bb64-254">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="7bb64-255">Realice una acción `dotnet build` seguida de una acción `dotnet run` para asegurarse de que tiene las asignaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="7bb64-255">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="7bb64-256">Debería ver la misma salida que antes.</span><span class="sxs-lookup"><span data-stu-id="7bb64-256">You should see the same output as before.</span></span> <span data-ttu-id="7bb64-257">Antes de procesar más propiedades desde el servidor web, vamos a hacer un cambio más a la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-257">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="7bb64-258">El miembro `Name` es un campo de acceso público.</span><span class="sxs-lookup"><span data-stu-id="7bb64-258">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="7bb64-259">No es una buena práctica orientada a objetos, así que vamos a cambiarlo por una propiedad.</span><span class="sxs-lookup"><span data-stu-id="7bb64-259">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="7bb64-260">Para nuestros propósitos, no necesitamos ejecutar ningún código específico al obtener o establecer la propiedad, pero al cambiar a una propiedad es más sencillo agregar esos cambios más adelante sin interrumpir el código que usa la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-260">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="7bb64-261">Quite la definición de campo y reemplácela por una [propiedad implementada automáticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="7bb64-261">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="7bb64-262">El compilador genera el cuerpo de los descriptores de acceso `get` y `set`, así como un campo privado para almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="7bb64-262">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="7bb64-263">Sería similar al siguiente código que podría escribir a mano:</span><span class="sxs-lookup"><span data-stu-id="7bb64-263">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="7bb64-264">Vamos a hacer un cambio más antes de agregar nuevas características.</span><span class="sxs-lookup"><span data-stu-id="7bb64-264">Let's make one more change before adding new features.</span></span> <span data-ttu-id="7bb64-265">El método `ProcessRepositories` puede realizar el trabajo asincrónico y devolver una colección de los repositorios.</span><span class="sxs-lookup"><span data-stu-id="7bb64-265">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="7bb64-266">Vamos a volver a `List<Repository>` desde ese método y a mover el código que escribe la información en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-266">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="7bb64-267">Cambie la signatura de `ProcessRepositories` para devolver una tarea cuyo resultado sea una lista de objetos `Repository`:</span><span class="sxs-lookup"><span data-stu-id="7bb64-267">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="7bb64-268">A continuación, devuelva solo los repositorios después de procesar la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="7bb64-268">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="7bb64-269">El compilador genera el objeto `Task<T>` para la devolución porque ha marcado este método como `async`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-269">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="7bb64-270">A continuación, vamos a modificar el método `Main` para que capture esos resultados y escriba cada nombre de repositorio en la consola.</span><span class="sxs-lookup"><span data-stu-id="7bb64-270">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="7bb64-271">Su método `Main` tiene ahora este aspecto:</span><span class="sxs-lookup"><span data-stu-id="7bb64-271">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="7bb64-272">El acceso a la propiedad `Result` de una tarea se bloquea hasta que finaliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="7bb64-272">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="7bb64-273">Normalmente, preferiría esperar (`await`) a que finalizara la tarea, como en el método `ProcessRepositories`, pero eso no se permite en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-273">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="7bb64-274">Leer más información</span><span class="sxs-lookup"><span data-stu-id="7bb64-274">Reading More Information</span></span>

<span data-ttu-id="7bb64-275">Para terminar esto, vamos a procesar unas cuantas propiedades más del paquete JSON que se envía desde la API de GitHub.</span><span class="sxs-lookup"><span data-stu-id="7bb64-275">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="7bb64-276">No quiere captar toso, sino que con solo agregar unas cuantas propiedades se demostrarán más características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-276">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="7bb64-277">Comencemos por agregar algunos tipos simples más a la definición de clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-277">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="7bb64-278">Agregue estas propiedades a esa clase:</span><span class="sxs-lookup"><span data-stu-id="7bb64-278">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="7bb64-279">Estas propiedades tienen integradas conversiones de tipo cadena (que es lo que contienen los paquetes JSON) para el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="7bb64-279">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="7bb64-280">Puede que no esté familiarizado con el tipo <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="7bb64-280">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="7bb64-281">Representa un identificador URI, o en este caso, una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="7bb64-281">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="7bb64-282">En el caso de los tipos `Uri` y `int`, si el paquete JSON contiene datos que no se convierten al tipo de destino, la acción de serialización iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="7bb64-282">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="7bb64-283">Una vez agregados estos, actualice el método `Main` para mostrar estos elementos:</span><span class="sxs-lookup"><span data-stu-id="7bb64-283">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
<span data-ttu-id="7bb64-284">Como paso final, vamos a agregar la información de la última operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="7bb64-284">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="7bb64-285">El formato de esta información es este en la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="7bb64-285">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="7bb64-286">Ese formato no sigue ninguno de los formatos estándar <xref:System.DateTime> de .NET.</span><span class="sxs-lookup"><span data-stu-id="7bb64-286">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="7bb64-287">Por este motivo, deberá escribir un método de conversión personalizado.</span><span class="sxs-lookup"><span data-stu-id="7bb64-287">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="7bb64-288">Probablemente tampoco querrá la cadena sin formato expuesta a los usuarios de la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-288">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="7bb64-289">Los atributos pueden también ayudarle a controlar eso.</span><span class="sxs-lookup"><span data-stu-id="7bb64-289">Attributes can help control that as well.</span></span> <span data-ttu-id="7bb64-290">En primer lugar, defina una propiedad `private` que contenga la representación de cadena de la fecha y hora de su clase `Repository`:</span><span class="sxs-lookup"><span data-stu-id="7bb64-290">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="7bb64-291">El atributo `DataMember` informa al serializador que esta se debe procesar, aunque no sea un miembro público.</span><span class="sxs-lookup"><span data-stu-id="7bb64-291">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="7bb64-292">A continuación, debe escribir una propiedad pública de solo lectura que convierta la cadena en un objeto <xref:System.DateTime> válido y que devuelva ese objeto <xref:System.DateTime>:</span><span class="sxs-lookup"><span data-stu-id="7bb64-292">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="7bb64-293">Repasemos las nuevas construcciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="7bb64-293">Let's go over the new constructs above.</span></span> <span data-ttu-id="7bb64-294">El atributo `IgnoreDataMember` indica al serializador que este tipo no se debe leer ni escribir de cualquier objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="7bb64-294">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="7bb64-295">Esta propiedad contiene solo contiene un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-295">This property contains only a `get` accessor.</span></span> <span data-ttu-id="7bb64-296">No hay descriptor de acceso `set`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-296">There is no `set` accessor.</span></span> <span data-ttu-id="7bb64-297">Así es cómo se define la propiedad de *solo lectura* en C#.</span><span class="sxs-lookup"><span data-stu-id="7bb64-297">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="7bb64-298">(Sí, puede crear propiedades de *solo escritura* en C#, pero su valor es limitado). El método <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analiza una cadena y crea un objeto <xref:System.DateTime> con un formato de fecha proporcionado, y agrega metadatos adicionales a `DateTime` mediante un objeto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="7bb64-298">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="7bb64-299">Si se produce un error en la operación de análisis, el descriptor de acceso de propiedad inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="7bb64-299">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="7bb64-300">Para usar <xref:System.Globalization.CultureInfo.InvariantCulture>, deberá agregar el espacio de nombres <xref:System.Globalization> a las instrucciones `using` en `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="7bb64-300">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="7bb64-301">Finalmente, agregue una instrucción más de salida en la consola y ya estará listo para compilar y ejecutar de nuevo esta aplicación:</span><span class="sxs-lookup"><span data-stu-id="7bb64-301">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="7bb64-302">La versión debe coincidir ahora con el [ejemplo terminado](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="7bb64-302">Your version should now match the [finished sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="7bb64-303">Conclusión</span><span class="sxs-lookup"><span data-stu-id="7bb64-303">Conclusion</span></span>

<span data-ttu-id="7bb64-304">En este tutorial se ha mostrado cómo realizar solicitudes web, analizar el resultado y visualizar las propiedades de los resultados.</span><span class="sxs-lookup"><span data-stu-id="7bb64-304">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="7bb64-305">También ha agregado nuevos paquetes como dependencias en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7bb64-305">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="7bb64-306">Ha visto algunas de las características del lenguaje C# compatibles con técnicas orientadas a objetos.</span><span class="sxs-lookup"><span data-stu-id="7bb64-306">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
