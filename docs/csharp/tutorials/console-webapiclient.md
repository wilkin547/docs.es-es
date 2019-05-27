---
title: Creación de un cliente de REST con .NET Core
description: Este tutorial le enseña varias características de .NET Core y el lenguaje C#.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: f6e3371a72810b30f804169be4025360aa10c477
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063886"
---
# <a name="rest-client"></a><span data-ttu-id="a20e9-103">Cliente REST</span><span class="sxs-lookup"><span data-stu-id="a20e9-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="a20e9-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="a20e9-104">Introduction</span></span>

<span data-ttu-id="a20e9-105">Este tutorial le enseña varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="a20e9-106">Aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a20e9-106">You’ll learn:</span></span>

* <span data-ttu-id="a20e9-107">Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a20e9-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="a20e9-108">Información general de las características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="a20e9-109">Administración de dependencias con NuGet</span><span class="sxs-lookup"><span data-stu-id="a20e9-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="a20e9-110">Comunicaciones HTTP</span><span class="sxs-lookup"><span data-stu-id="a20e9-110">HTTP Communications</span></span>
* <span data-ttu-id="a20e9-111">Procesamiento de información de JSON</span><span class="sxs-lookup"><span data-stu-id="a20e9-111">Processing JSON information</span></span>
* <span data-ttu-id="a20e9-112">Administración de la configuración con atributos</span><span class="sxs-lookup"><span data-stu-id="a20e9-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="a20e9-113">Creará una aplicación que emite solicitudes HTTP a un servicio REST en GitHub.</span><span class="sxs-lookup"><span data-stu-id="a20e9-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="a20e9-114">Leerá información en formato JSON y convertirá ese paquete JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="a20e9-115">Por último, verá cómo trabajar con objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="a20e9-116">Hay muchas características en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a20e9-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="a20e9-117">Vamos a compilarlas una a una.</span><span class="sxs-lookup"><span data-stu-id="a20e9-117">Let’s build them one by one.</span></span>

<span data-ttu-id="a20e9-118">Si prefiere seguir el [ejemplo final](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) de este tema, puede descargarlo.</span><span class="sxs-lookup"><span data-stu-id="a20e9-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="a20e9-119">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a20e9-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a20e9-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a20e9-120">Prerequisites</span></span>

<span data-ttu-id="a20e9-121">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a20e9-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="a20e9-122">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="a20e9-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="a20e9-123">Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="a20e9-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="a20e9-124">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="a20e9-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="a20e9-125">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="a20e9-126">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="a20e9-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="a20e9-127">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="a20e9-127">Create the Application</span></span>

<span data-ttu-id="a20e9-128">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-128">The first step is to create a new application.</span></span> <span data-ttu-id="a20e9-129">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="a20e9-130">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="a20e9-130">Make that the current directory.</span></span> <span data-ttu-id="a20e9-131">Escriba el comando `dotnet new console` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a20e9-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="a20e9-132">Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="a20e9-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="a20e9-133">Como se trata de un nuevo proyecto, ninguna de las dependencias está en su lugar, así que la primera ejecución descargará .NET Core Framework, instalará un certificado de desarrollo y ejecutará el gestor de paquetes NuGet para restaurar las dependencias que faltan.</span><span class="sxs-lookup"><span data-stu-id="a20e9-133">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework, install a development certificate and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="a20e9-134">Antes de empezar a hacer modificaciones, escriba `dotnet run` ([vea la nota](#dotnet-restore-note)) en el símbolo del sistema para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-134">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="a20e9-135">`dotnet run` ejecuta automáticamente `dotnet restore` si el entorno no tiene dependencias.</span><span class="sxs-lookup"><span data-stu-id="a20e9-135">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="a20e9-136">También ejecuta `dotnet build` si hay que volver a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-136">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="a20e9-137">Después de la instalación inicial, solo tendrá que ejecutar `dotnet restore` o `dotnet build` cuando tenga sentido para su proyecto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-137">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="a20e9-138">Adición de nuevas dependencias</span><span class="sxs-lookup"><span data-stu-id="a20e9-138">Adding New Dependencies</span></span>

<span data-ttu-id="a20e9-139">Uno de los principales objetivos de diseño de .NET Core es minimizar el tamaño de la instalación de .NET.</span><span class="sxs-lookup"><span data-stu-id="a20e9-139">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="a20e9-140">Si una aplicación necesita bibliotecas adicionales para algunas de sus características, agregará esas dependencias al archivo de proyecto (\*.csproj) de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-140">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="a20e9-141">En nuestro ejemplo, deberá agregar el paquete `System.Runtime.Serialization.Json` para que su aplicación pueda procesar respuestas JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-141">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="a20e9-142">Abra el archivo de proyecto `csproj`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-142">Open your `csproj` project file.</span></span> <span data-ttu-id="a20e9-143">La primera línea del archivo debe aparecer como:</span><span class="sxs-lookup"><span data-stu-id="a20e9-143">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="a20e9-144">Agregue lo siguiente inmediatamente después de esta línea:</span><span class="sxs-lookup"><span data-stu-id="a20e9-144">Add the following immediately after this line:</span></span>

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup>
```

<span data-ttu-id="a20e9-145">La mayoría de los editores de código proporcionarán la finalización de las distintas versiones de estas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a20e9-145">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="a20e9-146">Normalmente, querrá usar la versión más reciente de cualquier paquete que agregue.</span><span class="sxs-lookup"><span data-stu-id="a20e9-146">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="a20e9-147">Sin embargo, es importante asegurarse de que las versiones de todos los paquetes coincidan y que también coincida la versión del marco de trabajo de la aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a20e9-147">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="a20e9-148">Una vez realizados estos cambios, ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para que el paquete se instale en el sistema.</span><span class="sxs-lookup"><span data-stu-id="a20e9-148">After you've made these changes, execute `dotnet restore` ([see note](#dotnet-restore-note)) so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="a20e9-149">Realización de las solicitudes web</span><span class="sxs-lookup"><span data-stu-id="a20e9-149">Making Web Requests</span></span>

<span data-ttu-id="a20e9-150">Ahora está listo para comenzar a recuperar datos de la Web.</span><span class="sxs-lookup"><span data-stu-id="a20e9-150">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="a20e9-151">En esta aplicación, leerá información de la [API de GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="a20e9-151">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="a20e9-152">Vamos a leer información sobre los proyectos que aparecen en el paraguas [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="a20e9-152">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="a20e9-153">Para comenzar, realizará la solicitud a la API de GitHub para recuperar información sobre los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a20e9-153">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="a20e9-154">El punto de conexión que usará es: <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-154">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="a20e9-155">Quiere recuperar toda la información sobre estos proyectos, así que usará una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="a20e9-155">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="a20e9-156">El explorador también usa solicitudes HTTP GET, por lo que puede pegar esa dirección URL en él para ver la información que recibirá y procesará.</span><span class="sxs-lookup"><span data-stu-id="a20e9-156">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="a20e9-157">Usará la clase <xref:System.Net.Http.HttpClient> para realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="a20e9-157">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="a20e9-158">Al igual que las API de .NET modernas, <xref:System.Net.Http.HttpClient> admite solo métodos asincrónicos para sus API de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="a20e9-158">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="a20e9-159">Para empezar, cree un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a20e9-159">Start by making an async method.</span></span> <span data-ttu-id="a20e9-160">Rellenará la implementación mientras compila la funcionalidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-160">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="a20e9-161">Para comenzar, abra el archivo `program.cs` en el directorio del proyecto y agregue el siguiente método a la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="a20e9-161">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="a20e9-162">Deberá agregar una instrucción `using` en la parte superior del método `Main` para que el compilador de C# reconozca el tipo <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="a20e9-162">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="a20e9-163">Si compila el proyecto en este momento, obtendrá una advertencia generada para este método, porque no contiene ningún operador `await` y se ejecutará de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="a20e9-163">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="a20e9-164">Por ahora omítala; agregará los operadores `await` a medida que rellena el método.</span><span class="sxs-lookup"><span data-stu-id="a20e9-164">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="a20e9-165">A continuación, cambie el nombre del espacio de nombres definido en la instrucción `namespace` de su valor predeterminado de `ConsoleApp` a `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-165">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="a20e9-166">Más adelante definiremos una clase `repo` en este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a20e9-166">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="a20e9-167">A continuación, actualice el método `Main` para llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="a20e9-167">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="a20e9-168">El método `ProcessRepositories` devuelve una tarea. No debe salir del programa antes de que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="a20e9-168">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="a20e9-169">Por lo tanto, debe usar el método `Wait` para bloquear y esperar a que finalice la tarea:</span><span class="sxs-lookup"><span data-stu-id="a20e9-169">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="a20e9-170">Ahora, tiene un programa que no hace nada, pero lo hace de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a20e9-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="a20e9-171">Vamos a mejorarlo.</span><span class="sxs-lookup"><span data-stu-id="a20e9-171">Let's improve it.</span></span>

<span data-ttu-id="a20e9-172">Primero necesita un objeto capaz de recuperar datos de la Web; para ello, puede usar <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="a20e9-173">Este objeto administra la solicitud y las respuestas.</span><span class="sxs-lookup"><span data-stu-id="a20e9-173">This object handles the request and the responses.</span></span> <span data-ttu-id="a20e9-174">Cree una sola instancia de dicho tipo en la clase `Program` dentro del archivo Program.cs.</span><span class="sxs-lookup"><span data-stu-id="a20e9-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

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

<span data-ttu-id="a20e9-175">Volvamos al método `ProcessRepositories` y rellene una primera versión de él:</span><span class="sxs-lookup"><span data-stu-id="a20e9-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="a20e9-176">También deberá agregar dos nuevas instrucciones using en la parte superior del archivo para compilar esto:</span><span class="sxs-lookup"><span data-stu-id="a20e9-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="a20e9-177">Esta primera versión realiza una solicitud web para leer la lista de todos los repositorios en la organización dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="a20e9-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="a20e9-178">(El id. de gitHub para .NET Foundation es "dotnet").</span><span class="sxs-lookup"><span data-stu-id="a20e9-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="a20e9-179">Las primeras líneas configuran el objeto <xref:System.Net.Http.HttpClient> para esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="a20e9-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="a20e9-180">En primer lugar, se configura para aceptar las respuestas JSON de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a20e9-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="a20e9-181">Este formato es simplemente JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-181">This format is simply JSON.</span></span> <span data-ttu-id="a20e9-182">La siguiente línea agrega un encabezado de agente de usuario a todas las solicitudes desde este objeto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="a20e9-183">Estos dos encabezados se comprueban mediante el código de servidor de GitHub y son necesarios para recuperar información de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a20e9-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="a20e9-184">Después de haber configurado el objeto <xref:System.Net.Http.HttpClient>, realizará una solicitud web y recuperará la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a20e9-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="a20e9-185">En esta primera versión, usa el método de conveniencia <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="a20e9-186">Este método de conveniencia inicia una tarea que realiza la solicitud web y, a continuación, cuando la solicitud se devuelve, lee la secuencia de respuesta y extrae el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a20e9-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="a20e9-187">El cuerpo de la respuesta se devuelve como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="a20e9-188">La cadena está disponible cuando finaliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="a20e9-188">The string is available when the task completes.</span></span>

<span data-ttu-id="a20e9-189">Las dos últimas líneas de este método esperan a la tarea y, luego, imprimen la respuesta en la consola.</span><span class="sxs-lookup"><span data-stu-id="a20e9-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="a20e9-190">Compile la aplicación y ejecútela.</span><span class="sxs-lookup"><span data-stu-id="a20e9-190">Build the app, and run it.</span></span> <span data-ttu-id="a20e9-191">La advertencia de compilación desaparece ahora, porque `ProcessRepositories` contiene ahora un operador `await`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="a20e9-192">Verá una pantalla larga de texto con formato de JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="a20e9-193">Procesamiento del resultado JSON</span><span class="sxs-lookup"><span data-stu-id="a20e9-193">Processing the JSON Result</span></span>

<span data-ttu-id="a20e9-194">Llegados a este punto, ha escrito el código para recuperar una respuesta de un servidor web y mostrar el texto contiene esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="a20e9-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="a20e9-195">A continuación, vamos a convertir esa respuesta JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="a20e9-196">El serializador JSON convierte datos JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-196">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="a20e9-197">La primera tarea consiste en definir un tipo de clase de C# para que contenga la información que se usa de esta respuesta.</span><span class="sxs-lookup"><span data-stu-id="a20e9-197">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="a20e9-198">Vamos a crear esto lentamente, así que comience con un tipo simple de C# que contiene el nombre del repositorio:</span><span class="sxs-lookup"><span data-stu-id="a20e9-198">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

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

<span data-ttu-id="a20e9-199">Coloque el código anterior en un archivo nuevo llamado "repo.cs".</span><span class="sxs-lookup"><span data-stu-id="a20e9-199">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="a20e9-200">Esta versión de la clase representa la ruta de acceso más sencilla de procesar datos JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-200">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="a20e9-201">El nombre de clase y el nombre de miembro coinciden con los nombres usados en el paquete JSON, en lugar de las siguientes convenciones de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-201">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="a20e9-202">Más adelante proporcionará algunos atributos de configuración para corregir esto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-202">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="a20e9-203">Esta clase muestra otra característica importante de la serialización y deserialización de JSON: No todos los campos del paquete JSON forman parte de esta clase.</span><span class="sxs-lookup"><span data-stu-id="a20e9-203">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="a20e9-204">El serializador JSON pasará por alto la información que no esté incluida en el tipo de clase que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a20e9-204">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="a20e9-205">Esta característica facilita la creación de tipos que funcionan con solo un subconjunto de los campos del paquete JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-205">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="a20e9-206">Ahora que ha creado el tipo, vamos a deserializarlo.</span><span class="sxs-lookup"><span data-stu-id="a20e9-206">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="a20e9-207">Deberá crear un objeto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-207">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="a20e9-208">Este objeto debe conocer el tipo CLR esperado para que el paquete JSON se recupere.</span><span class="sxs-lookup"><span data-stu-id="a20e9-208">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="a20e9-209">El paquete de GitHub contiene una secuencia de repositorios, por lo que un tipo `List<repo>` es el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-209">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="a20e9-210">Agregue la línea siguiente al método `ProcessRepositories`:</span><span class="sxs-lookup"><span data-stu-id="a20e9-210">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="a20e9-211">Va a usar dos nuevos espacios de nombres, por lo que también deberá agregarlos:</span><span class="sxs-lookup"><span data-stu-id="a20e9-211">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="a20e9-212">A continuación, usará el serializador para convertir JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-212">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="a20e9-213">Reemplace la llamada a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> en su método `ProcessRepositories` por las dos líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a20e9-213">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="a20e9-214">Tenga en cuenta que ahora usa <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> en lugar de <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-214">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="a20e9-215">El serializador usa una secuencia en lugar de una cadena como su origen.</span><span class="sxs-lookup"><span data-stu-id="a20e9-215">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="a20e9-216">Vamos a explicar algunas características del lenguaje C# que se usan en la segunda línea anterior.</span><span class="sxs-lookup"><span data-stu-id="a20e9-216">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="a20e9-217">El argumento para <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> es una expresión `await`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-217">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="a20e9-218">Las expresiones Await pueden aparecer prácticamente en cualquier parte del código, aunque hasta ahora, únicamente las ha visto como parte de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-218">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="a20e9-219">En segundo lugar, el operador `as` convierte el tipo de tiempo de compilación `object` a `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-219">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span>
<span data-ttu-id="a20e9-220">La declaración de <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declara que devuelve un objeto de tipo <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-220">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a20e9-221"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> devolverá el tipo especificado al construirlo (`List<repo>` en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="a20e9-221"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="a20e9-222">Si la conversión no se realiza correctamente, el operador `as` se evalúa como `null`, en lugar de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="a20e9-222">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="a20e9-223">Casi ha terminado con esta sección.</span><span class="sxs-lookup"><span data-stu-id="a20e9-223">You're almost done with this section.</span></span> <span data-ttu-id="a20e9-224">Ahora que ha convertido el código JSON a objetos de C#, vamos a mostrar el nombre de cada repositorio.</span><span class="sxs-lookup"><span data-stu-id="a20e9-224">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="a20e9-225">Reemplace las líneas donde pone:</span><span class="sxs-lookup"><span data-stu-id="a20e9-225">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="a20e9-226">por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a20e9-226">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="a20e9-227">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a20e9-227">Compile and run the application.</span></span> <span data-ttu-id="a20e9-228">Se imprimirán los nombres de los repositorios que forman parte de .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="a20e9-228">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="a20e9-229">Control de la serialización</span><span class="sxs-lookup"><span data-stu-id="a20e9-229">Controlling Serialization</span></span>

<span data-ttu-id="a20e9-230">Antes de agregar más características, vamos a abordar el tipo `repo` y hacer que siga convenciones de C# más estándar.</span><span class="sxs-lookup"><span data-stu-id="a20e9-230">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="a20e9-231">Para ello, anotará el tipo `repo` con *atributos* que controlan cómo funciona el serializador de JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-231">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="a20e9-232">En su caso, usará estos atributos para definir una asignación entre los nombres de claves JSON y los nombres de miembros y clases de C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-232">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="a20e9-233">Los dos atributos que se usan son <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-233">The two attributes used are the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes.</span></span> <span data-ttu-id="a20e9-234">Por convención, todas las clases de atributo acaban en el sufijo `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-234">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="a20e9-235">Sin embargo, no es necesario usar ese sufijo cuando aplique un atributo.</span><span class="sxs-lookup"><span data-stu-id="a20e9-235">However, you do not need to use that suffix when you apply an attribute.</span></span>

<span data-ttu-id="a20e9-236">Los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> están en una biblioteca diferente, por lo que deberá agregar esa biblioteca a su archivo de proyecto de C# como una dependencia.</span><span class="sxs-lookup"><span data-stu-id="a20e9-236">The <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="a20e9-237">Agregue la siguiente línea a la sección `<ItemGroup>` del archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="a20e9-237">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="a20e9-238">Después de guardar el archivo, ejecute `dotnet restore` ([vea la nota](#dotnet-restore-note)) para recuperar este paquete.</span><span class="sxs-lookup"><span data-stu-id="a20e9-238">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="a20e9-239">A continuación, abra el archivo `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-239">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="a20e9-240">Vamos a cambiar el nombre por Pascal Case y a deletrear totalmente el nombre `Repository`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-240">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="a20e9-241">Queremos asignar nodos "repo" de JSON a este tipo, así que deberá instalar el atributo <xref:System.Runtime.Serialization.DataContractAttribute> en la declaración de clase.</span><span class="sxs-lookup"><span data-stu-id="a20e9-241">We still want to map JSON 'repo' nodes to this type, so you'll need to add the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class declaration.</span></span> <span data-ttu-id="a20e9-242">Establecerá la propiedad `Name` del atributo en el nombre de los nodos JSON que se asignan a este tipo:</span><span class="sxs-lookup"><span data-stu-id="a20e9-242">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="a20e9-243"><xref:System.Runtime.Serialization.DataContractAttribute> es miembro del espacio de nombres <xref:System.Runtime.Serialization>, así que deberá agregar la instrucción `using` adecuada al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="a20e9-243">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="a20e9-244">Ha cambiado el nombre de la clase `repo` por `Repository`, así que deberá hacer el mismo cambio en Program.cs (algunos editores pueden admitir una refactorización de cambio de nombre que realizará este cambio automáticamente):</span><span class="sxs-lookup"><span data-stu-id="a20e9-244">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="a20e9-245">A continuación, vamos a realizar el mismo cambio con el campo `name` mediante la clase <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-245">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="a20e9-246">Realice los siguientes cambios en la declaración del campo `name` en repo.cs:</span><span class="sxs-lookup"><span data-stu-id="a20e9-246">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="a20e9-247">Este cambio significa que debe cambiar el código que escribe el nombre de cada repositorio en program.cs:</span><span class="sxs-lookup"><span data-stu-id="a20e9-247">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="a20e9-248">Realice una acción `dotnet build` seguida de una acción `dotnet run` para asegurarse de que tiene las asignaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="a20e9-248">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="a20e9-249">Debería ver la misma salida que antes.</span><span class="sxs-lookup"><span data-stu-id="a20e9-249">You should see the same output as before.</span></span> <span data-ttu-id="a20e9-250">Antes de procesar más propiedades desde el servidor web, vamos a hacer un cambio más a la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-250">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="a20e9-251">El miembro `Name` es un campo de acceso público.</span><span class="sxs-lookup"><span data-stu-id="a20e9-251">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="a20e9-252">No es una buena práctica orientada a objetos, así que vamos a cambiarlo por una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a20e9-252">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="a20e9-253">Para nuestros propósitos, no necesitamos ejecutar ningún código específico al obtener o establecer la propiedad, pero al cambiar a una propiedad es más sencillo agregar esos cambios más adelante sin interrumpir el código que usa la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-253">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="a20e9-254">Quite la definición de campo y reemplácela por una [propiedad implementada automáticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="a20e9-254">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="a20e9-255">El compilador genera el cuerpo de los descriptores de acceso `get` y `set`, así como un campo privado para almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="a20e9-255">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="a20e9-256">Sería similar al siguiente código que podría escribir a mano:</span><span class="sxs-lookup"><span data-stu-id="a20e9-256">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name
{
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="a20e9-257">Vamos a hacer un cambio más antes de agregar nuevas características.</span><span class="sxs-lookup"><span data-stu-id="a20e9-257">Let's make one more change before adding new features.</span></span> <span data-ttu-id="a20e9-258">El método `ProcessRepositories` puede realizar el trabajo asincrónico y devolver una colección de los repositorios.</span><span class="sxs-lookup"><span data-stu-id="a20e9-258">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="a20e9-259">Vamos a volver a `List<Repository>` desde ese método y a mover el código que escribe la información en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-259">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="a20e9-260">Cambie la signatura de `ProcessRepositories` para devolver una tarea cuyo resultado sea una lista de objetos `Repository`:</span><span class="sxs-lookup"><span data-stu-id="a20e9-260">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="a20e9-261">A continuación, devuelva solo los repositorios después de procesar la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="a20e9-261">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="a20e9-262">El compilador genera el objeto `Task<T>` para la devolución porque ha marcado este método como `async`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-262">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="a20e9-263">A continuación, vamos a modificar el método `Main` para que capture esos resultados y escriba cada nombre de repositorio en la consola.</span><span class="sxs-lookup"><span data-stu-id="a20e9-263">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="a20e9-264">Su método `Main` tiene ahora este aspecto:</span><span class="sxs-lookup"><span data-stu-id="a20e9-264">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="a20e9-265">El acceso a la propiedad `Result` de una tarea se bloquea hasta que finaliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="a20e9-265">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="a20e9-266">Normalmente, preferiría esperar (`await`) a que finalizara la tarea, como en el método `ProcessRepositories`, pero eso no se permite en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-266">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="a20e9-267">Leer más información</span><span class="sxs-lookup"><span data-stu-id="a20e9-267">Reading More Information</span></span>

<span data-ttu-id="a20e9-268">Para terminar esto, vamos a procesar unas cuantas propiedades más del paquete JSON que se envía desde la API de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a20e9-268">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="a20e9-269">No quiere captar toso, sino que con solo agregar unas cuantas propiedades se demostrarán más características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-269">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="a20e9-270">Comencemos por agregar algunos tipos simples más a la definición de clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-270">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="a20e9-271">Agregue estas propiedades a esa clase:</span><span class="sxs-lookup"><span data-stu-id="a20e9-271">Add these properties to that class:</span></span>

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

<span data-ttu-id="a20e9-272">Estas propiedades tienen integradas conversiones de tipo cadena (que es lo que contienen los paquetes JSON) para el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="a20e9-272">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="a20e9-273">Puede que no esté familiarizado con el tipo <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="a20e9-273">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="a20e9-274">Representa un identificador URI, o en este caso, una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="a20e9-274">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="a20e9-275">En el caso de los tipos `Uri` y `int`, si el paquete JSON contiene datos que no se convierten al tipo de destino, la acción de serialización iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="a20e9-275">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="a20e9-276">Una vez agregados estos, actualice el método `Main` para mostrar estos elementos:</span><span class="sxs-lookup"><span data-stu-id="a20e9-276">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="a20e9-277">Como paso final, vamos a agregar la información de la última operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="a20e9-277">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="a20e9-278">El formato de esta información es este en la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="a20e9-278">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="a20e9-279">Ese formato no sigue ninguno de los formatos estándar <xref:System.DateTime> de .NET.</span><span class="sxs-lookup"><span data-stu-id="a20e9-279">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="a20e9-280">Por este motivo, deberá escribir un método de conversión personalizado.</span><span class="sxs-lookup"><span data-stu-id="a20e9-280">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="a20e9-281">Probablemente tampoco querrá la cadena sin formato expuesta a los usuarios de la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-281">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="a20e9-282">Los atributos pueden también ayudarle a controlar eso.</span><span class="sxs-lookup"><span data-stu-id="a20e9-282">Attributes can help control that as well.</span></span> <span data-ttu-id="a20e9-283">En primer lugar, defina una propiedad `private` que contenga la representación de cadena de la fecha y hora de su clase `Repository`:</span><span class="sxs-lookup"><span data-stu-id="a20e9-283">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="a20e9-284">El atributo <xref:System.Runtime.Serialization.DataMemberAttribute> informa al serializador que esta se debe procesar, aunque no sea un miembro público.</span><span class="sxs-lookup"><span data-stu-id="a20e9-284">The <xref:System.Runtime.Serialization.DataMemberAttribute> attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="a20e9-285">A continuación, debe escribir una propiedad pública de solo lectura que convierta la cadena en un objeto <xref:System.DateTime> válido y que devuelva ese objeto <xref:System.DateTime>:</span><span class="sxs-lookup"><span data-stu-id="a20e9-285">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

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

<span data-ttu-id="a20e9-286">Repasemos las nuevas construcciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a20e9-286">Let's go over the new constructs above.</span></span> <span data-ttu-id="a20e9-287">El atributo `IgnoreDataMember` indica al serializador que este tipo no se debe leer ni escribir de cualquier objeto JSON.</span><span class="sxs-lookup"><span data-stu-id="a20e9-287">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="a20e9-288">Esta propiedad contiene solo contiene un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-288">This property contains only a `get` accessor.</span></span> <span data-ttu-id="a20e9-289">No hay descriptor de acceso `set`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-289">There is no `set` accessor.</span></span> <span data-ttu-id="a20e9-290">Así es cómo se define la propiedad de *solo lectura* en C#.</span><span class="sxs-lookup"><span data-stu-id="a20e9-290">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="a20e9-291">(Sí, puede crear propiedades de *solo escritura* en C#, pero su valor es limitado). El método <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analiza una cadena y crea un objeto <xref:System.DateTime> con un formato de fecha proporcionado, y agrega metadatos adicionales a `DateTime` mediante un objeto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="a20e9-291">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="a20e9-292">Si se produce un error en la operación de análisis, el descriptor de acceso de propiedad inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="a20e9-292">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="a20e9-293">Para usar <xref:System.Globalization.CultureInfo.InvariantCulture>, deberá agregar el espacio de nombres <xref:System.Globalization> a las instrucciones `using` en `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="a20e9-293">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="a20e9-294">Finalmente, agregue una instrucción más de salida en la consola y ya estará listo para compilar y ejecutar de nuevo esta aplicación:</span><span class="sxs-lookup"><span data-stu-id="a20e9-294">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="a20e9-295">La versión debe coincidir ahora con el [ejemplo terminado](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="a20e9-295">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="a20e9-296">Conclusión</span><span class="sxs-lookup"><span data-stu-id="a20e9-296">Conclusion</span></span>

<span data-ttu-id="a20e9-297">En este tutorial se ha mostrado cómo realizar solicitudes web, analizar el resultado y visualizar las propiedades de los resultados.</span><span class="sxs-lookup"><span data-stu-id="a20e9-297">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="a20e9-298">También ha agregado nuevos paquetes como dependencias en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a20e9-298">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="a20e9-299">Ha visto algunas de las características del lenguaje C# compatibles con técnicas orientadas a objetos.</span><span class="sxs-lookup"><span data-stu-id="a20e9-299">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
