---
title: Estructura del proyecto para las Blazor aplicaciones
description: Obtenga información sobre cómo se comparan las estructuras de proyecto de formularios Web Forms y proyectos de ASP.NET Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: ba7113c88db728f30812821deaf7c06a80663d1f
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189094"
---
# <a name="project-structure-for-no-locblazor-apps"></a><span data-ttu-id="2adb0-103">Estructura del proyecto para las Blazor aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2adb0-103">Project structure for Blazor apps</span></span>

<span data-ttu-id="2adb0-104">A pesar de las diferencias importantes en la estructura del proyecto, ASP.NET Web Forms y Blazor comparta muchos conceptos similares.</span><span class="sxs-lookup"><span data-stu-id="2adb0-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="2adb0-105">Aquí veremos la estructura de un Blazor proyecto y lo comparamos con un proyecto de formularios web forms ASP.net.</span><span class="sxs-lookup"><span data-stu-id="2adb0-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="2adb0-106">Para crear su primera Blazor aplicación, siga las instrucciones de los [ Blazor pasos de introducción](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="2adb0-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="2adb0-107">Puede seguir las instrucciones para crear una Blazor aplicación de servidor o una Blazor WebAssembly aplicación hospedada en ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="2adb0-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="2adb0-108">A excepción de la lógica específica del modelo de hospedaje, la mayor parte del código en ambos proyectos es el mismo.</span><span class="sxs-lookup"><span data-stu-id="2adb0-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="2adb0-109">Archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="2adb0-109">Project file</span></span>

<span data-ttu-id="2adb0-110">Blazor Las aplicaciones de servidor son proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="2adb0-110">Blazor Server apps are .NET projects.</span></span> <span data-ttu-id="2adb0-111">El archivo de proyecto para la Blazor aplicación de servidor es tan sencillo como puede obtener:</span><span class="sxs-lookup"><span data-stu-id="2adb0-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2adb0-112">El archivo de proyecto de una Blazor WebAssembly aplicación tiene un aspecto ligeramente más implicado (los números de versión exactos pueden variar):</span><span class="sxs-lookup"><span data-stu-id="2adb0-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly" Version="5.0.0" />
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly.DevServer" Version="5.0.0" PrivateAssets="all" />
    <PackageReference Include="System.Net.Http.Json" Version="5.0.0" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="2adb0-113">BlazorWebAssemblylos destinos `Microsoft.NET.Sdk.BlazorWebAssembly` del proyecto en lugar del `Microsoft.NET.Sdk.Web` SDK porque se ejecutan en el explorador en un entorno de WebAssembly tiempo de ejecución .net basado en.</span><span class="sxs-lookup"><span data-stu-id="2adb0-113">Blazor WebAssembly project targets `Microsoft.NET.Sdk.BlazorWebAssembly` instead of `Microsoft.NET.Sdk.Web` sdk because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="2adb0-114">No se puede instalar .NET en un explorador Web como puede hacerlo en un servidor o un equipo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="2adb0-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="2adb0-115">Por consiguiente, el proyecto hace referencia al Blazor marco mediante referencias de paquete individuales.</span><span class="sxs-lookup"><span data-stu-id="2adb0-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="2adb0-116">Por comparación, un proyecto de formularios Web Forms de ASP.NET predeterminado incluye casi 300 líneas de XML en su archivo *. csproj* , la mayoría de las cuales está enumerando explícitamente los distintos archivos de código y contenido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adb0-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="2adb0-117">Con la versión de `.NET 5` `Blazor Server` y la `Blazor WebAssembly` aplicación puede compartir fácilmente un entorno de ejecución unificado.</span><span class="sxs-lookup"><span data-stu-id="2adb0-117">With the release of `.NET 5` both `Blazor Server` and `Blazor WebAssembly` app can easily share one unified runtime.</span></span>

<span data-ttu-id="2adb0-118">Aunque se admiten, las referencias de ensamblado individuales son menos comunes en los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="2adb0-118">Although they're supported, individual assembly references are less common in .NET projects.</span></span> <span data-ttu-id="2adb0-119">La mayoría de las dependencias del proyecto se administran como referencias de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="2adb0-119">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="2adb0-120">Solo necesita hacer referencia a las dependencias de paquete de nivel superior en los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="2adb0-120">You only need to reference top-level package dependencies in .NET projects.</span></span> <span data-ttu-id="2adb0-121">Las dependencias transitivas se incluyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-121">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="2adb0-122">En lugar de usar el archivo *packages.config* que se encuentra normalmente en los proyectos de formularios web forms de ASP.net para hacer referencia a los paquetes, las referencias de paquete se agregan al archivo de proyecto mediante el `<PackageReference>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2adb0-122">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="2adb0-123">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="2adb0-123">Entry point</span></span>

<span data-ttu-id="2adb0-124">El Blazor punto de entrada de la aplicación de servidor se define en el archivo *Program.CS* , como se verá en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="2adb0-124">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="2adb0-125">Cuando se ejecuta la aplicación, crea y ejecuta una instancia de host web con los valores predeterminados específicos de Web Apps.</span><span class="sxs-lookup"><span data-stu-id="2adb0-125">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="2adb0-126">El host de Web administra el Blazor ciclo de vida de la aplicación de servidor y configura los servicios de nivel de host.</span><span class="sxs-lookup"><span data-stu-id="2adb0-126">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="2adb0-127">Algunos ejemplos de estos servicios son la configuración, el registro, la inserción de dependencias y el servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="2adb0-127">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="2adb0-128">Este código es principalmente reutilizable y a menudo se deja sin cambios.</span><span class="sxs-lookup"><span data-stu-id="2adb0-128">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="2adb0-129">Blazorlas WebAssembly aplicaciones también definen un punto de entrada en *Program.CS*.</span><span class="sxs-lookup"><span data-stu-id="2adb0-129">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="2adb0-130">El código tiene un aspecto ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-130">The code looks slightly different.</span></span> <span data-ttu-id="2adb0-131">El código es similar en que está configurando el host de la aplicación para proporcionar los mismos servicios de nivel de host a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2adb0-131">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="2adb0-132">Sin embargo, el host de la WebAssembly aplicación no configura un servidor http porque se ejecuta directamente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="2adb0-132">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="2adb0-133">Blazor las aplicaciones tienen una `Startup` clase en lugar de un archivo *global. asax* para definir la lógica de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2adb0-133">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="2adb0-134">La `Startup` clase se usa para configurar la aplicación y los servicios específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2adb0-134">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="2adb0-135">En la Blazor aplicación de servidor, la `Startup` clase se usa para configurar el extremo de la conexión en tiempo real utilizada por Blazor entre los exploradores cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="2adb0-135">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="2adb0-136">En la Blazor WebAssembly aplicación, la `Startup` clase define los componentes raíz de la aplicación y dónde se deben representar.</span><span class="sxs-lookup"><span data-stu-id="2adb0-136">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="2adb0-137">Veremos más en profundidad la `Startup` clase en la sección de inicio de la [aplicación](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="2adb0-137">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="2adb0-138">Archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="2adb0-138">Static files</span></span>

<span data-ttu-id="2adb0-139">A diferencia de los proyectos de formularios Web Forms de ASP.NET, no todos los archivos de un Blazor proyecto se pueden solicitar como archivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="2adb0-139">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="2adb0-140">Solo los archivos de la carpeta *wwwroot* son direccionables por Web.</span><span class="sxs-lookup"><span data-stu-id="2adb0-140">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="2adb0-141">Esta carpeta se conoce como "raíz Web" de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2adb0-141">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="2adb0-142">Cualquier cosa fuera de la raíz Web de la aplicación *no es* direccionable por Web.</span><span class="sxs-lookup"><span data-stu-id="2adb0-142">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="2adb0-143">Este programa de instalación proporciona un nivel de seguridad adicional que evita la exposición accidental de archivos de proyecto a través de la Web.</span><span class="sxs-lookup"><span data-stu-id="2adb0-143">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="2adb0-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="2adb0-144">Configuration</span></span>

<span data-ttu-id="2adb0-145">La configuración de las aplicaciones de formularios Web Forms de ASP.NET se controla normalmente mediante uno o varios archivos *web.config* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-145">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="2adb0-146">Blazor Normalmente, las aplicaciones no tienen archivos *web.config* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-146">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="2adb0-147">Si lo hacen, el archivo solo se utiliza para configurar los valores específicos de IIS cuando se hospedan en IIS.</span><span class="sxs-lookup"><span data-stu-id="2adb0-147">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="2adb0-148">En su lugar, Blazor las aplicaciones de servidor usan las abstracciones de configuración de ASP.net Core ( Blazor WebAssembly las aplicaciones no admiten actualmente las mismas abstracciones de configuración, pero pueden ser una característica agregada en el futuro).</span><span class="sxs-lookup"><span data-stu-id="2adb0-148">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="2adb0-149">Por ejemplo, la Blazor aplicación de servidor predeterminada almacena algunos valores en *appsettings.jsen*.</span><span class="sxs-lookup"><span data-stu-id="2adb0-149">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="2adb0-150">Más información sobre la configuración en proyectos de ASP.NET Core en la sección de [configuración](./config.md) .</span><span class="sxs-lookup"><span data-stu-id="2adb0-150">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="2adb0-151">Componentes de Razor</span><span class="sxs-lookup"><span data-stu-id="2adb0-151">Razor components</span></span>

<span data-ttu-id="2adb0-152">La mayoría de los archivos de los Blazor proyectos son archivos *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-152">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="2adb0-153">Razor es un lenguaje de plantillas basado en HTML y C# que se usa para generar dinámicamente la interfaz de usuario Web.</span><span class="sxs-lookup"><span data-stu-id="2adb0-153">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="2adb0-154">Los archivos *. Razor* definen los componentes que componen la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2adb0-154">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="2adb0-155">En su mayor parte, los componentes son idénticos tanto para el Blazor servidor como para las Blazor WebAssembly aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2adb0-155">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="2adb0-156">Los componentes de Blazor son análogos a los controles de usuario de formularios Web Forms de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="2adb0-156">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="2adb0-157">Cada archivo de componente de Razor se compila en una clase .NET cuando se compila el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adb0-157">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="2adb0-158">La clase generada captura el estado del componente, la lógica de representación, los métodos de ciclo de vida, los controladores de eventos y otra lógica.</span><span class="sxs-lookup"><span data-stu-id="2adb0-158">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="2adb0-159">Veremos cómo crear componentes en la sección [creación de componentes de interfaz de usuario Blazor reutilizables con](./components.md) .</span><span class="sxs-lookup"><span data-stu-id="2adb0-159">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="2adb0-160">Los archivos *_Imports. Razor* no son archivos de componentes de Razor.</span><span class="sxs-lookup"><span data-stu-id="2adb0-160">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="2adb0-161">En su lugar, definen un conjunto de directivas de Razor para importar en otros archivos *. Razor* dentro de la misma carpeta y en sus subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="2adb0-161">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="2adb0-162">Por ejemplo, un archivo *_Imports. Razor* es una manera convencional de agregar `using` directivas para los espacios de nombres usados comúnmente:</span><span class="sxs-lookup"><span data-stu-id="2adb0-162">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="2adb0-163">Páginas</span><span class="sxs-lookup"><span data-stu-id="2adb0-163">Pages</span></span>

<span data-ttu-id="2adb0-164">¿Dónde están las páginas de las Blazor aplicaciones?</span><span class="sxs-lookup"><span data-stu-id="2adb0-164">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="2adb0-165">Blazor no define una extensión de archivo independiente para las páginas direccionables, como los archivos *. aspx* de las aplicaciones de formularios Web Forms de ASP.net.</span><span class="sxs-lookup"><span data-stu-id="2adb0-165">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="2adb0-166">En su lugar, las páginas se definen asignando rutas a los componentes.</span><span class="sxs-lookup"><span data-stu-id="2adb0-166">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="2adb0-167">Normalmente, una ruta se asigna mediante la `@page` Directiva Razor.</span><span class="sxs-lookup"><span data-stu-id="2adb0-167">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="2adb0-168">Por ejemplo, el `Counter` componente creado en el archivo *pages/Counter. Razor* define la ruta siguiente:</span><span class="sxs-lookup"><span data-stu-id="2adb0-168">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="2adb0-169">El enrutamiento en Blazor se controla en el lado cliente, no en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2adb0-169">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="2adb0-170">A medida que el usuario navega en el explorador, Blazor intercepta la navegación y, a continuación, representa el componente con la ruta correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-170">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="2adb0-171">Las rutas del componente no se deducen actualmente por la ubicación del archivo del componente, como sucede con las páginas *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-171">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="2adb0-172">Esta característica se puede Agregar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="2adb0-172">This feature may be added in the future.</span></span> <span data-ttu-id="2adb0-173">Cada ruta debe especificarse explícitamente en el componente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-173">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="2adb0-174">El almacenamiento de componentes enrutables en una carpeta *pages* no tiene ningún significado especial y es meramente una Convención.</span><span class="sxs-lookup"><span data-stu-id="2adb0-174">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="2adb0-175">Veremos más detalladamente el enrutamiento en Blazor en la sección [páginas, enrutamiento y diseños](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="2adb0-175">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="2adb0-176">Layout</span><span class="sxs-lookup"><span data-stu-id="2adb0-176">Layout</span></span>

<span data-ttu-id="2adb0-177">En las aplicaciones de formularios Web Forms de ASP.NET, un diseño de página común se controla mediante páginas maestras (*site. Master*).</span><span class="sxs-lookup"><span data-stu-id="2adb0-177">In ASP.NET Web Forms apps, a common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="2adb0-178">En Blazor las aplicaciones de, el diseño de página se controla mediante componentes de diseño (*Shared/MainLayout. Razor*).</span><span class="sxs-lookup"><span data-stu-id="2adb0-178">In Blazor apps, the page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="2adb0-179">Los componentes de diseño se tratarán con más detalle en la sección [página, enrutamiento y diseños](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="2adb0-179">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-no-locblazor"></a><span data-ttu-id="2adb0-180">Bootstrap Blazor</span><span class="sxs-lookup"><span data-stu-id="2adb0-180">Bootstrap Blazor</span></span>

<span data-ttu-id="2adb0-181">Para arrancar Blazor , la aplicación debe:</span><span class="sxs-lookup"><span data-stu-id="2adb0-181">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="2adb0-182">Especifique en qué lugar de la página se debe representar el componente raíz (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="2adb0-182">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="2adb0-183">Agregue el Blazor script de marco correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-183">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="2adb0-184">En la Blazor aplicación de servidor, la página host del componente raíz se define en el archivo *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-184">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="2adb0-185">Este archivo define una página de Razor, no un componente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-185">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="2adb0-186">Razor Pages usar sintaxis Razor para definir una página direccionable por el servidor, de forma muy parecida a una página *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="2adb0-186">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="2adb0-187">El `Html.RenderComponentAsync<TComponent>(RenderMode)` método se utiliza para definir dónde se debe representar un componente de nivel de raíz.</span><span class="sxs-lookup"><span data-stu-id="2adb0-187">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="2adb0-188">La `RenderMode` opción indica la manera en que se debe representar el componente.</span><span class="sxs-lookup"><span data-stu-id="2adb0-188">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="2adb0-189">En la tabla siguiente se describen las opciones admitidas `RenderMode` .</span><span class="sxs-lookup"><span data-stu-id="2adb0-189">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="2adb0-190">Opción</span><span class="sxs-lookup"><span data-stu-id="2adb0-190">Option</span></span>                        |<span data-ttu-id="2adb0-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="2adb0-191">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="2adb0-192">Se representa de forma interactiva una vez que se establece una conexión con el explorador</span><span class="sxs-lookup"><span data-stu-id="2adb0-192">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="2adb0-193">Primer prerepresentado y después representado de forma interactiva</span><span class="sxs-lookup"><span data-stu-id="2adb0-193">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="2adb0-194">Se representa como contenido estático</span><span class="sxs-lookup"><span data-stu-id="2adb0-194">Rendered as static content</span></span>|

<span data-ttu-id="2adb0-195">La referencia de script a *_framework/blazor.server.js* establece la conexión en tiempo real con el servidor y, a continuación, trata todas las interacciones del usuario y las actualizaciones de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="2adb0-195">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="2adb0-196">En la Blazor WebAssembly aplicación, la página host es un archivo HTML estático simple en *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="2adb0-196">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="2adb0-197">El `<div>` elemento con el identificador denominado `app` se utiliza para indicar dónde se debe representar el componente raíz.</span><span class="sxs-lookup"><span data-stu-id="2adb0-197">The `<div>` element with id named `app` is used to indicate where the root component should be rendered.</span></span>

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/app.css" rel="stylesheet" />
    <link href="blazor-web.styles.css" rel="stylesheet" />
</head>

<body>
    <div id="app">Loading...</div>

    <div id="blazor-error-ui">
        An unhandled error has occurred.
        <a href="" class="reload">Reload</a>
        <a class="dismiss">🗙</a>
    </div>
    <script src="_framework/blazor.webassembly.js"></script>
</body>

</html>

```

<span data-ttu-id="2adb0-198">El componente raíz que se va a representar se especifica en el método de la aplicación `Program.Main` con la flexibilidad de registrar los servicios mediante la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="2adb0-198">The root component to render is specified in the app's `Program.Main` method with the flexibility to register services through dependency injection.</span></span> <span data-ttu-id="2adb0-199">Para obtener más información, vea [ASP.net Core la Blazor inserción de dependencias](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).</span><span class="sxs-lookup"><span data-stu-id="2adb0-199">For more information, see [ASP.NET Core Blazor dependency injection](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).</span></span>

```csharp
public class Program
{
    public static async Task Main(string[] args)
    {
        var builder = WebAssemblyHostBuilder.CreateDefault(args);
        builder.RootComponents.Add<App>("#app");

        ....
        ....
    }
}
```

## <a name="build-output"></a><span data-ttu-id="2adb0-200">Resultado de la compilación</span><span class="sxs-lookup"><span data-stu-id="2adb0-200">Build output</span></span>

<span data-ttu-id="2adb0-201">Cuando se compila un Blazor proyecto, todos los componentes de Razor y los archivos de código se compilan en un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2adb0-201">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="2adb0-202">A diferencia de los proyectos de formularios Web Forms de ASP.NET, Blazor no admite la compilación en tiempo de ejecución de la lógica de IU.</span><span class="sxs-lookup"><span data-stu-id="2adb0-202">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="2adb0-203">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="2adb0-203">Run the app</span></span>

<span data-ttu-id="2adb0-204">Para ejecutar la Blazor aplicación de servidor, presione `F5` en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2adb0-204">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="2adb0-205">Blazor las aplicaciones no admiten la compilación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2adb0-205">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="2adb0-206">Para ver los resultados de los cambios de código y marcado de componentes, vuelva a compilar y reiniciar la aplicación con el depurador asociado.</span><span class="sxs-lookup"><span data-stu-id="2adb0-206">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="2adb0-207">Si se ejecuta sin el depurador adjunto ( `Ctrl+F5` ), Visual Studio inspecciona los cambios de archivo y reinicia la aplicación a medida que se realizan cambios.</span><span class="sxs-lookup"><span data-stu-id="2adb0-207">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="2adb0-208">Actualice manualmente el explorador a medida que se realicen cambios.</span><span class="sxs-lookup"><span data-stu-id="2adb0-208">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="2adb0-209">Para ejecutar la Blazor WebAssembly aplicación, elija uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2adb0-209">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="2adb0-210">Ejecute el proyecto de cliente directamente mediante el servidor de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="2adb0-210">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="2adb0-211">Ejecute el proyecto de servidor al hospedar la aplicación con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2adb0-211">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="2adb0-212">Blazorlas WebAssembly aplicaciones se pueden depurar en el explorador y Visual Studio. vea [depurar ASP.net Core Blazor WebAssembly ](/aspnet/core/blazor/debug) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2adb0-212">Blazor WebAssembly apps can be debugged in both browser and Visual Studio.See [Debug ASP.NET Core Blazor WebAssembly](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2adb0-213">[Anterior](hosting-models.md)
>[Siguiente](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="2adb0-213">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
