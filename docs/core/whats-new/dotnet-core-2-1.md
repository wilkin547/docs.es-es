---
title: Novedades de .NET Core 2.1
description: Obtenga información sobre las características nuevas de .NET Core 2.1.
dev_langs:
- csharp
- vb
author: rpetrusha
ms.author: ronpet
ms.date: 10/10/2018
ms.openlocfilehash: bf14e21ec4d390d8ab753bfa45533442ff4f6e68
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120952"
---
# <a name="whats-new-in-net-core-21"></a><span data-ttu-id="0bce5-103">Novedades de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0bce5-103">What's new in .NET Core 2.1</span></span>

<span data-ttu-id="0bce5-104">.NET Core 2.1 incluye mejoras y características nuevas en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bce5-104">.NET Core 2.1 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="0bce5-105">Herramientas</span><span class="sxs-lookup"><span data-stu-id="0bce5-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="0bce5-106">Puesta al día</span><span class="sxs-lookup"><span data-stu-id="0bce5-106">Roll forward</span></span>](#roll-forward)
- [<span data-ttu-id="0bce5-107">Implementación</span><span class="sxs-lookup"><span data-stu-id="0bce5-107">Deployment</span></span>](#deployment)
- [<span data-ttu-id="0bce5-108">Paquete de compatibilidad de Windows</span><span class="sxs-lookup"><span data-stu-id="0bce5-108">Windows Compatibility Pack</span></span>](#windows-compatibility-pack)
- [<span data-ttu-id="0bce5-109">Mejoras de la compilación JIT</span><span class="sxs-lookup"><span data-stu-id="0bce5-109">JIT compilation improvements</span></span>](#jit-compiler-improvements)
- [<span data-ttu-id="0bce5-110">Cambios en la API</span><span class="sxs-lookup"><span data-stu-id="0bce5-110">API changes</span></span>](#api-changes)

## <a name="tooling"></a><span data-ttu-id="0bce5-111">Tooling</span><span class="sxs-lookup"><span data-stu-id="0bce5-111">Tooling</span></span>

<span data-ttu-id="0bce5-112">El SDK de .NET Core 2.1 (v 2.1.300), el conjunto de herramientas incluidas con .NET Core 2.1, incluye los siguientes cambios y mejoras:</span><span class="sxs-lookup"><span data-stu-id="0bce5-112">The .NET Core 2.1 SDK (v 2.1.300), the tooling included with .NET Core 2.1, includes the following changes and enhancements:</span></span>

### <a name="build-performance-improvements"></a><span data-ttu-id="0bce5-113">Mejoras en el rendimiento de la compilación</span><span class="sxs-lookup"><span data-stu-id="0bce5-113">Build performance improvements</span></span>

<span data-ttu-id="0bce5-114">Un aspecto fundamental de .NET Core 2.1 es mejorar el rendimiento del tiempo de compilación, especialmente para compilaciones incrementales.</span><span class="sxs-lookup"><span data-stu-id="0bce5-114">A major focus of .NET Core 2.1 is improving build-time performance, particularly for incremental builds.</span></span> <span data-ttu-id="0bce5-115">Estas mejoras de rendimiento se aplican a las compilaciones de línea de comandos mediante `dotnet build` y a las compilaciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0bce5-115">These performance improvements apply to both command-line builds using `dotnet build` and to builds in Visual Studio.</span></span> <span data-ttu-id="0bce5-116">Algunas áreas individuales de mejora incluyen:</span><span class="sxs-lookup"><span data-stu-id="0bce5-116">Some individual areas of improvement include:</span></span>

- <span data-ttu-id="0bce5-117">Para la resolución de activos del paquete, solo se resuelven los activos utilizados por una compilación en lugar de todos los activos.</span><span class="sxs-lookup"><span data-stu-id="0bce5-117">For package asset resolution, resolving only assets used by a build rather than all assets.</span></span>

- <span data-ttu-id="0bce5-118">Almacenamiento en caché de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0bce5-118">Caching of assembly references.</span></span>

- <span data-ttu-id="0bce5-119">Uso de servidores de compilación de SDK de larga ejecución, que son procesos que se extienden a través de invocaciones `dotnet build` individuales.</span><span class="sxs-lookup"><span data-stu-id="0bce5-119">Use of long-running SDK build servers, which are processes that span across individual `dotnet build` invocations.</span></span> <span data-ttu-id="0bce5-120">Eliminan la necesidad de compilar mediante JIT grandes bloques de código cada vez que se ejecuta `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="0bce5-120">They eliminate the need to JIT-compile large blocks of code every time `dotnet build` is run.</span></span> <span data-ttu-id="0bce5-121">Los procesos del servidor de compilación se pueden terminar automáticamente con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0bce5-121">Build server processes can be automatically terminated with the following command:</span></span>

   ```console
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a><span data-ttu-id="0bce5-122">Nuevos comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="0bce5-122">New CLI commands</span></span>

<span data-ttu-id="0bce5-123">Una serie de herramientas que estaban disponibles solo en función del proyecto mediante [`DotnetCliToolReference`](../tools/extensibility.md) ahora están disponibles como parte del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-123">A number of tools that were available only on a per project basis using [`DotnetCliToolReference`](../tools/extensibility.md) are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="0bce5-124">Estas herramientas incluyen:</span><span class="sxs-lookup"><span data-stu-id="0bce5-124">These tools include:</span></span>

- <span data-ttu-id="0bce5-125">`dotnet watch` proporciona un monitor del sistema de archivos que espera que un archivo cambie antes de ejecutar un conjunto designado de comandos.</span><span class="sxs-lookup"><span data-stu-id="0bce5-125">`dotnet watch` provides a file system watcher that waits for a file to change before executing a designated set of commands.</span></span> <span data-ttu-id="0bce5-126">Por ejemplo, el siguiente comando vuelve a generar automáticamente el proyecto actual y genera un resultado detallado cada vez que cambie un archivo en él:</span><span class="sxs-lookup"><span data-stu-id="0bce5-126">For example, the following command automatically rebuilds the current project and generates verbose output whenever a file in it changes:</span></span>

   ```console
   dotnet watch -- --verbose build
   ```

   <span data-ttu-id="0bce5-127">Tenga en cuenta que la opción `--` precede a la opción `--verbose`.</span><span class="sxs-lookup"><span data-stu-id="0bce5-127">Note the `--` option that precedes the `--verbose` option.</span></span> <span data-ttu-id="0bce5-128">Delimita las opciones pasadas directamente al comando `dotnet watch` de los argumentos que se pasan al proceso `dotnet` secundario.</span><span class="sxs-lookup"><span data-stu-id="0bce5-128">It delimits the options passed directly to the `dotnet watch` command from the arguments that are passed to the child `dotnet` process.</span></span> <span data-ttu-id="0bce5-129">Sin él, la opción `--verbose` se aplica al comando `dotnet watch`, no al comando `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="0bce5-129">Without it, the `--verbose` option applies to the `dotnet watch` command, not the `dotnet build` command.</span></span>
  
   <span data-ttu-id="0bce5-130">Para obtener más información, consulte [Desarrollar aplicaciones ASP.NET Core con dotnet watch](/aspnet/core/tutorials/dotnet-watch).</span><span class="sxs-lookup"><span data-stu-id="0bce5-130">For more information, see [Develop ASP.NET Core apps using dotnet watch](/aspnet/core/tutorials/dotnet-watch)</span></span>

- <span data-ttu-id="0bce5-131">`dotnet dev-certs` genera y administra los certificados que se usan durante el desarrollo de aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-131">`dotnet dev-certs` generates and manages certificates used during development in ASP.NET Core applications.</span></span>

- <span data-ttu-id="0bce5-132">`dotnet user-secrets` administra los secretos en un almacén de secretos de usuario en aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-132">`dotnet user-secrets` manages the secrets in a user secret store in ASP.NET Core applications.</span></span>

- <span data-ttu-id="0bce5-133">`dotnet sql-cache` crea una tabla e índices en una base de datos de Microsoft SQL Server que se usará para el almacenamiento en caché distribuido.</span><span class="sxs-lookup"><span data-stu-id="0bce5-133">`dotnet sql-cache` creates a table and indexes in a Microsoft SQL Server database to be used for distributed caching.</span></span>

- <span data-ttu-id="0bce5-134">`dotnet ef` es una herramienta para administrar bases de datos, objetos <xref:Microsoft.EntityFrameworkCore.DbContext> y migraciones en las aplicaciones de Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-134">`dotnet ef` is a tool for managing databases, <xref:Microsoft.EntityFrameworkCore.DbContext> objects, and migrations in Entity Framework Core applications.</span></span> <span data-ttu-id="0bce5-135">Para obtener más información, vea [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet) (Herramienta de la línea de comandos de .NET de EF Core).</span><span class="sxs-lookup"><span data-stu-id="0bce5-135">For more information, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

### <a name="global-tools"></a><span data-ttu-id="0bce5-136">Herramientas globales</span><span class="sxs-lookup"><span data-stu-id="0bce5-136">Global Tools</span></span>

<span data-ttu-id="0bce5-137">.NET core 2.1 es compatible con *Herramientas globales*: es decir, las herramientas personalizadas que están disponibles globalmente desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0bce5-137">.NET Core 2.1 supports *Global Tools* -- that is, custom tools that are available globally from the command line.</span></span> <span data-ttu-id="0bce5-138">El modelo de extensibilidad en versiones previas de .NET Core permitió que las herramientas personalizadas estuvieran disponibles para cada proyecto solo utilizando [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).</span><span class="sxs-lookup"><span data-stu-id="0bce5-138">The extensibility model in previous versions of .NET Core made custom tools available on a per project basis only by using [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).</span></span>

<span data-ttu-id="0bce5-139">Para instalar una herramienta global, use el comando [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="0bce5-139">To install a Global Tool, you use the [dotnet tool install](../tools/dotnet-tool-install.md) command.</span></span> <span data-ttu-id="0bce5-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0bce5-140">For example:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="0bce5-141">Una vez instalada, la herramienta se puede ejecutar desde la línea de comandos especificando el nombre de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="0bce5-141">Once installed, the tool can be run from the command line by specifying the tool name.</span></span> <span data-ttu-id="0bce5-142">Para más información, vea [Información general sobre las herramientas globales de .NET Core](../tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0bce5-142">For more information, see [.NET Core Global Tools overview](../tools/global-tools.md).</span></span>

### <a name="tool-management-with-the-dotnet-tool-command"></a><span data-ttu-id="0bce5-143">Administración de herramientas con el comando `dotnet tool`</span><span class="sxs-lookup"><span data-stu-id="0bce5-143">Tool management with the `dotnet tool` command</span></span>

<span data-ttu-id="0bce5-144">En el SDK de .NET Core 2.1 (v. 2.1.300), todas las operaciones de herramientas utilizan el comando `dotnet tool`.</span><span class="sxs-lookup"><span data-stu-id="0bce5-144">In .NET Core SDK 2.1 (v 2.1.300), all tools operations use the `dotnet tool` command.</span></span> <span data-ttu-id="0bce5-145">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0bce5-145">The following options are available:</span></span>

- <span data-ttu-id="0bce5-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) para instalar una herramienta.</span><span class="sxs-lookup"><span data-stu-id="0bce5-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) to install a tool.</span></span>

- <span data-ttu-id="0bce5-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) para desinstalar y reinstalar una herramienta, lo cual la actualiza eficazmente.</span><span class="sxs-lookup"><span data-stu-id="0bce5-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) to uninstall and reinstall a tool, which effectively updates it.</span></span>

- <span data-ttu-id="0bce5-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) para enumerar las herramientas instaladas actualmente.</span><span class="sxs-lookup"><span data-stu-id="0bce5-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) to list currently installed tools.</span></span>

- <span data-ttu-id="0bce5-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) para desinstalar las herramientas instaladas actualmente.</span><span class="sxs-lookup"><span data-stu-id="0bce5-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) to uninstall currently installed tools.</span></span>

## <a name="roll-forward"></a><span data-ttu-id="0bce5-150">Puesta al día</span><span class="sxs-lookup"><span data-stu-id="0bce5-150">Roll forward</span></span>

<span data-ttu-id="0bce5-151">Todas las aplicaciones de .NET Core a partir de .NET Core 2.0 se ponen al día automáticamente a la *versión secundaria* más reciente instalada en un sistema.</span><span class="sxs-lookup"><span data-stu-id="0bce5-151">All .NET Core applications starting with the .NET Core 2.0 automatically roll forward to the latest *minor version* installed on a system.</span></span>

<span data-ttu-id="0bce5-152">A partir de .NET Core 2.0, si la versión de .NET Core que se creó una aplicación no está presente en tiempo de ejecución, la aplicación se ejecuta automáticamente en la *versión secundaria* instalada más reciente de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-152">Starting with .NET Core 2.0, if the version of .NET Core that an application was built with is not present at runtime, the application automatically runs against the latest installed *minor version* of .NET Core.</span></span> <span data-ttu-id="0bce5-153">En otras palabras, si una aplicación se compila con .NET Core 2.0, y .NET Core 2.0 no está presente en el sistema host pero sí lo está .NET Core 2.1, la aplicación se ejecuta con .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="0bce5-153">In other words, if an application is built with .NET Core 2.0, and .NET Core 2.0 is not present on the host system but .NET Core 2.1 is, the application runs with .NET Core 2.1.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bce5-154">Este comportamiento de puesta al día no se aplica para versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="0bce5-154">This roll-forward behavior doesn't apply to preview releases.</span></span> <span data-ttu-id="0bce5-155">Tampoco se aplica a las versiones principales.</span><span class="sxs-lookup"><span data-stu-id="0bce5-155">Nor does it apply to major releases.</span></span> <span data-ttu-id="0bce5-156">Por ejemplo, una aplicación .NET Core 1.0 no se actualizaría a .NET Core 2.0 o .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="0bce5-156">For example, a .NET Core 1.0 application wouldn't roll forward to .NET Core 2.0 or .NET Core 2.1.</span></span>

<span data-ttu-id="0bce5-157">También puede deshabilitarla la puesta al día de versiones secundarias de cualquiera de estas tres formas:</span><span class="sxs-lookup"><span data-stu-id="0bce5-157">You can also disable minor version roll forward in any of three ways:</span></span>

- <span data-ttu-id="0bce5-158">Establezca la variable de entorno `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` en 0.</span><span class="sxs-lookup"><span data-stu-id="0bce5-158">Set the `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` environment variable to 0.</span></span>

- <span data-ttu-id="0bce5-159">Agregue la siguiente línea al archivo runtimeconfig.json:</span><span class="sxs-lookup"><span data-stu-id="0bce5-159">Add the following line to the runtimeconfig.json file:</span></span>

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- <span data-ttu-id="0bce5-160">Cuando use [herramientas de la CLI de .NET Core](../tools/index.md), incluya la siguiente opción con un comando de .NET Core, como `run`:</span><span class="sxs-lookup"><span data-stu-id="0bce5-160">When using [.NET Core CLI tools](../tools/index.md), include the following option with a .NET Core command such as `run`:</span></span>

   ```console
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

## <a name="deployment"></a><span data-ttu-id="0bce5-161">Implementación</span><span class="sxs-lookup"><span data-stu-id="0bce5-161">Deployment</span></span>

### <a name="self-contained-application-servicing"></a><span data-ttu-id="0bce5-162">Mantenimiento de aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="0bce5-162">Self-contained application servicing</span></span>

<span data-ttu-id="0bce5-163">`dotnet publish` ahora publica aplicaciones independientes con una versión en tiempo de ejecución con mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0bce5-163">`dotnet publish` now publishes self-contained applications with a serviced runtime version.</span></span> <span data-ttu-id="0bce5-164">Cuando publica una aplicación independiente con el SDK 2.1 de .NET Core (v. 2.1.300), su aplicación incluye la última versión de tiempo de ejecución con mantenimiento conocida por ese SDK.</span><span class="sxs-lookup"><span data-stu-id="0bce5-164">When you publish a self-contained application with the .NET Core 2.1 SDK (v 2.1.300), your application includes the latest serviced runtime version known by that SDK.</span></span> <span data-ttu-id="0bce5-165">Cuando actualice a la versión más reciente del SDK, publicará con la versión más reciente del tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-165">When you upgrade to the latest SDK, you’ll publish with the latest .NET Core runtime version.</span></span> <span data-ttu-id="0bce5-166">Esto se aplica para tiempos de ejecución de .NET Core 1.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0bce5-166">This applies for .NET Core 1.0 runtimes and later.</span></span>

<span data-ttu-id="0bce5-167">La publicación independiente se basa en las versiones del tiempo de ejecución en NuGet.org. No necesita tener el tiempo de ejecución con mantenimiento en su máquina.</span><span class="sxs-lookup"><span data-stu-id="0bce5-167">Self-contained publishing relies on runtime versions on NuGet.org. You do not need to have the serviced runtime on your machine.</span></span>

<span data-ttu-id="0bce5-168">Con el SDK de .NET Core 2.0, las aplicaciones independientes se publican con el tiempo de ejecución de .NET Core 2.0.0 a menos que se especifique una versión diferente a través de la propiedad `RuntimeFrameworkVersion`.</span><span class="sxs-lookup"><span data-stu-id="0bce5-168">Using the .NET Core 2.0 SDK, self-contained applications are published with the .NET Core 2.0.0 runtime unless a different version is specified via the `RuntimeFrameworkVersion` property.</span></span> <span data-ttu-id="0bce5-169">Con este nuevo comportamiento, ya no será necesario configurar esta propiedad para seleccionar una versión de tiempo de ejecución más alta para una aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="0bce5-169">With this new behavior, you’ll no longer need to set this property to select a higher runtime version for a self-contained application.</span></span> <span data-ttu-id="0bce5-170">El enfoque más sencillo a partir de ahora es publicar siempre con el SDK de .NET Core 2.1 (v. 2.1.300).</span><span class="sxs-lookup"><span data-stu-id="0bce5-170">The easiest approach going forward is to always publish with .NET Core 2.1 SDK (v 2.1.300).</span></span>

<span data-ttu-id="0bce5-171">Para obtener más información, vea [Self-contained deployment runtime roll forward](../deploying/runtime-patch-selection.md) (Puesta al día de runtimes de implementación independientes).</span><span class="sxs-lookup"><span data-stu-id="0bce5-171">For more information, see [Self-contained deploymnet runtime roll forward](../deploying/runtime-patch-selection.md).</span></span>
## <a name="windows-compatibility-pack"></a><span data-ttu-id="0bce5-172">Paquete de compatibilidad de Windows</span><span class="sxs-lookup"><span data-stu-id="0bce5-172">Windows Compatibility Pack</span></span>

<span data-ttu-id="0bce5-173">Al trasladar el código existente de .NET Framework a .NET Core, puede usar el [paquete de compatibilidad de Windows](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="0bce5-173">When you port existing code from the .NET Framework to .NET Core, you can use the [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span> <span data-ttu-id="0bce5-174">Esto proporciona acceso a 20 000 API más de las que están disponibles en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-174">It provides access to 20,000 more APIs than are available in .NET Core.</span></span> <span data-ttu-id="0bce5-175">Estas API incluyen tipos en el espacio de nombres <xref:System.Drawing?displayProperty=nameWithType>, la clase <xref:System.Diagnostics.EventLog>, WMI, contadores de rendimiento, servicios de Windows y los tipos y miembros de Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="0bce5-175">These APIs include types in the <xref:System.Drawing?displayProperty=nameWithType> namespace, the <xref:System.Diagnostics.EventLog> class, WMI, Performance Counters, Windows Services, and the Windows registry types and members.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="0bce5-176">Mejoras del compilador JIT</span><span class="sxs-lookup"><span data-stu-id="0bce5-176">JIT compiler improvements</span></span>

<span data-ttu-id="0bce5-177">.NET Core incorpora una nueva tecnología de compilador JIT denominada *compilación por niveles* (también conocida como *optimización adaptable*) que puede mejorar significativamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0bce5-177">.NET Core incorporates a new JIT compiler technology called *tiered compilation* (also known as *adaptive optimization*) that can significantly improve performance.</span></span> <span data-ttu-id="0bce5-178">La compilación por niveles es una configuración opcional.</span><span class="sxs-lookup"><span data-stu-id="0bce5-178">Tiered compilation is an opt-in setting.</span></span>

<span data-ttu-id="0bce5-179">Una de las tareas importantes realizadas por el compilador JIT es optimizar la ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="0bce5-179">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="0bce5-180">Sin embargo, para las rutas de código poco utilizadas, el compilador puede dedicar más tiempo a la optimización del código del que dedica el tiempo de ejecución a ejecutar el código no optimizado.</span><span class="sxs-lookup"><span data-stu-id="0bce5-180">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends running unoptimized code.</span></span> <span data-ttu-id="0bce5-181">La compilación por niveles incluye dos fases en la compilación JIT:</span><span class="sxs-lookup"><span data-stu-id="0bce5-181">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="0bce5-182">Un **primer nivel**, que genera código tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="0bce5-182">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="0bce5-183">Un **segundo nivel**, que genera código optimizado para los métodos que se ejecutan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0bce5-183">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="0bce5-184">El segundo nivel de la compilación se realiza en paralelo para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0bce5-184">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="0bce5-185">Puede participar en la compilación en niveles de cualquiera de estas dos maneras.</span><span class="sxs-lookup"><span data-stu-id="0bce5-185">You can opt into tiered compilation in either of two ways.</span></span>

- <span data-ttu-id="0bce5-186">Para utilizar la compilación en capas en todos los proyectos que utilizan el SDK de .NET Core 2.1, establezca la variable de entorno siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bce5-186">To use tiered compilation in all projects that use the .NET Core 2.1 SDK, set the following environment variable:</span></span>

  ```console
  COMPlus_TieredCompilation="1"
  ```

- <span data-ttu-id="0bce5-187">Para utilizar la compilación por niveles por proyecto, agregue la propiedad `<TieredCompilation>` a la sección `<PropertyGroup>` del archivo de proyecto de MSBuild, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bce5-187">To use tiered compilation on a per-project basis, add the `<TieredCompilation>` property to the `<PropertyGroup>` section of the MSBuild project file, as the following example shows:</span></span>

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a><span data-ttu-id="0bce5-188">Cambios en la API</span><span class="sxs-lookup"><span data-stu-id="0bce5-188">API changes</span></span>

### <a name="spant-and-memoryt"></a><span data-ttu-id="0bce5-189">`Span<T>` y `Memory<T>`</span><span class="sxs-lookup"><span data-stu-id="0bce5-189">`Span<T>` and `Memory<T>`</span></span>

<span data-ttu-id="0bce5-190">.NET Core 2.1 incluye algunos tipos nuevos que hacen que trabajar con matrices y otros tipos de memoria sea mucho más eficiente.</span><span class="sxs-lookup"><span data-stu-id="0bce5-190">.NET Core 2.1 includes some new types that make working with arrays and other types of memory much more efficient.</span></span> <span data-ttu-id="0bce5-191">Estos nuevos tipos incluyen:</span><span class="sxs-lookup"><span data-stu-id="0bce5-191">The new types include:</span></span>

- <span data-ttu-id="0bce5-192"><xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-192"><xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="0bce5-193"><xref:System.Memory%601?displayProperty=nameWithType> y <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-193"><xref:System.Memory%601?displayProperty=nameWithType> and <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0bce5-194">Sin estos tipos, al pasar tales elementos como una porción de una matriz o una sección de un búfer de memoria, debe hacer una copia de una parte de los datos antes de pasarlo a un método.</span><span class="sxs-lookup"><span data-stu-id="0bce5-194">Without these types, when passing such items as a portion of an array or a section of a memory buffer, you have to make a copy of some portion of the data before passing it to a method.</span></span> <span data-ttu-id="0bce5-195">Estos tipos proporcionan una vista virtual de los datos que elimina la necesidad de ejecutar operaciones adicionales de copia y asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="0bce5-195">These types provide a virtual view of that data that eliminates the need for the additional memory allocation and copy operations.</span></span>

<span data-ttu-id="0bce5-196">En el ejemplo siguiente se usa una instancia de <xref:System.Span%601> y <xref:System.Memory%601> para proporcionar una vista virtual de 10 elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="0bce5-196">The following example uses a <xref:System.Span%601> and <xref:System.Memory%601> instance to provide a virtual view of 10 elements of an array.</span></span>

[!CODE-csharp[Span\<T>](~/samples/core/whats-new/whats-new-in-21/cs/program.cs)]

[!CODE-vb[Memory\<T>](~/samples/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a><span data-ttu-id="0bce5-197">Compresión de Brotli</span><span class="sxs-lookup"><span data-stu-id="0bce5-197">Brotli compression</span></span>

<span data-ttu-id="0bce5-198">.NET Core 2.1 agrega compatibilidad con la compresión y descompresión de Brotli.</span><span class="sxs-lookup"><span data-stu-id="0bce5-198">.NET Core 2.1 adds support for Brotli compression and decompression.</span></span> <span data-ttu-id="0bce5-199">Brotli es un algoritmo de compresión sin pérdida de datos de uso general que se define en [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) y es compatible con la mayoría de los exploradores web y servidores web principales.</span><span class="sxs-lookup"><span data-stu-id="0bce5-199">Brotli is a general-purpose lossless compression algorithm that is defined in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) and is supported by most web browsers and major web servers.</span></span> <span data-ttu-id="0bce5-200">Puede usar la clase <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> basada en secuencias o las clases <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> y <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> basadas en intervalos de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0bce5-200">You can use the stream-based <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> class or the high-performance span-based <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> and <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> classes.</span></span> <span data-ttu-id="0bce5-201">En el ejemplo siguiente se muestra la compresión con la clase <xref:System.IO.Compression.BrotliStream>:</span><span class="sxs-lookup"><span data-stu-id="0bce5-201">The following example illustrates compression with the <xref:System.IO.Compression.BrotliStream> class:</span></span>

[!CODE-csharp[Brotli compression](~/samples/core/whats-new/whats-new-in-21/cs/brotli.cs#1)]

<span data-ttu-id="0bce5-202">El comportamiento de <xref:System.IO.Compression.BrotliStream> es el mismo que <xref:System.IO.Compression.DeflateStream> y <xref:System.IO.Compression.GZipStream>, lo que facilita la conversión de código que llama a estas API a <xref:System.IO.Compression.BrotliStream>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-202">The <xref:System.IO.Compression.BrotliStream> behavior is the same as <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream>, which makes it easy to convert code that calls these APIs to <xref:System.IO.Compression.BrotliStream>.</span></span>

### <a name="new-cryptography-apis-and-cryptography-improvements"></a><span data-ttu-id="0bce5-203">Nuevas API de criptografía y mejoras de criptografía</span><span class="sxs-lookup"><span data-stu-id="0bce5-203">New cryptography APIs and cryptography improvements</span></span>

<span data-ttu-id="0bce5-204">.NET Core 2.1 incluye numerosas mejoras para las API de criptografía:</span><span class="sxs-lookup"><span data-stu-id="0bce5-204">.NET Core 2.1 includes numerous enhancements to the cryptography APIs:</span></span>

- <span data-ttu-id="0bce5-205"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> está disponible en el paquete System.Security.Cryptography.Pkcs.</span><span class="sxs-lookup"><span data-stu-id="0bce5-205"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> is available in the System.Security.Cryptography.Pkcs package.</span></span> <span data-ttu-id="0bce5-206">La implementación es la misma que la clase <xref:System.Security.Cryptography.Pkcs.SignedCms> en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0bce5-206">The implementation is the same as the <xref:System.Security.Cryptography.Pkcs.SignedCms> class in the .NET Framework.</span></span>

- <span data-ttu-id="0bce5-207">Las nuevas sobrecargas de los métodos <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> y <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> aceptan un identificador de algoritmo hash para permitir que los autores de la llamada obtengan valores de huella digital de certificado utilizando algoritmos distintos de SHA-1.</span><span class="sxs-lookup"><span data-stu-id="0bce5-207">New overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> and <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> methods accept a hash algorithm identifier to enable callers to get certificate thumbprint values using algorithms other than SHA-1.</span></span>

- <span data-ttu-id="0bce5-208">Las nuevas API de criptografía basadas en <xref:System.Span%601> están disponibles para crear valores hash, HMAC, generación de números aleatorios criptográficos, generación de firmas asimétricas, procesamiento de firmas asimétricas y cifrado RSA.</span><span class="sxs-lookup"><span data-stu-id="0bce5-208">New <xref:System.Span%601>-based cryptography APIs are available for hashing, HMAC, cryptographic random number generation, asymmetric signature generation, asymmetric signature processing, and RSA encryption.</span></span>

- <span data-ttu-id="0bce5-209">El rendimiento de <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> mejoró aproximadamente un 15 % mediante el uso de una implementación basada en <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-209">The performance of <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> has improved by about 15% by using a <xref:System.Span%601>-based implementation.</span></span>

- <span data-ttu-id="0bce5-210">La nueva clase <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> incluye dos nuevos métodos:</span><span class="sxs-lookup"><span data-stu-id="0bce5-210">The new <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> class includes two new methods:</span></span>

  - <span data-ttu-id="0bce5-211"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> tarda una cantidad fija de tiempo en devolver dos entradas cualesquiera de la misma longitud, siendo así adecuada para su uso en la comprobación criptográfica para evitar contribuir al control de tiempo de la información en el canal.</span><span class="sxs-lookup"><span data-stu-id="0bce5-211"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> takes a fixed amount of time to return for any two inputs of the same length, which makes it suitable for use in cryptographic verification to avoid contributing to timing side-channel information.</span></span>

  - <span data-ttu-id="0bce5-212"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> es una rutina de borrado de memoria que no se puede optimizar.</span><span class="sxs-lookup"><span data-stu-id="0bce5-212"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> is a memory-clearing routine that cannot be optimized.</span></span>

- <span data-ttu-id="0bce5-213">El método estático <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> rellena un <xref:System.Span%601> con valores aleatorios.</span><span class="sxs-lookup"><span data-stu-id="0bce5-213">The static <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> method fills a <xref:System.Span%601> with random values.</span></span>

- <span data-ttu-id="0bce5-214"><xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> ahora es compatible con Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="0bce5-214">The <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> is now supported on Linux and maxOS.</span></span>

- <span data-ttu-id="0bce5-215">La curva elíptica Diffie-Hellman (ECDH) ahora está disponible en la familia de clases <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-215">Elliptic-Curve Diffie-Hellman (ECDH) is now available in the <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType> class family.</span></span> <span data-ttu-id="0bce5-216">El área expuesta es la misma que en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0bce5-216">The surface area is the same as in the .NET Framework.</span></span>

- <span data-ttu-id="0bce5-217">La instancia devuelta por <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> puede cifrar o descifrar con OAEP con un resumen de SHA-2, así como generar o validar firmas mediante RSA-PSS.</span><span class="sxs-lookup"><span data-stu-id="0bce5-217">The instance returned by <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> can encrypt or decrypt with OAEP using a SHA-2 digest, as well as generate or validate signatures using RSA-PSS.</span></span>

### <a name="sockets-improvements"></a><span data-ttu-id="0bce5-218">Mejoras en los sockets</span><span class="sxs-lookup"><span data-stu-id="0bce5-218">Sockets improvements</span></span>

<span data-ttu-id="0bce5-219">.NET Core incluye un nuevo tipo, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> y una reescritura <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, que forman la base de las API de red de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="0bce5-219">.NET Core includes a new type, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, and a rewritten <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, that form the basis of higher-level networking APIs.</span></span>  <span data-ttu-id="0bce5-220"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, por ejemplo, es la base de la implementación <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-220"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, for example, is the basis of the <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="0bce5-221">En versiones anteriores de .NET Core, las API de nivel superior se basaban en implementaciones de redes nativas.</span><span class="sxs-lookup"><span data-stu-id="0bce5-221">In previous versions of .NET Core, higher-level APIs were based on native networking implementations.</span></span>

<span data-ttu-id="0bce5-222">La implementación de sockets introducida en .NET Core 2.1 presenta una serie de ventajas:</span><span class="sxs-lookup"><span data-stu-id="0bce5-222">The sockets implementation introduced in .NET Core 2.1 has a number of advantages:</span></span>

- <span data-ttu-id="0bce5-223">Una mejora significativa del rendimiento en comparación con la implementación anterior.</span><span class="sxs-lookup"><span data-stu-id="0bce5-223">A significant performance improvement when compared with the previous implementation.</span></span>

- <span data-ttu-id="0bce5-224">Eliminación de las dependencias de plataforma, lo que simplifica la implementación y el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0bce5-224">Elimination of platform dependencies, which simplifies deployment and servicing.</span></span>

- <span data-ttu-id="0bce5-225">Comportamiento coherente en todas las plataformas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bce5-225">Consistent behavior across all .NET Core platforms.</span></span>

<span data-ttu-id="0bce5-226"><xref:System.Net.Http.SocketsHttpHandler> es la implementación predeterminada en .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="0bce5-226"><xref:System.Net.Http.SocketsHttpHandler> is the default implementation in .NET Core 2.1.</span></span> <span data-ttu-id="0bce5-227">Sin embargo, puede configurar su aplicación para usar la clase anterior <xref:System.Net.Http.HttpClientHandler> llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="0bce5-227">However, you can configure your application to use the older <xref:System.Net.Http.HttpClientHandler> class by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

<span data-ttu-id="0bce5-228">También puede usar una variable de entorno para optar por no usar implementaciones de sockets basadas en <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-228">You can also use an environment variable to opt out of using sockets implementations based on <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="0bce5-229">Para ello, configure `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` en `false` o en 0.</span><span class="sxs-lookup"><span data-stu-id="0bce5-229">To do this, set the `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` to either `false` or 0.</span></span>

<span data-ttu-id="0bce5-230">En Windows, también puede optar por usar <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, que se basa en una implementación nativa, o la clase <xref:System.Net.Http.SocketsHttpHandler> pasando una instancia de la clase al constructor <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-230">On Windows, you can also choose to use <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, which relies on a native implementation, or the <xref:System.Net.Http.SocketsHttpHandler> class by passing an instance of the class to the <xref:System.Net.Http.HttpClient> constructor.</span></span>

<span data-ttu-id="0bce5-231">En Linux y macOS, solo se puede configurar <xref:System.Net.Http.HttpClient> para cada proceso.</span><span class="sxs-lookup"><span data-stu-id="0bce5-231">On Linux and macOS, you can only configure <xref:System.Net.Http.HttpClient> on a per-process basis.</span></span> <span data-ttu-id="0bce5-232">En Linux, deberá implementar [libcurl](https://curl.haxx.se/libcurl/) si desea usar la antigua implementación de <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="0bce5-232">On Linux, you need to deploy [libcurl](https://curl.haxx.se/libcurl/) if you want to use the old <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="0bce5-233">(Se instala con .NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="0bce5-233">(It is installed with .NET Core 2.0.)</span></span>

## <a name="see-also"></a><span data-ttu-id="0bce5-234">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bce5-234">See also</span></span>

* [<span data-ttu-id="0bce5-235">Novedades de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0bce5-235">What's new in .NET Core</span></span>](index.md)  
* [<span data-ttu-id="0bce5-236">Novedades de EF Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0bce5-236">New features in EF Core 2.1</span></span>](/ef/core/what-is-new/ef-core-2.1)  
* [<span data-ttu-id="0bce5-237">Novedades de ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0bce5-237">What's new in ASP.NET Core 2.1</span></span>](/aspnet/core/aspnetcore-2.1)
