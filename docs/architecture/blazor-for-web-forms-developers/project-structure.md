---
title: Estructura del proyecto para aplicaciones Blazor
description: Conozca cómo se comparan las estructuras de proyecto de ASP.NET proyectos de formularios Web Forms y Blazor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401746"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="98f88-103">Estructura del proyecto para aplicaciones Blazor</span><span class="sxs-lookup"><span data-stu-id="98f88-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="98f88-104">A pesar de sus significativas diferencias en la estructura del proyecto, ASP.NET Web Forms y Blazor comparten muchos conceptos similares.</span><span class="sxs-lookup"><span data-stu-id="98f88-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="98f88-105">Aquí, veremos la estructura de un proyecto Blazor y lo compararemos con un proyecto de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="98f88-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="98f88-106">Para crear su primera aplicación Blazor, siga las instrucciones de los [pasos de introducción de Blazor](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="98f88-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="98f88-107">Puede seguir las instrucciones para crear una aplicación Blazor Server o una aplicación Blazor WebAssembly hospedada en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="98f88-108">A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código de ambos proyectos es el mismo.</span><span class="sxs-lookup"><span data-stu-id="98f88-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="98f88-109">Archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="98f88-109">Project file</span></span>

<span data-ttu-id="98f88-110">Las aplicaciones de Blazor Server son proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="98f88-111">El archivo de proyecto para la aplicación Blazor Server es tan simple como puede obtener:</span><span class="sxs-lookup"><span data-stu-id="98f88-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="98f88-112">El archivo de proyecto para una aplicación Blazor WebAssembly parece un poco más implicado (los números de versión exactos pueden variar):</span><span class="sxs-lookup"><span data-stu-id="98f88-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="98f88-113">Los proyectos blazor WebAssembly tienen como destino .NET Standard en lugar de .NET Core porque se ejecutan en el explorador en un tiempo de ejecución de .NET basado en WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="98f88-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="98f88-114">No puede instalar .NET en un explorador web como en un servidor o equipo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="98f88-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="98f88-115">Por consiguiente, el proyecto hace referencia al marco Blazor utilizando referencias de paquetes individuales.</span><span class="sxs-lookup"><span data-stu-id="98f88-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="98f88-116">En comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *.csproj,* la mayoría de los cuales enumera explícitamente los distintos archivos de código y contenido del proyecto.</span><span class="sxs-lookup"><span data-stu-id="98f88-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="98f88-117">Muchas de las simplificaciones de los proyectos basados en .NET Core y .NET Standard `Microsoft.NET.Sdk.Web` proceden de los destinos predeterminados y las propiedades importadas haciendo referencia al SDK, a menudo denominado simplemente el SDK web.</span><span class="sxs-lookup"><span data-stu-id="98f88-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="98f88-118">El SDK web incluye comodines y otras comodidades que simplifican la inclusión de código y archivos de contenido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="98f88-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="98f88-119">No es necesario enumerar los archivos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="98f88-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="98f88-120">Al tener como destino .NET Core, el SDK web también agrega referencias de marco de trabajo a los marcos compartidos de .NET Core y ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="98f88-121">Los marcos de trabajo son visibles desde **el** > **marcos** de trabajo nodo en el Explorador de **soluciones** ventana.</span><span class="sxs-lookup"><span data-stu-id="98f88-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="98f88-122">Los marcos compartidos son colecciones de ensamblados que se instalaron en el equipo al instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="98f88-123">Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="98f88-124">La mayoría de las dependencias del proyecto se controlan como referencias de paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="98f88-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="98f88-125">Solo necesita hacer referencia a dependencias de paquetes de nivel superior en proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="98f88-126">Las dependencias transitivas se incluyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="98f88-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="98f88-127">En lugar de usar el archivo *packages.config* que se encuentra normalmente en ASP.NET proyectos `<PackageReference>` de formularios Web Forms para hacer referencia a paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el elemento.</span><span class="sxs-lookup"><span data-stu-id="98f88-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="98f88-128">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="98f88-128">Entry point</span></span>

<span data-ttu-id="98f88-129">El punto de entrada de la aplicación Blazor Server se define en el archivo *Program.cs,* como se verá en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="98f88-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="98f88-130">Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con valores predeterminados específicos de las aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="98f88-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="98f88-131">El host web administra el ciclo de vida de la aplicación Blazor Server y configura servicios de nivel de host.</span><span class="sxs-lookup"><span data-stu-id="98f88-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="98f88-132">Ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="98f88-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="98f88-133">Este código es principalmente reutilizable y a menudo se deja sin cambios.</span><span class="sxs-lookup"><span data-stu-id="98f88-133">This code is mostly boilerplate and is often left unchanged.</span></span>

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

<span data-ttu-id="98f88-134">Las aplicaciones Blazor WebAssembly también definen un punto de entrada en *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="98f88-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="98f88-135">El código se ve ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="98f88-135">The code looks slightly different.</span></span> <span data-ttu-id="98f88-136">El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98f88-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="98f88-137">Sin embargo, el host de la aplicación WebAssembly no configura un servidor HTTP porque se ejecuta directamente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="98f88-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="98f88-138">Las aplicaciones Blazor tienen una `Startup` clase en lugar de un archivo *Global.asax* para definir la lógica de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98f88-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="98f88-139">La `Startup` clase se usa para configurar la aplicación y los servicios específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98f88-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="98f88-140">En la aplicación Blazor `Startup` Server, la clase se utiliza para configurar el punto de conexión para la conexión en tiempo real utilizada por Blazor entre los exploradores del cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="98f88-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="98f88-141">En la aplicación Blazor `Startup` WebAssembly, la clase define los componentes raíz de la aplicación y dónde se deben representar.</span><span class="sxs-lookup"><span data-stu-id="98f88-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="98f88-142">Echaremos un vistazo más `Startup` profundo a la clase en la sección Inicio de la [aplicación.](./app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="98f88-143">Archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="98f88-143">Static files</span></span>

<span data-ttu-id="98f88-144">A diferencia de ASP.NET proyectos de formularios Web Forms, no todos los archivos de un proyecto de Blazor se pueden solicitar como archivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="98f88-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="98f88-145">Solo los archivos de la carpeta *wwwroot* son direccionables por la web.</span><span class="sxs-lookup"><span data-stu-id="98f88-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="98f88-146">Esta carpeta se refiere a la "raíz web" de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98f88-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="98f88-147">Cualquier cosa fuera de la raíz web de la aplicación *no es* direccionable a la web.</span><span class="sxs-lookup"><span data-stu-id="98f88-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="98f88-148">Esta configuración proporciona un nivel adicional de seguridad que evita la exposición accidental de archivos de proyecto a través de la web.</span><span class="sxs-lookup"><span data-stu-id="98f88-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="98f88-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="98f88-149">Configuration</span></span>

<span data-ttu-id="98f88-150">La configuración en ASP.NET aplicaciones de formularios Web Forms normalmente se controla mediante uno o varios archivos *web.config.*</span><span class="sxs-lookup"><span data-stu-id="98f88-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="98f88-151">Las aplicaciones blazor normalmente no tienen archivos *web.config.*</span><span class="sxs-lookup"><span data-stu-id="98f88-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="98f88-152">Si lo hacen, el archivo solo se usa para configurar la configuración específica de IIS cuando se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="98f88-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="98f88-153">En su lugar, las aplicaciones de Blazor Server usan las abstracciones de configuración de ASP.NET Core (las aplicaciones Blazor WebAssembly no admiten actualmente las mismas abstracciones de configuración, pero puede ser una característica agregada en el futuro).</span><span class="sxs-lookup"><span data-stu-id="98f88-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="98f88-154">Por ejemplo, la aplicación Blazor Server predeterminada almacena algunos valores en *appsettings.json*.</span><span class="sxs-lookup"><span data-stu-id="98f88-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

<span data-ttu-id="98f88-155">Aprenderemos más sobre la configuración en ASP.NET proyectos Core en la sección [Configuración.](./config.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="98f88-156">Componentes de Razor</span><span class="sxs-lookup"><span data-stu-id="98f88-156">Razor components</span></span>

<span data-ttu-id="98f88-157">La mayoría de los archivos de los proyectos de Blazor son archivos *.razor.*</span><span class="sxs-lookup"><span data-stu-id="98f88-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="98f88-158">Razor es un lenguaje de plantillas basado en HTML y C- que se usa para generar dinámicamente la interfaz de usuario web.</span><span class="sxs-lookup"><span data-stu-id="98f88-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="98f88-159">Los archivos *.razor* definen los componentes que componen la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98f88-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="98f88-160">En su mayor parte, los componentes son idénticos para las aplicaciones Blazor Server y Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="98f88-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="98f88-161">Los componentes de Blazor son análogos a los controles de usuario en ASP.NET formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="98f88-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="98f88-162">Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto.</span><span class="sxs-lookup"><span data-stu-id="98f88-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="98f88-163">La clase generada captura el estado del componente, la lógica de representación, los métodos del ciclo de vida, los controladores de eventos y otra lógica.</span><span class="sxs-lookup"><span data-stu-id="98f88-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="98f88-164">Veremos la creación de componentes en la sección Creación de componentes de interfaz de [usuario reutilizables con Blazor.](./components.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="98f88-165">Los archivos *_Imports.razor* no son archivos de componentes de Razor.</span><span class="sxs-lookup"><span data-stu-id="98f88-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="98f88-166">En su lugar, definen un conjunto de directivas Razor para importar en otros archivos *.razor* dentro de la misma carpeta y en sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="98f88-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="98f88-167">Por ejemplo, un archivo *_Imports.razor* es `using` una forma convencional de agregar instrucciones para espacios de nombres de uso común:</span><span class="sxs-lookup"><span data-stu-id="98f88-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a><span data-ttu-id="98f88-168">Páginas</span><span class="sxs-lookup"><span data-stu-id="98f88-168">Pages</span></span>

<span data-ttu-id="98f88-169">¿Dónde están las páginas de las aplicaciones de Blazor?</span><span class="sxs-lookup"><span data-stu-id="98f88-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="98f88-170">Blazor no define una extensión de archivo independiente para páginas direccionables, como los archivos *.aspx* en ASP.NET aplicaciones de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="98f88-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="98f88-171">En su lugar, las páginas se definen asignando rutas a los componentes.</span><span class="sxs-lookup"><span data-stu-id="98f88-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="98f88-172">Normalmente, una ruta `@page` se asigna mediante la directiva Razor.</span><span class="sxs-lookup"><span data-stu-id="98f88-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="98f88-173">Por ejemplo, `Counter` el componente creado en el archivo *Pages/Counter.razor* define la ruta siguiente:</span><span class="sxs-lookup"><span data-stu-id="98f88-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="98f88-174">El enrutamiento en Blazor se maneja en el lado del cliente, no en el servidor.</span><span class="sxs-lookup"><span data-stu-id="98f88-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="98f88-175">A medida que el usuario navega en el explorador, Blazor intercepta la navegación y, a continuación, representa el componente con la ruta coincidente.</span><span class="sxs-lookup"><span data-stu-id="98f88-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="98f88-176">Las rutas de componentes no se deducen actualmente por la ubicación del archivo del componente como lo son con las páginas *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="98f88-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="98f88-177">Esta función se puede agregar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="98f88-177">This feature may be added in the future.</span></span> <span data-ttu-id="98f88-178">Cada ruta debe especificarse explícitamente en el componente.</span><span class="sxs-lookup"><span data-stu-id="98f88-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="98f88-179">Almacenar componentes enrutables en una carpeta *Pages* no tiene un significado especial y es puramente una convención.</span><span class="sxs-lookup"><span data-stu-id="98f88-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="98f88-180">Veremos con más detalle el enrutamiento en Blazor en la sección [Páginas, enrutamiento y diseños.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="98f88-181">Diseño</span><span class="sxs-lookup"><span data-stu-id="98f88-181">Layout</span></span>

<span data-ttu-id="98f88-182">En ASP.NET aplicaciones de formularios Web Forms, el diseño de página común se controla mediante páginas maestras (*Site.Master*).</span><span class="sxs-lookup"><span data-stu-id="98f88-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="98f88-183">En las aplicaciones blazor, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout.razor*).</span><span class="sxs-lookup"><span data-stu-id="98f88-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="98f88-184">Los componentes de diseño se tratarán con más detalle en la sección [Página, enrutamiento y diseños.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="98f88-185">Bootstrap Blazor</span><span class="sxs-lookup"><span data-stu-id="98f88-185">Bootstrap Blazor</span></span>

<span data-ttu-id="98f88-186">Para arrancar Blazor, la aplicación debe:</span><span class="sxs-lookup"><span data-stu-id="98f88-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="98f88-187">Especifique en qué parte de la página se debe representar el componente raíz (*App.Razor*).</span><span class="sxs-lookup"><span data-stu-id="98f88-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="98f88-188">Agregue el script de marco Blazor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="98f88-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="98f88-189">En la aplicación Blazor Server, la página host del componente raíz se define en el archivo *_Host.cshtml.*</span><span class="sxs-lookup"><span data-stu-id="98f88-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="98f88-190">Este archivo define una página de razor, no un componente.</span><span class="sxs-lookup"><span data-stu-id="98f88-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="98f88-191">Razor Pages usa la sintaxis de Razor para definir una página direccionable por el servidor, muy similar a una página *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="98f88-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="98f88-192">El `Html.RenderComponentAsync<TComponent>(RenderMode)` método se utiliza para definir dónde se debe representar un componente de nivel raíz.</span><span class="sxs-lookup"><span data-stu-id="98f88-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="98f88-193">La `RenderMode` opción indica la forma en que se debe representar el componente.</span><span class="sxs-lookup"><span data-stu-id="98f88-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="98f88-194">En la tabla siguiente `RenderMode` se describen las opciones admitidas.</span><span class="sxs-lookup"><span data-stu-id="98f88-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="98f88-195">Opción</span><span class="sxs-lookup"><span data-stu-id="98f88-195">Option</span></span>                        |<span data-ttu-id="98f88-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="98f88-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="98f88-197">Renderizado interactivamente una vez que se establece una conexión con el navegador</span><span class="sxs-lookup"><span data-stu-id="98f88-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="98f88-198">Primero prerendered y luego renderizado interactivamente</span><span class="sxs-lookup"><span data-stu-id="98f88-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="98f88-199">Representado como contenido estático</span><span class="sxs-lookup"><span data-stu-id="98f88-199">Rendered as static content</span></span>|

<span data-ttu-id="98f88-200">La referencia de script a *_framework/blazor.server.js* establece la conexión en tiempo real con el servidor y, a continuación, se ocupa de todas las interacciones del usuario y actualizaciones de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98f88-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

<span data-ttu-id="98f88-201">En la aplicación Blazor WebAssembly, la página host es un archivo HTML estático simple en *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="98f88-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="98f88-202">El `<app>` elemento se utiliza para indicar dónde se debe representar el componente raíz.</span><span class="sxs-lookup"><span data-stu-id="98f88-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

<span data-ttu-id="98f88-203">El componente específico que se va `Startup.Configure` a representar se configura en el método de la aplicación con un selector CSS correspondiente que indica dónde se debe representar el componente.</span><span class="sxs-lookup"><span data-stu-id="98f88-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a><span data-ttu-id="98f88-204">Resultado de la compilación</span><span class="sxs-lookup"><span data-stu-id="98f88-204">Build output</span></span>

<span data-ttu-id="98f88-205">Cuando se compila un proyecto de Blazor, todos los archivos de código y componentes de Razor se compilan en un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98f88-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="98f88-206">A diferencia de ASP.NET proyectos de formularios Web Forms, Blazor no admite la compilación en tiempo de ejecución de la lógica de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98f88-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="98f88-207">Ejecución la aplicación</span><span class="sxs-lookup"><span data-stu-id="98f88-207">Run the app</span></span>

<span data-ttu-id="98f88-208">Para ejecutar la aplicación Blazor Server, presione `F5` en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98f88-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="98f88-209">Las aplicaciones blazor no admiten la compilación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="98f88-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="98f88-210">Para ver los resultados de los cambios de marcado de código y componentes, vuelva a generar y reinicie la aplicación con el depurador adjunto.</span><span class="sxs-lookup"><span data-stu-id="98f88-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="98f88-211">Si se ejecuta sin`Ctrl+F5`el depurador adjunto ( ), Visual Studio busca cambios en los archivos y reinicia la aplicación a medida que se realizan cambios.</span><span class="sxs-lookup"><span data-stu-id="98f88-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="98f88-212">Actualice manualmente el explorador a medida que se realizan cambios.</span><span class="sxs-lookup"><span data-stu-id="98f88-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="98f88-213">Para ejecutar la aplicación Blazor WebAssembly, elija uno de los siguientes enfoques:</span><span class="sxs-lookup"><span data-stu-id="98f88-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="98f88-214">Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="98f88-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="98f88-215">Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="98f88-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="98f88-216">Las aplicaciones WebAssembly de Blazor no admiten la depuración mediante Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98f88-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="98f88-217">Para ejecutar la `Ctrl+F5` aplicación, `F5`use en lugar de .</span><span class="sxs-lookup"><span data-stu-id="98f88-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="98f88-218">En su lugar, puede depurar las aplicaciones Blazor WebAssembly directamente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="98f88-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="98f88-219">Consulte [Depurar ASP.NET Core Blazor](/aspnet/core/blazor/debug) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="98f88-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="98f88-220">[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="98f88-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
