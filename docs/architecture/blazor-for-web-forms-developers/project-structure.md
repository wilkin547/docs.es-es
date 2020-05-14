---
title: Estructura del proyecto para aplicaciones increíbles
description: Obtenga información sobre cómo se comparan las estructuras de proyecto de los proyectos de formularios Web Forms y increíbles de ASP.NET.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 7e622663bedce13c93b8d72f5a699d076e8139b7
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394779"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="b4df1-103">Estructura del proyecto para aplicaciones increíbles</span><span class="sxs-lookup"><span data-stu-id="b4df1-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b4df1-104">A pesar de las diferencias importantes de la estructura del proyecto, los formularios Web Forms de ASP.NET y el increíbles comparten muchos conceptos similares.</span><span class="sxs-lookup"><span data-stu-id="b4df1-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="b4df1-105">Aquí veremos la estructura de un proyecto increíble y lo comparamos con un proyecto de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b4df1-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="b4df1-106">Para crear su primera aplicación increíble, siga las instrucciones de los [pasos de introducción más rápido](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="b4df1-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="b4df1-107">Puede seguir las instrucciones para crear una aplicación de servidor más brillante o una aplicación webassembly increíblemente hospedada en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="b4df1-108">A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código en ambos proyectos es el mismo.</span><span class="sxs-lookup"><span data-stu-id="b4df1-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="b4df1-109">Archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="b4df1-109">Project file</span></span>

<span data-ttu-id="b4df1-110">Las aplicaciones de servidor increíbles son proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="b4df1-111">El archivo de proyecto de la aplicación de servidor de extraordinariamente es tan sencillo como puede obtener:</span><span class="sxs-lookup"><span data-stu-id="b4df1-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="b4df1-112">El archivo de proyecto de una aplicación de webassembly increíblemente es algo más complicado (los números de versión exactos pueden variar):</span><span class="sxs-lookup"><span data-stu-id="b4df1-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="b4df1-113">Los proyectos de webassembly increíbles tienen como destino .NET Standard en lugar de .NET Core porque se ejecutan en el explorador en un entorno de tiempo de ejecución .NET basado en webassembly.</span><span class="sxs-lookup"><span data-stu-id="b4df1-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="b4df1-114">No se puede instalar .NET en un explorador Web como puede hacerlo en un servidor o un equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="b4df1-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="b4df1-115">Por consiguiente, el proyecto hace referencia al marco de trabajo de extraordinarias mediante referencias de paquetes individuales.</span><span class="sxs-lookup"><span data-stu-id="b4df1-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="b4df1-116">Por comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *. csproj* , la mayoría de las cuales está enumerando explícitamente los distintos archivos de código y contenido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4df1-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="b4df1-117">Muchas de las simplificaciones en los proyectos basados en .NET Core y .NET Standard proceden de los destinos y propiedades predeterminados importados mediante referencia al `Microsoft.NET.Sdk.Web` SDK, que a menudo se conoce como el SDK Web.</span><span class="sxs-lookup"><span data-stu-id="b4df1-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="b4df1-118">El SDK de web incluye caracteres comodín y otras ventajas que simplifican la inclusión de archivos de código y contenido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4df1-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="b4df1-119">No es necesario enumerar los archivos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="b4df1-120">Cuando el destino es .NET Core, el SDK de web también agrega referencias de marco de trabajo a .NET Core y ASP.NET Core Marcos compartidos.</span><span class="sxs-lookup"><span data-stu-id="b4df1-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="b4df1-121">Los marcos de trabajo son visibles desde el nodo marcos de **dependencias**  >  **Frameworks** de la ventana de **Explorador de soluciones** .</span><span class="sxs-lookup"><span data-stu-id="b4df1-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="b4df1-122">Los marcos compartidos son colecciones de ensamblados que se instalaron en el equipo al instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="b4df1-123">Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="b4df1-124">La mayoría de las dependencias del proyecto se administran como referencias de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4df1-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="b4df1-125">Solo necesita hacer referencia a las dependencias de paquete de nivel superior en los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="b4df1-126">Las dependencias transitivas se incluyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="b4df1-127">En lugar de usar el archivo *packages. config* que se encuentra normalmente en los proyectos de formularios web forms de ASP.net para hacer referencia a los paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el `<PackageReference>` elemento.</span><span class="sxs-lookup"><span data-stu-id="b4df1-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="b4df1-128">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="b4df1-128">Entry point</span></span>

<span data-ttu-id="b4df1-129">El punto de entrada de la aplicación de servidor de increíbles se define en el archivo *Program.CS* , como se verá en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b4df1-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="b4df1-130">Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con los valores predeterminados específicos de Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b4df1-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="b4df1-131">El host Web administra el ciclo de vida de la aplicación de servidor increíble y configura los servicios de nivel de host.</span><span class="sxs-lookup"><span data-stu-id="b4df1-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="b4df1-132">Algunos ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="b4df1-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="b4df1-133">Este código es principalmente reutilizable y a menudo se deja sin cambios.</span><span class="sxs-lookup"><span data-stu-id="b4df1-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="b4df1-134">Las aplicaciones de webassembly increíbles también definen un punto de entrada en *Program.CS*.</span><span class="sxs-lookup"><span data-stu-id="b4df1-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="b4df1-135">El código tiene un aspecto ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-135">The code looks slightly different.</span></span> <span data-ttu-id="b4df1-136">El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4df1-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="b4df1-137">Sin embargo, el host de aplicación de webassembly no configura un servidor HTTP porque se ejecuta directamente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="b4df1-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="b4df1-138">Las aplicaciones increíbles tienen una `Startup` clase en lugar de un archivo *global. asax* para definir la lógica de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4df1-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="b4df1-139">La `Startup` clase se usa para configurar la aplicación y los servicios específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4df1-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="b4df1-140">En la aplicación de servidor de extraordinarias, la `Startup` clase se usa para configurar el punto de conexión para la conexión en tiempo real utilizada por el increíbles entre los exploradores cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="b4df1-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="b4df1-141">En la aplicación webassembly de extraordinarias, la `Startup` clase define los componentes raíz de la aplicación y dónde se deben representar.</span><span class="sxs-lookup"><span data-stu-id="b4df1-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="b4df1-142">Veremos más en profundidad la `Startup` clase en la sección de inicio de la [aplicación](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="b4df1-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="b4df1-143">Archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="b4df1-143">Static files</span></span>

<span data-ttu-id="b4df1-144">A diferencia de los proyectos de formularios Web Forms de ASP.NET, no todos los archivos de un proyecto más increíblemente se pueden solicitar como archivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="b4df1-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="b4df1-145">Solo los archivos de la carpeta *wwwroot* son direccionables por Web.</span><span class="sxs-lookup"><span data-stu-id="b4df1-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="b4df1-146">Esta carpeta se conoce como "raíz Web" de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4df1-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="b4df1-147">Cualquier cosa fuera de la raíz Web de la aplicación *no es* direccionable por Web.</span><span class="sxs-lookup"><span data-stu-id="b4df1-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="b4df1-148">Este programa de instalación proporciona un nivel de seguridad adicional que evita la exposición accidental de archivos de proyecto a través de la Web.</span><span class="sxs-lookup"><span data-stu-id="b4df1-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="b4df1-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="b4df1-149">Configuration</span></span>

<span data-ttu-id="b4df1-150">La configuración de las aplicaciones de formularios Web Forms de ASP.NET se controla normalmente mediante uno o más archivos *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="b4df1-151">Las aplicaciones increíbles no suelen tener archivos *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="b4df1-152">Si lo hacen, el archivo solo se utiliza para configurar los valores específicos de IIS cuando se hospedan en IIS.</span><span class="sxs-lookup"><span data-stu-id="b4df1-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="b4df1-153">En su lugar, las aplicaciones de servidor increíbles usan las abstracciones de configuración de ASP.NET Core (las aplicaciones webassembly increíblemente no admiten actualmente las mismas abstracciones de configuración, pero pueden ser una característica agregada en el futuro).</span><span class="sxs-lookup"><span data-stu-id="b4df1-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="b4df1-154">Por ejemplo, la aplicación de servidor increíblemente predeterminada almacena algunos valores en *appSettings. JSON*.</span><span class="sxs-lookup"><span data-stu-id="b4df1-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="b4df1-155">Más información sobre la configuración en proyectos de ASP.NET Core en la sección de [configuración](./config.md) .</span><span class="sxs-lookup"><span data-stu-id="b4df1-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="b4df1-156">Componentes de Razor</span><span class="sxs-lookup"><span data-stu-id="b4df1-156">Razor components</span></span>

<span data-ttu-id="b4df1-157">La mayoría de los archivos de los proyectos más increíbles son archivos *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="b4df1-158">Razor es un lenguaje de plantillas basado en HTML y C# que se usa para generar dinámicamente la interfaz de usuario Web.</span><span class="sxs-lookup"><span data-stu-id="b4df1-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="b4df1-159">Los archivos *. Razor* definen los componentes que componen la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4df1-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="b4df1-160">En la mayoría de los casos, los componentes son idénticos para las aplicaciones de servidor y de webassembler increíblemente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="b4df1-161">Los componentes de extraordinariamente son análogos a los controles de usuario de formularios Web Forms de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b4df1-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="b4df1-162">Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b4df1-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="b4df1-163">La clase generada captura el estado del componente, la lógica de representación, los métodos de ciclo de vida, los controladores de eventos y otra lógica.</span><span class="sxs-lookup"><span data-stu-id="b4df1-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="b4df1-164">Veremos la creación de componentes en la sección [creación de componentes de interfaz de usuario reutilizables con](./components.md) más increíble.</span><span class="sxs-lookup"><span data-stu-id="b4df1-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="b4df1-165">Los archivos *_Imports. Razor* no son archivos de componentes de Razor.</span><span class="sxs-lookup"><span data-stu-id="b4df1-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="b4df1-166">En su lugar, definen un conjunto de directivas de Razor para importar en otros archivos *. Razor* dentro de la misma carpeta y en sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="b4df1-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="b4df1-167">Por ejemplo, un archivo *_Imports. Razor* es una manera convencional de agregar `using` directivas para los espacios de nombres usados comúnmente:</span><span class="sxs-lookup"><span data-stu-id="b4df1-167">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="b4df1-168">Páginas</span><span class="sxs-lookup"><span data-stu-id="b4df1-168">Pages</span></span>

<span data-ttu-id="b4df1-169">¿Dónde están las páginas de las aplicaciones increíbles?</span><span class="sxs-lookup"><span data-stu-id="b4df1-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="b4df1-170">El increíble no define una extensión de archivo independiente para las páginas direccionables, como los archivos *. aspx* de las aplicaciones de formularios Web Forms de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="b4df1-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="b4df1-171">En su lugar, las páginas se definen asignando rutas a los componentes.</span><span class="sxs-lookup"><span data-stu-id="b4df1-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="b4df1-172">Normalmente, una ruta se asigna mediante la `@page` Directiva Razor.</span><span class="sxs-lookup"><span data-stu-id="b4df1-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="b4df1-173">Por ejemplo, el `Counter` componente creado en el archivo *pages/Counter. Razor* define la ruta siguiente:</span><span class="sxs-lookup"><span data-stu-id="b4df1-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="b4df1-174">El enrutamiento en increíblemente se controla en el lado cliente, no en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b4df1-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="b4df1-175">A medida que el usuario navega en el explorador, increíble intercepta la navegación y, a continuación, representa el componente con la ruta coincidente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="b4df1-176">Las rutas del componente no se deducen actualmente por la ubicación del archivo del componente, como sucede con las páginas *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="b4df1-177">Esta característica se puede Agregar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="b4df1-177">This feature may be added in the future.</span></span> <span data-ttu-id="b4df1-178">Cada ruta debe especificarse explícitamente en el componente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="b4df1-179">El almacenamiento de componentes enrutables en una carpeta *pages* no tiene ningún significado especial y es meramente una Convención.</span><span class="sxs-lookup"><span data-stu-id="b4df1-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="b4df1-180">En la sección [páginas, enrutamiento y diseños](./pages-routing-layouts.md) veremos más detalladamente el enrutamiento en el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="b4df1-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="b4df1-181">Diseño</span><span class="sxs-lookup"><span data-stu-id="b4df1-181">Layout</span></span>

<span data-ttu-id="b4df1-182">En las aplicaciones de formularios Web Forms de ASP.NET, el diseño de página común se controla mediante páginas maestras (*site. Master*).</span><span class="sxs-lookup"><span data-stu-id="b4df1-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="b4df1-183">En las aplicaciones increíbles, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout. Razor*).</span><span class="sxs-lookup"><span data-stu-id="b4df1-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="b4df1-184">Los componentes de diseño se tratarán con más detalle en la sección [página, enrutamiento y diseños](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="b4df1-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="b4df1-185">Arranque rápido</span><span class="sxs-lookup"><span data-stu-id="b4df1-185">Bootstrap Blazor</span></span>

<span data-ttu-id="b4df1-186">Para arrancar increíble, la aplicación debe:</span><span class="sxs-lookup"><span data-stu-id="b4df1-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="b4df1-187">Especifique en qué lugar de la página se debe representar el componente raíz (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="b4df1-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="b4df1-188">Agregue el correspondiente script del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b4df1-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="b4df1-189">En la aplicación de servidor de extraordinarias, la página host del componente raíz se define en el archivo *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="b4df1-190">Este archivo define una página de Razor, no un componente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="b4df1-191">Razor Pages usar sintaxis Razor para definir una página direccionable por el servidor, de forma muy parecida a una página *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="b4df1-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="b4df1-192">El `Html.RenderComponentAsync<TComponent>(RenderMode)` método se utiliza para definir dónde se debe representar un componente de nivel de raíz.</span><span class="sxs-lookup"><span data-stu-id="b4df1-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="b4df1-193">La `RenderMode` opción indica la manera en que se debe representar el componente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="b4df1-194">En la tabla siguiente se describen las opciones admitidas `RenderMode` .</span><span class="sxs-lookup"><span data-stu-id="b4df1-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="b4df1-195">Opción</span><span class="sxs-lookup"><span data-stu-id="b4df1-195">Option</span></span>                        |<span data-ttu-id="b4df1-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4df1-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="b4df1-197">Se representa de forma interactiva una vez que se establece una conexión con el explorador</span><span class="sxs-lookup"><span data-stu-id="b4df1-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="b4df1-198">Primer prerepresentado y después representado de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="b4df1-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="b4df1-199">Se representa como contenido estático</span><span class="sxs-lookup"><span data-stu-id="b4df1-199">Rendered as static content</span></span>|

<span data-ttu-id="b4df1-200">La referencia de script a *_framework/blazor.Server.js* establece la conexión en tiempo real con el servidor y, a continuación, trata todas las interacciones del usuario y las actualizaciones de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4df1-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="b4df1-201">En la aplicación increíblemente webassembly, la página host es un simple archivo HTML estático en *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="b4df1-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="b4df1-202">El `<app>` elemento se utiliza para indicar dónde se debe representar el componente raíz.</span><span class="sxs-lookup"><span data-stu-id="b4df1-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="b4df1-203">El componente específico que se va a representar se configura en el método de la aplicación `Startup.Configure` con un selector de CSS correspondiente que indica dónde se debe representar el componente.</span><span class="sxs-lookup"><span data-stu-id="b4df1-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="b4df1-204">Resultado de la compilación</span><span class="sxs-lookup"><span data-stu-id="b4df1-204">Build output</span></span>

<span data-ttu-id="b4df1-205">Cuando se crea un proyecto increíblemente brillante, todos los archivos de código y componentes de Razor se compilan en un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b4df1-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="b4df1-206">A diferencia de los proyectos de formularios Web Forms de ASP.NET, increíble no admite la compilación en tiempo de ejecución de la lógica de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4df1-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="b4df1-207">Ejecución la aplicación</span><span class="sxs-lookup"><span data-stu-id="b4df1-207">Run the app</span></span>

<span data-ttu-id="b4df1-208">Para ejecutar la aplicación de servidor de extraordinarias, presione `F5` en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4df1-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="b4df1-209">Las aplicaciones increíbles no admiten la compilación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4df1-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="b4df1-210">Para ver los resultados de los cambios de código y marcado de componentes, vuelva a compilar y reiniciar la aplicación con el depurador asociado.</span><span class="sxs-lookup"><span data-stu-id="b4df1-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="b4df1-211">Si se ejecuta sin el depurador adjunto ( `Ctrl+F5` ), Visual Studio inspecciona los cambios de archivo y reinicia la aplicación a medida que se realizan cambios.</span><span class="sxs-lookup"><span data-stu-id="b4df1-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="b4df1-212">Actualice manualmente el explorador a medida que se realicen cambios.</span><span class="sxs-lookup"><span data-stu-id="b4df1-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="b4df1-213">Para ejecutar la aplicación increíblemente webassembly, elija uno de los siguientes enfoques:</span><span class="sxs-lookup"><span data-stu-id="b4df1-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="b4df1-214">Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b4df1-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="b4df1-215">Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4df1-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="b4df1-216">Las aplicaciones de webassembly increíbles no admiten la depuración con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4df1-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="b4df1-217">Para ejecutar la aplicación, use `Ctrl+F5` en lugar de `F5` .</span><span class="sxs-lookup"><span data-stu-id="b4df1-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="b4df1-218">En su lugar, puede depurar aplicaciones webassembly increíblemente directamente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="b4df1-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="b4df1-219">Consulte [depuración de ASP.net Core extraordinarias](/aspnet/core/blazor/debug) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b4df1-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b4df1-220">[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="b4df1-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
