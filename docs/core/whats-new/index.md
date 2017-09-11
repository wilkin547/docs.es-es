---
title: Novedades de .NET Core 2.0
description: "Obtenga información sobre las características nuevas de .NET Core."
keywords: .NET, .NET Core
author: rpetrusha
ms.author: ronpet
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: b47d4c74a01b99d743b69328c201096bc8d89794
ms.openlocfilehash: e43f72ebd26c34636c239d8ac9f749d52d3f60a0
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="whats-new-in-net-core"></a><span data-ttu-id="75ea8-104">Novedades de .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-104">What's new in .NET Core</span></span>

<span data-ttu-id="75ea8-105">.NET Core 2.0 incluye mejoras y características nuevas en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="75ea8-105">.NET Core 2.0 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="75ea8-106">Herramientas</span><span class="sxs-lookup"><span data-stu-id="75ea8-106">Tooling</span></span>](#tooling)
- [<span data-ttu-id="75ea8-107">Compatibilidad con lenguajes</span><span class="sxs-lookup"><span data-stu-id="75ea8-107">Language support</span></span>](#language-support)
- [<span data-ttu-id="75ea8-108">Mejoras en la plataforma</span><span class="sxs-lookup"><span data-stu-id="75ea8-108">Platform improvements</span></span>](#platform-improvements)
- [<span data-ttu-id="75ea8-109">Cambios en la API</span><span class="sxs-lookup"><span data-stu-id="75ea8-109">API changes</span></span>](#api-changes-and-library-support)
- [<span data-ttu-id="75ea8-110">Integración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75ea8-110">Visual Studio integration</span></span>](#visual-studio-integration)
- [<span data-ttu-id="75ea8-111">Mejoras en la documentación</span><span class="sxs-lookup"><span data-stu-id="75ea8-111">Documentation improvements</span></span>](#documentation-improvements) 

## <a name="tooling"></a><span data-ttu-id="75ea8-112">Tooling</span><span class="sxs-lookup"><span data-stu-id="75ea8-112">Tooling</span></span>

### <a name="dotnet-restore-runs-implicitly"></a><span data-ttu-id="75ea8-113">dotnet restore se ejecuta de manera implícita</span><span class="sxs-lookup"><span data-stu-id="75ea8-113">dotnet restore runs implicitly</span></span>

<span data-ttu-id="75ea8-114">En las versiones anteriores de .NET Core, era necesario ejecutar el comando [dotnet restore](../tools/dotnet-restore.md) para descargar dependencias inmediatamente después de crear un proyecto nuevo con el comando [dotnet new](../tools/dotnet-new.md), así como también cada vez que se agregaba una dependencia nueva al proyecto.</span><span class="sxs-lookup"><span data-stu-id="75ea8-114">In previous versions of .NET Core, you had to run the [dotnet restore](../tools/dotnet-restore.md) command to download dependencies immediately after you created a new project with the [dotnet new](../tools/dotnet-new.md) command, as well as whenever you added a new dependency to your project.</span></span> <span data-ttu-id="75ea8-115">En .NET Core 2.0, `dotnet restore` se ejecuta de manera implícita cuando se ejecuta el comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="75ea8-115">In .NET Core 2.0, `dotnet restore` runs implicitly when the `dotnet new` command executes.</span></span> <span data-ttu-id="75ea8-116">También se ejecuta de manera implícita si es necesario actualizar las dependencias cuando se ejecutan otros comandos, como `run`, `build` y `publish`.</span><span class="sxs-lookup"><span data-stu-id="75ea8-116">It also runs implicitly if dependencies need to be updated when other commands, such as the `run`, `build`, and `publish` commands, execute.</span></span>

<span data-ttu-id="75ea8-117">También puede deshabilitar la invocación automática de `dotnet restore` si pasa el modificador `--no-restore` a los comandos `new`, `run`, `build`, `publish`, `pack` y `test`.</span><span class="sxs-lookup"><span data-stu-id="75ea8-117">You can also disable the automatic invocation of `dotnet restore` by passing the `--no-restore` switch to the `new`, `run`, `build`, `publish`, `pack`, and `test` commands.</span></span> 

### <a name="retargeting-to-net-core-20"></a><span data-ttu-id="75ea8-118">Redestinación a .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="75ea8-118">Retargeting to .NET Core 2.0</span></span>

<span data-ttu-id="75ea8-119">Si el SDK de .NET Core 2.0 SDK está instalado, los proyectos que tienen .NET Core 1.x como destino se pueden redestinar a .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="75ea8-119">If the .NET Core 2.0 SDK is installed, projects that target .NET Core 1.x can be retargeted to .NET Core 2.0.</span></span> 

<span data-ttu-id="75ea8-120">Para redestinar a .NET Core 2.0, edite el archivo del proyecto cambiando el valor del elemento `<TargetFramework>` (o del elemento `<TargetFrameworks>`, si tiene más de un destino en el archivo del proyecto) de 1.x a 2.0:</span><span class="sxs-lookup"><span data-stu-id="75ea8-120">To retarget to .NET Core 2.0, edit your project file by changing the value of the `<TargetFramework>` element (or the `<TargetFrameworks>` element if you have more than one target in your project file) from 1.x to 2.0:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="75ea8-121">También puede redestinar las bibliotecas de .NET Standard a .NET Standard 2.0 del mismo modo:</span><span class="sxs-lookup"><span data-stu-id="75ea8-121">You can also retarget .NET Standard libraries to .NET Standard 2.0 the same way:</span></span>

```xml
<PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
 </PropertyGroup>
```

<span data-ttu-id="75ea8-122">Para más información sobre cómo migrar el proyecto a .NET Core 2.0, consulte el artículo sobre [migración de ASP.NET Core 1.x a ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span><span class="sxs-lookup"><span data-stu-id="75ea8-122">For more information about migrating your project to .NET Core 2.0, see [Migrating from ASP.NET Core 1.x to ASP.NET Core 2.0](/aspnet/core/migration/1x-to-2x/index).</span></span>

## <a name="language-support"></a><span data-ttu-id="75ea8-123">Compatibilidad con lenguajes</span><span class="sxs-lookup"><span data-stu-id="75ea8-123">Language support</span></span>

<span data-ttu-id="75ea8-124">Además de admitir C# y F#, .NET Core 2.0 también es compatible con Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="75ea8-124">In addition to supporting C# and F#, .NET Core 2.0 also supports Visual Basic.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="75ea8-125">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ea8-125">Visual Basic</span></span>

<span data-ttu-id="75ea8-126">Con la versión 2.0, .NET Core ahora es compatible con Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="75ea8-126">With version 2.0, .NET Core now supports Visual Basic 2017.</span></span> <span data-ttu-id="75ea8-127">Puede usar Visual Basic para crear los tipos de proyecto siguientes:</span><span class="sxs-lookup"><span data-stu-id="75ea8-127">You can use Visual Basic to create the following project types:</span></span>

- <span data-ttu-id="75ea8-128">Aplicaciones de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-128">.NET Core console apps</span></span>
- <span data-ttu-id="75ea8-129">Bibliotecas de clases .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-129">.NET Core class libraries</span></span>
- <span data-ttu-id="75ea8-130">Bibliotecas de clases .NET Standard</span><span class="sxs-lookup"><span data-stu-id="75ea8-130">.NET Standard class libraries</span></span>
- <span data-ttu-id="75ea8-131">Proyectos de prueba unitaria .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-131">.NET Core unit test projects</span></span>
- <span data-ttu-id="75ea8-132">Proyectos de prueba xUnit .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-132">.NET Core xUnit test projects</span></span> 

<span data-ttu-id="75ea8-133">Por ejemplo, para crear una aplicación "Hola mundo" de Visual Basic, haga estos pasos en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="75ea8-133">For example, to create a Visual Basic "Hello World" application, do the following steps from the command line:</span></span>

1. <span data-ttu-id="75ea8-134">En una ventana de la consola, cree un directorio para el proyecto y conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="75ea8-134">Open a console window, create a directory for your project, and make it the current directory.</span></span>

1. <span data-ttu-id="75ea8-135">Escriba el comando `dotnet new console -lang vb`.</span><span class="sxs-lookup"><span data-stu-id="75ea8-135">Enter the command `dotnet new console -lang vb`.</span></span>

   <span data-ttu-id="75ea8-136">El comando crea un archivo del proyecto con una extensión de archivo `.vbproj`, además de un archivo de código fuente de Visual Basic llamado *Program.vb*.</span><span class="sxs-lookup"><span data-stu-id="75ea8-136">The command creates a project file with a `.vbproj` file extension, along with a Visual Basic source code file named *Program.vb*.</span></span> <span data-ttu-id="75ea8-137">Este archivo contiene el código fuente para escribir la cadena "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="75ea8-137">This file contains the source code to write the string "Hello World!"</span></span> <span data-ttu-id="75ea8-138">en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="75ea8-138">to the console window.</span></span>
  
1.  <span data-ttu-id="75ea8-139">Escriba el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="75ea8-139">Enter the command `dotnet run`.</span></span> <span data-ttu-id="75ea8-140">Las [herramientas de la CLI de .NET Core](../tools/index.md) compila y ejecuta automáticamente la aplicación, con lo que se muestra el mensaje "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="75ea8-140">The [.NET Core CLI tools](../tools/index.md) automatically compile and execute the application, which displays the message "Hello World!"</span></span> <span data-ttu-id="75ea8-141">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="75ea8-141">in the console window.</span></span>

### <a name="support-for-c-71"></a><span data-ttu-id="75ea8-142">Compatibilidad con C# 7.1</span><span class="sxs-lookup"><span data-stu-id="75ea8-142">Support for C# 7.1</span></span>

<span data-ttu-id="75ea8-143">.NET Core 2.0 es compatible con C# 7.1, que agrega varias características nuevas, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="75ea8-143">.NET Core 2.0 supports C# 7.1, which adds a number of new features, including:</span></span>

- <span data-ttu-id="75ea8-144">El método `Main`, el punto de entrada de la aplicación, se puede marcar con la palabra clave [async](../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="75ea8-144">The `Main` method, the application entry point, can be marked with the [async](../../csharp/language-reference/keywords/async.md) keyword.</span></span>
- <span data-ttu-id="75ea8-145">Nombres de tupla deducidos.</span><span class="sxs-lookup"><span data-stu-id="75ea8-145">Inferred tuple names.</span></span>
- <span data-ttu-id="75ea8-146">Expresiones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="75ea8-146">Default expressions.</span></span>

<!-- For more information see [link to C# what's new](url). -->

## <a name="platform-improvements"></a><span data-ttu-id="75ea8-147">Mejoras en la plataforma</span><span class="sxs-lookup"><span data-stu-id="75ea8-147">Platform improvements</span></span>

<span data-ttu-id="75ea8-148">.NET Core 2.0 incluye varias características que facilitan la instalación de .NET Core y su uso en sistemas operativos compatibles.</span><span class="sxs-lookup"><span data-stu-id="75ea8-148">.NET Core 2.0 includes a number of features that make it easier to install .NET Core and to use it on supported operating systems.</span></span>

### <a name="net-core-for-linux-is-a-single-implementation"></a><span data-ttu-id="75ea8-149">.NET Core para Linux es una sola implementación</span><span class="sxs-lookup"><span data-stu-id="75ea8-149">.NET Core for Linux is a single implementation</span></span>

<span data-ttu-id="75ea8-150">.NET Core 2.0 ofrece una sola implementación de Linux que funciona en varias distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="75ea8-150">.NET Core 2.0 offers a single Linux implementation that works on multiple Linux distributions.</span></span> <span data-ttu-id="75ea8-151">.NET Core 1.x requería que descargara una implementación de Linux específica para la distribución.</span><span class="sxs-lookup"><span data-stu-id="75ea8-151">.NET Core 1.x required that you download a distribution-specific Linux implementation.</span></span>

<span data-ttu-id="75ea8-152">También puede desarrollar aplicaciones que tienen Linux como destino como un solo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="75ea8-152">You can also develop apps that target Linux as a single operating system.</span></span> <span data-ttu-id="75ea8-153">.NET Core 1.x requería que se tuviera cada distribución de Linux como destino de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="75ea8-153">.NET Core 1.x required that you target each Linux distribution separately.</span></span> 

### <a name="support-for-the-apple-cryptographic-libraries"></a><span data-ttu-id="75ea8-154">Compatibilidad con las bibliotecas de cifrado de Apple</span><span class="sxs-lookup"><span data-stu-id="75ea8-154">Support for the Apple cryptographic libraries</span></span>

<span data-ttu-id="75ea8-155">.NET Core 1.x en macOS requería la biblioteca de cifrado del kit de herramientas OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="75ea8-155">.NET Core 1.x on macOS required the OpenSSL toolkit's cryptographic library.</span></span> <span data-ttu-id="75ea8-156">.NET Core 2.0 usa las bibliotecas de cifrado de Apple y no requiere OpenSSL, por lo que ya no es necesario instalarlo.</span><span class="sxs-lookup"><span data-stu-id="75ea8-156">.NET Core 2.0 uses the Apple cryptographic libraries and doesn't require OpenSSL, so you no longer need to install it.</span></span> 

## <a name="api-changes-and-library-support"></a><span data-ttu-id="75ea8-157">Cambios en la API y compatibilidad con bibliotecas</span><span class="sxs-lookup"><span data-stu-id="75ea8-157">API changes and library support</span></span>

### <a name="support-for-net-standard-20"></a><span data-ttu-id="75ea8-158">Compatibilidad con .NET Standard 2.0</span><span class="sxs-lookup"><span data-stu-id="75ea8-158">Support for .NET Standard 2.0</span></span>

<span data-ttu-id="75ea8-159">.NET Standard define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar.</span><span class="sxs-lookup"><span data-stu-id="75ea8-159">The .NET Standard defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="75ea8-160">.NET Standard está dirigido a los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="75ea8-160">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="75ea8-161">Pretende garantizar la funcionalidad que está disponible a una biblioteca que tiene como destino una versión de .NET Standard en cada implementación de .NET.</span><span class="sxs-lookup"><span data-stu-id="75ea8-161">It aims to guarantee the functionality that is available to a library that targets a version of the .NET Standard on each .NET implementation.</span></span> <span data-ttu-id="75ea8-162">.NET Core 1.x es compatible con la versión 1.6 de .NET Standard; .NET Core 2.0 es compatible con la versión más reciente, .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="75ea8-162">.NET Core 1.x supports the .NET Standard version 1.6; .NET Core 2.0 supports the latest version, .NET Standard 2.0.</span></span> <span data-ttu-id="75ea8-163">Para más información, consulte [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="75ea8-163">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="75ea8-164">.NET Standard 2.0 incluye más de 20 000 API más que las disponibles en .NET Standard 1.6.</span><span class="sxs-lookup"><span data-stu-id="75ea8-164">.NET Standard 2.0 includes over 20,000 more APIs than were available in the .NET Standard 1.6.</span></span> <span data-ttu-id="75ea8-165">Gran parte de esta área expuesta expandida es resultado de la incorporación de las API comunes de .NET Framework y Xamarin en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="75ea8-165">Much of this expanded surface area results from incorporating APIs that are common to the .NET Framework and Xamarin into .NET Standard.</span></span>

<span data-ttu-id="75ea8-166">Las bibliotecas de clases .NET Standard 2.0 también pueden hacer referencia a bibliotecas de clases .NET Framework siempre que llamen a las API que existen en .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="75ea8-166">.NET Standard 2.0 class libraries can also reference .NET Framework class libraries, provided that they call APIs that are present in the .NET Standard 2.0.</span></span> <span data-ttu-id="75ea8-167">No es necesario realizar una nueva compilación de las bibliotecas .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75ea8-167">No recompilation of the .NET Framework libraries is required.</span></span>

<span data-ttu-id="75ea8-168">Si desea ver una lista de las API que se agregaron a .NET Standard desde la última versión, .NET Standard 1.6, consulte el artículo de [comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span><span class="sxs-lookup"><span data-stu-id="75ea8-168">For a list of the APIs that have been added to the .NET Standard since its last version, the .NET Standard 1.6, see [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

### <a name="expanded-surface-area"></a><span data-ttu-id="75ea8-169">Área expuesta expandida</span><span class="sxs-lookup"><span data-stu-id="75ea8-169">Expanded surface area</span></span>

<span data-ttu-id="75ea8-170">La cantidad total de API disponibles en .NET Core 2.0 aumentó más del doble en comparación con .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="75ea8-170">The total number of APIs available on .NET Core 2.0 has more than doubled in comparison with .NET Core 1.1.</span></span> 

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="75ea8-171">Compatibilidad con las bibliotecas .NET Framework</span><span class="sxs-lookup"><span data-stu-id="75ea8-171">Support for .NET Framework libraries</span></span>

<span data-ttu-id="75ea8-172">El código de .NET Core puede hacer referencia a bibliotecas .NET Framework existentes, incluidos paquetes NuGet existentes.</span><span class="sxs-lookup"><span data-stu-id="75ea8-172">.NET Core code can reference existing .NET Framework libraries, including existing NuGet packages.</span></span> <span data-ttu-id="75ea8-173">Tenga en cuenta que las bibliotecas deben usar las API que se encuentran en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="75ea8-173">Note that the libraries must use APIs that are found in .NET Standard.</span></span>

## <a name="visual-studio-integration"></a><span data-ttu-id="75ea8-174">integración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75ea8-174">Visual Studio integration</span></span>

<span data-ttu-id="75ea8-175">Visual Studio 2017 versión 15.3 y, en algunos casos, Visual Studio para Mac, ofrecen varias mejoras importantes para los desarrolladores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75ea8-175">Visual Studio 2017 version 15.3 and in some cases Visual Studio for Mac offer a number of significant enhancements for .NET Core developers.</span></span>

### <a name="retargeting-net-core-apps-and-net-standard-libraries"></a><span data-ttu-id="75ea8-176">Redestinación de aplicaciones .NET Core y bibliotecas .NET Standard</span><span class="sxs-lookup"><span data-stu-id="75ea8-176">Retargeting .NET Core apps and .NET Standard libraries</span></span>

<span data-ttu-id="75ea8-177">Si el SDK de .NET Core 2.0 SDK está instalado, puede redestinar los proyectos de .NET Core 1.x a .NET Core 2.0 y las bibliotecas .NET Standard 1.x a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="75ea8-177">If the .NET Core 2.0 SDK is installed, you can retarget .NET Core 1.x projects to .NET Core 2.0 and .NET Standard 1.x libraries to .NET Standard 2.0.</span></span> 

<span data-ttu-id="75ea8-178">Para redestinar el proyecto en Visual Studio, abra la pestaña **Aplicación** del cuadro de diálogo de propiedades del proyecto y cambie el valor de **plataforma de destino** a **.NET Core 2.0** o **.NET Standard 2.0**.</span><span class="sxs-lookup"><span data-stu-id="75ea8-178">To retarget your project in Visual Studio, you open the **Application** tab of the project's properties dialog and change the **Target framework** value to **.NET Core 2.0** or **.NET Standard 2.0**.</span></span> <span data-ttu-id="75ea8-179">También puede cambiarlo si hace clic con el botón derecho en el proyecto y selecciona la opción **Edit \*.csproj file** (Editar archivo .csproj).</span><span class="sxs-lookup"><span data-stu-id="75ea8-179">You can also change it by right-clicking on the project and selecting the **Edit \*.csproj file** option.</span></span> <span data-ttu-id="75ea8-180">Para más información, consulte la sección [Herramientas](#tooling) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="75ea8-180">For more information, see the [Tooling](#tooling) section earlier in this topic.</span></span>

### <a name="live-unit-testing-support-for-net-core"></a><span data-ttu-id="75ea8-181">Compatibilidad con Live Unit Testing en .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-181">Live Unit Testing support for .NET Core</span></span>

<span data-ttu-id="75ea8-182">Cada vez que modifique el código, Live Unit Testing ejecuta automáticamente y en segundo plano cualquier prueba unitaria afectada y presenta los resultados y la cobertura de código en vivo en el entorno de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75ea8-182">Whenever you modify your code, Live Unit Testing automatically runs any affected unit tests in the background and displays the results and code coverage live in the Visual Studio environment.</span></span> <span data-ttu-id="75ea8-183">.NET Core 2.0 ahora admite Live Unit Testing.</span><span class="sxs-lookup"><span data-stu-id="75ea8-183">.NET Core 2.0 now supports Live Unit Testing.</span></span> <span data-ttu-id="75ea8-184">Anteriormente, Live Unit Testing solo estaba disponible para aplicaciones .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75ea8-184">Previously, Live Unit Testing was available only for .NET Framework applications.</span></span> 

<span data-ttu-id="75ea8-185">Para más información, consulte [Live Unit Testing con Visual Studio 2017](/visualstudio/test/live-unit-testing) y las [Preguntas más frecuentes de Live Unit Testing](/visualstudio/test/live-unit-testing-faq).</span><span class="sxs-lookup"><span data-stu-id="75ea8-185">For more information, see [Live Unit Testing with Visual Studio 2017](/visualstudio/test/live-unit-testing) and the [Live Unit Testing FAQ](/visualstudio/test/live-unit-testing-faq).</span></span>

### <a name="better-support-for-multiple-target-frameworks"></a><span data-ttu-id="75ea8-186">Mejor compatibilidad con varias plataformas de destino</span><span class="sxs-lookup"><span data-stu-id="75ea8-186">Better support for multiple target frameworks</span></span>

<span data-ttu-id="75ea8-187">Si compila un proyecto para varias plataformas de destino, ahora puede seleccionar la plataforma de destino en el menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="75ea8-187">If you're building a project for multiple target frameworks, you can now select the target platform from the top-level menu.</span></span> <span data-ttu-id="75ea8-188">En la figura siguiente, un proyecto llamado SCD1 tiene como destino Mac OS X 10.11 (`osx.10.11-x64`) de 64 bits y Windows 10/Windows Server 2016 (`win10-x64`) de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="75ea8-188">In the following figure, a project named SCD1 targets 64-bit Mac OS X 10.11 (`osx.10.11-x64`) and 64-bit Windows 10/Windows Server 2016 (`win10-x64`).</span></span> <span data-ttu-id="75ea8-189">Puede seleccionar la plataforma de destino antes de seleccionar el botón del proyecto, en este caso para ejecutar una compilación de depuración.</span><span class="sxs-lookup"><span data-stu-id="75ea8-189">You can select the target framework before selecting the project button, in this case to run a debug build.</span></span>

![Selección de la plataforma de destino al compilar un proyecto](media/multitarget.png) 

### <a name="side-by-side-support-for-net-core-sdks"></a><span data-ttu-id="75ea8-191">Compatibilidad en paralelo con SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="75ea8-191">Side-by-side support for .NET Core SDKs</span></span>

<span data-ttu-id="75ea8-192">Ahora es posible instalar el SDK de .NET Core de manera independiente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75ea8-192">You can now install the .NET Core SDK independently of Visual Studio.</span></span> <span data-ttu-id="75ea8-193">Esto permite que una versión única de Visual Studio compile proyectos que tienen como destino distintas versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75ea8-193">This makes it possible for a single version of Visual Studio to build projects that target different versions of .NET Core.</span></span> <span data-ttu-id="75ea8-194">Anteriormente, Visual Studio y el SDK de .NET Core estaban estrechamente relacionados; una versión específica del SDK acompañaba a una versión específica de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75ea8-194">Previously, Visual Studio and the .NET Core SDK were tightly coupled; a particular version of the SDK accompanied a particular version of Visual Studio.</span></span>

## <a name="documentation-improvements"></a><span data-ttu-id="75ea8-195">Mejoras en la documentación</span><span class="sxs-lookup"><span data-stu-id="75ea8-195">Documentation improvements</span></span>

### <a name="net-application-architecture"></a><span data-ttu-id="75ea8-196">Arquitectura de aplicación de .NET</span><span class="sxs-lookup"><span data-stu-id="75ea8-196">.NET Application Architecture</span></span>

<span data-ttu-id="75ea8-197">[Arquitectura de aplicación de .NET](https://www.microsoft.com/net/learn/architecture) le permite acceder a un conjunto de libros electrónicos que brindan guía, procedimientos recomendados y aplicaciones de ejemplo cuando use .NET para compilar:</span><span class="sxs-lookup"><span data-stu-id="75ea8-197">[.NET Application Architecture](https://www.microsoft.com/net/learn/architecture) gives you access to a set of eBooks that provide guidance, best practices, and sample applications when using .NET to build:</span></span>

- <span data-ttu-id="75ea8-198">Microservicios y contenedores Docker.</span><span class="sxs-lookup"><span data-stu-id="75ea8-198">Microservices and Docker containers.</span></span>
- <span data-ttu-id="75ea8-199">Aplicaciones web con ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="75ea8-199">Web applications with ASP.NET.</span></span>
- <span data-ttu-id="75ea8-200">Aplicaciones móviles con Xamarin.</span><span class="sxs-lookup"><span data-stu-id="75ea8-200">Mobile applications with Xamarin.</span></span>
- <span data-ttu-id="75ea8-201">Aplicaciones que se implementan en la nube con Azure.</span><span class="sxs-lookup"><span data-stu-id="75ea8-201">Applications that are deployed to the Cloud with Azure.</span></span>

## <a name="see-also"></a><span data-ttu-id="75ea8-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="75ea8-202">See also</span></span>
 [<span data-ttu-id="75ea8-203">Novedades de ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="75ea8-203">What's new in ASP.NET Core 2.0</span></span>](/aspnet/core/aspnetcore-2.0)

