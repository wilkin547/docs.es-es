---
title: Novedades de .NET Core 2.0
description: Obtenga información sobre las características nuevas de .NET Core.
ms.date: 08/13/2017
ms.openlocfilehash: 115b3adc72b6798c6a7bac9cc18044a8822808a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397846"
---
# <a name="whats-new-in-net-core-20"></a><span data-ttu-id="fd283-103">Novedades de .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fd283-103">What's new in .NET Core 2.0</span></span>

<span data-ttu-id="fd283-104">.NET Core 2.0 incluye mejoras y características nuevas en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd283-104">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="fd283-105">Herramientas</span><span class="sxs-lookup"><span data-stu-id="fd283-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="fd283-106">Compatibilidad con lenguajes</span><span class="sxs-lookup"><span data-stu-id="fd283-106">Language support</span></span>](#language-support)
- [<span data-ttu-id="fd283-107">Mejoras en la plataforma</span><span class="sxs-lookup"><span data-stu-id="fd283-107">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="fd283-108">Cambios en la API</span><span class="sxs-lookup"><span data-stu-id="fd283-108">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="fd283-109">Integración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd283-109">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="fd283-110">Mejoras en la documentación</span><span class="sxs-lookup"><span data-stu-id="fd283-110">Documentation improvements</span></span>](#documentation-improvements)

## <a name="tooling"></a><span data-ttu-id="fd283-111">Tooling</span><span class="sxs-lookup"><span data-stu-id="fd283-111">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="fd283-112">dotnet restore se ejecuta de manera implícita</span><span class="sxs-lookup"><span data-stu-id="fd283-112">dotnet restore runs implicitly</span></span>

<span data-ttu-id="fd283-113">En las versiones anteriores de .NET Core, era necesario ejecutar el comando [dotnet restore](../tools/dotnet-restore.md) para descargar dependencias inmediatamente después de crear un proyecto nuevo con el comando [dotnet new](../tools/dotnet-new.md), así como también cada vez que se agregaba una dependencia nueva al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fd283-113">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="fd283-114">También puede deshabilitar la invocación automática de `dotnet restore` si pasa el modificador `--no-restore` a los comandos `new`, `run`, `build`, `publish`, `pack` y `test`.</span><span class="sxs-lookup"><span data-stu-id="fd283-114">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span>

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="fd283-115">Redestinación a .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fd283-115">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="fd283-116">Si el SDK de .NET Core 2.0 SDK está instalado, los proyectos que tienen .NET Core 1.x como destino se pueden redestinar a .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="fd283-116">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span>

<span data-ttu-id="fd283-117">Para redestinar a .NET Core 2.0, edite el archivo del proyecto cambiando el valor del elemento `<TargetFramework>` (o del elemento `<TargetFrameworks>`, si tiene más de un destino en el archivo del proyecto) de 1.x a 2.0:</span><span class="sxs-lookup"><span data-stu-id="fd283-117">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="fd283-118">También puede redestinar las bibliotecas de .NET Standard a .NET Standard 2.0 del mismo modo:</span><span class="sxs-lookup"><span data-stu-id="fd283-118">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="fd283-119">Para más información sobre cómo migrar el proyecto a .NET Core 2.0, consulte el artículo sobre [migración de ASP.NET Core 1.x a ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span><span class="sxs-lookup"><span data-stu-id="fd283-119">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="fd283-120">Compatibilidad con lenguajes</span><span class="sxs-lookup"><span data-stu-id="fd283-120">Language support</span></span>

<span data-ttu-id="fd283-121">Además de admitir C# y F#, .NET Core 2.0 también es compatible con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fd283-121">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="fd283-122">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fd283-122">Visual Basic</span></span>

<span data-ttu-id="fd283-123">Con la versión 2.0, .NET Core ahora es compatible con Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="fd283-123">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="fd283-124">Puede usar Visual Basic para crear los tipos de proyecto siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd283-124">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="fd283-125">Aplicaciones de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-125">.NET Core console apps</span></span>
- <span data-ttu-id="fd283-126">Bibliotecas de clases .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-126">.NET Core class libraries</span></span>
- <span data-ttu-id="fd283-127">Bibliotecas de clases .NET Standard</span><span class="sxs-lookup"><span data-stu-id="fd283-127">.NET Standard class libraries</span></span>
- <span data-ttu-id="fd283-128">Proyectos de prueba unitaria .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-128">.NET Core unit test projects</span></span>
- <span data-ttu-id="fd283-129">Proyectos de prueba xUnit .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-129">.NET Core xUnit test projects</span></span>

<span data-ttu-id="fd283-130">Por ejemplo, para crear una aplicación "Hola mundo" de Visual Basic, haga estos pasos en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="fd283-130">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="fd283-131">En una ventana de la consola, cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="fd283-131">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="fd283-132">Escriba el comando `dotnet new console -lang vb`.</span><span class="sxs-lookup"><span data-stu-id="fd283-132">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="fd283-133">El comando crea un archivo del proyecto con una extensión de archivo `.vbproj`, además de un archivo de código fuente de Visual Basic llamado *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="fd283-133">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="fd283-134">Este archivo contiene el código fuente para escribir la cadena "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="fd283-134">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="fd283-135">en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="fd283-135">to the console window.</span></span>

1. <span data-ttu-id="fd283-136">Escriba el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="fd283-136">Enter the command `dotnet run`.</span></span> <span data-ttu-id="fd283-137">La [CLI de .NET Core](../tools/index.md) compila y ejecuta automáticamente la aplicación, con lo que se muestra el mensaje "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="fd283-137">The [.NET Core CLI](../tools/index.md) automatically compiles and executes the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="fd283-138">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="fd283-138">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="fd283-139">Compatibilidad con C# 7.1</span><span class="sxs-lookup"><span data-stu-id="fd283-139">Support for C# 7.1</span></span>

<span data-ttu-id="fd283-140">.NET Core 2.0 es compatible con C# 7.1, que agrega varias características nuevas, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd283-140">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="fd283-141">El método `Main`, el punto de entrada de la aplicación, se puede marcar con la palabra clave [async](../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="fd283-141">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="fd283-142">Nombres de tupla deducidos.</span><span class="sxs-lookup"><span data-stu-id="fd283-142">Inferred tuple names.</span></span>
- <span data-ttu-id="fd283-143">Expresiones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="fd283-143">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="fd283-144">Mejoras en la plataforma</span><span class="sxs-lookup"><span data-stu-id="fd283-144">Platform improvements</span></span>

<span data-ttu-id="fd283-145">.NET Core 2.0 incluye varias características que facilitan la instalación de .NET Core y su uso en sistemas operativos compatibles.</span><span class="sxs-lookup"><span data-stu-id="fd283-145">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="fd283-146">.NET Core para Linux es una sola implementación</span><span class="sxs-lookup"><span data-stu-id="fd283-146">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="fd283-147">.NET Core 2.0 ofrece una sola implementación de Linux que funciona en varias distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="fd283-147">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="fd283-148">.NET Core 1.x requería que descargara una implementación de Linux específica para la distribución.</span><span class="sxs-lookup"><span data-stu-id="fd283-148">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="fd283-149">También puede desarrollar aplicaciones que tienen Linux como destino como un solo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fd283-149">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="fd283-150">.NET Core 1.x requería que se tuviera cada distribución de Linux como destino de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="fd283-150">.NET Core 1.x required that you target each Linux distribution separately.</span></span>

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="fd283-151">Compatibilidad con las bibliotecas de cifrado de Apple</span><span class="sxs-lookup"><span data-stu-id="fd283-151">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="fd283-152">.NET Core 1.x en macOS requería la biblioteca de cifrado del kit de herramientas OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="fd283-152">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="fd283-153">.NET Core 2.0 usa las bibliotecas de cifrado de Apple y no requiere OpenSSL, por lo que ya no es necesario instalarlo.</span><span class="sxs-lookup"><span data-stu-id="fd283-153">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span>

## <a name="api-changes-and-library-support"></a><span data-ttu-id="fd283-154">Cambios en la API y compatibilidad con bibliotecas</span><span class="sxs-lookup"><span data-stu-id="fd283-154">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="fd283-155">Compatibilidad con .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="fd283-155">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="fd283-156">.NET Standard define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="fd283-156">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="fd283-157">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="fd283-157">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="fd283-158">Pretende garantizar la funcionalidad que está disponible a una biblioteca que tiene como destino una versión de .NET Standard en cada implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="fd283-158">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="fd283-159">.NET Core 1.x es compatible con la versión 1.6 de .NET Standard; .NET Core 2.0 es compatible con la versión más reciente, .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="fd283-159">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="fd283-160">Para más información, consulte [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="fd283-160">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="fd283-161">.NET Standard 2.0 incluye más de 20 000 API más que las disponibles en .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="fd283-161">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="fd283-162">Gran parte de esta área expuesta expandida es resultado de la incorporación de las API comunes de .NET Framework y Xamarin en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fd283-162">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="fd283-163">Las bibliotecas de clases .NET Standard 2.0 también pueden hacer referencia a bibliotecas de clases .NET Framework siempre que llamen a las API que existen en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="fd283-163">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="fd283-164">No es necesario realizar una nueva compilación de las bibliotecas .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd283-164">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="fd283-165">Si desea ver una lista de las API que se agregaron a .NET Standard desde la última versión, .NET Standard 1.6, consulte el artículo de [comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="fd283-165">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="fd283-166">Área expuesta expandida</span><span class="sxs-lookup"><span data-stu-id="fd283-166">Expanded surface area</span></span>

<span data-ttu-id="fd283-167">La cantidad total de API disponibles en .NET Core 2.0 aumentó más del doble en comparación con .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="fd283-167">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span>

<span data-ttu-id="fd283-168">Además, con el [paquete de compatibilidad de Windows](../porting/windows-compat-pack.md), la migración desde .NET Framework ahora es mucho más fácil.</span><span class="sxs-lookup"><span data-stu-id="fd283-168">And with the [Windows Compatibility Pack](../porting/windows-compat-pack.md) porting from .NET Framework has also become much simpler.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="fd283-169">Compatibilidad con las bibliotecas .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd283-169">Support for .NET Framework libraries</span></span>

<span data-ttu-id="fd283-170">El código de .NET Core puede hacer referencia a bibliotecas .NET Framework existentes, incluidos paquetes NuGet existentes.</span><span class="sxs-lookup"><span data-stu-id="fd283-170">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="fd283-171">Tenga en cuenta que las bibliotecas deben usar las API que se encuentran en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fd283-171">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="fd283-172">integración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fd283-172">Visual Studio integration</span></span>

<span data-ttu-id="fd283-173">Visual Studio 2017 versión 15.3 y, en algunos casos, Visual Studio para Mac, ofrecen varias mejoras importantes para los desarrolladores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd283-173">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="fd283-174">Redestinación de aplicaciones .NET Core y bibliotecas .NET Standard</span><span class="sxs-lookup"><span data-stu-id="fd283-174">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="fd283-175">Si el SDK de .NET Core 2.0 SDK está instalado, puede redestinar los proyectos de .NET Core 1.x a .NET Core 2.0 y las bibliotecas .NET Standard 1.x a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="fd283-175">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span>

<span data-ttu-id="fd283-176">Para redestinar el proyecto en Visual Studio, abra la pestaña **Aplicación** del cuadro de diálogo de propiedades del proyecto y cambie el valor de **plataforma de destino** a **.NET Core 2.0** o **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="fd283-176">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="fd283-177">También puede cambiarlo si hace clic con el botón derecho en el proyecto y selecciona la opción **Edit \*.csproj file** (Editar archivo .csproj).</span><span class="sxs-lookup"><span data-stu-id="fd283-177">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="fd283-178">Para más información, consulte la sección [Herramientas](#tooling) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="fd283-178">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="fd283-179">Compatibilidad con Live Unit Testing en .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-179">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="fd283-180">Cada vez que modifique el código, Live Unit Testing ejecuta automáticamente y en segundo plano cualquier prueba unitaria afectada y presenta los resultados y la cobertura de código en vivo en el entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd283-180">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="fd283-181">.NET Core 2.0 ahora admite Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="fd283-181">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="fd283-182">Anteriormente, Live Unit Testing solo estaba disponible para aplicaciones .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd283-182">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span>

<span data-ttu-id="fd283-183">Para obtener más información, consulte [Live Unit Testing con Visual Studio](/visualstudio/test/live-unit-testing) y las [preguntas más frecuentes de Live Unit Testing](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="fd283-183">For more information, see [Live Unit Testing with Visual Studio](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="fd283-184">Mejor compatibilidad con varias plataformas de destino</span><span class="sxs-lookup"><span data-stu-id="fd283-184">Better support for multiple target frameworks</span></span>

<span data-ttu-id="fd283-185">Si compila un proyecto para varias plataformas de destino, ahora puede seleccionar la plataforma de destino en el menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="fd283-185">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="fd283-186">En la figura siguiente, un proyecto llamado SCD1 tiene como destino macOS X 10.11 (`osx.10.11-x64`) de 64 bits y Windows 10/Windows Server 2016 (`win10-x64`) de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fd283-186">In the following figure, a project named SCD1 targets 64-bit macOS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="fd283-187">Puede seleccionar la plataforma de destino antes de seleccionar el botón del proyecto, en este caso para ejecutar una compilación de depuración.</span><span class="sxs-lookup"><span data-stu-id="fd283-187">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Captura de pantalla en la que se muestra la selección de la plataforma de destino al crear un proyecto.](./media/dotnet-core-2-0/target-framework-selection.png)

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="fd283-189">Compatibilidad en paralelo con SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fd283-189">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="fd283-190">Ahora es posible instalar el SDK de .NET Core de manera independiente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd283-190">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="fd283-191">Esto permite que una versión única de Visual Studio compile proyectos que tienen como destino distintas versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd283-191">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="fd283-192">Anteriormente, Visual Studio y el SDK de .NET Core estaban estrechamente relacionados; una versión específica del SDK acompañaba a una versión específica de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd283-192">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="fd283-193">Mejoras en la documentación</span><span class="sxs-lookup"><span data-stu-id="fd283-193">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="fd283-194">Arquitectura de aplicación de .NET</span><span class="sxs-lookup"><span data-stu-id="fd283-194">.NET Application Architecture</span></span>

<span data-ttu-id="fd283-195">[Arquitectura de aplicación de .NET](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) le permite acceder a un conjunto de libros electrónicos que ofrecen orientación, procedimientos recomendados y aplicaciones de ejemplo cuando use .NET para compilar:</span><span class="sxs-lookup"><span data-stu-id="fd283-195">[.NET Application Architecture](https://dotnet.microsoft.com/learn/dotnet/architecture-guides) gives you access to a set of e-books that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- [<span data-ttu-id="fd283-196">Microservicios y contenedores Docker</span><span class="sxs-lookup"><span data-stu-id="fd283-196">Microservices and Docker containers</span></span>](../../architecture/microservices/index.md)
- [<span data-ttu-id="fd283-197">Aplicaciones web con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fd283-197">Web applications with ASP.NET</span></span>](../../architecture/modern-web-apps-azure/index.md)
- [<span data-ttu-id="fd283-198">Aplicaciones móviles con Xamarin</span><span class="sxs-lookup"><span data-stu-id="fd283-198">Mobile applications with Xamarin</span></span>](/xamarin/xamarin-forms/enterprise-application-patterns/index)
- [<span data-ttu-id="fd283-199">Aplicaciones que se implementan en la nube con Azure</span><span class="sxs-lookup"><span data-stu-id="fd283-199">Applications that are deployed to the Cloud with Azure</span></span>](/azure/architecture/reference-architectures/index)

## <a name="see-also"></a><span data-ttu-id="fd283-200">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd283-200">See also</span></span>

- [<span data-ttu-id="fd283-201">Novedades de ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fd283-201">What's new in ASP.NET Core 2.0</span></span>](/aspnet/core/aspnetcore-2.0)
