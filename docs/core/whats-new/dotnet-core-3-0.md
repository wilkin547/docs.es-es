---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 05/06/2019
ms.openlocfilehash: f7dc95a9f0b652f1509720fb987cbdb88f64e78c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689256"
---
# <a name="whats-new-in-net-core-30-preview-5"></a><span data-ttu-id="69705-103">Novedades de .NET Core 3.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="69705-103">What's new in .NET Core 3.0 (Preview 5)</span></span>

<span data-ttu-id="69705-104">En este artículo se describen las novedades de .NET Core 3.0 (a través de la versión preliminar 5).</span><span class="sxs-lookup"><span data-stu-id="69705-104">This article describes what is new in .NET Core 3.0 (through preview 5).</span></span> <span data-ttu-id="69705-105">Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="69705-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="69705-106">Mediante el componente Escritorio de Windows del SDK de .NET Core 3.0, puede portar sus aplicaciones de Windows Forms y Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="69705-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="69705-107">Para ser más precisos, el componente Escritorio de Windows solo se admite e incluye en Windows.</span><span class="sxs-lookup"><span data-stu-id="69705-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="69705-108">Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="69705-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="69705-109">.NET Core 3.0 agrega compatibilidad con C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="69705-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="69705-110">Se recomienda muy especialmente utilizar la versión más reciente de Visual Studio 2019 Update 1 Preview o VSCode con la extensión de OmniSharp.</span><span class="sxs-lookup"><span data-stu-id="69705-110">It's highly recommended that you use the latest release of Visual Studio 2019 Update 1 Preview or VSCode with the OmniSharp extension.</span></span>

<span data-ttu-id="69705-111">[Descargue la versión preliminar 5 de .NET Core 3.0 y empiece a trabajar](https://aka.ms/netcore3download) ya en Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="69705-111">[Download and get started with .NET Core 3.0 Preview 5](https://aka.ms/netcore3download) right now on Windows, Mac, and Linux.</span></span>

<span data-ttu-id="69705-112">Si desea obtener más información sobre cada versión preliminar, vea los anuncios siguientes:</span><span class="sxs-lookup"><span data-stu-id="69705-112">For more information about each preview release, see the following announcements:</span></span>

- [<span data-ttu-id="69705-113">Anuncio de la versión preliminar 5 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="69705-113">.NET Core 3.0 Preview 5 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [<span data-ttu-id="69705-114">Anuncio de la versión preliminar 4 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="69705-114">.NET Core 3.0 Preview 4 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [<span data-ttu-id="69705-115">Anuncio de la versión preliminar 3 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="69705-115">.NET Core 3.0 Preview 3 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [<span data-ttu-id="69705-116">Anuncio de la versión preliminar 2 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="69705-116">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [<span data-ttu-id="69705-117">Anuncio de la versión preliminar 1 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="69705-117">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="69705-118">Windows Installer del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="69705-118">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="69705-119">El instalador MSI para Windows ha cambiado a partir de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="69705-119">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="69705-120">Los instaladores del SDK actualizarán ahora las versiones de la banda de características del SDK.</span><span class="sxs-lookup"><span data-stu-id="69705-120">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="69705-121">Las bandas de características se definen en los grupos de *centenas* de la sección *revisión* del número de versión.</span><span class="sxs-lookup"><span data-stu-id="69705-121">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="69705-122">Por ejemplo, **3.0.\*101**\* y **3.0.\*201**\* son versiones de dos bandas de características distintas mientras que **3.0.\*101**\* y **3.0.\*199**\* están en la misma banda de características.</span><span class="sxs-lookup"><span data-stu-id="69705-122">For example, **3.0.\*101**\* and **3.0.\*201**\* are versions in two different feature bands while **3.0.\*101**\* and **3.0.\*199**\* are in the same feature band.</span></span> <span data-ttu-id="69705-123">Y, cuando se instale el SDK **3.0.\*101**\* de .NET Core, se quitará el SDK **3.0.\*100**\* de .NET Core de la máquina si existe.</span><span class="sxs-lookup"><span data-stu-id="69705-123">And, when .NET Core SDK **3.0.\*101**\* is installed, .NET Core SDK **3.0.\*100**\* will be removed from the machine if it exists.</span></span> <span data-ttu-id="69705-124">Cuando se instale el SDK **3.0.\*200**\* de .NET Core en la misma máquina, no se quitará el SDK **3.0.\*101**\* de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="69705-124">When .NET Core SDK **3.0.\*200**\* is installed on the same machine, .NET Core SDK **3.0.\*101**\* won't be removed.</span></span>

<span data-ttu-id="69705-125">Para obtener más información sobre las versiones, vea el artículo de [introducción a la creación de versiones de .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="69705-125">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

## <a name="c-80-preview"></a><span data-ttu-id="69705-126">Versión preliminar de C# 8.0</span><span class="sxs-lookup"><span data-stu-id="69705-126">C# 8.0 preview</span></span>

<span data-ttu-id="69705-127">.NET Core 3.0 admite la versión preliminar de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="69705-127">.NET Core 3.0 supports C# 8 preview.</span></span> <span data-ttu-id="69705-128">Para obtener más información sobre las características de C# 8.0, vea [Novedades de C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="69705-128">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="69705-129">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="69705-129">.NET Standard 2.1</span></span>

<span data-ttu-id="69705-130">Aunque .NET Core 3.0 admite **.NET Standard 2.1**, la plantilla predeterminada `dotnet new classlib` genera un proyecto destinado a **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="69705-130">Even though .NET Core 3.0 supports **.NET Standard 2.1**, the default `dotnet new classlib` template generates a project that targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="69705-131">Para destinarlo a **.NET Standard 2.1**, edite el archivo de proyecto y cambie la propiedad `TargetFramework` a `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="69705-131">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
 
  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>
 
</Project>
```

<span data-ttu-id="69705-132">Si usa Visual Studio, necesita Visual Studio 2019, ya que Visual Studio 2017 no admite **.NET Standard 2.1** ni **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="69705-132">If you're using Visual Studio, you need Visual Studio 2019, as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span> <span data-ttu-id="69705-133">Se recomienda muy especialmente utilizar [Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/).</span><span class="sxs-lookup"><span data-stu-id="69705-133">We highly recommend that you use [Visual Studio 2019 Update 1 Preview](https://visualstudio.microsoft.com/vs/preview/).</span></span>

## <a name="improved-net-core-version-apis"></a><span data-ttu-id="69705-134">API de versión mejoradas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="69705-134">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="69705-135">A partir de .NET Core 3.0, las API de versión incluidas con .NET Core ahora devuelven la información que se espera.</span><span class="sxs-lookup"><span data-stu-id="69705-135">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="69705-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="69705-136">For example:</span></span>

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="69705-137">Cambio importante.</span><span class="sxs-lookup"><span data-stu-id="69705-137">Breaking change.</span></span> <span data-ttu-id="69705-138">Se trata técnicamente de un cambio importante, porque ha cambiado el esquema de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="69705-138">This is technically a breaking change because the versioning scheme has changed.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="69705-139">Elementos intrínsecos dependientes de la plataforma .NET</span><span class="sxs-lookup"><span data-stu-id="69705-139">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="69705-140">Se han agregado API que permiten el acceso a determinadas instrucciones CPU orientadas al rendimiento, como los conjuntos de **instrucciones de manipulación de bits** o **SIMD**.</span><span class="sxs-lookup"><span data-stu-id="69705-140">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="69705-141">Estas instrucciones pueden ayudar a conseguir importantes mejoras de rendimiento en ciertos escenarios, como el procesamiento de datos con eficiencia en paralelo.</span><span class="sxs-lookup"><span data-stu-id="69705-141">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> 

<span data-ttu-id="69705-142">En su caso, las bibliotecas de .NET han comenzado a utilizar estas instrucciones para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69705-142">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="69705-143">Para obtener más información, vea el artículo sobre [elementos intrínsecos dependientes de la plataforma .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span><span class="sxs-lookup"><span data-stu-id="69705-143">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

## <a name="default-executables"></a><span data-ttu-id="69705-144">Archivos ejecutables predeterminados</span><span class="sxs-lookup"><span data-stu-id="69705-144">Default executables</span></span>

<span data-ttu-id="69705-145">.NET Core compila ahora [archivos ejecutables dependientes del marco](../deploying/index.md#framework-dependent-executables-fde) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69705-145">.NET Core now builds [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="69705-146">Este comportamiento es nuevo en las aplicaciones que usan una versión de .NET Core instalada globalmente.</span><span class="sxs-lookup"><span data-stu-id="69705-146">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="69705-147">Anteriormente, solo las [implementaciones independientes](../deploying/index.md#self-contained-deployments-scd) generarían un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="69705-147">Previously, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="69705-148">Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable que coincide con el entorno y la plataforma del SDK que se usa.</span><span class="sxs-lookup"><span data-stu-id="69705-148">During `dotnet build` or `dotnet publish`, an executable is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="69705-149">Estos ejecutables funcionan de la misma forma que los ejecutables nativos:</span><span class="sxs-lookup"><span data-stu-id="69705-149">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="69705-150">Haga doble clic en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="69705-150">You can double-click on the executable.</span></span>
* <span data-ttu-id="69705-151">También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="69705-151">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="single-file-executables"></a><span data-ttu-id="69705-152">Archivos ejecutables de único archivo</span><span class="sxs-lookup"><span data-stu-id="69705-152">Single-file executables</span></span>

<span data-ttu-id="69705-153">El comando `dotnet publish` admite empaquetar la aplicación en un ejecutable de archivo único específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="69705-153">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="69705-154">El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69705-154">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="69705-155">Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación.</span><span class="sxs-lookup"><span data-stu-id="69705-155">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="69705-156">El inicio es más rápido cuando se vuelve a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69705-156">Startup is faster when the application is run again.</span></span> <span data-ttu-id="69705-157">La aplicación no necesita extraerse por segunda vez a menos que se haya utilizado una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="69705-157">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="69705-158">Para publicar un ejecutable de archivo único, establezca `PublishSingleFile` en el proyecto o en la línea de comandos con el comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="69705-158">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

<span data-ttu-id="69705-159">Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="69705-159">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="69705-160">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="69705-160">Tiered compilation</span></span>

<span data-ttu-id="69705-161">La [compilación en niveles](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) está activada de forma predeterminada con .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="69705-161">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="69705-162">Esta característica permite que el runtime utilice el compilador Just-In-Time (JIT) de forma más flexible para generar un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69705-162">This feature enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance.</span></span>

<span data-ttu-id="69705-163">La principal ventaja de TC es permitir el uso de métodos de compilación y recompilación JIT de mayor lentitud pero más rápidos para generar código, o de mayor calidad pero más lentos para generar código.</span><span class="sxs-lookup"><span data-stu-id="69705-163">The main benefit of TC is to enable (re-)jitting methods with slower-but-faster to produce code or higher-quality-but-slower to produce code.</span></span> <span data-ttu-id="69705-164">Esto contribuye a aumentar el rendimiento de una aplicación a medida que pasa por distintas fases de ejecución, desde el inicio hasta alcanzar el estado estable.</span><span class="sxs-lookup"><span data-stu-id="69705-164">This helps increase performance of an application as it goes through various stages of execution, from startup through steady-state.</span></span> <span data-ttu-id="69705-165">Esto contrasta con el enfoque no TC, donde cada método se compila de una sola manera (al igual que el nivel de alta calidad), que se inclina por el estado estable sobre el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="69705-165">This contrasts with the non-TC approach, where every method is compiled a single way (the same as the high-quality tier), which is biased to steady-state over startup performance.</span></span>

<span data-ttu-id="69705-166">Para habilitar JIT rápido (código de nivel 0 con compilación JIT), use esta opción en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="69705-166">To enable Quick JIT (tier 0 jitted code), use this setting in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="69705-167">Para deshabilitar completamente TC, use esta opción en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="69705-167">To disable TC completely, use this setting in your project file:</span></span>

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="build-copies-dependencies"></a><span data-ttu-id="69705-168">Compilación de dependencias de copias</span><span class="sxs-lookup"><span data-stu-id="69705-168">Build copies dependencies</span></span>

<span data-ttu-id="69705-169">El comando `dotnet build` copia ahora las dependencias de NuGet para la aplicación de la caché de NuGet a la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="69705-169">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="69705-170">Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="69705-170">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="69705-171">Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.</span><span class="sxs-lookup"><span data-stu-id="69705-171">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-tools"></a><span data-ttu-id="69705-172">Herramientas locales</span><span class="sxs-lookup"><span data-stu-id="69705-172">Local tools</span></span>

<span data-ttu-id="69705-173">.NET Core 3.0 presenta herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="69705-173">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="69705-174">Las herramientas locales son similares a las [herramientas globales](../tools/global-tools.md) pero están asociadas a una ubicación concreta en el disco.</span><span class="sxs-lookup"><span data-stu-id="69705-174">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="69705-175">Las herramientas locales no están disponibles globalmente y se distribuyen como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="69705-175">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="69705-176">Si ha probado herramientas locales en la versión preliminar 1 de .NET Core 3.0, tales como la ejecución de `dotnet tool restore` o de `dotnet tool install`, elimine la carpeta de caché de herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="69705-176">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="69705-177">En caso contrario, las herramientas locales no funcionan en las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="69705-177">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="69705-178">Esta carpeta se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="69705-178">This folder is located at:</span></span>
>
> <span data-ttu-id="69705-179">En macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="69705-179">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="69705-180">En Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="69705-180">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="69705-181">Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="69705-181">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="69705-182">Este archivo de manifiesto define las herramientas que estarán disponibles en esa carpeta y a continuación.</span><span class="sxs-lookup"><span data-stu-id="69705-182">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="69705-183">Puede distribuir el archivo de manifiesto con su código para asegurarse de que todo aquel que trabaje con su código pueda restaurar y utilizar las mismas herramientas.</span><span class="sxs-lookup"><span data-stu-id="69705-183">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="69705-184">Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="69705-184">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="69705-185">Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="69705-185">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="69705-186">Para instalar estas herramientas local o globalmente, aún tendría que instalar [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="69705-186">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="major-version-roll-forward"></a><span data-ttu-id="69705-187">Puesta al día de versiones principales</span><span class="sxs-lookup"><span data-stu-id="69705-187">Major-version Roll Forward</span></span>

<span data-ttu-id="69705-188">.NET Core 3.0 presenta una característica opcional que permite poner la aplicación al día con la versión principal más reciente de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="69705-188">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="69705-189">Además, se agregó una nueva configuración para controlar cómo se aplica la puesta al día a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69705-189">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="69705-190">Esto se puede configurar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="69705-190">This can be configured in the following ways:</span></span>

- <span data-ttu-id="69705-191">Propiedad de archivo del proyecto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="69705-191">Project file property: `RollForward`</span></span>
- <span data-ttu-id="69705-192">Propiedad de archivo de configuración del entorno de ejecución: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="69705-192">Runtime configuration file property: `rollForward`</span></span>
- <span data-ttu-id="69705-193">Variable de entorno: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="69705-193">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="69705-194">Argumento de línea de comandos: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="69705-194">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="69705-195">Debe especificarse uno de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="69705-195">One of the following values must be specified.</span></span> <span data-ttu-id="69705-196">Si se omite la configuración, **Minor** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69705-196">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="69705-197">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="69705-197">**LatestPatch**</span></span>\
<span data-ttu-id="69705-198">Se pone al día con la última versión de revisión.</span><span class="sxs-lookup"><span data-stu-id="69705-198">Roll forward to the highest patch version.</span></span> <span data-ttu-id="69705-199">Se deshabilita la puesta al día de versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="69705-199">This disables minor version roll forward.</span></span>
- <span data-ttu-id="69705-200">**Minor**</span><span class="sxs-lookup"><span data-stu-id="69705-200">**Minor**</span></span>\
<span data-ttu-id="69705-201">Se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="69705-201">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="69705-202">Si se encuentra la versión secundaria solicitada, se utiliza la directiva **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="69705-202">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="69705-203">**Major**</span><span class="sxs-lookup"><span data-stu-id="69705-203">**Major**</span></span>\
<span data-ttu-id="69705-204">Se pone al día con la versión secundaria mínima superior, y la versión secundaria mínima, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="69705-204">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="69705-205">Si se encuentra la versión principal solicitada, se utiliza la directiva **Minor**.</span><span class="sxs-lookup"><span data-stu-id="69705-205">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="69705-206">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="69705-206">**LatestMinor**</span></span>\
<span data-ttu-id="69705-207">Se pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="69705-207">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="69705-208">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="69705-208">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="69705-209">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="69705-209">**LatestMajor**</span></span>\
<span data-ttu-id="69705-210">Se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="69705-210">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="69705-211">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="69705-211">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="69705-212">**Disable**</span><span class="sxs-lookup"><span data-stu-id="69705-212">**Disable**</span></span>\
<span data-ttu-id="69705-213">No se pone al día.</span><span class="sxs-lookup"><span data-stu-id="69705-213">Don't roll forward.</span></span> <span data-ttu-id="69705-214">Solo se enlaza a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="69705-214">Only bind to specified version.</span></span> <span data-ttu-id="69705-215">No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="69705-215">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="69705-216">Este valor solo se recomienda a efectos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="69705-216">This value is only recommended for testing.</span></span>

<span data-ttu-id="69705-217">Además del valor **Disable**, todos los valores usarán la última versión de revisión disponible.</span><span class="sxs-lookup"><span data-stu-id="69705-217">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="69705-218">Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="69705-218">Windows desktop</span></span>

<span data-ttu-id="69705-219">.NET Core 3.0 admite aplicaciones de escritorio de Windows con Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="69705-219">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="69705-220">Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="69705-220">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="69705-221">El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="69705-221">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="69705-222">Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="69705-222">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="69705-223">Visual Studio 2019 agrega plantillas de **nuevo proyecto** para WPF y Windows Forms de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="69705-223">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="69705-224">Para obtener más información sobre cómo migrar una aplicación existente de .NET Framework, vea los artículos sobre [cómo portar proyectos de WPF](../porting/wpf.md) y [cómo portar proyectos de Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="69705-224">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../porting/wpf.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

## <a name="com-callable-components---windows-desktop"></a><span data-ttu-id="69705-225">Componentes COM invocables: Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="69705-225">COM-callable components - Windows Desktop</span></span>

<span data-ttu-id="69705-226">En Windows, ahora puede crear componentes COM administrados invocables.</span><span class="sxs-lookup"><span data-stu-id="69705-226">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="69705-227">Esta capacidad es fundamental para usar .NET Core con modelos de complemento COM, así como para ofrecer paridad con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69705-227">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="69705-228">A diferencia de .NET Framework, donde se utilizó *mscoree.dll* como servidor COM, .NET Core agregará un archivo dll de inicio nativo al directorio *bin* al compilar el componente COM.</span><span class="sxs-lookup"><span data-stu-id="69705-228">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="69705-229">Para ver un ejemplo de cómo crear un componente COM y usarlo, consulte la [demostración de COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="69705-229">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

## <a name="msix-deployment---windows-desktop"></a><span data-ttu-id="69705-230">Implementación de MSIX: Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="69705-230">MSIX Deployment - Windows Desktop</span></span>

<span data-ttu-id="69705-231">[MSIX](https://docs.microsoft.com/windows/msix/) es un nuevo formato de paquete de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="69705-231">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="69705-232">Se puede usar para implementar aplicaciones de escritorio de .NET Core 3.0 en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="69705-232">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="69705-233">El [proyecto de paquete de aplicación de Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponible en Visual Studio 2019, le permite crear paquetes de MSIX con aplicaciones de .NET Core [independientes](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="69705-233">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

<span data-ttu-id="69705-234">El archivo del proyecto de .NET Core debe especificar los tiempos de ejecución admitidos en la propiedad `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="69705-234">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-highdpi"></a><span data-ttu-id="69705-235">HighDPI de WinForms</span><span class="sxs-lookup"><span data-stu-id="69705-235">WinForms HighDPI</span></span>

<span data-ttu-id="69705-236">En .NET Core, las aplicaciones de Windows Forms pueden establecer el modo de valores altos de PPP con <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69705-236">.NET Core Windows Forms applications can set High DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="69705-237">El método `SetHighDpiMode` establece el modo de valores altos de PPP correspondiente a menos que la opción se haya establecido por otros medios como `App.Manifest` o P/Invoke antes de `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="69705-237">The `SetHighDpiMode` method sets the corresponding High DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="69705-238">Los posibles valores de `highDpiMode`, expresados por la enumeración <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> son:</span><span class="sxs-lookup"><span data-stu-id="69705-238">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

* `DpiUnaware`
* `SystemAware`
* `PerMonitor`
* `PerMonitorV2`
* `DpiUnawareGdiScaled`

<span data-ttu-id="69705-239">Para obtener más información sobre los modos de valores altos de PPP, vea el artículo sobre [desarrollo de aplicaciones de escritorio con valores altos de PPP en Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="69705-239">For more information about High DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="69705-240">Rangos e índices</span><span class="sxs-lookup"><span data-stu-id="69705-240">Ranges and indices</span></span>

<span data-ttu-id="69705-241">El nuevo tipo <xref:System.Index?displayProperty=nameWithType> se puede utilizar para la indización.</span><span class="sxs-lookup"><span data-stu-id="69705-241">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="69705-242">Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:</span><span class="sxs-lookup"><span data-stu-id="69705-242">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="69705-243">Existe también el tipo <xref:System.Range?displayProperty=nameWithType>, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de intervalo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="69705-243">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="69705-244">Luego puede crear un índice con un `Range`, lo que genera un segmento:</span><span class="sxs-lookup"><span data-stu-id="69705-244">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="69705-245">Para obtener más información, vea el [tutorial sobre intervalos e índices](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="69705-245">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="69705-246">Flujos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="69705-246">Async streams</span></span>

<span data-ttu-id="69705-247">El tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> es una nueva versión asincrónica de <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="69705-247">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="69705-248">El lenguaje permite ejecutar la instrucción `await foreach` en `IAsyncEnumerable<T>` para consumir sus elementos, y usar la instrucción `yield return` en ellos para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="69705-248">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="69705-249">En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="69705-249">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="69705-250">La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="69705-250">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="69705-251">Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="69705-251">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

<span data-ttu-id="69705-252">Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="69705-252">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="69705-253">Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.</span><span class="sxs-lookup"><span data-stu-id="69705-253">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="69705-254">Para obtener más información, vea el [tutorial sobre flujos asincrónicos](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="69705-254">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="69705-255">Mejoras de punto flotante de IEEE</span><span class="sxs-lookup"><span data-stu-id="69705-255">IEEE Floating-point improvements</span></span>

<span data-ttu-id="69705-256">Las API de punto flotante se actualizan para cumplir con la [revisión IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="69705-256">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="69705-257">El objetivo de estos cambios es exponer todas operaciones **requeridas** y asegurarse de que cumplen con la especificación IEEE. Para obtener más información sobre las mejoras de punto flotante, vea la entrada de blog sobre [mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="69705-257">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="69705-258">Entre las correcciones de análisis y formato se incluyen:</span><span class="sxs-lookup"><span data-stu-id="69705-258">Parsing and formatting fixes include:</span></span>

* <span data-ttu-id="69705-259">Analice y redondee entradas de cualquier longitud correctamente.</span><span class="sxs-lookup"><span data-stu-id="69705-259">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="69705-260">Analice y formatee el cero negativo correctamente.</span><span class="sxs-lookup"><span data-stu-id="69705-260">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="69705-261">Análisis correcto de `Infinity` y `NaN` al hacer una comprobación que no distingue mayúsculas de minúsculas y permitir un `+` anterior opcional cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="69705-261">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="69705-262">Entre las nuevas API <xref:System.Math?displayProperty=nameWithType> se incluyen:</span><span class="sxs-lookup"><span data-stu-id="69705-262">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

* <span data-ttu-id="69705-263"><xref:System.Math.BitIncrement(System.Double)> y <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="69705-263"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="69705-264">Corresponde a las operaciones IEEE `nextUp` y `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="69705-264">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="69705-265">Devuelven el número de punto flotante más pequeño que compara mayor o menor que la entrada (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="69705-265">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="69705-266">Por ejemplo, `Math.BitIncrement(0.0)` devolvería `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="69705-266">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* <span data-ttu-id="69705-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> y <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="69705-267"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="69705-268">Corresponde a las operaciones IEEE `maxNumMag` y `minNumMag`, que devuelven el valor que es mayor o menor en magnitud de las dos entradas (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="69705-268">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="69705-269">Por ejemplo, `Math.MaxMagnitude(2.0, -3.0)` devolvería `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="69705-269">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="69705-270">Corresponde a la operación IEEE `logB` que devuelve un valor entero, devuelve el logaritmo en base 2 integral del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="69705-270">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="69705-271">Este método es efectivamente el mismo que `floor(log2(x))`, pero con errores de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="69705-271">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="69705-272">Corresponde a la operación IEEE `scaleB` que toma un valor integral, devuelve eficazmente `x * pow(2, n)`, pero se realiza con errores de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="69705-272">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="69705-273">Corresponde a la operación IEEE `log2`. Devuelve el logaritmo de base 2.</span><span class="sxs-lookup"><span data-stu-id="69705-273">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="69705-274">Minimiza el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="69705-274">It minimizes rounding error.</span></span>

* <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="69705-275">Corresponde a la operación IEEE `fma`. Realiza una multiplicación y suma fusionadas.</span><span class="sxs-lookup"><span data-stu-id="69705-275">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="69705-276">Es decir, realiza `(x * y) + z` como operación única, minimizando así el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="69705-276">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="69705-277">Un ejemplo sería `FusedMultiplyAdd(1e308, 2.0, -1e308)`, que devuelve `1e308`.</span><span class="sxs-lookup"><span data-stu-id="69705-277">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="69705-278">La operación `(1e308 * 2.0) - 1e308` regular devuelve `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="69705-278">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="69705-279">Corresponde a la operación IEEE `copySign`. Devuelve el valor de `x`, pero con el signo de `y`.</span><span class="sxs-lookup"><span data-stu-id="69705-279">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="69705-280">Compatibilidad con JSON integrada con rápido rendimiento</span><span class="sxs-lookup"><span data-stu-id="69705-280">Fast built-in JSON support</span></span>

<span data-ttu-id="69705-281">Los usuarios de .NET han contado en gran medida en [**Json.NET**](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones.</span><span class="sxs-lookup"><span data-stu-id="69705-281">.NET users have largely relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="69705-282">**Json.NET** utiliza cadenas de .NET como tipo de datos base, que, en esencia, es UTF-16.</span><span class="sxs-lookup"><span data-stu-id="69705-282">**Json.NET** uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="69705-283">La nueva compatibilidad con JSON integrada es el alto rendimiento, una baja asignación y se basa en `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="69705-283">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="69705-284">Se han agregado tres nuevos tipos relacionados con JSON principales a .NET Core 3.0 y el espacio de nombres <xref:System.Text.Json?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69705-284">Three new main JSON-related types have been added to .NET Core 3.0 the <xref:System.Text.Json?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="69705-285">Estos tipos *aún* no admiten la serialización y deserialización de objetos CLR estándar (POCO).</span><span class="sxs-lookup"><span data-stu-id="69705-285">These types don't *yet* support plain old CLR object (POCO) serialization and deserialization.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="69705-286">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="69705-286">Utf8JsonReader</span></span>

<span data-ttu-id="69705-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="69705-287"><xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="69705-288">`Utf8JsonReader` es un tipo fundamental, de bajo nivel, que se puede usar para compilar los analizadores personalizados y deserializadores.</span><span class="sxs-lookup"><span data-stu-id="69705-288">The `Utf8JsonReader` is a foundational, low-level type, that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="69705-289">La lectura a través de una carga JSON con el nuevo lector `Utf8JsonReader` es el doble de rápido que con el lector de **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="69705-289">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="69705-290">No se asigna hasta que haya que actualizar tokens JSON como cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="69705-290">It doesn't allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="69705-291">Este es un ejemplo de lectura a través del archivo [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creado por Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="69705-291">Here is an example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a><span data-ttu-id="69705-292">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="69705-292">Utf8JsonWriter</span></span>

<span data-ttu-id="69705-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> proporciona una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento, sin almacenar en caché y de solo avance a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="69705-293"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="69705-294">Al igual que el lector, el sistema de escritura es un tipo fundamental, de bajo nivel, que puede usarse para generar serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="69705-294">Like the reader, the writer is a foundational, low-level type, that can be used to build custom serializers.</span></span> <span data-ttu-id="69705-295">Escribir una carga JSON con el nuevo `Utf8JsonWriter` es un 30-80 % más rápido que con el escritor de **Json.NET** y no se asigna.</span><span class="sxs-lookup"><span data-stu-id="69705-295">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and doesn't allocate.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="69705-296">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="69705-296">JsonDocument</span></span>

<span data-ttu-id="69705-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> se basa en `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="69705-297"><xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="69705-298">`JsonDocument` proporciona la capacidad de analizar datos JSON y crear un Document Object Model (DOM) de solo lectura que se puede consultar para admitir el acceso aleatorio y la enumeración.</span><span class="sxs-lookup"><span data-stu-id="69705-298">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="69705-299">A los elementos JSON que componen los datos se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement> que se expone mediante `JsonDocument` como una propiedad denominada `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="69705-299">The JSON elements that compose the data can be accessed via the <xref:System.Text.Json.JsonElement> type that is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="69705-300">El `JsonElement` contiene la matriz de JSON y enumeradores del objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="69705-300">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="69705-301">El análisis de una carga útil típica de JSON y el acceso a todos sus miembros usando `JsonDocument` es 2-3 veces más rápido que con **Json.NET** con pequeñas asignaciones de datos de tamaño razonable (es decir, < 1 MB).</span><span class="sxs-lookup"><span data-stu-id="69705-301">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with little allocations for data that is reasonably sized (that is, < 1 MB).</span></span>

<span data-ttu-id="69705-302">A continuación se muestra un uso del ejemplo del `JsonDocument` y `JsonElement` que se puede utilizar como punto inicial:</span><span class="sxs-lookup"><span data-stu-id="69705-302">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

<span data-ttu-id="69705-303">Este es un ejemplo de lectura de C# 8.0 a través del archivo [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) creado por Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="69705-303">Here is a C# 8.0 example of reading through the [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) file created by Visual Studio Code:</span></span>

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a><span data-ttu-id="69705-304">JsonSerializer</span><span class="sxs-lookup"><span data-stu-id="69705-304">JsonSerializer</span></span>

<span data-ttu-id="69705-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> se compila sobre <xref:System.Text.Json.Utf8JsonReader> y <xref:System.Text.Json.Utf8JsonWriter> para proporcionar una rápida opción de serialización de baja memoria cuando se trabaja con documentos y fragmentos de JSON.</span><span class="sxs-lookup"><span data-stu-id="69705-305"><xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> is built on top of <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter> to provide a fast low-memory serialization option when working with JSON documents and fragments.</span></span>

<span data-ttu-id="69705-306">EXAMINAR: https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md para ver un ejemplo de portar en este artículo</span><span class="sxs-lookup"><span data-stu-id="69705-306">EXAMINE: https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md for an example to port to this article</span></span>

<span data-ttu-id="69705-307">Este es un ejemplo de serialización de un objeto en JSON:</span><span class="sxs-lookup"><span data-stu-id="69705-307">Here is an example of serializing an object to JSON:</span></span>

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

<span data-ttu-id="69705-308">Este es un ejemplo de deserialización de una cadena JSON en un objeto.</span><span class="sxs-lookup"><span data-stu-id="69705-308">Here is an example of deserializing a JSON string to an object.</span></span> <span data-ttu-id="69705-309">Puede usar la cadena JSON generada en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="69705-309">You can use the JSON string produced by the previous example:</span></span>

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a><span data-ttu-id="69705-310">Mejoras de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="69705-310">Interop improvements</span></span>

<span data-ttu-id="69705-311">.NET Core 3.0 mejora la interoperabilidad nativa de API.</span><span class="sxs-lookup"><span data-stu-id="69705-311">.NET Core 3.0 improves native API interop.</span></span>

### <a name="type-nativelibrary"></a><span data-ttu-id="69705-312">Tipo: NativeLibrary</span><span class="sxs-lookup"><span data-stu-id="69705-312">Type: NativeLibrary</span></span>

<span data-ttu-id="69705-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> ofrece una encapsulación para cargar una biblioteca nativa (con la misma lógica de carga que P/Invoke en .NET Core) y proporcionar funciones auxiliares relevantes, como `getSymbol`.</span><span class="sxs-lookup"><span data-stu-id="69705-313"><xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> provides an encapsulation for loading a native library (using the same load logic as .NET Core P/Invoke) and providing the relevant helper functions such as `getSymbol`.</span></span> <span data-ttu-id="69705-314">Para obtener un ejemplo de código, vea la [demostración de DLLMap](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="69705-314">For a code example, see the [DLLMap Demo](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="69705-315">Interoperabilidad nativa de Windows</span><span class="sxs-lookup"><span data-stu-id="69705-315">Windows Native Interop</span></span>

<span data-ttu-id="69705-316">Windows ofrece una API nativa enriquecida en forma de API de C sin formato, COM y WinRT.</span><span class="sxs-lookup"><span data-stu-id="69705-316">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="69705-317">Mientras que .NET Core admite **P/Invoke**, .NET Core 3.0 agrega la capacidad de **API COM CoCreate** y **API WinRT Activate**.</span><span class="sxs-lookup"><span data-stu-id="69705-317">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="69705-318">Para obtener un ejemplo de código, vea la [demostración de Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="69705-318">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="http2-support"></a><span data-ttu-id="69705-319">Compatibilidad con HTTP/2</span><span class="sxs-lookup"><span data-stu-id="69705-319">HTTP/2 support</span></span>

<span data-ttu-id="69705-320">El tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> es compatible con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="69705-320">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="69705-321">La compatibilidad está actualmente deshabilitada, pero puede activarse llamando a `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` antes de usar <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="69705-321">Support is currently disabled but can be turned on by calling `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` before you use <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="69705-322">También puede habilitar la compatibilidad con HTTP/2 estableciendo la variable de entorno `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` en `true` antes de ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69705-322">You can also enable HTTP/2 support by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` environment variable to `true` before you run your app.</span></span>

<span data-ttu-id="69705-323">Si se habilita HTTP/2, se negociará la versión del protocolo HTTP a través de TLS/ALPN y solo se usará HTTP/2 si el servidor opta por usarlo.</span><span class="sxs-lookup"><span data-stu-id="69705-323">If HTTP/2 is enabled, the HTTP protocol version will be negotiated via TLS/ALPN, and HTTP/2 will only be used if the server elects to use it.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="69705-324">TLS 1.3 y OpenSSL 1.1.1 en Linux</span><span class="sxs-lookup"><span data-stu-id="69705-324">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="69705-325">.NET Core aprovecha ahora la ventaja de la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), cuando está disponible en un entorno determinado.</span><span class="sxs-lookup"><span data-stu-id="69705-325">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="69705-326">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="69705-326">With TLS 1.3:</span></span>

* <span data-ttu-id="69705-327">Se han mejorado los tiempos de conexión con menores recorridos de ida y vuelta necesarios entre el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="69705-327">Connection times are improved with reduced round trips required between the client and server.</span></span>
* <span data-ttu-id="69705-328">Se ha mejorado la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros.</span><span class="sxs-lookup"><span data-stu-id="69705-328">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="69705-329">Cuando está disponible, .NET Core 3.0 utiliza **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** en un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="69705-329">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="69705-330">Si **OpenSSL 1.1.1** está disponible, los tipos <xref:System.Net.Security.SslStream?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>, utilizarán **TLS 1.3** (suponiendo que el cliente y el servidor admitan **TLS 1.3**).</span><span class="sxs-lookup"><span data-stu-id="69705-330">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

>[!IMPORTANT]
><span data-ttu-id="69705-331">Windows y macOS aún no admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="69705-331">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="69705-332">.NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="69705-332">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="69705-333">El siguiente ejemplo de C# 8.0 muestra .NET Core 3.0 en Ubuntu 18.10 al conectarse a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="69705-333">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a><span data-ttu-id="69705-334">Cifrados de criptografía</span><span class="sxs-lookup"><span data-stu-id="69705-334">Cryptography ciphers</span></span>

<span data-ttu-id="69705-335">.NET 3.0 agrega compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> y <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectivamente.</span><span class="sxs-lookup"><span data-stu-id="69705-335">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="69705-336">Estos dos algoritmos son [algoritmos AEAD (Authenticated Encryption with Associated Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="69705-336">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="69705-337">El código siguiente muestra cómo utilizar cifrado `AesGcm` para cifrar y descifrar datos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="69705-337">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="69705-338">Importación y exportación de claves criptográfica</span><span class="sxs-lookup"><span data-stu-id="69705-338">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="69705-339">.NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas en formatos estándar.</span><span class="sxs-lookup"><span data-stu-id="69705-339">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="69705-340">No es necesario utilizar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="69705-340">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="69705-341">Todos los tipos de clave, como *RSA*, *DSA*, *ECDsa* y *ECDiffieHellman*, admiten los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="69705-341">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

* <span data-ttu-id="69705-342">**Clave pública**</span><span class="sxs-lookup"><span data-stu-id="69705-342">**Public Key**</span></span>
  * <span data-ttu-id="69705-343">SubjectPublicKeyInfo X.509</span><span class="sxs-lookup"><span data-stu-id="69705-343">X.509 SubjectPublicKeyInfo</span></span>

* <span data-ttu-id="69705-344">**Clave privada**</span><span class="sxs-lookup"><span data-stu-id="69705-344">**Private key**</span></span>
  * <span data-ttu-id="69705-345">PrivateKeyInfo PKCS#8</span><span class="sxs-lookup"><span data-stu-id="69705-345">PKCS#8 PrivateKeyInfo</span></span>
  * <span data-ttu-id="69705-346">EncryptedPrivateKeyInfo PKCS#8</span><span class="sxs-lookup"><span data-stu-id="69705-346">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="69705-347">Las claves RSA también admiten:</span><span class="sxs-lookup"><span data-stu-id="69705-347">RSA keys also support:</span></span>

* <span data-ttu-id="69705-348">**Clave pública**</span><span class="sxs-lookup"><span data-stu-id="69705-348">**Public Key**</span></span>
  * <span data-ttu-id="69705-349">RSAPublicKey PKCS#1</span><span class="sxs-lookup"><span data-stu-id="69705-349">PKCS#1 RSAPublicKey</span></span>

* <span data-ttu-id="69705-350">**Clave privada**</span><span class="sxs-lookup"><span data-stu-id="69705-350">**Private key**</span></span>
  * <span data-ttu-id="69705-351">RSAPrivateKey PKCS#1</span><span class="sxs-lookup"><span data-stu-id="69705-351">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="69705-352">Los métodos de exportación generan datos binarios con codificación DER y los métodos de importación esperan lo mismo.</span><span class="sxs-lookup"><span data-stu-id="69705-352">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="69705-353">Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.</span><span class="sxs-lookup"><span data-stu-id="69705-353">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="69705-354">Los archivos **PKCS#8** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> y los archivos **PFX/PKCS#12** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69705-354">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="69705-355">Los archivos **PFX/PKCS#12** se pueden manipular con <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="69705-355">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="69705-356">SerialPort para Linux</span><span class="sxs-lookup"><span data-stu-id="69705-356">SerialPort for Linux</span></span>

<span data-ttu-id="69705-357">.NET Core 3.0 admite <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.</span><span class="sxs-lookup"><span data-stu-id="69705-357">.NET Core 3.0 supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="69705-358">Anteriormente, .NET Core solo admitía el uso de `SerialPort` en Windows.</span><span class="sxs-lookup"><span data-stu-id="69705-358">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

## <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="69705-359">Docker y límites de memoria de cgroup</span><span class="sxs-lookup"><span data-stu-id="69705-359">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="69705-360">A partir de la versión preliminar 3, la ejecución de .NET Core 3.0 en Linux con Docker funciona mejor con límites de memoria de cgroup.</span><span class="sxs-lookup"><span data-stu-id="69705-360">Starting with Preview 3, running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="69705-361">La ejecución de un contenedor de Docker con límites de memoria, como con `docker run -m`, cambia el comportamiento de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="69705-361">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

* <span data-ttu-id="69705-362">Tamaño predeterminado del montón del recolector de elementos no utilizados (GC): máximo de 20 MB o 75 % del límite de memoria en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="69705-362">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
* <span data-ttu-id="69705-363">Puede establecerse el tamaño explícito como número absoluto o porcentaje del límite de cgroup.</span><span class="sxs-lookup"><span data-stu-id="69705-363">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
* <span data-ttu-id="69705-364">El tamaño mínimo del segmento reservado por el montón de GC es de 16 MB.</span><span class="sxs-lookup"><span data-stu-id="69705-364">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="69705-365">Con este tamaño se reduce el número de montones que se crean en las máquinas.</span><span class="sxs-lookup"><span data-stu-id="69705-365">This size reduces the number of heaps that are created on machines.</span></span>

## <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="69705-366">Tamaños del montón de recolección de elementos no utilizados más pequeños</span><span class="sxs-lookup"><span data-stu-id="69705-366">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="69705-367">Se ha reducido el tamaño predeterminado del montón del recolector de elementos no utilizados, lo que se traduce en que .NET Core usa menos memoria.</span><span class="sxs-lookup"><span data-stu-id="69705-367">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="69705-368">Este cambio se adapta mejor al presupuesto de asignación de generación 0 con tamaños de caché de procesador moderno.</span><span class="sxs-lookup"><span data-stu-id="69705-368">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

## <a name="garbage-collection-large-page-support"></a><span data-ttu-id="69705-369">Compatibilidad con Large Pages de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="69705-369">Garbage Collection Large Page support</span></span>

<span data-ttu-id="69705-370">Large Pages (también conocida como Huge Pages en Linux) es una característica en la que el sistema operativo es capaz de establecer regiones de memoria más grandes que el tamaño de página nativo (a menudo, 4 K) para mejorar el rendimiento de la aplicación que solicita estas páginas grandes.</span><span class="sxs-lookup"><span data-stu-id="69705-370">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="69705-371">Ahora, el recolector de elementos no utilizados puede configurarse con el valor **GCLargePages** como característica opcional para elegir la asignación de páginas grandes en Windows.</span><span class="sxs-lookup"><span data-stu-id="69705-371">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="69705-372">Compatibilidad de GPIO con Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="69705-372">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="69705-373">Se han publicado dos paquetes en NuGet que puede usar para la programación de GPIO:</span><span class="sxs-lookup"><span data-stu-id="69705-373">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

* [<span data-ttu-id="69705-374">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="69705-374">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
* [<span data-ttu-id="69705-375">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="69705-375">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="69705-376">Los paquetes GPIO incluyen interfaces API para dispositivos *GPIO*, *SPI*, *I2C* y *PWM*.</span><span class="sxs-lookup"><span data-stu-id="69705-376">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="69705-377">El paquete de enlaces de IoT incluye enlaces de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="69705-377">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="69705-378">Para obtener más información, vea el [repositorio de GitHub de los dispositivos](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="69705-378">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="69705-379">Compatibilidad con ARM64 para Linux</span><span class="sxs-lookup"><span data-stu-id="69705-379">ARM64 Linux support</span></span>

<span data-ttu-id="69705-380">.NET Core 3.0 agrega compatibilidad con ARM64 para Linux.</span><span class="sxs-lookup"><span data-stu-id="69705-380">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="69705-381">El principal caso de uso de ARM64 son escenarios de IoT.</span><span class="sxs-lookup"><span data-stu-id="69705-381">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="69705-382">Para obtener más información, vea el artículo sobre el [estado de ARM64 de .NET Core](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="69705-382">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="69705-383">[Hay imágenes de docker para .NET Core en ARM64](https://hub.docker.com/r/microsoft/dotnet/) disponibles para Alpine, Debian y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="69705-383">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="69705-384">Windows aún no ofrece soporte técnico para **ARM64**.</span><span class="sxs-lookup"><span data-stu-id="69705-384">**ARM64** Windows support isn't yet available.</span></span>
