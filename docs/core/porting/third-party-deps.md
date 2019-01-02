---
title: Análisis de las dependencias para trasladar código a .NET Core
description: Obtenga información sobre cómo analizar dependencias externas para trasladar el proyecto de .NET Framework a .NET Core.
author: cartermp
ms.date: 12/04/2018
ms.custom: seodec18
ms.openlocfilehash: dce8e6cd4986b15cf926154b378964db4beef398
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170332"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a><span data-ttu-id="c0400-103">Análisis de las dependencias para trasladar código a .NET Core</span><span class="sxs-lookup"><span data-stu-id="c0400-103">Analyze your dependencies to port code to .NET Core</span></span>

<span data-ttu-id="c0400-104">Para trasladar el código a .NET Core o .NET Standard, debe comprender las dependencias.</span><span class="sxs-lookup"><span data-stu-id="c0400-104">To port your code to .NET Core or .NET Standard, you must understand your dependencies.</span></span> <span data-ttu-id="c0400-105">Las dependencias externas son los [paquetes NuGet](#analyze-referenced-nuget-packages-on-your-project) o [DLL](#analyze-dependencies-that-arent-nuget-packages) a los que hace referencia en el proyecto, pero que no compila.</span><span class="sxs-lookup"><span data-stu-id="c0400-105">External dependencies are the [NuGet packages](#analyze-referenced-nuget-packages-on-your-project) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you reference in your project, but that you don't build.</span></span> <span data-ttu-id="c0400-106">Evalúe cada dependencia y desarrolle un plan de contingencia para las que no son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-106">Evaluate each dependency and develop a contingency plan for the ones that aren't compatible with .NET Core.</span></span> <span data-ttu-id="c0400-107">Aquí se muestra cómo determinar si una dependencia es compatible con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-107">Here's how to determine if a dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-projects"></a><span data-ttu-id="c0400-108">Análisis de los paquetes NuGet a los que se hace referencia en los proyectos</span><span class="sxs-lookup"><span data-stu-id="c0400-108">Analyze referenced NuGet packages in your projects</span></span>

<span data-ttu-id="c0400-109">Si hace referencia a paquetes NuGet en el proyecto, debe comprobar si son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-109">If you reference NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="c0400-110">Hay dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="c0400-110">There are two ways to accomplish that:</span></span>

* [<span data-ttu-id="c0400-111">A través de la aplicación NuGet Package Explorer</span><span class="sxs-lookup"><span data-stu-id="c0400-111">Using the NuGet Package Explorer app</span></span>](#analyze-nuget-packages-using-nuget-package-explorer)
* [<span data-ttu-id="c0400-112">A través del sitio de nuget.org</span><span class="sxs-lookup"><span data-stu-id="c0400-112">Using the nuget.org site</span></span>](#analyze-nuget-packages-using-nugetorg)

<span data-ttu-id="c0400-113">Después de analizar los paquetes, si no son compatibles con .NET Core y solo se centran en .NET Framework, puede comprobar si el [modo de compatibilidad de .NET Framework](#net-framework-compatibility-mode) le puede ayudar con el proceso de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="c0400-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="c0400-114">Analizar los paquetes NuGet con NuGet Package Explorer</span><span class="sxs-lookup"><span data-stu-id="c0400-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="c0400-115">Los paquetes NuGet son un conjunto de carpetas que contienen ensamblados específicos de plataforma,</span><span class="sxs-lookup"><span data-stu-id="c0400-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="c0400-116">por lo que debe comprobar si hay una carpeta que contenga un ensamblado compatible dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="c0400-117">La manera más fácil de inspeccionar las carpetas de paquetes NuGet consiste en usar la herramienta [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="c0400-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="c0400-118">Después de instalarla, siga estos pasos para ver los nombres de las carpetas:</span><span class="sxs-lookup"><span data-stu-id="c0400-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="c0400-119">Abra NuGet Package Explorer.</span><span class="sxs-lookup"><span data-stu-id="c0400-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="c0400-120">Haga clic en **Open package from online feed** (Abrir paquete desde fuente en línea).</span><span class="sxs-lookup"><span data-stu-id="c0400-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="c0400-121">Busque el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="c0400-122">Seleccione el nombre del paquete en los resultados de la búsqueda y haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="c0400-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="c0400-123">Expanda la carpeta *lib* de la derecha y examine los nombres de las carpetas.</span><span class="sxs-lookup"><span data-stu-id="c0400-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="c0400-124">Busque una carpeta que tenga cualquiera de estos nombres:</span><span class="sxs-lookup"><span data-stu-id="c0400-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
netcoreapp2.1
netcoreapp2.2
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="c0400-125">Estos valores son los [monikers de la plataforma de destino (TFM)](../../standard/frameworks.md) que se asignan a las versiones de los perfiles de [.NET Standard](../../standard/net-standard.md), .NET Core y de la Biblioteca de clases portable (PCL) tradicional compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0400-126">Cuando examine los TFM compatibles con un paquete, tenga en cuenta que `netcoreapp*`, aunque sea compatible, es solo para los proyectos de .NET Core, y no para los proyectos de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c0400-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="c0400-127">Las bibliotecas que solo tienen como destino `netcoreapp*` (y no `netstandard*`) solo las pueden consumir otras aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="c0400-128">Analizar los paquetes NuGet mediante nuget.org</span><span class="sxs-lookup"><span data-stu-id="c0400-128">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="c0400-129">Como alternativa, en la sección **Dependencies** (Dependencias) de la página de un paquete de [nuget.org](https://www.nuget.org/) puede ver los TFM que admite cada paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-129">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="c0400-130">Aunque el uso del sitio es un método más sencillo para comprobar la compatibilidad, la información de las **dependencias** no está disponible en el sitio para todos los paquetes.</span><span class="sxs-lookup"><span data-stu-id="c0400-130">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="c0400-131">Modo de compatibilidad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c0400-131">.NET Framework compatibility mode</span></span>

<span data-ttu-id="c0400-132">Después de analizar los paquetes NuGet, puede que observe que solo tienen como destino .NET Framework, al igual que la mayoría de los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="c0400-132">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="c0400-133">A partir de .NET Standard 2.0 se ha introducido el modo de compatibilidad de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0400-133">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="c0400-134">Este modo de compatibilidad permite que los proyectos de .NET Standard y .NET Core hagan referencia a bibliotecas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c0400-134">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="c0400-135">La acción de hacer referencias a bibliotecas de .NET Framework no funciona para todos los proyectos; por ejemplo, si la biblioteca usa API de Windows Presentation Foundation (WPF) pero desbloquea muchos escenarios de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="c0400-135">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="c0400-136">Al hacer referencia a paquetes NuGet que tienen como destino .NET Framework en el proyecto, como [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), recibirá una advertencia de reserva de paquete ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) parecida al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0400-136">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="c0400-137">Esta advertencia se muestra cuando agrega el paquete y cada vez que compila para asegurarse de que prueba ese paquete con el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0400-137">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="c0400-138">Si el proyecto funciona según lo previsto, puede suprimir la advertencia editando las propiedades del paquete en Visual Studio o editando manualmente el archivo del proyecto en su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="c0400-138">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="c0400-139">Para suprimir la advertencia editando el archivo del proyecto, busque la entrada `PackageReference` del paquete del que quiere suprimir la advertencia y agregue el atributo `NoWarn`.</span><span class="sxs-lookup"><span data-stu-id="c0400-139">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="c0400-140">El atributo `NoWarn` acepta una lista separada por comas de todos los identificadores de advertencia.</span><span class="sxs-lookup"><span data-stu-id="c0400-140">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="c0400-141">En el ejemplo siguiente se muestra cómo suprimir la advertencia `NU1701` del paquete `Huitian.PowerCollections` editando manualmente el archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="c0400-141">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="c0400-142">Para más información sobre cómo suprimir advertencias del compilador en Visual Studio, vea [Supresión de las advertencias para paquetes NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span><span class="sxs-lookup"><span data-stu-id="c0400-142">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span></span>

### <a name="port-your-packages-to-packagereference"></a><span data-ttu-id="c0400-143">Traslado de los paquetes a `PackageReference`</span><span class="sxs-lookup"><span data-stu-id="c0400-143">Port your packages to `PackageReference`</span></span>

<span data-ttu-id="c0400-144">.NET core usa [PackageReference](/nuget/consume-packages/package-references-in-project-files) para especificar las dependencias del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-144">.NET Core uses [PackageReference](/nuget/consume-packages/package-references-in-project-files) to specify package dependencies.</span></span> <span data-ttu-id="c0400-145">Si usa [packages.config](/nuget/reference/packages-config) para especificar los paquetes, deberá convertir a `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="c0400-145">If you are using [packages.config](/nuget/reference/packages-config) to specify your packages, you will need to convert over to `PackageReference`.</span></span>

<span data-ttu-id="c0400-146">Puede aprender más en [Migrate from packages.config to PackageReference](/nuget/reference/migrate-packages-config-to-package-reference) (Migración de packages.config a PackageReference).</span><span class="sxs-lookup"><span data-stu-id="c0400-146">You can learn more at [Migrate from packages.config to PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="c0400-147">Qué hacer cuando su dependencia del paquete NuGet no se ejecuta en .NET Core</span><span class="sxs-lookup"><span data-stu-id="c0400-147">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="c0400-148">Si un paquete NuGet del que depende no se ejecuta en .NET Core, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0400-148">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="c0400-149">Si el proyecto es de código abierto y está hospedado en algún lugar como GitHub, puede implicar directamente a los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="c0400-149">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="c0400-150">Puede ponerse en contacto directamente con el autor en [nuget.org](https://www.nuget.org/). Busque el paquete y haga clic en **Contact Owners** (Póngase en contacto con los propietarios) a la izquierda de la página del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-150">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="c0400-151">Puede buscar otro paquete que se ejecute en .NET Core que efectúe la misma tarea que el paquete que estaba usando.</span><span class="sxs-lookup"><span data-stu-id="c0400-151">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="c0400-152">Puede intentar volver a escribir el código de lo que hacía el paquete usted mismo.</span><span class="sxs-lookup"><span data-stu-id="c0400-152">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="c0400-153">Puede eliminar la dependencia en el paquete mediante el cambio de la funcionalidad de la aplicación, al menos hasta que esté disponible una versión compatible del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0400-153">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="c0400-154">No olvide que los mantenedores de los proyectos de código abierto y los publicadores de paquetes NuGet suelen ser voluntarios.</span><span class="sxs-lookup"><span data-stu-id="c0400-154">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="c0400-155">Colaboran porque les importa un dominio determinado, lo hacen de forma gratuita y en muchas ocasiones tienen otro trabajo,</span><span class="sxs-lookup"><span data-stu-id="c0400-155">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="c0400-156">por lo que debe ser consciente de ello al ponerse en contacto con ellos para solicitar soporte técnico de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-156">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="c0400-157">Si no puede resolver el problema con ninguna de las sugerencias anteriores, puede que deba efectuar la portabilidad a .NET Core en otro momento.</span><span class="sxs-lookup"><span data-stu-id="c0400-157">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="c0400-158">Al equipo de .NET le gustaría saber qué bibliotecas son las más importantes para que sean compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-158">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="c0400-159">Puede enviar un correo electrónico a dotnet@microsoft.com indicando las bibliotecas que le gustaría usar.</span><span class="sxs-lookup"><span data-stu-id="c0400-159">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="c0400-160">Analizar dependencias que no son paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="c0400-160">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="c0400-161">Puede que tenga una dependencia que no sea un paquete NuGet, como un archivo DLL, en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="c0400-161">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="c0400-162">La única manera de determinar la portabilidad de esa dependencia consiste en ejecutar la herramienta [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport).</span><span class="sxs-lookup"><span data-stu-id="c0400-162">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="c0400-163">La herramienta puede analizar ensamblados que tienen como destino .NET Framework e identificar API que no se pueden portar a otras plataformas de .NET, como .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c0400-163">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="c0400-164">Puede ejecutar la herramienta como una aplicación de consola o como [extensión de Visual Studio](../../standard/analyzers/portability-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="c0400-164">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0400-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c0400-165">Next steps</span></span>

<span data-ttu-id="c0400-166">Si está realizando la portabilidad de una biblioteca, consulte [Porting your Libraries](libraries.md) (Portabilidad de las bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="c0400-166">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
