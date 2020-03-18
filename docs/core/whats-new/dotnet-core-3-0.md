---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 6e85c2c3e796ae59a13f944bd4913e4b7316c56a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397828"
---
# <a name="whats-new-in-net-core-30"></a><span data-ttu-id="e33e1-103">Novedades de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e33e1-103">What's new in .NET Core 3.0</span></span>

<span data-ttu-id="e33e1-104">En este artículo se describen las novedades de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-104">This article describes what is new in .NET Core 3.0.</span></span> <span data-ttu-id="e33e1-105">Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="e33e1-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="e33e1-106">Mediante el componente Escritorio de Windows del SDK de .NET Core 3.0, puede portar sus aplicaciones de Windows Forms y Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e33e1-106">By using the .NET Core 3.0 SDK component Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="e33e1-107">Para ser más precisos, el componente Escritorio de Windows solo se admite e incluye en Windows.</span><span class="sxs-lookup"><span data-stu-id="e33e1-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="e33e1-108">Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-108">For more information, see the [Windows desktop](#windows-desktop) section later in this article.</span></span>

<span data-ttu-id="e33e1-109">.NET Core 3.0 agrega compatibilidad con C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-109">.NET Core 3.0 adds support for C# 8.0.</span></span> <span data-ttu-id="e33e1-110">Se recomienda encarecidamente usar [Visual Studio 2019, versión 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o una versión posterior, [Visual Studio para Mac 8.3](/visualstudio/mac/install-preview) o una versión posterior, o [Visual Studio Code](https://code.visualstudio.com/) con la última **extensión de C#** .</span><span class="sxs-lookup"><span data-stu-id="e33e1-110">It's highly recommended that you use [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or newer, [Visual Studio for Mac 8.3](/visualstudio/mac/install-preview) or newer, or [Visual Studio Code](https://code.visualstudio.com/) with the latest **C# extension**.</span></span>

<span data-ttu-id="e33e1-111">[Descargue .NET Core 3.0 y empiece a trabajar](https://aka.ms/netcore3download) ya en Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="e33e1-111">[Download and get started with .NET Core 3.0](https://aka.ms/netcore3download) right now on Windows, macOS, or Linux.</span></span>

<span data-ttu-id="e33e1-112">Para obtener más información acerca de la versión, consulte el [anuncio de .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="e33e1-112">For more information about the release, see the [.NET Core 3.0 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).</span></span>

<span data-ttu-id="e33e1-113">Microsoft considera .NET Core RC1 como listo para producción y es totalmente compatible.</span><span class="sxs-lookup"><span data-stu-id="e33e1-113">.NET Core RC1 was considered production ready by Microsoft and was fully supported.</span></span> <span data-ttu-id="e33e1-114">Si usa una versión preliminar, debe pasar a la versión RTM para obtener soporte técnico continuo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-114">If you're using a preview release, you must move to the RTM version for continued support.</span></span>

## <a name="language-improvements-c-80"></a><span data-ttu-id="e33e1-115">Mejoras del lenguaje C# 8.0</span><span class="sxs-lookup"><span data-stu-id="e33e1-115">Language improvements C# 8.0</span></span>

<span data-ttu-id="e33e1-116">C# 8.0 también forma parte de esta versión, que incluye la característica de [tipos de referencia que aceptan valores NULL](../../csharp/tutorials/nullable-reference-types.md), [flujos asincrónicos](../../csharp/tutorials/generate-consume-asynchronous-stream.md) y [más patrones](../../csharp/tutorials/pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-116">C# 8.0 is also part of this release, which includes the [nullable reference types](../../csharp/tutorials/nullable-reference-types.md) feature, [async streams](../../csharp/tutorials/generate-consume-asynchronous-stream.md), and [more patterns](../../csharp/tutorials/pattern-matching.md).</span></span> <span data-ttu-id="e33e1-117">Para obtener más información sobre las características de C# 8.0, vea [Novedades de C# 8.0](../../csharp/whats-new/csharp-8.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-117">For more information about C# 8.0 features, see [What's new in C# 8.0](../../csharp/whats-new/csharp-8.md).</span></span>

<span data-ttu-id="e33e1-118">Se han agregado mejoras del lenguaje para admitir las siguientes características de API que se detallan a continuación:</span><span class="sxs-lookup"><span data-stu-id="e33e1-118">Language enhancements were added to support the following API features detailed below:</span></span>

- [<span data-ttu-id="e33e1-119">Rangos e índices</span><span class="sxs-lookup"><span data-stu-id="e33e1-119">Ranges and indices</span></span>](#ranges-and-indices)
- [<span data-ttu-id="e33e1-120">Flujos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="e33e1-120">Async streams</span></span>](#async-streams)

## <a name="net-standard-21"></a><span data-ttu-id="e33e1-121">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="e33e1-121">.NET Standard 2.1</span></span>

<span data-ttu-id="e33e1-122">.NET Core 3.0 implementa **.NET Standard 2.1**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-122">.NET Core 3.0 implements **.NET Standard 2.1**.</span></span> <span data-ttu-id="e33e1-123">Pero la plantilla predeterminada `dotnet new classlib` genera un proyecto que sigue destinado a **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-123">However, the default `dotnet new classlib` template generates a project that still targets **.NET Standard 2.0**.</span></span> <span data-ttu-id="e33e1-124">Para destinarlo a **.NET Standard 2.1**, edite el archivo de proyecto y cambie la propiedad `TargetFramework` a `netstandard2.1`:</span><span class="sxs-lookup"><span data-stu-id="e33e1-124">To target **.NET Standard 2.1**, edit your project file and change the `TargetFramework` property to `netstandard2.1`:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="e33e1-125">Si usa Visual Studio, necesita [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), ya que Visual Studio 2017 no admite **.NET Standard 2.1** ni **.NET Core 3.0**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-125">If you're using Visual Studio, you need [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), as Visual Studio 2017 doesn't support **.NET Standard 2.1** or **.NET Core 3.0**.</span></span>

## <a name="compiledeploy"></a><span data-ttu-id="e33e1-126">Compilación e implementación</span><span class="sxs-lookup"><span data-stu-id="e33e1-126">Compile/Deploy</span></span>

### <a name="default-executables"></a><span data-ttu-id="e33e1-127">Archivos ejecutables predeterminados</span><span class="sxs-lookup"><span data-stu-id="e33e1-127">Default executables</span></span>

<span data-ttu-id="e33e1-128">Ahora .NET Core compila [archivos ejecutables dependientes del entorno de ejecución](../deploying/index.md#publish-runtime-dependent) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-128">.NET Core now builds [runtime-dependent executables](../deploying/index.md#publish-runtime-dependent) by default.</span></span> <span data-ttu-id="e33e1-129">Este comportamiento es nuevo en las aplicaciones que usan una versión de .NET Core instalada globalmente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-129">This behavior is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="e33e1-130">Anteriormente, solo las [implementaciones independientes](../deploying/index.md#publish-self-contained) generarían un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="e33e1-130">Previously, only [self-contained deployments](../deploying/index.md#publish-self-contained) would produce an executable.</span></span>

<span data-ttu-id="e33e1-131">Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable (conocido como **appHost**) que coincide con el entorno y la plataforma del SDK que se usa.</span><span class="sxs-lookup"><span data-stu-id="e33e1-131">During `dotnet build` or `dotnet publish`, an executable (known as the **appHost**) is created that matches the environment and platform of the SDK you're using.</span></span> <span data-ttu-id="e33e1-132">Estos ejecutables funcionan de la misma forma que los ejecutables nativos:</span><span class="sxs-lookup"><span data-stu-id="e33e1-132">You can expect the same things with these executables as you would other native executables, such as:</span></span>

- <span data-ttu-id="e33e1-133">Haga doble clic en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="e33e1-133">You can double-click on the executable.</span></span>
- <span data-ttu-id="e33e1-134">También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="e33e1-134">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

### <a name="macos-apphost-and-notarization"></a><span data-ttu-id="e33e1-135">appHost y certificación de macOS</span><span class="sxs-lookup"><span data-stu-id="e33e1-135">macOS appHost and notarization</span></span>

<span data-ttu-id="e33e1-136">*Solo para macOS*</span><span class="sxs-lookup"><span data-stu-id="e33e1-136">*macOS only*</span></span>

<span data-ttu-id="e33e1-137">A partir del SDK de .NET Core 3.0 para macOS certificado, el valor para generar un archivo ejecutable predeterminado (conocido como appHost) está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-137">Starting with the notarized .NET Core SDK 3.0 for macOS, the setting to produce a default executable (known as the appHost) is disabled by default.</span></span> <span data-ttu-id="e33e1-138">Para obtener más información, vea [Certificación de macOS Catalina y el impacto en las descargas y proyectos de .NET Core](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-138">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="e33e1-139">Cuando la configuración de appHost está habilitada, .NET Core genera un ejecutable Mach-O nativo al compilar o publicar.</span><span class="sxs-lookup"><span data-stu-id="e33e1-139">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="e33e1-140">La aplicación se ejecuta en el contexto de appHost cuando se ejecuta desde el código fuente con el comando `dotnet run` o mediante el inicio directo del ejecutable Mach-O.</span><span class="sxs-lookup"><span data-stu-id="e33e1-140">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="e33e1-141">Sin appHost, la única manera en que un usuario puede iniciar una aplicación [dependiente del entorno de ejecución](../deploying/index.md#publish-runtime-dependent) es con el comando `dotnet <filename.dll>`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-141">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="e33e1-142">Siempre se crea un instancia de appHost al publicar la aplicación de manera [independiente](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="e33e1-142">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="e33e1-143">Puede configurar appHost en el nivel de proyecto, o bien cambiar la instancia de appHost de un comando `dotnet` específico con el parámetro `-p:UseAppHost`:</span><span class="sxs-lookup"><span data-stu-id="e33e1-143">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="e33e1-144">Archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="e33e1-144">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="e33e1-145">Parámetro de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="e33e1-145">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="e33e1-146">Para obtener más información sobre la configuración de `UseAppHost`, vea [Propiedades de MSBuild para Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="e33e1-146">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="single-file-executables"></a><span data-ttu-id="e33e1-147">Archivos ejecutables de único archivo</span><span class="sxs-lookup"><span data-stu-id="e33e1-147">Single-file executables</span></span>

<span data-ttu-id="e33e1-148">El comando `dotnet publish` admite empaquetar la aplicación en un ejecutable de archivo único específico de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e33e1-148">The `dotnet publish` command supports packaging your app into a platform-specific single-file executable.</span></span> <span data-ttu-id="e33e1-149">El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-149">The executable is self-extracting and contains all dependencies (including native) that are required to run your app.</span></span> <span data-ttu-id="e33e1-150">Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-150">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="e33e1-151">El inicio es más rápido cuando se vuelve a ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-151">Startup is faster when the application is run again.</span></span> <span data-ttu-id="e33e1-152">La aplicación no necesita extraerse por segunda vez a menos que se haya utilizado una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e33e1-152">The application doesn't need to extract itself a second time unless a new version was used.</span></span>

<span data-ttu-id="e33e1-153">Para publicar un ejecutable de archivo único, establezca `PublishSingleFile` en el proyecto o en la línea de comandos con el comando `dotnet publish`:</span><span class="sxs-lookup"><span data-stu-id="e33e1-153">To publish a single-file executable, set the `PublishSingleFile` in your project or on the command line with the `dotnet publish` command:</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

<span data-ttu-id="e33e1-154">o bien</span><span class="sxs-lookup"><span data-stu-id="e33e1-154">-or-</span></span>

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

<span data-ttu-id="e33e1-155">Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-155">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).</span></span>

### <a name="assembly-linking"></a><span data-ttu-id="e33e1-156">Vinculación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="e33e1-156">Assembly linking</span></span>

<span data-ttu-id="e33e1-157">El SDL de .NET Core 3.0 cuenta con una herramienta que puede reducir el tamaño de las aplicaciones mediante el análisis de IL y el recorte de los ensamblados no usados.</span><span class="sxs-lookup"><span data-stu-id="e33e1-157">The .NET core 3.0 SDK comes with a tool that can reduce the size of apps by analyzing IL and trimming unused assemblies.</span></span>

<span data-ttu-id="e33e1-158">Las aplicaciones independientes incluyen todo lo necesario para ejecutar el código, sin necesidad de instalar .NET en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="e33e1-158">Self-contained apps include everything needed to run your code, without requiring .NET to be installed on the host computer.</span></span> <span data-ttu-id="e33e1-159">Sin embargo, muchas veces, la aplicación solo requiere un pequeño subconjunto de marco para que funcione, y otras bibliotecas que no se utilizan podrían quitarse.</span><span class="sxs-lookup"><span data-stu-id="e33e1-159">However, many times the app only requires a small subset of the framework to function, and other unused libraries could be removed.</span></span>

<span data-ttu-id="e33e1-160">.NET Core incluye ahora un valor que usará la herramienta [Enlazador de IL](https://github.com/mono/linker) para examinar el nivel de integridad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-160">.NET Core now includes a setting that will use the [IL linker](https://github.com/mono/linker) tool to scan the IL of your app.</span></span> <span data-ttu-id="e33e1-161">Esta herramienta detecta el código que es necesario y, después, recorta las bibliotecas no utilizadas.</span><span class="sxs-lookup"><span data-stu-id="e33e1-161">This tool detects what code is required, and then trims unused libraries.</span></span> <span data-ttu-id="e33e1-162">Esta herramienta puede reducir significativamente el tamaño de implementación de algunas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e33e1-162">This tool can significantly reduce the deployment size of some apps.</span></span>

<span data-ttu-id="e33e1-163">Para habilitar esta herramienta, agregue el valor `<PublishTrimmed>` en el proyecto y publique una aplicación independiente:</span><span class="sxs-lookup"><span data-stu-id="e33e1-163">To enable this tool, add the `<PublishTrimmed>` setting in your project and publish a self-contained app:</span></span>

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

<span data-ttu-id="e33e1-164">Por ejemplo, la nueva y básica plantilla de proyecto de consola "Hola mundo" que se incluye, cuando se publica, tiene un tamaño aproximado de 70 MB.</span><span class="sxs-lookup"><span data-stu-id="e33e1-164">As an example, the basic "hello world" new console project template that is included, when published, hits about 70 MB in size.</span></span> <span data-ttu-id="e33e1-165">Mediante el uso de `<PublishTrimmed>`, ese tamaño se reduce a unos 30 MB.</span><span class="sxs-lookup"><span data-stu-id="e33e1-165">By using `<PublishTrimmed>`, that size is reduced to about 30 MB.</span></span>

<span data-ttu-id="e33e1-166">Es importante tener en cuenta que las aplicaciones o marcos (incluidos ASP.NET Core y WPF) que usan la reflexión o las características dinámicas relacionadas, se interrumpirán a menudo cuando se recorten.</span><span class="sxs-lookup"><span data-stu-id="e33e1-166">It's important to consider that applications or frameworks (including ASP.NET Core and WPF) that use reflection or related dynamic features, will often break when trimmed.</span></span> <span data-ttu-id="e33e1-167">Esta interrupción se produce porque el enlazador no conoce este comportamiento dinámico y no puede determinar qué tipos de marco son necesarios para la reflexión.</span><span class="sxs-lookup"><span data-stu-id="e33e1-167">This breakage occurs because the linker doesn't know about this dynamic behavior and can't determine which framework types are required for reflection.</span></span> <span data-ttu-id="e33e1-168">La herramienta Enlazador de IL puede configurarse para tener en cuenta este escenario.</span><span class="sxs-lookup"><span data-stu-id="e33e1-168">The IL Linker tool can be configured to be aware of this scenario.</span></span>

<span data-ttu-id="e33e1-169">Por encima de todo lo demás, no olvide probar la aplicación después del recorte.</span><span class="sxs-lookup"><span data-stu-id="e33e1-169">Above all else, be sure to test your app after trimming.</span></span>

<span data-ttu-id="e33e1-170">Para más información sobre la herramienta Enlazador de IL, vea la [documentación](https://aka.ms/dotnet-illink) o visite el repositorio [mono/linker]( https://github.com/mono/linker).</span><span class="sxs-lookup"><span data-stu-id="e33e1-170">For more information about the IL Linker tool, see the [documentation](https://aka.ms/dotnet-illink) or visit the [mono/linker]( https://github.com/mono/linker) repo.</span></span>

### <a name="tiered-compilation"></a><span data-ttu-id="e33e1-171">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="e33e1-171">Tiered compilation</span></span>

<span data-ttu-id="e33e1-172">La [compilación en niveles](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) está activada de forma predeterminada con .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-172">[Tiered compilation](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (TC) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="e33e1-173">Esta característica permite que el runtime use el compilador Just-In-Time (JIT) de forma más flexible para lograr un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e33e1-173">This feature enables the runtime to more adaptively use the just-in-time (JIT) compiler to achieve better performance.</span></span>

<span data-ttu-id="e33e1-174">La principal ventaja de la compilación en niveles es que ofrece dos maneras de aplicar JIT a los métodos: con un nivel de menor calidad, pero más rápido, o un nivel de mayor calidad, pero más lento.</span><span class="sxs-lookup"><span data-stu-id="e33e1-174">The main benefit of tiered compilation is to provide two ways of jitting methods: in a lower-quality-but-faster tier or a higher-quality-but-slower tier.</span></span> <span data-ttu-id="e33e1-175">La calidad se refiere al grado de optimización del método.</span><span class="sxs-lookup"><span data-stu-id="e33e1-175">The quality refers to how well the method is optimized.</span></span> <span data-ttu-id="e33e1-176">La compilación en niveles contribuye a mejorar el rendimiento de una aplicación a medida que pasa por distintas fases de ejecución, desde el inicio hasta el estado estable.</span><span class="sxs-lookup"><span data-stu-id="e33e1-176">TC helps to improve the performance of an application as it goes through various stages of execution, from startup through steady state.</span></span> <span data-ttu-id="e33e1-177">Cuando la compilación en niveles está deshabilitada, todos los métodos se compilan de una manera única que prima el rendimiento de estado estable sobre el rendimiento de inicio.</span><span class="sxs-lookup"><span data-stu-id="e33e1-177">When tiered compilation is disabled, every method is compiled in a single way that's biased to steady-state performance over startup performance.</span></span>

<span data-ttu-id="e33e1-178">Cuando la compilación en niveles está habilitada, se aplica el comportamiento siguiente a la compilación de métodos al iniciar una aplicación:</span><span class="sxs-lookup"><span data-stu-id="e33e1-178">When TC is enabled, the following behavior applies for method compilation when an app starts up:</span></span>

- <span data-ttu-id="e33e1-179">Si el método tiene código compilado mediante Ahead-Of-Time, o [ReadyToRun](#readytorun-images), se usa el código generado previamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-179">If the method has ahead-of-time-compiled code, or [ReadyToRun](#readytorun-images), the pregenerated code is used.</span></span>
- <span data-ttu-id="e33e1-180">De lo contrario, el método se compila mediante JIT.</span><span class="sxs-lookup"><span data-stu-id="e33e1-180">Otherwise, the method is jitted.</span></span> <span data-ttu-id="e33e1-181">Normalmente, estos métodos son genéricos con respecto a los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="e33e1-181">Typically, these methods are generics over value types.</span></span>
  - <span data-ttu-id="e33e1-182">*JIT rápido* produce código de menor calidad (o menos optimizado) más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-182">*Quick JIT* produces lower-quality (or less optimized) code more quickly.</span></span> <span data-ttu-id="e33e1-183">En .NET Core 3.0, JIT rápido está habilitado de forma predeterminada para los métodos que no contienen ningún bucle y tiene preferencia durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="e33e1-183">In .NET Core 3.0, Quick JIT is enabled by default for methods that don't contain loops and is preferred during startup.</span></span>
  - <span data-ttu-id="e33e1-184">JIT de optimización completa produce código de mayor calidad (o más optimizado) más lentamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-184">The fully optimizing JIT produces higher-quality (or more optimized) code more slowly.</span></span> <span data-ttu-id="e33e1-185">En el caso de los métodos en los que no se use la compilación mediante JIT rápida (por ejemplo, si el método tiene el atributo <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), se utilizará la compilación mediante JIT totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-185">For methods where Quick JIT would not be used (for example, if the method is attributed with <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), the fully optimizing JIT is used.</span></span>

<span data-ttu-id="e33e1-186">En el caso de los métodos a los que se llama con frecuencia, el compilador Just-in-Time al final crea código totalmente optimizado en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e33e1-186">For frequently called methods, the just-in-time compiler eventually creates fully optimized code in the background.</span></span> <span data-ttu-id="e33e1-187">Luego, el código optimizado reemplaza el código compilado previamente de ese método.</span><span class="sxs-lookup"><span data-stu-id="e33e1-187">The optimized code then replaces the pre-compiled code for that method.</span></span>

<span data-ttu-id="e33e1-188">El código generado con compilación mediante JIT rápida puede ejecutarse más lentamente, asignar más memoria o usar más espacio de pila.</span><span class="sxs-lookup"><span data-stu-id="e33e1-188">Code generated by Quick JIT may run slower, allocate more memory, or use more stack space.</span></span> <span data-ttu-id="e33e1-189">Si hay problemas, puede deshabilitar JIT rápido con esta propiedad de MSBuild en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="e33e1-189">If there are issues, you can disabled Quick JIT using this MSBuild property in the project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

<span data-ttu-id="e33e1-190">Para deshabilitar completamente la compilación en niveles, use esta propiedad de MSBuild en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="e33e1-190">To disable TC completely, use this MSBuild property in your project file:</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="e33e1-191">Si cambia esta configuración en el archivo de proyecto, es posible que deba realizar una compilación limpia para que se refleje la nueva configuración (elimine los directorios `obj` y `bin` y vuelva a compilar).</span><span class="sxs-lookup"><span data-stu-id="e33e1-191">If you change these settings in the project file, you may need to perform a clean build for the new settings to be reflected (delete the `obj` and `bin` directories and rebuild).</span></span>

<span data-ttu-id="e33e1-192">Para obtener más información sobre la configuración de la compilación en tiempo de ejecución, vea [Opciones de configuración del entorno de ejecución para compilación](../run-time-config/compilation.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-192">For more information about configuring compilation at run time, see [Run-time configuration options for compilation](../run-time-config/compilation.md).</span></span>

### <a name="readytorun-images"></a><span data-ttu-id="e33e1-193">Imágenes ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="e33e1-193">ReadyToRun images</span></span>

<span data-ttu-id="e33e1-194">Puede mejorar el tiempo de inicio de la aplicación .NET Core mediante la compilación de los ensamblados de aplicación como el formato ReadyToRun (R2R).</span><span class="sxs-lookup"><span data-stu-id="e33e1-194">You can improve the startup time of your .NET Core application by compiling your application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="e33e1-195">R2R es una forma de compilación Ahead Of Time (AOT).</span><span class="sxs-lookup"><span data-stu-id="e33e1-195">R2R is a form of ahead-of-time (AOT) compilation.</span></span>

<span data-ttu-id="e33e1-196">Los binarios de R2R mejoran el rendimiento de inicio reduciendo la cantidad de trabajo que el compilador Just-In-Time (JIT) debe llevar a cabo cuando se carga la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-196">R2R binaries improve startup performance by reducing the amount of work the just-in-time (JIT) compiler needs to do as your application loads.</span></span> <span data-ttu-id="e33e1-197">Los binarios contienen código nativo similar en comparación con lo que generaría el compilador JIT.</span><span class="sxs-lookup"><span data-stu-id="e33e1-197">The binaries contain similar native code compared to what the JIT would produce.</span></span> <span data-ttu-id="e33e1-198">Sin embargo, los binarios de R2R son más grandes porque contienen tanto el código de lenguaje intermedio (IL), que sigue siendo necesario para algunos escenarios, como la versión nativa del mismo código.</span><span class="sxs-lookup"><span data-stu-id="e33e1-198">However, R2R binaries are larger because they contain both intermediate language (IL) code, which is still needed for some scenarios, and the native version of the same code.</span></span> <span data-ttu-id="e33e1-199">R2R solo está disponible cuando publica una aplicación independiente que tenga como destino entornos de tiempo de ejecución específicos (RID), como Linux x64 o Windows x64.</span><span class="sxs-lookup"><span data-stu-id="e33e1-199">R2R is only available when you publish a self-contained app that targets specific runtime environments (RID) such as Linux x64 or Windows x64.</span></span>

<span data-ttu-id="e33e1-200">Para compilar el proyecto como ReadyToRun, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e33e1-200">To compile your project as ReadyToRun, do the following:</span></span>

01. <span data-ttu-id="e33e1-201">Agregue el valor `<PublishReadyToRun>` al proyecto:</span><span class="sxs-lookup"><span data-stu-id="e33e1-201">Add the `<PublishReadyToRun>` setting to your project:</span></span>

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. <span data-ttu-id="e33e1-202">Publique una aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-202">Publish a self-contained app.</span></span> <span data-ttu-id="e33e1-203">Por ejemplo, este comando crea una aplicación independiente para la versión de 64 bits de Windows:</span><span class="sxs-lookup"><span data-stu-id="e33e1-203">For example, this command creates a self-contained app for the 64-bit version of Windows:</span></span>

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a><span data-ttu-id="e33e1-204">Restricciones multiplataforma y de arquitectura</span><span class="sxs-lookup"><span data-stu-id="e33e1-204">Cross platform/architecture restrictions</span></span>

<span data-ttu-id="e33e1-205">Actualmente, el compilador ReadyToRun no admite la compatibilidad cruzada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-205">The ReadyToRun compiler doesn't currently support cross-targeting.</span></span> <span data-ttu-id="e33e1-206">Debe compilar en un destino dado.</span><span class="sxs-lookup"><span data-stu-id="e33e1-206">You must compile on a given target.</span></span> <span data-ttu-id="e33e1-207">Por ejemplo, si desea imágenes R2R para Windows x64, deberá ejecutar el comando de publicación en ese entorno.</span><span class="sxs-lookup"><span data-stu-id="e33e1-207">For example, if you want R2R images for Windows x64, you need to run the publish command on that environment.</span></span>

<span data-ttu-id="e33e1-208">Excepciones de la compatibilidad cruzada:</span><span class="sxs-lookup"><span data-stu-id="e33e1-208">Exceptions to cross-targeting:</span></span>

- <span data-ttu-id="e33e1-209">Windows x64 se puede usar para compilar imágenes de Windows ARM32, ARM64 y x86.</span><span class="sxs-lookup"><span data-stu-id="e33e1-209">Windows x64 can be used to compile Windows ARM32, ARM64, and x86 images.</span></span>
- <span data-ttu-id="e33e1-210">Windows x86 se puede usar para compilar imágenes de Windows ARM32.</span><span class="sxs-lookup"><span data-stu-id="e33e1-210">Windows x86 can be used to compile Windows ARM32 images.</span></span>
- <span data-ttu-id="e33e1-211">Linux x64 se puede usar para compilar imágenes de Linux ARM32 y ARM64.</span><span class="sxs-lookup"><span data-stu-id="e33e1-211">Linux x64 can be used to compile Linux ARM32 and ARM64 images.</span></span>

## <a name="runtimesdk"></a><span data-ttu-id="e33e1-212">Runtime y SDK</span><span class="sxs-lookup"><span data-stu-id="e33e1-212">Runtime/SDK</span></span>

### <a name="major-version-runtime-roll-forward"></a><span data-ttu-id="e33e1-213">Puesta al día del runtime de versiones principales</span><span class="sxs-lookup"><span data-stu-id="e33e1-213">Major-version runtime roll forward</span></span>

<span data-ttu-id="e33e1-214">.NET Core 3.0 presenta una característica opcional que permite poner la aplicación al día con la versión principal más reciente de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e33e1-214">.NET Core 3.0 introduces an opt-in feature that allows your app to roll forward to the latest major version of .NET Core.</span></span> <span data-ttu-id="e33e1-215">Además, se agregó una nueva configuración para controlar cómo se aplica la puesta al día a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-215">Additionally, a new setting has been added to control how roll forward is applied to your app.</span></span> <span data-ttu-id="e33e1-216">Esto se puede configurar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="e33e1-216">This can be configured in the following ways:</span></span>

- <span data-ttu-id="e33e1-217">Propiedad de archivo del proyecto: `RollForward`</span><span class="sxs-lookup"><span data-stu-id="e33e1-217">Project file property: `RollForward`</span></span>
- <span data-ttu-id="e33e1-218">Propiedad de archivo de configuración en tiempo de ejecución: `rollForward`</span><span class="sxs-lookup"><span data-stu-id="e33e1-218">Run-time configuration file property: `rollForward`</span></span>
- <span data-ttu-id="e33e1-219">Variable de entorno: `DOTNET_ROLL_FORWARD`</span><span class="sxs-lookup"><span data-stu-id="e33e1-219">Environment variable: `DOTNET_ROLL_FORWARD`</span></span>
- <span data-ttu-id="e33e1-220">Argumento de línea de comandos: `--roll-forward`</span><span class="sxs-lookup"><span data-stu-id="e33e1-220">Command-line argument: `--roll-forward`</span></span>

<span data-ttu-id="e33e1-221">Debe especificarse uno de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-221">One of the following values must be specified.</span></span> <span data-ttu-id="e33e1-222">Si se omite la configuración, **Minor** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e33e1-222">If the setting is omitted, **Minor** is the default.</span></span>

- <span data-ttu-id="e33e1-223">**LatestPatch**</span><span class="sxs-lookup"><span data-stu-id="e33e1-223">**LatestPatch**</span></span>\
<span data-ttu-id="e33e1-224">Se pone al día con la última versión de revisión.</span><span class="sxs-lookup"><span data-stu-id="e33e1-224">Roll forward to the highest patch version.</span></span> <span data-ttu-id="e33e1-225">Se deshabilita la puesta al día de versiones secundarias.</span><span class="sxs-lookup"><span data-stu-id="e33e1-225">This disables minor version roll forward.</span></span>
- <span data-ttu-id="e33e1-226">**Minor**</span><span class="sxs-lookup"><span data-stu-id="e33e1-226">**Minor**</span></span>\
<span data-ttu-id="e33e1-227">Se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-227">Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="e33e1-228">Si se encuentra la versión secundaria solicitada, se utiliza la directiva **LatestPatch**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-228">If the requested minor version is present, then the **LatestPatch** policy is used.</span></span>
- <span data-ttu-id="e33e1-229">**Major**</span><span class="sxs-lookup"><span data-stu-id="e33e1-229">**Major**</span></span>\
<span data-ttu-id="e33e1-230">Se pone al día con la versión secundaria mínima superior, y la versión secundaria mínima, si no se encuentra la versión secundaria solicitada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-230">Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="e33e1-231">Si se encuentra la versión principal solicitada, se utiliza la directiva **Minor**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-231">If the requested major version is present, then the **Minor** policy is used.</span></span>
- <span data-ttu-id="e33e1-232">**LatestMinor**</span><span class="sxs-lookup"><span data-stu-id="e33e1-232">**LatestMinor**</span></span>\
<span data-ttu-id="e33e1-233">Se pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-233">Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="e33e1-234">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-234">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e33e1-235">**LatestMajor**</span><span class="sxs-lookup"><span data-stu-id="e33e1-235">**LatestMajor**</span></span>\
<span data-ttu-id="e33e1-236">Se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-236">Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="e33e1-237">Se destina a escenarios de hospedaje de componentes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-237">Intended for component hosting scenarios.</span></span>
- <span data-ttu-id="e33e1-238">**Disable**</span><span class="sxs-lookup"><span data-stu-id="e33e1-238">**Disable**</span></span>\
<span data-ttu-id="e33e1-239">No se pone al día.</span><span class="sxs-lookup"><span data-stu-id="e33e1-239">Don't roll forward.</span></span> <span data-ttu-id="e33e1-240">Solo se enlaza a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-240">Only bind to specified version.</span></span> <span data-ttu-id="e33e1-241">No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-241">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="e33e1-242">Este valor solo se recomienda a efectos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="e33e1-242">This value is only recommended for testing.</span></span>

<span data-ttu-id="e33e1-243">Además del valor **Disable**, todos los valores usarán la última versión de revisión disponible.</span><span class="sxs-lookup"><span data-stu-id="e33e1-243">Besides the **Disable** setting, all settings will use the highest available patch version.</span></span>

### <a name="build-copies-dependencies"></a><span data-ttu-id="e33e1-244">Compilación de dependencias de copias</span><span class="sxs-lookup"><span data-stu-id="e33e1-244">Build copies dependencies</span></span>

<span data-ttu-id="e33e1-245">El comando `dotnet build` copia ahora las dependencias de NuGet para la aplicación de la caché de NuGet a la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-245">The `dotnet build` command now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="e33e1-246">Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-246">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="e33e1-247">Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.</span><span class="sxs-lookup"><span data-stu-id="e33e1-247">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

### <a name="local-tools"></a><span data-ttu-id="e33e1-248">Herramientas locales</span><span class="sxs-lookup"><span data-stu-id="e33e1-248">Local tools</span></span>

<span data-ttu-id="e33e1-249">.NET Core 3.0 presenta herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="e33e1-249">.NET Core 3.0 introduces local tools.</span></span> <span data-ttu-id="e33e1-250">Las herramientas locales son similares a las [herramientas globales](../tools/global-tools.md) pero están asociadas a una ubicación concreta en el disco.</span><span class="sxs-lookup"><span data-stu-id="e33e1-250">Local tools are similar to [global tools](../tools/global-tools.md) but are associated with a particular location on disk.</span></span> <span data-ttu-id="e33e1-251">Las herramientas locales no están disponibles globalmente y se distribuyen como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="e33e1-251">Local tools aren't available globally and are distributed as NuGet packages.</span></span>

> [!WARNING]
> <span data-ttu-id="e33e1-252">Si ha probado herramientas locales en la versión preliminar 1 de .NET Core 3.0, tales como la ejecución de `dotnet tool restore` o de `dotnet tool install`, elimine la carpeta de caché de herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="e33e1-252">If you tried local tools in .NET Core 3.0 Preview 1, such as running `dotnet tool restore` or `dotnet tool install`, delete the local tools cache folder.</span></span> <span data-ttu-id="e33e1-253">En caso contrario, las herramientas locales no funcionan en las versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-253">Otherwise, local tools won't work on any newer release.</span></span> <span data-ttu-id="e33e1-254">Esta carpeta se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="e33e1-254">This folder is located at:</span></span>
>
> <span data-ttu-id="e33e1-255">En macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e33e1-255">On macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="e33e1-256">En Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="e33e1-256">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>

<span data-ttu-id="e33e1-257">Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e33e1-257">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="e33e1-258">Este archivo de manifiesto define las herramientas que estarán disponibles en esa carpeta y a continuación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-258">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="e33e1-259">Puede distribuir el archivo de manifiesto con su código para asegurarse de que todo aquel que trabaje con su código pueda restaurar y utilizar las mismas herramientas.</span><span class="sxs-lookup"><span data-stu-id="e33e1-259">You can distribute the manifest file with your code to ensure that anyone who works with your code can restore and use the same tools.</span></span>

<span data-ttu-id="e33e1-260">Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e33e1-260">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="e33e1-261">Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e33e1-261">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="e33e1-262">Para instalar estas herramientas local o globalmente, aún tendría que instalar [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="e33e1-262">To install these tools globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

### <a name="new-globaljson-options"></a><span data-ttu-id="e33e1-263">Opciones nuevas de global.json</span><span class="sxs-lookup"><span data-stu-id="e33e1-263">New global.json options</span></span>

<span data-ttu-id="e33e1-264">El archivo *global.json* tiene opciones nuevas que proporcionan más flexibilidad cuando se intenta definir qué versión de la SDK de .NET Core se usa.</span><span class="sxs-lookup"><span data-stu-id="e33e1-264">The *global.json* file has new options that provide more flexibility when you're trying to define which version of the .NET Core SDK is used.</span></span> <span data-ttu-id="e33e1-265">Las opciones nuevas son:</span><span class="sxs-lookup"><span data-stu-id="e33e1-265">The new options are:</span></span>

- <span data-ttu-id="e33e1-266">`allowPrerelease`: Indica si la resolución del SDK debe tener en cuenta las versiones preliminares a la hora de seleccionar la versión del SDK que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e33e1-266">`allowPrerelease`: Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>
- <span data-ttu-id="e33e1-267">`rollForward`: indica la directiva de puesta al día que se va a usar al seleccionar una versión del SDK, ya sea como reserva si falta una versión específica del SDK o como una directiva para usar una versión superior.</span><span class="sxs-lookup"><span data-stu-id="e33e1-267">`rollForward`: Indicates the roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span>

<span data-ttu-id="e33e1-268">Para más información sobre los cambios, incluidos los valores predeterminados, los valores admitidos y reglas de coincidencia nuevas, consulte la [información general de global.json](../tools/global-json.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-268">For more information about the changes including default values, supported values, and new matching rules, see [global.json overview](../tools/global-json.md).</span></span>

### <a name="smaller-garbage-collection-heap-sizes"></a><span data-ttu-id="e33e1-269">Tamaños del montón de recolección de elementos no utilizados más pequeños</span><span class="sxs-lookup"><span data-stu-id="e33e1-269">Smaller Garbage Collection heap sizes</span></span>

<span data-ttu-id="e33e1-270">Se ha reducido el tamaño predeterminado del montón del recolector de elementos no utilizados, lo que se traduce en que .NET Core usa menos memoria.</span><span class="sxs-lookup"><span data-stu-id="e33e1-270">The Garbage Collector's default heap size has been reduced resulting in .NET Core using less memory.</span></span> <span data-ttu-id="e33e1-271">Este cambio se adapta mejor al presupuesto de asignación de generación 0 con tamaños de caché de procesador moderno.</span><span class="sxs-lookup"><span data-stu-id="e33e1-271">This change better aligns with the generation 0 allocation budget with modern processor cache sizes.</span></span>

### <a name="garbage-collection-large-page-support"></a><span data-ttu-id="e33e1-272">Compatibilidad con Large Pages de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="e33e1-272">Garbage Collection Large Page support</span></span>

<span data-ttu-id="e33e1-273">Large Pages (también conocida como Huge Pages en Linux) es una característica en la que el sistema operativo es capaz de establecer regiones de memoria más grandes que el tamaño de página nativo (a menudo, 4 K) para mejorar el rendimiento de la aplicación que solicita estas páginas grandes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-273">Large Pages (also known as Huge Pages on Linux) is a feature where the operating system is able to establish memory regions larger than the native page size (often 4K) to improve performance of the application requesting these large pages.</span></span>

<span data-ttu-id="e33e1-274">Ahora, el recolector de elementos no utilizados puede configurarse con el valor **GCLargePages** como característica opcional para elegir la asignación de páginas grandes en Windows.</span><span class="sxs-lookup"><span data-stu-id="e33e1-274">The Garbage Collector can now be configured with the **GCLargePages** setting as an opt-in feature to choose to allocate large pages on Windows.</span></span>

## <a name="windows-desktop--com"></a><span data-ttu-id="e33e1-275">Escritorio de Windows y COM</span><span class="sxs-lookup"><span data-stu-id="e33e1-275">Windows Desktop & COM</span></span>

### <a name="net-core-sdk-windows-installer"></a><span data-ttu-id="e33e1-276">Windows Installer del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e33e1-276">.NET Core SDK Windows Installer</span></span>

<span data-ttu-id="e33e1-277">El instalador MSI para Windows ha cambiado a partir de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-277">The MSI installer for Windows has changed starting with .NET Core 3.0.</span></span> <span data-ttu-id="e33e1-278">Los instaladores del SDK actualizarán ahora las versiones de la banda de características del SDK.</span><span class="sxs-lookup"><span data-stu-id="e33e1-278">The SDK installers will now upgrade SDK feature-band releases in place.</span></span> <span data-ttu-id="e33e1-279">Las bandas de características se definen en los grupos de *centenas* de la sección *revisión* del número de versión.</span><span class="sxs-lookup"><span data-stu-id="e33e1-279">Feature bands are defined in the *hundreds* groups in the *patch* section of the version number.</span></span> <span data-ttu-id="e33e1-280">Por ejemplo, **3.0._101_** y **3.0._201_** son versiones de dos bandas de características distintas mientras que **3.0._101_** y **3.0._199_** están en la misma banda de características.</span><span class="sxs-lookup"><span data-stu-id="e33e1-280">For example, **3.0._101_** and **3.0._201_** are versions in two different feature bands while **3.0._101_** and **3.0._199_** are in the same feature band.</span></span> <span data-ttu-id="e33e1-281">Y, cuando se instale el SDK **3.0._101_** de .NET Core, se quitará el SDK **3.0._100_** de .NET Core de la máquina si existe.</span><span class="sxs-lookup"><span data-stu-id="e33e1-281">And, when .NET Core SDK **3.0._101_** is installed, .NET Core SDK **3.0._100_** will be removed from the machine if it exists.</span></span> <span data-ttu-id="e33e1-282">Cuando se instale el SDK **3.0._200_** de .NET Core en la misma máquina, no se quitará el SDK **3.0._101_** de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e33e1-282">When .NET Core SDK **3.0._200_** is installed on the same machine, .NET Core SDK **3.0._101_** won't be removed.</span></span>

<span data-ttu-id="e33e1-283">Para obtener más información sobre las versiones, vea el artículo de [introducción a la creación de versiones de .NET Core](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-283">For more information about versioning, see [Overview of how .NET Core is versioned](../versions/index.md).</span></span>

### <a name="windows-desktop"></a><span data-ttu-id="e33e1-284">Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="e33e1-284">Windows desktop</span></span>

<span data-ttu-id="e33e1-285">.NET Core 3.0 admite aplicaciones de escritorio de Windows con Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e33e1-285">.NET Core 3.0 supports Windows desktop applications using Windows Presentation Foundation (WPF) and Windows Forms.</span></span> <span data-ttu-id="e33e1-286">Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="e33e1-286">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="e33e1-287">El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-287">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="e33e1-288">Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="e33e1-288">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```dotnetcli
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="e33e1-289">Visual Studio 2019 agrega plantillas de **nuevo proyecto** para WPF y Windows Forms de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-289">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span>

<span data-ttu-id="e33e1-290">Para obtener más información sobre cómo migrar una aplicación existente de .NET Framework, vea los artículos sobre [cómo portar proyectos de WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) y [cómo portar proyectos de Windows Forms](../porting/winforms.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-290">For more information about how to port an existing .NET Framework application, see [Port WPF projects](../../desktop-wpf/migration/convert-project-from-net-framework.md) and [Port Windows Forms projects](../porting/winforms.md).</span></span>

#### <a name="winforms-high-dpi"></a><span data-ttu-id="e33e1-291">PPP alto de WinForms</span><span class="sxs-lookup"><span data-stu-id="e33e1-291">WinForms high DPI</span></span>

<span data-ttu-id="e33e1-292">En .NET Core, las aplicaciones de Windows Forms pueden establecer el modo de valores altos de PPP con <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e33e1-292">.NET Core Windows Forms applications can set high DPI mode with <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e33e1-293">El método `SetHighDpiMode` establece el modo de valores altos de PPP correspondiente a menos que la opción se haya establecido por otros medios como `App.Manifest` o P/Invoke antes de `Application.Run`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-293">The `SetHighDpiMode` method sets the corresponding high DPI mode unless the setting has been set by other means like `App.Manifest` or P/Invoke before `Application.Run`.</span></span>

<span data-ttu-id="e33e1-294">Los posibles valores de `highDpiMode`, expresados por la enumeración <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> son:</span><span class="sxs-lookup"><span data-stu-id="e33e1-294">The possible `highDpiMode` values, as expressed by the <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> enum are:</span></span>

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

<span data-ttu-id="e33e1-295">Para más información sobre los modos de valores altos de PPP, consulte el artículo sobre [desarrollo de aplicaciones de escritorio con valores altos de PPP en Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span><span class="sxs-lookup"><span data-stu-id="e33e1-295">For more information about high DPI modes, see [High DPI Desktop Application Development on Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).</span></span>

### <a name="create-com-components"></a><span data-ttu-id="e33e1-296">Creación de componentes COM</span><span class="sxs-lookup"><span data-stu-id="e33e1-296">Create COM components</span></span>

<span data-ttu-id="e33e1-297">En Windows, ahora puede crear componentes COM administrados invocables.</span><span class="sxs-lookup"><span data-stu-id="e33e1-297">On Windows, you can now create COM-callable managed components.</span></span> <span data-ttu-id="e33e1-298">Esta capacidad es fundamental para usar .NET Core con modelos de complemento COM, así como para ofrecer paridad con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e33e1-298">This capability is critical to use .NET Core with COM add-in models and also to provide parity with .NET Framework.</span></span>

<span data-ttu-id="e33e1-299">A diferencia de .NET Framework, donde se utilizó *mscoree.dll* como servidor COM, .NET Core agregará un archivo dll de inicio nativo al directorio *bin* al compilar el componente COM.</span><span class="sxs-lookup"><span data-stu-id="e33e1-299">Unlike .NET Framework where the *mscoree.dll* was used as the COM server, .NET Core will add a native launcher dll to the *bin* directory when you build your COM component.</span></span>

<span data-ttu-id="e33e1-300">Para ver un ejemplo de cómo crear un componente COM y usarlo, consulte la [demostración de COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="e33e1-300">For an example of how to create a COM component and consume it, see the [COM Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span></span>

### <a name="windows-native-interop"></a><span data-ttu-id="e33e1-301">Interoperabilidad nativa de Windows</span><span class="sxs-lookup"><span data-stu-id="e33e1-301">Windows Native Interop</span></span>

<span data-ttu-id="e33e1-302">Windows ofrece una API nativa enriquecida en forma de API de C sin formato, COM y WinRT.</span><span class="sxs-lookup"><span data-stu-id="e33e1-302">Windows offers a rich native API in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="e33e1-303">Mientras que .NET Core admite **P/Invoke**, .NET Core 3.0 agrega la capacidad de **API COM CoCreate** y **API WinRT Activate**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-303">While .NET Core supports **P/Invoke**, .NET Core 3.0 adds the ability to **CoCreate COM APIs** and **Activate WinRT APIs**.</span></span> <span data-ttu-id="e33e1-304">Para obtener un ejemplo de código, vea la [demostración de Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="e33e1-304">For a code example, see the [Excel Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

### <a name="msix-deployment"></a><span data-ttu-id="e33e1-305">Implementación de MSIX</span><span class="sxs-lookup"><span data-stu-id="e33e1-305">MSIX Deployment</span></span>

<span data-ttu-id="e33e1-306">[MSIX](https://docs.microsoft.com/windows/msix/) es un nuevo formato de paquete de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e33e1-306">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows application package format.</span></span> <span data-ttu-id="e33e1-307">Se puede usar para implementar aplicaciones de escritorio de .NET Core 3.0 en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e33e1-307">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="e33e1-308">El [proyecto de paquete de aplicación de Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponible en Visual Studio 2019, le permite crear paquetes de MSIX con aplicaciones de .NET Core [independientes](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="e33e1-308">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#publish-self-contained) .NET Core applications.</span></span>

<span data-ttu-id="e33e1-309">El archivo del proyecto de .NET Core debe especificar los tiempos de ejecución admitidos en la propiedad `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="e33e1-309">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a><span data-ttu-id="e33e1-310">Mejoras de Linux</span><span class="sxs-lookup"><span data-stu-id="e33e1-310">Linux improvements</span></span>

### <a name="serialport-for-linux"></a><span data-ttu-id="e33e1-311">SerialPort para Linux</span><span class="sxs-lookup"><span data-stu-id="e33e1-311">SerialPort for Linux</span></span>

<span data-ttu-id="e33e1-312">.Net Core 3.0 proporciona compatibilidad básica para <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.</span><span class="sxs-lookup"><span data-stu-id="e33e1-312">.NET Core 3.0 provides basic support for <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="e33e1-313">Anteriormente, .NET Core solo admitía el uso de `SerialPort` en Windows.</span><span class="sxs-lookup"><span data-stu-id="e33e1-313">Previously, .NET Core only supported using `SerialPort` on Windows.</span></span>

<span data-ttu-id="e33e1-314">Para obtener más información sobre la compatibilidad limitada para el puerto de serie en Linux, vea [Problema #33146 de GitHub](https://github.com/dotnet/corefx/issues/33146).</span><span class="sxs-lookup"><span data-stu-id="e33e1-314">For more information about the limited support for the serial port on Linux, see [GitHub issue #33146](https://github.com/dotnet/corefx/issues/33146).</span></span>

### <a name="docker-and-cgroup-memory-limits"></a><span data-ttu-id="e33e1-315">Docker y límites de memoria de cgroup</span><span class="sxs-lookup"><span data-stu-id="e33e1-315">Docker and cgroup memory Limits</span></span>

<span data-ttu-id="e33e1-316">La ejecución de .NET Core 3.0 en Linux con Docker funciona mejor con límites de memoria de cgroup.</span><span class="sxs-lookup"><span data-stu-id="e33e1-316">Running .NET Core 3.0 on Linux with Docker works better with cgroup memory limits.</span></span> <span data-ttu-id="e33e1-317">La ejecución de un contenedor de Docker con límites de memoria, como con `docker run -m`, cambia el comportamiento de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e33e1-317">Running a Docker container with memory limits, such as with `docker run -m`, changes how .NET Core behaves.</span></span>

- <span data-ttu-id="e33e1-318">Tamaño predeterminado del montón del recolector de elementos no utilizados (GC): máximo de 20 MB o 75 % del límite de memoria en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e33e1-318">Default Garbage Collector (GC) heap size: maximum of 20 mb or 75% of the memory limit on the container.</span></span>
- <span data-ttu-id="e33e1-319">Puede establecerse el tamaño explícito como número absoluto o porcentaje del límite de cgroup.</span><span class="sxs-lookup"><span data-stu-id="e33e1-319">Explicit size can be set as an absolute number or percentage of cgroup limit.</span></span>
- <span data-ttu-id="e33e1-320">El tamaño mínimo del segmento reservado por el montón de GC es de 16 MB.</span><span class="sxs-lookup"><span data-stu-id="e33e1-320">Minimum reserved segment size per GC heap is 16 mb.</span></span> <span data-ttu-id="e33e1-321">Con este tamaño se reduce el número de montones que se crean en las máquinas.</span><span class="sxs-lookup"><span data-stu-id="e33e1-321">This size reduces the number of heaps that are created on machines.</span></span>

### <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="e33e1-322">Compatibilidad de GPIO con Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="e33e1-322">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="e33e1-323">Se han publicado dos paquetes en NuGet que puede usar para la programación de GPIO:</span><span class="sxs-lookup"><span data-stu-id="e33e1-323">Two packages have been released to NuGet that you can use for GPIO programming:</span></span>

- [<span data-ttu-id="e33e1-324">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="e33e1-324">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio)
- [<span data-ttu-id="e33e1-325">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="e33e1-325">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings)

<span data-ttu-id="e33e1-326">Los paquetes GPIO incluyen interfaces API para dispositivos *GPIO*, *SPI*, *I2C* y *PWM*.</span><span class="sxs-lookup"><span data-stu-id="e33e1-326">The GPIO packages include APIs for *GPIO*, *SPI*, *I2C*, and *PWM* devices.</span></span> <span data-ttu-id="e33e1-327">El paquete de enlaces de IoT incluye enlaces de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e33e1-327">The IoT bindings package includes device bindings.</span></span> <span data-ttu-id="e33e1-328">Para obtener más información, vea el [repositorio de GitHub de los dispositivos](https://github.com/dotnet/iot/blob/master/src/devices/).</span><span class="sxs-lookup"><span data-stu-id="e33e1-328">For more information, see the [devices GitHub repo](https://github.com/dotnet/iot/blob/master/src/devices/).</span></span>

### <a name="arm64-linux-support"></a><span data-ttu-id="e33e1-329">Compatibilidad con ARM64 para Linux</span><span class="sxs-lookup"><span data-stu-id="e33e1-329">ARM64 Linux support</span></span>

<span data-ttu-id="e33e1-330">.NET Core 3.0 agrega compatibilidad con ARM64 para Linux.</span><span class="sxs-lookup"><span data-stu-id="e33e1-330">.NET Core 3.0 adds support for ARM64 for Linux.</span></span> <span data-ttu-id="e33e1-331">El principal caso de uso de ARM64 son escenarios de IoT.</span><span class="sxs-lookup"><span data-stu-id="e33e1-331">The primary use case for ARM64 is currently with IoT scenarios.</span></span> <span data-ttu-id="e33e1-332">Para obtener más información, vea el artículo sobre el [estado de ARM64 de .NET Core](https://github.com/dotnet/announcements/issues/82).</span><span class="sxs-lookup"><span data-stu-id="e33e1-332">For more information, see [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82).</span></span>

<span data-ttu-id="e33e1-333">[Hay imágenes de docker para .NET Core en ARM64](https://hub.docker.com/r/microsoft/dotnet/) disponibles para Alpine, Debian y Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e33e1-333">[Docker images for .NET Core on ARM64](https://hub.docker.com/r/microsoft/dotnet/) are available for Alpine, Debian, and Ubuntu.</span></span>

> [!NOTE]
> <span data-ttu-id="e33e1-334">Windows aún no ofrece soporte técnico para **ARM64**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-334">**ARM64** Windows support isn't yet available.</span></span>

## <a name="security"></a><span data-ttu-id="e33e1-335">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e33e1-335">Security</span></span>

### <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="e33e1-336">TLS 1.3 y OpenSSL 1.1.1 en Linux</span><span class="sxs-lookup"><span data-stu-id="e33e1-336">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="e33e1-337">.NET Core aprovecha ahora la ventaja de la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), cuando está disponible en un entorno determinado.</span><span class="sxs-lookup"><span data-stu-id="e33e1-337">.NET Core now takes advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it's available in a given environment.</span></span> <span data-ttu-id="e33e1-338">Con TLS 1.3:</span><span class="sxs-lookup"><span data-stu-id="e33e1-338">With TLS 1.3:</span></span>

- <span data-ttu-id="e33e1-339">Se han mejorado los tiempos de conexión con menores recorridos de ida y vuelta necesarios entre el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="e33e1-339">Connection times are improved with reduced round trips required between the client and server.</span></span>
- <span data-ttu-id="e33e1-340">Se ha mejorado la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros.</span><span class="sxs-lookup"><span data-stu-id="e33e1-340">Improved security because of the removal of various obsolete and insecure cryptographic algorithms.</span></span>

<span data-ttu-id="e33e1-341">Cuando está disponible, .NET Core 3.0 utiliza **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** en un sistema Linux.</span><span class="sxs-lookup"><span data-stu-id="e33e1-341">When available, .NET Core 3.0 uses **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** on a Linux system.</span></span> <span data-ttu-id="e33e1-342">Si **OpenSSL 1.1.1** está disponible, los tipos <xref:System.Net.Security.SslStream?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>, utilizarán **TLS 1.3** (suponiendo que el cliente y el servidor admitan **TLS 1.3**).</span><span class="sxs-lookup"><span data-stu-id="e33e1-342">When **OpenSSL 1.1.1** is available, both <xref:System.Net.Security.SslStream?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> types will use **TLS 1.3** (assuming both the client and server support **TLS 1.3**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e33e1-343">Windows y macOS aún no admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-343">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="e33e1-344">.NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e33e1-344">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

<span data-ttu-id="e33e1-345">El siguiente ejemplo de C# 8.0 muestra .NET Core 3.0 en Ubuntu 18.10 al conectarse a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="e33e1-345">The following C# 8.0 example demonstrates .NET Core 3.0 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a><span data-ttu-id="e33e1-346">Cifrados de criptografía</span><span class="sxs-lookup"><span data-stu-id="e33e1-346">Cryptography ciphers</span></span>

<span data-ttu-id="e33e1-347">.NET 3.0 agrega compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> y <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-347">.NET 3.0 adds support for **AES-GCM** and **AES-CCM** ciphers, implemented with <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> and <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> respectively.</span></span> <span data-ttu-id="e33e1-348">Estos dos algoritmos son [algoritmos AEAD (Authenticated Encryption with Associated Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).</span><span class="sxs-lookup"><span data-stu-id="e33e1-348">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption).</span></span>

<span data-ttu-id="e33e1-349">El código siguiente muestra cómo utilizar cifrado `AesGcm` para cifrar y descifrar datos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="e33e1-349">The following code demonstrates using `AesGcm` cipher to encrypt and decrypt random data.</span></span>

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a><span data-ttu-id="e33e1-350">Importación y exportación de claves criptográfica</span><span class="sxs-lookup"><span data-stu-id="e33e1-350">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="e33e1-351">.NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas en formatos estándar.</span><span class="sxs-lookup"><span data-stu-id="e33e1-351">.NET Core 3.0 supports the import and export of asymmetric public and private keys from standard formats.</span></span> <span data-ttu-id="e33e1-352">No es necesario utilizar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="e33e1-352">You don't need to use an X.509 certificate.</span></span>

<span data-ttu-id="e33e1-353">Todos los tipos de clave, como *RSA*, *DSA*, *ECDsa* y *ECDiffieHellman*, admiten los siguientes formatos:</span><span class="sxs-lookup"><span data-stu-id="e33e1-353">All key types, such as *RSA*, *DSA*, *ECDsa*, and *ECDiffieHellman*, support the following formats:</span></span>

- <span data-ttu-id="e33e1-354">**Clave pública**</span><span class="sxs-lookup"><span data-stu-id="e33e1-354">**Public Key**</span></span>
  - <span data-ttu-id="e33e1-355">SubjectPublicKeyInfo X.509</span><span class="sxs-lookup"><span data-stu-id="e33e1-355">X.509 SubjectPublicKeyInfo</span></span>

- <span data-ttu-id="e33e1-356">**Clave privada**</span><span class="sxs-lookup"><span data-stu-id="e33e1-356">**Private key**</span></span>
  - <span data-ttu-id="e33e1-357">PrivateKeyInfo PKCS#8</span><span class="sxs-lookup"><span data-stu-id="e33e1-357">PKCS#8 PrivateKeyInfo</span></span>
  - <span data-ttu-id="e33e1-358">EncryptedPrivateKeyInfo PKCS#8</span><span class="sxs-lookup"><span data-stu-id="e33e1-358">PKCS#8 EncryptedPrivateKeyInfo</span></span>

<span data-ttu-id="e33e1-359">Las claves RSA también admiten:</span><span class="sxs-lookup"><span data-stu-id="e33e1-359">RSA keys also support:</span></span>

- <span data-ttu-id="e33e1-360">**Clave pública**</span><span class="sxs-lookup"><span data-stu-id="e33e1-360">**Public Key**</span></span>
  - <span data-ttu-id="e33e1-361">RSAPublicKey PKCS#1</span><span class="sxs-lookup"><span data-stu-id="e33e1-361">PKCS#1 RSAPublicKey</span></span>

- <span data-ttu-id="e33e1-362">**Clave privada**</span><span class="sxs-lookup"><span data-stu-id="e33e1-362">**Private key**</span></span>
  - <span data-ttu-id="e33e1-363">RSAPrivateKey PKCS#1</span><span class="sxs-lookup"><span data-stu-id="e33e1-363">PKCS#1 RSAPrivateKey</span></span>

<span data-ttu-id="e33e1-364">Los métodos de exportación generan datos binarios con codificación DER y los métodos de importación esperan lo mismo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-364">The export methods produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="e33e1-365">Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.</span><span class="sxs-lookup"><span data-stu-id="e33e1-365">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

<span data-ttu-id="e33e1-366">Los archivos **PKCS#8** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> y los archivos **PFX/PKCS#12** se pueden inspeccionar con <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e33e1-366">**PKCS#8** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> and **PFX/PKCS#12** files can be inspected with <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e33e1-367">Los archivos **PFX/PKCS#12** se pueden manipular con <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e33e1-367">**PFX/PKCS#12** files can be manipulated with <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.</span></span>

## <a name="net-core-30-api-changes"></a><span data-ttu-id="e33e1-368">Cambios de API en .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e33e1-368">.NET Core 3.0 API changes</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="e33e1-369">Rangos e índices</span><span class="sxs-lookup"><span data-stu-id="e33e1-369">Ranges and indices</span></span>

<span data-ttu-id="e33e1-370">El nuevo tipo <xref:System.Index?displayProperty=nameWithType> se puede utilizar para la indización.</span><span class="sxs-lookup"><span data-stu-id="e33e1-370">The new <xref:System.Index?displayProperty=nameWithType> type can be used for indexing.</span></span> <span data-ttu-id="e33e1-371">Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:</span><span class="sxs-lookup"><span data-stu-id="e33e1-371">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="e33e1-372">Existe también el tipo <xref:System.Range?displayProperty=nameWithType>, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de intervalo `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="e33e1-372">There's also the <xref:System.Range?displayProperty=nameWithType> type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="e33e1-373">Luego puede crear un índice con un `Range`, lo que genera un segmento:</span><span class="sxs-lookup"><span data-stu-id="e33e1-373">You can then index with a `Range`, which produces a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

<span data-ttu-id="e33e1-374">Para obtener más información, vea el [tutorial sobre intervalos e índices](../../csharp/tutorials/ranges-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-374">For more information, see the [ranges and indices tutorial](../../csharp/tutorials/ranges-indexes.md).</span></span>

### <a name="async-streams"></a><span data-ttu-id="e33e1-375">Flujos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="e33e1-375">Async streams</span></span>

<span data-ttu-id="e33e1-376">El tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> es una nueva versión asincrónica de <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e33e1-376">The <xref:System.Collections.Generic.IAsyncEnumerable%601> type is a new asynchronous version of <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e33e1-377">El lenguaje permite ejecutar la instrucción `await foreach` en `IAsyncEnumerable<T>` para consumir sus elementos, y usar la instrucción `yield return` en ellos para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="e33e1-377">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="e33e1-378">En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="e33e1-378">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="e33e1-379">La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="e33e1-379">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="e33e1-380">Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="e33e1-380">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="e33e1-381">Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-381">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="e33e1-382">Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-382">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

<span data-ttu-id="e33e1-383">Para obtener más información, vea el [tutorial sobre flujos asincrónicos](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-383">For more information, see the [async streams tutorial](../../csharp/tutorials/generate-consume-asynchronous-stream.md).</span></span>

### <a name="ieee-floating-point"></a><span data-ttu-id="e33e1-384">Punto flotante de IEEE</span><span class="sxs-lookup"><span data-stu-id="e33e1-384">IEEE Floating-point</span></span>

<span data-ttu-id="e33e1-385">Las API de punto flotante se actualizan para cumplir con la [revisión IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="e33e1-385">Floating point APIs are being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="e33e1-386">El objetivo de estos cambios es exponer todas operaciones **requeridas** y asegurarse de que cumplen con la especificación IEEE. Para obtener más información sobre las mejoras de punto flotante, vea la entrada de blog sobre [mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="e33e1-386">The goal of these changes is to expose all **required** operations and ensure that they're behaviorally compliant with the IEEE spec. For more information about floating-point improvements, see the [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

<span data-ttu-id="e33e1-387">Entre las correcciones de análisis y formato se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e33e1-387">Parsing and formatting fixes include:</span></span>

- <span data-ttu-id="e33e1-388">Analice y redondee entradas de cualquier longitud correctamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-388">Correctly parse and round inputs of any length.</span></span>
- <span data-ttu-id="e33e1-389">Analice y formatee el cero negativo correctamente.</span><span class="sxs-lookup"><span data-stu-id="e33e1-389">Correctly parse and format negative zero.</span></span>
- <span data-ttu-id="e33e1-390">Análisis correcto de `Infinity` y `NaN` al hacer una comprobación que no distingue mayúsculas de minúsculas y permitir un `+` anterior opcional cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="e33e1-390">Correctly parse `Infinity` and `NaN` by doing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="e33e1-391">Entre las nuevas API <xref:System.Math?displayProperty=nameWithType> se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e33e1-391">New <xref:System.Math?displayProperty=nameWithType> APIs include:</span></span>

- <span data-ttu-id="e33e1-392"><xref:System.Math.BitIncrement(System.Double)> y <xref:System.Math.BitDecrement(System.Double)></span><span class="sxs-lookup"><span data-stu-id="e33e1-392"><xref:System.Math.BitIncrement(System.Double)> and <xref:System.Math.BitDecrement(System.Double)></span></span>\
<span data-ttu-id="e33e1-393">Corresponde a las operaciones IEEE `nextUp` y `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-393">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="e33e1-394">Devuelven el número de punto flotante más pequeño que compara mayor o menor que la entrada (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="e33e1-394">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="e33e1-395">Por ejemplo, `Math.BitIncrement(0.0)` devolvería `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-395">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

- <span data-ttu-id="e33e1-396"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> y <xref:System.Math.MinMagnitude(System.Double,System.Double)></span><span class="sxs-lookup"><span data-stu-id="e33e1-396"><xref:System.Math.MaxMagnitude(System.Double,System.Double)> and <xref:System.Math.MinMagnitude(System.Double,System.Double)></span></span>\
<span data-ttu-id="e33e1-397">Corresponde a las operaciones IEEE `maxNumMag` y `minNumMag`, que devuelven el valor que es mayor o menor en magnitud de las dos entradas (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="e33e1-397">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="e33e1-398">Por ejemplo, `Math.MaxMagnitude(2.0, -3.0)` devolvería `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-398">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

- <xref:System.Math.ILogB(System.Double)>\
<span data-ttu-id="e33e1-399">Corresponde a la operación IEEE `logB` que devuelve un valor entero, devuelve el logaritmo en base 2 integral del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-399">Corresponds to the `logB` IEEE operation that returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="e33e1-400">Este método es efectivamente el mismo que `floor(log2(x))`, pero con errores de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-400">This method is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
<span data-ttu-id="e33e1-401">Corresponde a la operación IEEE `scaleB` que toma un valor integral, devuelve eficazmente `x * pow(2, n)`, pero se realiza con errores de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-401">Corresponds to the `scaleB` IEEE operation that takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

- <xref:System.Math.Log2(System.Double)>\
<span data-ttu-id="e33e1-402">Corresponde a la operación IEEE `log2`. Devuelve el logaritmo de base 2.</span><span class="sxs-lookup"><span data-stu-id="e33e1-402">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="e33e1-403">Minimiza el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-403">It minimizes rounding error.</span></span>

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
<span data-ttu-id="e33e1-404">Corresponde a la operación IEEE `fma`. Realiza una multiplicación y suma fusionadas.</span><span class="sxs-lookup"><span data-stu-id="e33e1-404">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="e33e1-405">Es decir, realiza `(x * y) + z` como operación única, de forma que se minimiza el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-405">That is, it does `(x * y) + z` as a single operation, thereby minimizing the rounding error.</span></span> <span data-ttu-id="e33e1-406">Un ejemplo es `FusedMultiplyAdd(1e308, 2.0, -1e308)`, que devuelve `1e308`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-406">An example is `FusedMultiplyAdd(1e308, 2.0, -1e308)`, which returns `1e308`.</span></span> <span data-ttu-id="e33e1-407">La operación `(1e308 * 2.0) - 1e308` regular devuelve `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-407">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

- <xref:System.Math.CopySign(System.Double,System.Double)>\
<span data-ttu-id="e33e1-408">Corresponde a la operación IEEE `copySign`. Devuelve el valor de `x`, pero con el signo de `y`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-408">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

### <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="e33e1-409">Elementos intrínsecos dependientes de la plataforma .NET</span><span class="sxs-lookup"><span data-stu-id="e33e1-409">.NET Platform-Dependent Intrinsics</span></span>

<span data-ttu-id="e33e1-410">Se han agregado API que permiten el acceso a determinadas instrucciones CPU orientadas al rendimiento, como los conjuntos de **instrucciones de manipulación de bits** o **SIMD**.</span><span class="sxs-lookup"><span data-stu-id="e33e1-410">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="e33e1-411">Estas instrucciones pueden ayudar a conseguir importantes mejoras de rendimiento en ciertos escenarios, como el procesamiento de datos con eficiencia en paralelo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-411">These instructions can help achieve significant performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span>

<span data-ttu-id="e33e1-412">En su caso, las bibliotecas de .NET han comenzado a utilizar estas instrucciones para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e33e1-412">Where appropriate, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="e33e1-413">Para obtener más información, vea el artículo sobre [elementos intrínsecos dependientes de la plataforma .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span><span class="sxs-lookup"><span data-stu-id="e33e1-413">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md).</span></span>

### <a name="improved-net-core-version-apis"></a><span data-ttu-id="e33e1-414">API de versión mejoradas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e33e1-414">Improved .NET Core Version APIs</span></span>

<span data-ttu-id="e33e1-415">A partir de .NET Core 3.0, las API de versión incluidas con .NET Core ahora devuelven la información que se espera.</span><span class="sxs-lookup"><span data-stu-id="e33e1-415">Starting with .NET Core 3.0, the version APIs provided with .NET Core now return the information you expect.</span></span> <span data-ttu-id="e33e1-416">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e33e1-416">For example:</span></span>

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
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> <span data-ttu-id="e33e1-417">Cambio importante.</span><span class="sxs-lookup"><span data-stu-id="e33e1-417">Breaking change.</span></span> <span data-ttu-id="e33e1-418">Se trata técnicamente de un cambio importante, porque ha cambiado el esquema de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="e33e1-418">This is technically a breaking change because the versioning scheme has changed.</span></span>

### <a name="fast-built-in-json-support"></a><span data-ttu-id="e33e1-419">Compatibilidad con JSON integrada con rápido rendimiento</span><span class="sxs-lookup"><span data-stu-id="e33e1-419">Fast built-in JSON support</span></span>

<span data-ttu-id="e33e1-420">Los usuarios de .NET se han basado en gran medida en [Newtonsoft.Json](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones.</span><span class="sxs-lookup"><span data-stu-id="e33e1-420">.NET users have largely relied on [Newtonsoft.Json](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="e33e1-421">`Newtonsoft.Json` usa cadenas de .NET como tipo de datos base, que, en esencia, es UTF-16.</span><span class="sxs-lookup"><span data-stu-id="e33e1-421">`Newtonsoft.Json` uses .NET strings as its base datatype, which is UTF-16 under the hood.</span></span>

<span data-ttu-id="e33e1-422">La nueva compatibilidad integrada con JSON es de alto rendimiento, baja asignación y funciona con texto JSON codificado UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e33e1-422">The new built-in JSON support is high-performance, low allocation, and works with UTF-8 encoded JSON text.</span></span> <span data-ttu-id="e33e1-423">Para obtener más información sobre el espacio de nombres <xref:System.Text.Json> y los tipos, vea los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e33e1-423">For more information about the <xref:System.Text.Json> namespace and types, see the following articles:</span></span>

* [<span data-ttu-id="e33e1-424">Serialización JSON en .NET: información general</span><span class="sxs-lookup"><span data-stu-id="e33e1-424">JSON serialization in .NET - overview</span></span>](../../standard/serialization/system-text-json-overview.md)
* <span data-ttu-id="e33e1-425">En [Procedimiento para serializar y deserializar JSON en .NET](../../standard/serialization/system-text-json-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="e33e1-425">[How to serialize and deserialize JSON in .NET](../../standard/serialization/system-text-json-how-to.md).</span></span>
* [<span data-ttu-id="e33e1-426">Migración desde Newtonsoft.json a System.Text.Json</span><span class="sxs-lookup"><span data-stu-id="e33e1-426">How to migrate from Newtonsoft.Json to System.Text.Json</span></span>](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a><span data-ttu-id="e33e1-427">Compatibilidad con HTTP/2</span><span class="sxs-lookup"><span data-stu-id="e33e1-427">HTTP/2 support</span></span>

<span data-ttu-id="e33e1-428">El tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> es compatible con el protocolo HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="e33e1-428">The <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> type supports the HTTP/2 protocol.</span></span> <span data-ttu-id="e33e1-429">Si se habilita HTTP/2, la versión del protocolo HTTP se negocia a través de TLS/ALPN y HTTP/2 solo se usa si el servidor opta por usarlo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-429">If HTTP/2 is enabled, the HTTP protocol version is negotiated via TLS/ALPN, and HTTP/2 is used if the server elects to use it.</span></span>

<span data-ttu-id="e33e1-430">El protocolo predeterminado sigue siendo HTTP/1.1, pero se puede habilitar HTTP/2 de dos maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="e33e1-430">The default protocol remains HTTP/1.1, but HTTP/2 can be enabled in two different ways.</span></span> <span data-ttu-id="e33e1-431">En primer lugar, puede establecer el mensaje de solicitud HTTP para usar HTTP/2:</span><span class="sxs-lookup"><span data-stu-id="e33e1-431">First, you can set the HTTP request message to use HTTP/2:</span></span>

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

<span data-ttu-id="e33e1-432">En segundo lugar, puede cambiar <xref:System.Net.Http.HttpClient> para usar HTTP/2 de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="e33e1-432">Second, you can change <xref:System.Net.Http.HttpClient> to use HTTP/2 by default:</span></span>

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

<span data-ttu-id="e33e1-433">Muchas veces cuando está desarrollando una aplicación, desea utilizar una conexión no cifrada.</span><span class="sxs-lookup"><span data-stu-id="e33e1-433">Many times when you're developing an application, you want to use an unencrypted connection.</span></span> <span data-ttu-id="e33e1-434">Si sabe que el punto de conexión de destino utilizará HTTP/2, puede activar las conexiones no cifradas para HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="e33e1-434">If you know the target endpoint will be using HTTP/2, you can turn on unencrypted connections for HTTP/2.</span></span> <span data-ttu-id="e33e1-435">Puede activarlas estableciendo la variable de entorno `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` en `1` o habilitándolas en el contexto de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e33e1-435">You can turn it on by setting the `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` environment variable to `1` or by enabling it in the app context:</span></span>

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a><span data-ttu-id="e33e1-436">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e33e1-436">Next steps</span></span>

- [<span data-ttu-id="e33e1-437">Revise los cambios importantes entre .NET Core 2.2 y 3.0.</span><span class="sxs-lookup"><span data-stu-id="e33e1-437">Review the breaking changes between .NET Core 2.2 and 3.0.</span></span>](../compatibility/2.2-3.0.md)
- [<span data-ttu-id="e33e1-438">Revise los cambios importantes de .NET Core 3.0 para aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e33e1-438">Review the breaking changes in .NET Core 3.0 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-30)
