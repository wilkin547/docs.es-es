---
title: Creación de un cliente de REST con .NET Core
description: Este tutorial le enseña varias características de .NET Core y el lenguaje C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 09eda08f82490070c66d0b290359872c1043b0c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737578"
---
# <a name="rest-client"></a><span data-ttu-id="41b3c-103">Cliente REST</span><span class="sxs-lookup"><span data-stu-id="41b3c-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="41b3c-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="41b3c-104">Introduction</span></span>

<span data-ttu-id="41b3c-105">Este tutorial le enseña varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="41b3c-106">Aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41b3c-106">You’ll learn:</span></span>

* <span data-ttu-id="41b3c-107">Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="41b3c-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="41b3c-108">Información general de las características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="41b3c-109">Administración de dependencias con NuGet</span><span class="sxs-lookup"><span data-stu-id="41b3c-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="41b3c-110">Comunicaciones HTTP</span><span class="sxs-lookup"><span data-stu-id="41b3c-110">HTTP Communications</span></span>
* <span data-ttu-id="41b3c-111">Procesamiento de información de JSON</span><span class="sxs-lookup"><span data-stu-id="41b3c-111">Processing JSON information</span></span>
* <span data-ttu-id="41b3c-112">Administración de la configuración con atributos</span><span class="sxs-lookup"><span data-stu-id="41b3c-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="41b3c-113">Creará una aplicación que emite solicitudes HTTP a un servicio REST en GitHub.</span><span class="sxs-lookup"><span data-stu-id="41b3c-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="41b3c-114">Leerá información en formato JSON y convertirá ese paquete JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="41b3c-115">Por último, verá cómo trabajar con objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="41b3c-116">Este tutorial incluye muchas características.</span><span class="sxs-lookup"><span data-stu-id="41b3c-116">There are many features in this tutorial.</span></span> <span data-ttu-id="41b3c-117">Vamos a compilarlas una a una.</span><span class="sxs-lookup"><span data-stu-id="41b3c-117">Let’s build them one by one.</span></span>

<span data-ttu-id="41b3c-118">Si prefiere seguir el [ejemplo final](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) de este tema, puede descargarlo.</span><span class="sxs-lookup"><span data-stu-id="41b3c-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="41b3c-119">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="41b3c-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41b3c-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="41b3c-120">Prerequisites</span></span>

<span data-ttu-id="41b3c-121">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="41b3c-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="41b3c-122">Puede encontrar las instrucciones de instalación en la página [Descargas de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="41b3c-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="41b3c-123">Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="41b3c-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="41b3c-124">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="41b3c-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="41b3c-125">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="41b3c-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="41b3c-126">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="41b3c-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="41b3c-127">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="41b3c-127">Create the Application</span></span>

<span data-ttu-id="41b3c-128">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-128">The first step is to create a new application.</span></span> <span data-ttu-id="41b3c-129">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="41b3c-130">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="41b3c-130">Make that the current directory.</span></span> <span data-ttu-id="41b3c-131">Escriba el siguiente comando en la ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="41b3c-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="41b3c-132">Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="41b3c-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="41b3c-133">El nombre del proyecto es "WebApiClient".</span><span class="sxs-lookup"><span data-stu-id="41b3c-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="41b3c-134">Como se trata de un proyecto nuevo, ninguna de las dependencias está en su lugar,</span><span class="sxs-lookup"><span data-stu-id="41b3c-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="41b3c-135">así que la primera ejecución descargará .NET Core Framework, instalará un certificado de desarrollo y ejecutará el gestor de paquetes NuGet para restaurar las dependencias que faltan.</span><span class="sxs-lookup"><span data-stu-id="41b3c-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="41b3c-136">Antes de empezar a hacer modificaciones, escriba `dotnet run` ([vea la nota](#dotnet-restore-note)) en el símbolo del sistema para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="41b3c-137">`dotnet run` ejecuta automáticamente `dotnet restore` si el entorno no tiene dependencias.</span><span class="sxs-lookup"><span data-stu-id="41b3c-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="41b3c-138">También ejecuta `dotnet build` si hay que volver a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="41b3c-139">Después de la instalación inicial, solo tendrá que ejecutar `dotnet restore` o `dotnet build` cuando tenga sentido para su proyecto.</span><span class="sxs-lookup"><span data-stu-id="41b3c-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="41b3c-140">Adición de nuevas dependencias</span><span class="sxs-lookup"><span data-stu-id="41b3c-140">Adding New Dependencies</span></span>

<span data-ttu-id="41b3c-141">Uno de los principales objetivos de diseño de .NET Core es minimizar el tamaño de la instalación de .NET.</span><span class="sxs-lookup"><span data-stu-id="41b3c-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="41b3c-142">Si una aplicación necesita bibliotecas adicionales para algunas de sus características, agregará esas dependencias al archivo de proyecto (\*.csproj) de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="41b3c-143">En nuestro ejemplo, deberá agregar el paquete `System.Runtime.Serialization.Json` para que su aplicación pueda procesar respuestas JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="41b3c-144">Necesitará el paquete `System.Runtime.Serialization.Json` para esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="41b3c-145">Agréguelo al proyecto ejecutando el siguiente comando de la [CLI de .NET](../../core/tools/dotnet-add-package.md):</span><span class="sxs-lookup"><span data-stu-id="41b3c-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="41b3c-146">Realización de las solicitudes web</span><span class="sxs-lookup"><span data-stu-id="41b3c-146">Making Web Requests</span></span>

<span data-ttu-id="41b3c-147">Ahora está listo para comenzar a recuperar datos de la Web.</span><span class="sxs-lookup"><span data-stu-id="41b3c-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="41b3c-148">En esta aplicación, leerá información de la [API de GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="41b3c-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="41b3c-149">Vamos a leer información sobre los proyectos que aparecen en el paraguas [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="41b3c-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="41b3c-150">Para comenzar, realizará la solicitud a la API de GitHub para recuperar información sobre los proyectos.</span><span class="sxs-lookup"><span data-stu-id="41b3c-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="41b3c-151">El punto de conexión que usará es: <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="41b3c-152">Quiere recuperar toda la información sobre estos proyectos, así que usará una solicitud HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="41b3c-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="41b3c-153">El explorador también usa solicitudes HTTP GET, por lo que puede pegar esa dirección URL en él para ver la información que recibirá y procesará.</span><span class="sxs-lookup"><span data-stu-id="41b3c-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="41b3c-154">Usará la clase <xref:System.Net.Http.HttpClient> para realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="41b3c-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="41b3c-155">Al igual que las API de .NET modernas, <xref:System.Net.Http.HttpClient> admite solo métodos asincrónicos para sus API de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="41b3c-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="41b3c-156">Para empezar, cree un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="41b3c-156">Start by making an async method.</span></span> <span data-ttu-id="41b3c-157">Rellenará la implementación mientras compila la funcionalidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="41b3c-158">Para comenzar, abra el archivo `program.cs` en el directorio del proyecto y agregue el siguiente método a la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="41b3c-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="41b3c-159">Tiene que agregar una directiva `using` en la parte superior del método `Main` para que el compilador de C# reconozca el tipo <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="41b3c-159">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="41b3c-160">Si compila el proyecto en este momento, obtendrá una advertencia generada para este método, porque no contiene ningún operador `await` y se ejecutará de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="41b3c-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="41b3c-161">Por ahora omítala; agregará los operadores `await` a medida que rellena el método.</span><span class="sxs-lookup"><span data-stu-id="41b3c-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="41b3c-162">A continuación, cambie el nombre del espacio de nombres definido en la instrucción `namespace` de su valor predeterminado de `ConsoleApp` a `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="41b3c-163">Más adelante definiremos una clase `repo` en este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="41b3c-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="41b3c-164">A continuación, actualice el método `Main` para llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="41b3c-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="41b3c-165">El método `ProcessRepositories` devuelve una tarea. No debe salir del programa antes de que esta finalice.</span><span class="sxs-lookup"><span data-stu-id="41b3c-165">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="41b3c-166">Por lo tanto, debe cambiar la firma de `Main`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="41b3c-167">Agregue el modificador `async` y cambie el tipo de valor devuelto a `Task`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="41b3c-168">A continuación, en el cuerpo del método, agregue una llamada a `ProcessRepositories`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="41b3c-169">Agregue la palabra clave `await` a esa llamada al método:</span><span class="sxs-lookup"><span data-stu-id="41b3c-169">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="41b3c-170">Ahora, tiene un programa que no hace nada, pero lo hace de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="41b3c-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="41b3c-171">Vamos a mejorarlo.</span><span class="sxs-lookup"><span data-stu-id="41b3c-171">Let's improve it.</span></span>

<span data-ttu-id="41b3c-172">Primero necesita un objeto capaz de recuperar datos de la Web; para ello, puede usar <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="41b3c-173">Este objeto administra la solicitud y las respuestas.</span><span class="sxs-lookup"><span data-stu-id="41b3c-173">This object handles the request and the responses.</span></span> <span data-ttu-id="41b3c-174">Cree una sola instancia de ese tipo en la clase `Program`, dentro del archivo *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="41b3c-174">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="41b3c-175">Volvamos al método `ProcessRepositories` y rellene una primera versión de él:</span><span class="sxs-lookup"><span data-stu-id="41b3c-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="41b3c-176">También tiene que agregar dos nuevas directivas `using` en la parte superior del archivo para que este se compile:</span><span class="sxs-lookup"><span data-stu-id="41b3c-176">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="41b3c-177">Esta primera versión realiza una solicitud web para leer la lista de todos los repositorios en la organización dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="41b3c-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="41b3c-178">(El id. de gitHub para .NET Foundation es "dotnet").</span><span class="sxs-lookup"><span data-stu-id="41b3c-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="41b3c-179">Las primeras líneas configuran el objeto <xref:System.Net.Http.HttpClient> para esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="41b3c-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="41b3c-180">En primer lugar, se configura para aceptar las respuestas JSON de GitHub.</span><span class="sxs-lookup"><span data-stu-id="41b3c-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="41b3c-181">Este formato es simplemente JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-181">This format is simply JSON.</span></span> <span data-ttu-id="41b3c-182">La siguiente línea agrega un encabezado de agente de usuario a todas las solicitudes desde este objeto.</span><span class="sxs-lookup"><span data-stu-id="41b3c-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="41b3c-183">Estos dos encabezados se comprueban mediante el código de servidor de GitHub y son necesarios para recuperar información de GitHub.</span><span class="sxs-lookup"><span data-stu-id="41b3c-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="41b3c-184">Después de haber configurado el objeto <xref:System.Net.Http.HttpClient>, realizará una solicitud web y recuperará la respuesta.</span><span class="sxs-lookup"><span data-stu-id="41b3c-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="41b3c-185">En esta primera versión, usa el método de conveniencia <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="41b3c-186">Este método de conveniencia inicia una tarea que realiza la solicitud web y, a continuación, cuando la solicitud se devuelve, lee la secuencia de respuesta y extrae el contenido de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="41b3c-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="41b3c-187">El cuerpo de la respuesta se devuelve como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="41b3c-188">La cadena está disponible cuando finaliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="41b3c-188">The string is available when the task completes.</span></span>

<span data-ttu-id="41b3c-189">Las dos últimas líneas de este método esperan a la tarea y, luego, imprimen la respuesta en la consola.</span><span class="sxs-lookup"><span data-stu-id="41b3c-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="41b3c-190">Compile la aplicación y ejecútela.</span><span class="sxs-lookup"><span data-stu-id="41b3c-190">Build the app, and run it.</span></span> <span data-ttu-id="41b3c-191">La advertencia de compilación desaparece ahora, porque `ProcessRepositories` contiene ahora un operador `await`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="41b3c-192">Verá una pantalla larga de texto con formato de JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="41b3c-193">Procesamiento del resultado JSON</span><span class="sxs-lookup"><span data-stu-id="41b3c-193">Processing the JSON Result</span></span>

<span data-ttu-id="41b3c-194">Llegados a este punto, ha escrito el código para recuperar una respuesta de un servidor web y mostrar el texto contiene esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="41b3c-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="41b3c-195">A continuación, vamos a convertir esa respuesta JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="41b3c-196">La clase <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> serializa objetos a JSON y deserializa JSON en objetos.</span><span class="sxs-lookup"><span data-stu-id="41b3c-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="41b3c-197">Empiece por definir una clase para representar el objeto JSON `repo` devuelto desde la API de GitHub:</span><span class="sxs-lookup"><span data-stu-id="41b3c-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="41b3c-198">Coloque el código anterior en un archivo nuevo llamado "repo.cs".</span><span class="sxs-lookup"><span data-stu-id="41b3c-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="41b3c-199">Esta versión de la clase representa la ruta de acceso más sencilla de procesar datos JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="41b3c-200">El nombre de clase y el nombre de miembro coinciden con los nombres usados en el paquete JSON, en lugar de las siguientes convenciones de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="41b3c-201">Más adelante proporcionará algunos atributos de configuración para corregir esto.</span><span class="sxs-lookup"><span data-stu-id="41b3c-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="41b3c-202">Esta clase muestra otra característica importante de la serialización y deserialización de JSON: No todos los campos del paquete JSON forman parte de esta clase.</span><span class="sxs-lookup"><span data-stu-id="41b3c-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="41b3c-203">El serializador JSON pasará por alto la información que no esté incluida en el tipo de clase que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="41b3c-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="41b3c-204">Esta característica facilita la creación de tipos que funcionan con solo un subconjunto de los campos del paquete JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="41b3c-205">Ahora que ha creado el tipo, vamos a deserializarlo.</span><span class="sxs-lookup"><span data-stu-id="41b3c-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="41b3c-206">A continuación, usará el serializador para convertir JSON en objetos de C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="41b3c-207">Reemplace la llamada a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> en su método `ProcessRepositories` por las tres líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="41b3c-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="41b3c-208">Está usando un nuevo espacio de nombres, por lo que deberá agregarlo también en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="41b3c-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="41b3c-209">Tenga en cuenta que ahora usa <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> en lugar de <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="41b3c-210">El serializador usa una secuencia en lugar de una cadena como su origen.</span><span class="sxs-lookup"><span data-stu-id="41b3c-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="41b3c-211">Vamos a explicar algunas características del lenguaje C# que se usan en la segunda línea del fragmento de código anterior.</span><span class="sxs-lookup"><span data-stu-id="41b3c-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="41b3c-212">El primer argumento para <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> es una expresión `await`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="41b3c-213">Los otros dos parámetros son opcionales y se omiten en el fragmento de código. Las expresiones Await pueden aparecer prácticamente en cualquier parte del código, aunque hasta ahora, únicamente las ha visto como parte de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="41b3c-214">El método `Deserialize` es *genérico*, lo que significa que debe proporcionar argumentos de tipo para el tipo de objetos que se debe crear a partir del texto JSON.</span><span class="sxs-lookup"><span data-stu-id="41b3c-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="41b3c-215">En este ejemplo, se va a deserializar a un `List<Repository>`, que es otro objeto genérico, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="41b3c-216">La clase `List<>` administra una colección de objetos.</span><span class="sxs-lookup"><span data-stu-id="41b3c-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="41b3c-217">El argumento de tipo declara el tipo de objetos almacenados en `List<>`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="41b3c-218">El texto JSON representa una colección de objetos de repositorio, por lo que el argumento de tipo es `Repository`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="41b3c-219">Casi ha terminado con esta sección.</span><span class="sxs-lookup"><span data-stu-id="41b3c-219">You're almost done with this section.</span></span> <span data-ttu-id="41b3c-220">Ahora que ha convertido el código JSON a objetos de C#, vamos a mostrar el nombre de cada repositorio.</span><span class="sxs-lookup"><span data-stu-id="41b3c-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="41b3c-221">Reemplace las líneas donde pone:</span><span class="sxs-lookup"><span data-stu-id="41b3c-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="41b3c-222">por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41b3c-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="41b3c-223">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="41b3c-223">Compile and run the application.</span></span> <span data-ttu-id="41b3c-224">Se imprimirán los nombres de los repositorios que forman parte de .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="41b3c-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="41b3c-225">Control de la serialización</span><span class="sxs-lookup"><span data-stu-id="41b3c-225">Controlling Serialization</span></span>

<span data-ttu-id="41b3c-226">Antes de agregar más características, vamos a abordar la propiedad `name` mediante el atributo `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="41b3c-227">Realice los siguientes cambios en la declaración del campo `name` en repo.cs:</span><span class="sxs-lookup"><span data-stu-id="41b3c-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="41b3c-228">Para usar el atributo `[JsonPropertyName]`, tiene que agregar el espacio de nombres <xref:System.Text.Json.Serialization> a las directivas `using`:</span><span class="sxs-lookup"><span data-stu-id="41b3c-228">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="41b3c-229">Este cambio significa que debe cambiar el código que escribe el nombre de cada repositorio en program.cs:</span><span class="sxs-lookup"><span data-stu-id="41b3c-229">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="41b3c-230">Ejecute `dotnet run` para asegurarse de que tiene las asignaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="41b3c-230">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="41b3c-231">Debería ver la misma salida que antes.</span><span class="sxs-lookup"><span data-stu-id="41b3c-231">You should see the same output as before.</span></span>

<span data-ttu-id="41b3c-232">Vamos a hacer un cambio más antes de agregar nuevas características.</span><span class="sxs-lookup"><span data-stu-id="41b3c-232">Let's make one more change before adding new features.</span></span> <span data-ttu-id="41b3c-233">El método `ProcessRepositories` puede realizar el trabajo asincrónico y devolver una colección de los repositorios.</span><span class="sxs-lookup"><span data-stu-id="41b3c-233">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="41b3c-234">Vamos a volver a `List<Repository>` desde ese método y a mover el código que escribe la información en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-234">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="41b3c-235">Cambie la signatura de `ProcessRepositories` para devolver una tarea cuyo resultado sea una lista de objetos `Repository`:</span><span class="sxs-lookup"><span data-stu-id="41b3c-235">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="41b3c-236">A continuación, devuelva solo los repositorios después de procesar la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="41b3c-236">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="41b3c-237">El compilador genera el objeto `Task<T>` para la devolución porque ha marcado este método como `async`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-237">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="41b3c-238">A continuación, vamos a modificar el método `Main` para que capture esos resultados y escriba cada nombre de repositorio en la consola.</span><span class="sxs-lookup"><span data-stu-id="41b3c-238">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="41b3c-239">Su método `Main` tiene ahora este aspecto:</span><span class="sxs-lookup"><span data-stu-id="41b3c-239">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="41b3c-240">Leer más información</span><span class="sxs-lookup"><span data-stu-id="41b3c-240">Reading More Information</span></span>

<span data-ttu-id="41b3c-241">Para terminar esto, vamos a procesar unas cuantas propiedades más del paquete JSON que se envía desde la API de GitHub.</span><span class="sxs-lookup"><span data-stu-id="41b3c-241">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="41b3c-242">No quiere captar toso, sino que con solo agregar unas cuantas propiedades se demostrarán más características del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-242">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="41b3c-243">Comencemos por agregar algunos tipos simples más a la definición de clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-243">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="41b3c-244">Agregue estas propiedades a esa clase:</span><span class="sxs-lookup"><span data-stu-id="41b3c-244">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="41b3c-245">Estas propiedades tienen integradas conversiones de tipo cadena (que es lo que contienen los paquetes JSON) para el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="41b3c-245">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="41b3c-246">Puede que no esté familiarizado con el tipo <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="41b3c-246">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="41b3c-247">Representa un identificador URI, o en este caso, una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="41b3c-247">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="41b3c-248">En el caso de los tipos `Uri` y `int`, si el paquete JSON contiene datos que no se convierten al tipo de destino, la acción de serialización iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="41b3c-248">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="41b3c-249">Una vez agregados estos, actualice el método `Main` para mostrar estos elementos:</span><span class="sxs-lookup"><span data-stu-id="41b3c-249">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="41b3c-250">Como paso final, vamos a agregar la información de la última operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="41b3c-250">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="41b3c-251">El formato de esta información es este en la respuesta JSON:</span><span class="sxs-lookup"><span data-stu-id="41b3c-251">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="41b3c-252">Ese formato no sigue ninguno de los formatos estándar <xref:System.DateTime> de .NET.</span><span class="sxs-lookup"><span data-stu-id="41b3c-252">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="41b3c-253">Por este motivo, deberá escribir un método de conversión personalizado.</span><span class="sxs-lookup"><span data-stu-id="41b3c-253">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="41b3c-254">Probablemente tampoco querrá la cadena sin formato expuesta a los usuarios de la clase `Repository`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-254">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="41b3c-255">Los atributos pueden también ayudarle a controlar eso.</span><span class="sxs-lookup"><span data-stu-id="41b3c-255">Attributes can help control that as well.</span></span> <span data-ttu-id="41b3c-256">En primer lugar, defina una propiedad `public` que contendrá la representación de cadena de la fecha y hora en la clase `Repository` y una propiedad `LastPush` `readonly` que devuelve una cadena con formato que representa la fecha devuelta:</span><span class="sxs-lookup"><span data-stu-id="41b3c-256">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="41b3c-257">Vamos a repasar las nuevas construcciones que acabamos de definir.</span><span class="sxs-lookup"><span data-stu-id="41b3c-257">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="41b3c-258">La propiedad `LastPush` se define utilizando un *miembro con forma de expresión* para el descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-258">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="41b3c-259">No hay descriptor de acceso `set`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-259">There is no `set` accessor.</span></span> <span data-ttu-id="41b3c-260">Omitiendo el descriptor de acceso `set` es la forma en que se define una propiedad *de solo lectura* en C#.</span><span class="sxs-lookup"><span data-stu-id="41b3c-260">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="41b3c-261">(Sí, puede crear propiedades de *solo escritura* en C#, pero su valor es limitado). El método <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analiza una cadena y crea un objeto <xref:System.DateTime> con un formato de fecha proporcionado, y agrega metadatos adicionales a `DateTime` mediante un objeto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="41b3c-261">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="41b3c-262">Si se produce un error en la operación de análisis, el descriptor de acceso de propiedad inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="41b3c-262">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="41b3c-263">Para usar <xref:System.Globalization.CultureInfo.InvariantCulture>, tiene que agregar el espacio de nombres <xref:System.Globalization> a las directivas `using` de `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="41b3c-263">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` directives in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="41b3c-264">Finalmente, agregue una instrucción más de salida en la consola y ya estará listo para compilar y ejecutar de nuevo esta aplicación:</span><span class="sxs-lookup"><span data-stu-id="41b3c-264">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="41b3c-265">La versión debe coincidir ahora con el [ejemplo terminado](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="41b3c-265">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="41b3c-266">Conclusión</span><span class="sxs-lookup"><span data-stu-id="41b3c-266">Conclusion</span></span>

<span data-ttu-id="41b3c-267">En este tutorial se ha mostrado cómo realizar solicitudes web, analizar el resultado y visualizar las propiedades de los resultados.</span><span class="sxs-lookup"><span data-stu-id="41b3c-267">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="41b3c-268">También ha agregado nuevos paquetes como dependencias en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="41b3c-268">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="41b3c-269">Ha visto algunas de las características del lenguaje C# compatibles con técnicas orientadas a objetos.</span><span class="sxs-lookup"><span data-stu-id="41b3c-269">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
