---
title: Compilación de .NET Core a partir del código fuente
description: Obtenga información sobre cómo compilar .NET Core y la CLI de .NET Core a partir del código fuente.
author: bleroy
ms.date: 06/28/2017
ms.openlocfilehash: fe5431667d861d830c2ec56252e6e3e2ca08a866
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740918"
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="5159a-103">Compilación de .NET Core a partir del código fuente</span><span class="sxs-lookup"><span data-stu-id="5159a-103">Build .NET Core from source</span></span>

<span data-ttu-id="5159a-104">La capacidad de compilar .NET Core a partir de su código fuente es importante en varios sentidos: facilita la portabilidad de .NET Core a nuevas plataformas, permite contribuciones y correcciones del producto y permite crear versiones personalizadas de .NET.</span><span class="sxs-lookup"><span data-stu-id="5159a-104">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="5159a-105">En este artículo, se proporcionan instrucciones para los desarrolladores que quieren compilar y distribuir sus propias versiones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5159a-105">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="5159a-106">Compilación de CLR a partir del código fuente</span><span class="sxs-lookup"><span data-stu-id="5159a-106">Build the CLR from source</span></span>

<span data-ttu-id="5159a-107">El código fuente de CLR de .NET Core puede encontrarse en el repositorio [dotnet/runtime](https://github.com/dotnet/runtime/) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="5159a-107">The source code for the .NET CoreCLR can be found in the [dotnet/runtime](https://github.com/dotnet/runtime/) repository on GitHub.</span></span>

<span data-ttu-id="5159a-108">Actualmente, la compilación depende de los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="5159a-108">The build currently depends on the following prerequisites:</span></span>

- [<span data-ttu-id="5159a-109">Git</span><span class="sxs-lookup"><span data-stu-id="5159a-109">Git</span></span>](https://git-scm.com/)
- [<span data-ttu-id="5159a-110">CMake</span><span class="sxs-lookup"><span data-stu-id="5159a-110">CMake</span></span>](https://cmake.org/)
- [<span data-ttu-id="5159a-111">Python</span><span class="sxs-lookup"><span data-stu-id="5159a-111">Python</span></span>](https://www.python.org/)
- <span data-ttu-id="5159a-112">un compilador de C++.</span><span class="sxs-lookup"><span data-stu-id="5159a-112">a C++ compiler.</span></span>

<span data-ttu-id="5159a-113">Para compilar CLR después de instalar estos requisitos previos, invoque el script de compilación (`build.cmd` en Windows, o `build.sh` en Linux y macOS) en la base del repositorio [dotnet/runtime](https://github.com/dotnet/runtime/).</span><span class="sxs-lookup"><span data-stu-id="5159a-113">After you've installed these prerequisites, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of the [dotnet/runtime](https://github.com/dotnet/runtime/) repository.</span></span>

<span data-ttu-id="5159a-114">La instalación de los componentes varía según el sistema operativo (SO).</span><span class="sxs-lookup"><span data-stu-id="5159a-114">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="5159a-115">Consulte las instrucciones de compilación de su sistema operativo específico:</span><span class="sxs-lookup"><span data-stu-id="5159a-115">See the build instructions for your specific OS:</span></span>

- [<span data-ttu-id="5159a-116">Windows</span><span class="sxs-lookup"><span data-stu-id="5159a-116">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
- [<span data-ttu-id="5159a-117">Linux</span><span class="sxs-lookup"><span data-stu-id="5159a-117">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
- [<span data-ttu-id="5159a-118">macOS</span><span class="sxs-lookup"><span data-stu-id="5159a-118">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
- [<span data-ttu-id="5159a-119">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="5159a-119">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
- [<span data-ttu-id="5159a-120">NetBSD</span><span class="sxs-lookup"><span data-stu-id="5159a-120">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="5159a-121">No hay ninguna compilación cruzada entre sistemas operativos (solo para ARM, que se basa en X64).</span><span class="sxs-lookup"><span data-stu-id="5159a-121">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="5159a-122">Debe estar en la plataforma concreta para compilar esa plataforma.</span><span class="sxs-lookup"><span data-stu-id="5159a-122">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="5159a-123">La compilación tiene dos `buildTypes` principales:</span><span class="sxs-lookup"><span data-stu-id="5159a-123">The build has two main `buildTypes`:</span></span>

- <span data-ttu-id="5159a-124">Debug (valor predeterminado): compila el tiempo de ejecución con las optimizaciones mínimas y las comprobaciones (aserciones) en tiempo de ejecución adicionales.</span><span class="sxs-lookup"><span data-stu-id="5159a-124">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="5159a-125">Aunque esta reducción en el nivel de optimización y las comprobaciones adicionales ralentizan la ejecución en tiempo de ejecución, resultan útiles para realizar la depuración.</span><span class="sxs-lookup"><span data-stu-id="5159a-125">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="5159a-126">Este es el valor recomendado para los entornos de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="5159a-126">This is the recommended setting for development and testing environments.</span></span>
- <span data-ttu-id="5159a-127">Release: compila el tiempo de ejecución con las optimizaciones completas y sin las comprobaciones en tiempo de ejecución adicionales.</span><span class="sxs-lookup"><span data-stu-id="5159a-127">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="5159a-128">Aunque el rendimiento en tiempo de ejecución será mucho más rápido, puede tardar un poco más en compilarse y puede resultar complicado realizar la depuración.</span><span class="sxs-lookup"><span data-stu-id="5159a-128">This will yield much faster run-time performance, but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="5159a-129">Pase `release` al script de compilación para seleccionar este tipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5159a-129">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="5159a-130">Además, de forma predeterminada, la compilación no solo crea los archivos ejecutables en tiempo de ejecución, sino que también compila todas las pruebas.</span><span class="sxs-lookup"><span data-stu-id="5159a-130">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="5159a-131">Hay bastantes pruebas, lo que exige una cantidad considerable de tiempo que no es necesario si tan solo se quiere experimentar con los cambios.</span><span class="sxs-lookup"><span data-stu-id="5159a-131">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="5159a-132">Para omitir las compilaciones de pruebas, agregue el argumento `skiptests` al script de compilación, como en el ejemplo siguiente (reemplace `.\build` con `./build.sh` en los equipos Unix):</span><span class="sxs-lookup"><span data-stu-id="5159a-132">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests
```

<span data-ttu-id="5159a-133">En el ejemplo anterior, se ha mostrado cómo compilar el tipo `Debug`, que tiene las comprobaciones (aserciones) en tiempo de desarrollo habilitadas y las optimizaciones deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="5159a-133">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="5159a-134">Para compilar el tipo de versión (velocidad máxima), haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5159a-134">To build the release (full speed) flavor, do the following:</span></span>

```bat
    .\build release skiptests
```

<span data-ttu-id="5159a-135">Puede encontrar más opciones de compilación con build si usa el calificador -?</span><span class="sxs-lookup"><span data-stu-id="5159a-135">You can find more build options with build by using the -?</span></span> <span data-ttu-id="5159a-136">o -help.</span><span class="sxs-lookup"><span data-stu-id="5159a-136">or -help qualifier.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="5159a-137">Usar la compilación</span><span class="sxs-lookup"><span data-stu-id="5159a-137">Using Your Build</span></span>

<span data-ttu-id="5159a-138">La compilación coloca todos los archivos generados en el directorio `bin` en la base del repositorio.</span><span class="sxs-lookup"><span data-stu-id="5159a-138">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="5159a-139">Hay un directorio *bin\Log* que contiene archivos de registro generados durante la compilación (más útil cuando se produce un error en la compilación).</span><span class="sxs-lookup"><span data-stu-id="5159a-139">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="5159a-140">La salida real se coloca en un directorio *bin\Producto\[plataforma].[arquitectura de CPU].[tipo de compilación]* , como *bin\Producto\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="5159a-140">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="5159a-141">Aunque el resultado de la compilación "sin procesar" a veces resulta útil, normalmente solo interesan los paquetes de NuGet, que se colocan en el subdirectorio `.nuget\pkg` del directorio de salida anterior.</span><span class="sxs-lookup"><span data-stu-id="5159a-141">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="5159a-142">Hay dos técnicas básicas para usar el nuevo tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="5159a-142">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="5159a-143">**Use dotnet.exe y NuGet para crear una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="5159a-143">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="5159a-144">Vea [Usar la compilación](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) para obtener instrucciones sobre cómo crear un programa que use el nuevo tiempo de ejecución mediante paquetes de NuGet que acaba de crear y la interfaz de la línea de comandos (CLI) de "dotnet".</span><span class="sxs-lookup"><span data-stu-id="5159a-144">See [Using Your Build](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-your-build.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="5159a-145">Esta técnica es la forma probable en que los desarrolladores que no usan el tiempo de ejecución van a consumir el nuevo tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5159a-145">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>

 2. <span data-ttu-id="5159a-146">**Use corerun.exe para ejecutar una aplicación con archivos DLL sin empaquetar**.</span><span class="sxs-lookup"><span data-stu-id="5159a-146">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="5159a-147">Este repositorio también define un host simple denominado corerun.exe que NO tiene ninguna dependencia en NuGet.</span><span class="sxs-lookup"><span data-stu-id="5159a-147">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="5159a-148">Debe indicar al host de dónde obtiene los archivos DLL necesarios que usa y tiene que recopilarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="5159a-148">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="5159a-149">Esta técnica se usa en todas las pruebas del repositorio [dotnet/runtime](https://github.com/dotnet/runtime), y es útil para el bucle local rápido "editar-compilar-depurar", como en el caso de las pruebas unitarias preliminares.</span><span class="sxs-lookup"><span data-stu-id="5159a-149">This technique is used by all the tests in the [dotnet/runtime](https://github.com/dotnet/runtime) repo, and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="5159a-150">Vea [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md) (Ejecutar aplicaciones de .NET Core con CoreRun.exe) para obtener más información sobre el uso de esta técnica.</span><span class="sxs-lookup"><span data-stu-id="5159a-150">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/runtime/blob/master/docs/workflow/testing/using-corerun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="5159a-151">Compilar la CLI a partir del código fuente</span><span class="sxs-lookup"><span data-stu-id="5159a-151">Build the CLI from source</span></span>

<span data-ttu-id="5159a-152">El código fuente de la CLI de .NET Core puede encontrarse en el repositorio [dotnet/cli](https://github.com/dotnet/cli/) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="5159a-152">The source code for the .NET Core CLI can be found in the [dotnet/cli](https://github.com/dotnet/cli/) repository on GitHub.</span></span>

<span data-ttu-id="5159a-153">Para compilar la CLI de .NET Core, necesita tener lo siguiente instalado en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5159a-153">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

- <span data-ttu-id="5159a-154">Windows y Linux:</span><span class="sxs-lookup"><span data-stu-id="5159a-154">Windows & Linux:</span></span>
  - <span data-ttu-id="5159a-155">GIT en la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5159a-155">git on the PATH</span></span>
- <span data-ttu-id="5159a-156">macOS:</span><span class="sxs-lookup"><span data-stu-id="5159a-156">macOS:</span></span>
  - <span data-ttu-id="5159a-157">GIT en la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5159a-157">git on the PATH</span></span>
  - <span data-ttu-id="5159a-158">Xcode</span><span class="sxs-lookup"><span data-stu-id="5159a-158">Xcode</span></span>
  - <span data-ttu-id="5159a-159">OpenSSL</span><span class="sxs-lookup"><span data-stu-id="5159a-159">OpenSSL</span></span>

<span data-ttu-id="5159a-160">Para compilar, ejecute `build.cmd` en Windows, o `build.sh` en Linux y macOS desde la raíz.</span><span class="sxs-lookup"><span data-stu-id="5159a-160">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="5159a-161">Si no quiere ejecutar pruebas, ejecute `build.cmd -t:Compile` o `./build.sh -t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="5159a-161">If you don't want to execute tests, run `build.cmd -t:Compile` or `./build.sh -t:Compile`.</span></span> <span data-ttu-id="5159a-162">Para compilar la CLI en macOS Sierra, debe ejecutar `export DOTNET_RUNTIME_ID=osx.10.11-x64` para establecer la variable de entorno DOTNET_RUNTIME_ID.</span><span class="sxs-lookup"><span data-stu-id="5159a-162">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="5159a-163">Usar la compilación</span><span class="sxs-lookup"><span data-stu-id="5159a-163">Using your build</span></span>

<span data-ttu-id="5159a-164">Use el ejecutable `dotnet` de *artifacts/{os}-{arch}/stage2* para probar la CLI que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5159a-164">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="5159a-165">Si quiere usar la salida de compilación al invocar a `dotnet` desde la consola actual, también puede agregar *artifacts/{os}-{arch}/stage2* a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5159a-165">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="5159a-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="5159a-166">See also</span></span>

- [<span data-ttu-id="5159a-167">Entorno de ejecución .NET</span><span class="sxs-lookup"><span data-stu-id="5159a-167">.NET Runtime</span></span>](https://github.com/dotnet/runtime/blob/master/README.md)
- <span data-ttu-id="5159a-168">[.NET Core CLI Developer Guide](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md) (Guía para desarrolladores de la CLI de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="5159a-168">[.NET Core CLI Developer Guide](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)</span></span>
- [<span data-ttu-id="5159a-169">Empaquetado de distribución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5159a-169">.NET Core distribution packaging</span></span>](./distribution-packaging.md)
