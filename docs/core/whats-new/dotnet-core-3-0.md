---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 26fb7cb25b9bf7f00f87059fbe1848763f7f175d
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415551"
---
# <a name="whats-new-in-net-core-30-preview-1"></a><span data-ttu-id="22183-103">Novedades de .NET Core 3.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="22183-103">What's new in .NET Core 3.0 (Preview 1)</span></span>

<span data-ttu-id="22183-104">En este artículo se describen las novedades de .NET Core 3.0 (versión preliminar 1).</span><span class="sxs-lookup"><span data-stu-id="22183-104">This article describes what is new in .NET Core 3.0 (preview 1).</span></span> <span data-ttu-id="22183-105">Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="22183-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="22183-106">Mediante el uso de un componente de .NET Core 3.0 denominado "Escritorio de Windows", puede trasladar sus aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="22183-106">By utilizing a .NET Core 3.0 component called Windows Desktop, you can port your Windows Forms Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="22183-107">Para ser más precisos, el componente Escritorio de Windows solo se admite en Windows.</span><span class="sxs-lookup"><span data-stu-id="22183-107">To be clear, the Windows Desktop component is only supported on Windows.</span></span> <span data-ttu-id="22183-108">Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) de más adelante.</span><span class="sxs-lookup"><span data-stu-id="22183-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="22183-109">.NET Core 3.0 agrega compatibilidad con C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="22183-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="22183-110">[Descargue .NET Core 3 (versión preliminar 1) y empiece a usarlo](https://aka.ms/netcore3download) ahora mismo en Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="22183-110">[Download and get started with .NET Core 3 Preview 1](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="22183-111">Puede ver los detalles completos de la versión en las [notas de la versión preliminar 1 de .NET Core 3](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="22183-111">You can see complete details of the release in the [.NET Core 3 Preview 1 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="22183-112">Para obtener más información, consulte el [anuncio sobre la versión preliminar 1 de .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span><span class="sxs-lookup"><span data-stu-id="22183-112">For more information, see the [.NET Core 3.0 Preview 1 announcement](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).</span></span>

## <a name="net-standard-21"></a><span data-ttu-id="22183-113">.NET Standard 2.1</span><span class="sxs-lookup"><span data-stu-id="22183-113">.NET Standard 2.1</span></span>

<span data-ttu-id="22183-114">.NET Core 3.0 también implementa .NET Standard 2.1.</span><span class="sxs-lookup"><span data-stu-id="22183-114">.NET Core 3.0 implements .NET Standard 2.1.</span></span>

## <a name="default-executables"></a><span data-ttu-id="22183-115">Archivos ejecutables predeterminados</span><span class="sxs-lookup"><span data-stu-id="22183-115">Default executables</span></span>

<span data-ttu-id="22183-116">.NET Core compilará ahora los [archivos ejecutables dependientes de marco de trabajo](../deploying/index.md#framework-dependent-executables-fde) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22183-116">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="22183-117">Se trata de una novedad en las aplicaciones que usan una versión de .NET Core instalada de forma global.</span><span class="sxs-lookup"><span data-stu-id="22183-117">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="22183-118">Hasta ahora, solo las [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) producirían un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="22183-118">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="22183-119">Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable siempre que coincida con el entorno y la plataforma del SDK que usa.</span><span class="sxs-lookup"><span data-stu-id="22183-119">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="22183-120">Estos ejecutables funcionan de la misma forma que los ejecutables nativos:</span><span class="sxs-lookup"><span data-stu-id="22183-120">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="22183-121">Haga doble clic en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="22183-121">You can double-click on the executable.</span></span>
* <span data-ttu-id="22183-122">También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="22183-122">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="22183-123">Compilación de dependencias de copias</span><span class="sxs-lookup"><span data-stu-id="22183-123">Build copies dependencies</span></span>

<span data-ttu-id="22183-124">`dotnet build` ahora copia las dependencias de NuGet de la aplicación desde la caché de NuGet en la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="22183-124">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="22183-125">Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="22183-125">Previously, dependencies were only copied as part of `dotnet publish`.</span></span> 

<span data-ttu-id="22183-126">Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.</span><span class="sxs-lookup"><span data-stu-id="22183-126">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>


## <a name="local-dotnet-tools"></a><span data-ttu-id="22183-127">Herramientas de dotnet locales</span><span class="sxs-lookup"><span data-stu-id="22183-127">Local dotnet tools</span></span>

<span data-ttu-id="22183-128">Aunque .NET Core 2.1 admitía herramientas globales, .NET Core 3.0 ahora cuenta con herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="22183-128">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="22183-129">Las herramientas locales son similares a las globales, pero están asociadas a una ubicación concreta del disco.</span><span class="sxs-lookup"><span data-stu-id="22183-129">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="22183-130">De este modo, se pueden usar herramientas por proyecto y por repositorio.</span><span class="sxs-lookup"><span data-stu-id="22183-130">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="22183-131">Las herramientas instaladas de forma local no están disponibles de manera global.</span><span class="sxs-lookup"><span data-stu-id="22183-131">Any tool installed locally isn't available globally.</span></span>

<span data-ttu-id="22183-132">Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="22183-132">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="22183-133">Este archivo de manifiesto define las herramientas que estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="22183-133">This manifest file defines the tools to be available.</span></span> <span data-ttu-id="22183-134">Al crear este archivo de manifiesto en la raíz del repositorio, asegúrese de que cualquier usuario que clone el código pueda restaurar y usar las herramientas que se necesitan para trabajar correctamente con el código.</span><span class="sxs-lookup"><span data-stu-id="22183-134">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="22183-135">Cuando el archivo de manifiesto de herramientas locales está disponible, use el comando siguiente para descargar e instalar automáticamente estas herramientas de manera local:</span><span class="sxs-lookup"><span data-stu-id="22183-135">When the local tools manifest file is available, use the following command to automatically download and install those tools locally:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="22183-136">Ejecute una herramienta local con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="22183-136">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="22183-137">Cuando se llama a una herramienta local, dotnet busca un manifiesto en la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="22183-137">When a local tool is called, dotnet searches for a manifest up the directory structure.</span></span> <span data-ttu-id="22183-138">Cuando se encuentra un archivo de manifiesto de herramientas, se busca la herramienta solicitada.</span><span class="sxs-lookup"><span data-stu-id="22183-138">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="22183-139">Si se encuentra la herramienta, incluirá la información necesaria para encontrar la herramienta en la ubicación de paquetes globales NuGet.</span><span class="sxs-lookup"><span data-stu-id="22183-139">If the tool is found, it includes the information needed to find the tool in the NuGet global packages location.</span></span> 

<span data-ttu-id="22183-140">Si la herramienta se encuentra en el manifiesto, pero no en la caché, el usuario recibe un error.</span><span class="sxs-lookup"><span data-stu-id="22183-140">If the tool is found in the manifest, but not the cache, the user receives an error.</span></span> <span data-ttu-id="22183-141">Se mejorará el mensaje después de la versión preliminar 1 para pedir al usuario que ejecute `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="22183-141">The message will be improved after Preview 1 to request the user run `dotnet tool restore`.</span></span>

<span data-ttu-id="22183-142">Para agregar herramientas locales a un directorio, deberá crear primero el archivo de manifiesto de herramientas.</span><span class="sxs-lookup"><span data-stu-id="22183-142">To add local tools to a directory, you need to first create the tool manifest file.</span></span> <span data-ttu-id="22183-143">Después de la versión preliminar 1, ofreceremos un mecanismo para crear los archivos de manifiesto de herramientas, por ejemplo, una nueva plantilla de dotnet.</span><span class="sxs-lookup"><span data-stu-id="22183-143">After Preview 1, we will offer a mechanism for creating tool manifest files, such as a dotnet new template.</span></span> <span data-ttu-id="22183-144">Para la versión preliminar 1, debe crear un archivo denominado "`dotnet-tools.json`" con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="22183-144">For Preview 1 you must create the file named `dotnet-tools.json` with the following contents:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="22183-145">Una vez que se crea el manifiesto, podrá agregarle herramientas locales mediante lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22183-145">Once the manifest is created, you can add local tools to it using:</span></span>

```console
dotnet tool install <toolPackageId>
```

<span data-ttu-id="22183-146">Este comando instala la versión más reciente de la herramienta, a menos que se especifique otra.</span><span class="sxs-lookup"><span data-stu-id="22183-146">This command installs the latest version of the tool, unless another version is specified.</span></span>  <span data-ttu-id="22183-147">Aunque eligiera automáticamente la más reciente, la versión de la herramienta se escribe en el archivo de manifiesto de herramientas para permitir que se pueda restaurar o ejecutar la versión correcta de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="22183-147">Even if the latest version was automatically chosen, the version of the tool is written into the tool manifest file to allow the correct version of the tool to be restored or run.</span></span>

<span data-ttu-id="22183-148">El archivo de manifiesto de herramientas está diseñado para poder modificarse manualmente (podría hacerlo para actualizar la versión necesaria para trabajar con el repositorio).</span><span class="sxs-lookup"><span data-stu-id="22183-148">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span>

<span data-ttu-id="22183-149">A continuación, se muestra un archivo `dotnet-tools.json` de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="22183-149">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="22183-150">Para quitar una herramienta del archivo de manifiesto de herramientas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="22183-150">To remove a tool from the tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <toolPackageId>
```

<span data-ttu-id="22183-151">Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="22183-151">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="22183-152">Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="22183-152">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="22183-153">Para instalarlas de forma global o local, aún es necesario instalar el [entorno de ejecución de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="22183-153">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="22183-154">Para obtener más información, consulte [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288) (Documentación de la versión preliminar anticipada de las herramientas locales).</span><span class="sxs-lookup"><span data-stu-id="22183-154">For more information, see [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="22183-155">Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="22183-155">Windows desktop</span></span>

<span data-ttu-id="22183-156">A partir de la versión preliminar 1 de .NET Core 3.0, puede compilar aplicaciones de Escritorio de Windows con WPF y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="22183-156">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="22183-157">Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="22183-157">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="22183-158">El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="22183-158">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="22183-159">Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="22183-159">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="22183-160">También puede abrir, iniciar y depurar proyectos de Windows Forms y WPF de .NET Core 3.0 en la versión preliminar 1 de Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="22183-160">You can also open, launch, and debug .NET Core 3.0 WPF and Windows Forms projects in Visual Studio 2019 Preview 1.</span></span> <span data-ttu-id="22183-161">Actualmente se pueden abrir estos proyectos en Visual Studio 2017 15.9; sin embargo, no se trata de un escenario compatible (y debe [habilitar las versiones preliminares](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span><span class="sxs-lookup"><span data-stu-id="22183-161">It's currently possible to open these projects in Visual Studio 2017 15.9, however, it isn't a supported scenario (and you need to [enable previews](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).</span></span>

<span data-ttu-id="22183-162">Los nuevos proyectos son los mismos que los existentes de .NET Core, con algunas adiciones.</span><span class="sxs-lookup"><span data-stu-id="22183-162">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="22183-163">Esta es la comparación del proyecto de consola de .NET Core básico y un proyecto básico de Windows Forms y WPF.</span><span class="sxs-lookup"><span data-stu-id="22183-163">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="22183-164">En un proyecto de consola de .NET Core, se usa el SDK `Microsoft.NET.Sdk` y se declara una dependencia en .NET Core 3.0 a través del marco de destino `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="22183-164">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="22183-165">Para crear una aplicación de Escritorio de Windows, use el SDK `Microsoft.NET.Sdk.WindowsDesktop` y elija qué marco de interfaz de usuario usará:</span><span class="sxs-lookup"><span data-stu-id="22183-165">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="22183-166">Para elegir Windows Forms en WPF, establezca `UseWindowsForms` en lugar de `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="22183-166">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="22183-167">`UseWPF` y `UseWindowsForms` se puede establecer en `true` si la aplicación usa ambos marcos, por ejemplo, cuando un cuadro de diálogo de Windows Forms hospeda un control de WPF.</span><span class="sxs-lookup"><span data-stu-id="22183-167">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="22183-168">Comparta sus comentarios en los repositorios [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) y [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="22183-168">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="fast-built-in-json-support"></a><span data-ttu-id="22183-169">Compatibilidad con JSON integrada con rápido rendimiento</span><span class="sxs-lookup"><span data-stu-id="22183-169">Fast built-in JSON support</span></span>

<span data-ttu-id="22183-170">`System.Text.Json.Utf8JsonReader` es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="22183-170">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="22183-171">`Utf8JsonReader` es un tipo fundamental de bajo nivel que puede utilizarse para crear analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="22183-171">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="22183-172">La lectura a través de una carga JSON con el nuevo lector `Utf8JsonReader` es el doble de rápido que con el lector de [Json.NET](https://www.newtonsoft.com/json).</span><span class="sxs-lookup"><span data-stu-id="22183-172">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from [Json.NET](https://www.newtonsoft.com/json).</span></span> <span data-ttu-id="22183-173">No se realiza la asignación hasta que se necesite actualizar los tokens JSON como cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="22183-173">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="22183-174">Esta nueva API incluirá los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="22183-174">This new API will include the following components:</span></span>

* <span data-ttu-id="22183-175">En la versión preliminar 1: lector JSON (acceso secuencial)</span><span class="sxs-lookup"><span data-stu-id="22183-175">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="22183-176">Próximamente: escritor JSON, DOM (acceso aleatorio), y serializador y deserializador poco</span><span class="sxs-lookup"><span data-stu-id="22183-176">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="22183-177">Este es el bucle de lectura básico para el lector `Utf8JsonReader` que puede utilizarse como punto inicial:</span><span class="sxs-lookup"><span data-stu-id="22183-177">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

<span data-ttu-id="22183-178">El ecosistema .NET depende de [Json.NET](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones.</span><span class="sxs-lookup"><span data-stu-id="22183-178">The .NET ecosystem has relied on [Json.NET](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="22183-179">JSON.NET utiliza cadenas .NET como su tipo de datos base, que son UTF-16 en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="22183-179">JSON.NET uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span> 

<span data-ttu-id="22183-180">En .NET Core 2.1 y 3.0, hemos agregado nuevas API que permiten escribir las API de JSON (como `Utf8JsonReader`) que requieren mucho menos memoria, en función del uso de cadenas UTF-8 y `Span<T>`, y satisfacen mejor las necesidades de aplicaciones de alto rendimiento, como Kestrel, el servidor web de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="22183-180">In .NET Core 2.1 and 3.0, we added new APIs that makes it possible to write JSON APIs (such as `Utf8JsonReader`) that require much less memory, based on using `Span<T>` and UTF-8 strings, and better serve the needs of high-throughput applications like Kestrel, ASP.NET Core web server.</span></span>

## <a name="ranges-and-indices"></a><span data-ttu-id="22183-181">Rangos e índices</span><span class="sxs-lookup"><span data-stu-id="22183-181">Ranges and indices</span></span>

<span data-ttu-id="22183-182">El nuevo tipo `Index` se puede utilizar para la indización.</span><span class="sxs-lookup"><span data-stu-id="22183-182">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="22183-183">Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:</span><span class="sxs-lookup"><span data-stu-id="22183-183">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="22183-184">También hay un tipo `Range`, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de rango `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="22183-184">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="22183-185">A continuación, puede crear un índice con un rango `Range` con el fin de generar un segmento:</span><span class="sxs-lookup"><span data-stu-id="22183-185">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> <span data-ttu-id="22183-186">Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) admite la sintaxis de `Range` y `Index`.</span><span class="sxs-lookup"><span data-stu-id="22183-186">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports syntax for `Range` and `Index`.</span></span>

## <a name="async-streams"></a><span data-ttu-id="22183-187">Flujos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="22183-187">Async streams</span></span>

<span data-ttu-id="22183-188">El tipo `IAsyncEnumerable<T>` es una nueva versión asincrónica de `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="22183-188">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="22183-189">El lenguaje permite ejecutar la instrucción `await foreach` en los flujos para consumir sus elementos, y ejecutar la instrucción `yield return` en ellos para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="22183-189">The language lets you `await foreach` over these to consume their elements, and `yield return` to them to produce elements.</span></span>

<span data-ttu-id="22183-190">En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="22183-190">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="22183-191">La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="22183-191">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="22183-192">Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="22183-192">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> <span data-ttu-id="22183-193">Actualmente, en la versión preliminar 1 de .NET Core 3.0 hay un error con `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="22183-193">.NET Core 3.0 Preview 1 currently has a bug with `await foreach`.</span></span> <span data-ttu-id="22183-194">En su lugar, use `GetEnumerator` y `MoveNext` en procesar los elementos.</span><span class="sxs-lookup"><span data-stu-id="22183-194">Instead, use `GetEnumerator` and `MoveNext` to process elements.</span></span> <span data-ttu-id="22183-195">Para obtener más información, consulte [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span><span class="sxs-lookup"><span data-stu-id="22183-195">For more information, see [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).</span></span>

<span data-ttu-id="22183-196">Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="22183-196">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="22183-197">Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.</span><span class="sxs-lookup"><span data-stu-id="22183-197">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="22183-198">Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) admite la sintaxis de `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="22183-198">Only [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) supports `await foreach` syntax.</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="22183-199">Tipo: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="22183-199">Type: SequenceReader</span></span>

<span data-ttu-id="22183-200">En .NET Core 3.0, se ha agregado `System.Buffers.SequenceReader`, que se puede usar como lector de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="22183-200">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="22183-201">De este modo, se puede realizar un análisis de alto rendimiento y de asignación baja de los datos `System.IO.Pipelines` que pueden atravesar varios búferes de respaldo.</span><span class="sxs-lookup"><span data-stu-id="22183-201">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span> 

<span data-ttu-id="22183-202">En el ejemplo siguiente, se interrumpe una entrada `Sequence` en las líneas delimitadas `CR/LF` válidas:</span><span class="sxs-lookup"><span data-stu-id="22183-202">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="22183-203">Tipo: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="22183-203">Type: MetadataLoadContext</span></span>

<span data-ttu-id="22183-204">Se ha agregado el tipo `MetadataLoadContext` que permite leer los metadatos de ensamblado sin que afecte al dominio de aplicación del llamador.</span><span class="sxs-lookup"><span data-stu-id="22183-204">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="22183-205">Los ensamblados se leen como datos, incluidos los ensamblados compilados para arquitecturas y plataformas distintas al entorno en tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="22183-205">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="22183-206">`MetadataLoadContext` se superpone con <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, que solo está disponible en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22183-206">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="22183-207">`MetdataLoadContext` está disponible en el paquete [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="22183-207">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="22183-208">Se trata de un paquete de .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="22183-208">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="22183-209">`MetadataLoadContext`expone las API similares al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, pero no se basa en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="22183-209">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="22183-210">De forma similar a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` habilita la carga de ensamblados dentro del universo de carga de ensamblados aislados.</span><span class="sxs-lookup"><span data-stu-id="22183-210">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="22183-211">Las API de `MetdataLoadContext` devuelven objetos <xref:System.Reflection.Assembly>, lo que permite el uso de API de reflexión conocidas.</span><span class="sxs-lookup"><span data-stu-id="22183-211">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="22183-212">Las API orientadas a la ejecución, como [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), no se permiten y generan la excepción InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="22183-212">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="22183-213">El ejemplo siguiente muestra cómo buscar tipos concretos en un ensamblado que implementa una interfaz determinada:</span><span class="sxs-lookup"><span data-stu-id="22183-213">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="22183-214">Los escenarios para `MetadataLoadContext` incluyen características de tiempo de diseño, herramientas de tiempo de compilación y características de alumbrado en tiempo de ejecución que necesitan inspeccionar un conjunto de ensamblados como datos y que tienen todos los bloqueos de archivo y la memoria liberada después de la inspección.</span><span class="sxs-lookup"><span data-stu-id="22183-214">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="22183-215">`MetadataLoadContext` tiene una clase de resolución que se transmite a su constructor.</span><span class="sxs-lookup"><span data-stu-id="22183-215">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="22183-216">El trabajo de la resolución consiste en cargar un ensamblado `Assembly` dado su `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="22183-216">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="22183-217">La clase de la resolución se deriva de la clase abstracta `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="22183-217">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="22183-218">Se proporciona una implementación de la resolución para escenarios basados en rutas de acceso con `PathAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="22183-218">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="22183-219">[MetadataLoadContext pruebas](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) muestra muchos casos de uso.</span><span class="sxs-lookup"><span data-stu-id="22183-219">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="22183-220">Las [pruebas de ensamblado](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) son un buen punto inicial.</span><span class="sxs-lookup"><span data-stu-id="22183-220">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="22183-221">TLS 1.3 y OpenSSL 1.1.1 en Linux</span><span class="sxs-lookup"><span data-stu-id="22183-221">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="22183-222">.NET Core ahora usará la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/) cuando esté disponible en un entorno determinado.</span><span class="sxs-lookup"><span data-stu-id="22183-222">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="22183-223">TLS 1.3 aporta varias ventajas, según el [equipo de OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="22183-223">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="22183-224">Mejora de los tiempos de conexión gracias a una reducción del número de recorridos de ida y vuelta necesario entre el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="22183-224">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="22183-225">Mejora de la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros y al mayor cifrado del protocolo de enlace de la conexión.</span><span class="sxs-lookup"><span data-stu-id="22183-225">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="22183-226">La versión preliminar 1 de .NET Core 3.0 puede usar **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (la mejor versión que se encuentre en un sistema Linux).</span><span class="sxs-lookup"><span data-stu-id="22183-226">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="22183-227">Cuando **OpenSSL 1.1.1** está disponible, los tipos SslStream y HttpClient usarán **TLS 1.3** al usar `SslProtocols.None` (protocolos predeterminados del sistema), dando por sentado que el cliente y el servidor admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="22183-227">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="22183-228">En el siguiente ejemplo se muestra la versión preliminar 1 de .NET Core 3.0 en Ubuntu 18.10 con conexión a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="22183-228">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="22183-229">Windows y macOS aún no admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="22183-229">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="22183-230">.NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="22183-230">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="22183-231">Criptografía</span><span class="sxs-lookup"><span data-stu-id="22183-231">Cryptography</span></span>

<span data-ttu-id="22183-232">Se ha agregado compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan a través de `System.Security.Cryptography.AesGcm` y `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="22183-232">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="22183-233">Estos algoritmos son el [cifrado autenticado con algoritmos de datos de asociación (AEAD)](https://en.wikipedia.org/wiki/Authenticated_encryption) y los primeros algoritmos de cifrado autenticado (AE) agregados a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22183-233">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="22183-234">En el código siguiente se muestra cómo utilizar el cifrado **AesGcm** para cifrar y descifrar datos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="22183-234">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="22183-235">El código de **AesCcm** sería casi idéntico (solo los nombres de variables de clase serían diferentes).</span><span class="sxs-lookup"><span data-stu-id="22183-235">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="22183-236">Importación y exportación de claves criptográfica</span><span class="sxs-lookup"><span data-stu-id="22183-236">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="22183-237">La versión preliminar 1 de .NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas de los formatos estándar, sin necesidad de usar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="22183-237">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="22183-238">Todos los tipos de clave (RSA, DSA, ECDsa y ECDiffieHellman) son compatibles con el formato **X.509 SubjectPublicKeyInfo** de las claves públicas, y con los formatos **PKCS #8 PrivateKeyInfo** y **EncryptedPrivateKeyInfo de PKCS #8**  de las claves privadas.</span><span class="sxs-lookup"><span data-stu-id="22183-238">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="22183-239">Además, RSA admite **PKCS #1 RSAPublicKey** y **PKCS #1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="22183-239">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="22183-240">Todos los métodos de exportación e importación generan datos binarios con codificación DER.</span><span class="sxs-lookup"><span data-stu-id="22183-240">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="22183-241">Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.</span><span class="sxs-lookup"><span data-stu-id="22183-241">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="22183-242">Los archivos PKCS#8 pueden inspeccionarse con la clase `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="22183-242">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="22183-243">Los archivos PFX/PKCS#12 se pueden inspeccionar y manipular con `System.Security.Cryptography.Pkcs.Pkcs12Info` y `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="22183-243">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="22183-244">SerialPort para Linux</span><span class="sxs-lookup"><span data-stu-id="22183-244">SerialPort for Linux</span></span>

<span data-ttu-id="22183-245">.NET Core 3.0 ahora admite <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.</span><span class="sxs-lookup"><span data-stu-id="22183-245">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="22183-246">Anteriormente, .NET Core solo admite el uso del tipo `SerialPort` en Windows.</span><span class="sxs-lookup"><span data-stu-id="22183-246">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="22183-247">Más mejoras de BCL</span><span class="sxs-lookup"><span data-stu-id="22183-247">More BCL Improvements</span></span>

<span data-ttu-id="22183-248">`Span<T>`, `Memory<T>` y los tipos relacionados que se introdujeron en .NET Core 2.1 se han optimizado en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="22183-248">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="22183-249">Operaciones comunes, como la construcción de intervalos, la segmentación, el análisis y la aplicación de formato funcionan mejor ahora.</span><span class="sxs-lookup"><span data-stu-id="22183-249">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span> 

<span data-ttu-id="22183-250">Además, los tipos como `String` se han mejorado para que sean más eficaces cuando se utilizan como claves con `Dictionary<TKey, TValue>` y otras colecciones.</span><span class="sxs-lookup"><span data-stu-id="22183-250">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="22183-251">No se requiere ningún cambio de código para aprovechar estas mejoras.</span><span class="sxs-lookup"><span data-stu-id="22183-251">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="22183-252">Las mejoras siguientes también son nuevas en la versión preliminar 1 de .NET Core 3:</span><span class="sxs-lookup"><span data-stu-id="22183-252">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="22183-253">Compatibilidad con Brotli integrada en HttpClient</span><span class="sxs-lookup"><span data-stu-id="22183-253">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="22183-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="22183-254">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="22183-255">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="22183-255">Unsafe.Unbox</span></span>
* <span data-ttu-id="22183-256">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="22183-256">CancellationToken.Unregister</span></span>
* <span data-ttu-id="22183-257">Operadores aritméticos complejos</span><span class="sxs-lookup"><span data-stu-id="22183-257">Complex arithmetic operators</span></span>
* <span data-ttu-id="22183-258">API de socket para TCP persistente</span><span class="sxs-lookup"><span data-stu-id="22183-258">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="22183-259">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="22183-259">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="22183-260">Análisis de IPEndPoint</span><span class="sxs-lookup"><span data-stu-id="22183-260">IPEndPoint parsing</span></span>
* <span data-ttu-id="22183-261">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="22183-261">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="22183-262">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="22183-262">Tiered compilation</span></span>

<span data-ttu-id="22183-263">La [compilación en niveles](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) está activada de forma predeterminada con .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="22183-263">[Tiered compilation](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="22183-264">Se trata de una característica que permite que el entorno de ejecución use de forma más adaptable el compilador Just-In-Time (JIT) para obtener un mejor rendimiento, tanto en el inicio como al maximizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="22183-264">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="22183-265">Se agregó como una característica opcional en [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) y, más tarde, se habilitó de forma predeterminada en la [versión preliminar 2 de .NET Core 2.2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="22183-265">This feature was added as an opt-in feature in [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="22183-266">Posteriormente, se revirtió a opcional con .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="22183-266">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="22183-267">Compatibilidad con ARM64 para Linux</span><span class="sxs-lookup"><span data-stu-id="22183-267">ARM64 Linux support</span></span>

<span data-ttu-id="22183-268">Vamos a agregar compatibilidad con ARM64 para Linux en esta versión.</span><span class="sxs-lookup"><span data-stu-id="22183-268">We are adding support for ARM64 for Linux this release.</span></span> <span data-ttu-id="22183-269">Para poner en contexto, hemos agregado compatibilidad con ARM32 para Linux con .NET Core 2.1 y Windows con .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="22183-269">For context, we added support for ARM32 for Linux with .NET Core 2.1 and Windows with .NET Core 2.2.</span></span> <span data-ttu-id="22183-270">El principal caso de uso de ARM64 son escenarios de IoT.</span><span class="sxs-lookup"><span data-stu-id="22183-270">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="22183-271">Las [imágenes de Docker de Alpine, Debian y Ubuntu están disponibles en .NET Core para ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="22183-271">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="22183-272">Consulte la página sobre el [estado de ARM64 para .NET Core](https://github.com/dotnet/announcements/issues/82) si desea obtener más información.</span><span class="sxs-lookup"><span data-stu-id="22183-272">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="22183-273">Windows aún no ofrece soporte técnico para **ARM64**.</span><span class="sxs-lookup"><span data-stu-id="22183-273">**ARM64** Windows support isn't yet available.</span></span>
