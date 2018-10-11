---
title: Uso de .NET Core SDK y herramientas de integración continua (CI)
description: Información sobre el uso del SDK de .NET Core y sus herramientas en el servidor de compilación.
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.openlocfilehash: 207a6740f2a483d532c194b2bf8112898e9c3463
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2018
ms.locfileid: "47233250"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="637e1-103">Uso de .NET Core SDK y herramientas de integración continua (CI)</span><span class="sxs-lookup"><span data-stu-id="637e1-103">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

## <a name="overview"></a><span data-ttu-id="637e1-104">Información general</span><span class="sxs-lookup"><span data-stu-id="637e1-104">Overview</span></span>

<span data-ttu-id="637e1-105">En este documento se describe el uso del SDK de .NET Core y sus herramientas en un servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-105">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="637e1-106">El conjunto de herramientas de .NET Core funciona tanto de forma interactiva, donde un desarrollador escribe comandos en un símbolo del sistema, como de manera automática, donde un servidor de integración continua (CI) ejecuta un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-106">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="637e1-107">Los comandos, las opciones, las entradas y las salidas son los mismos, y solo lo que el usuario especifica sirve para adquirir las herramientas y un sistema para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="637e1-107">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="637e1-108">Este documento se centra en escenarios de adquisición de herramientas de integración continua, donde además se ofrecen recomendaciones sobre cómo diseñar y estructurar los scripts de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-108">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="637e1-109">Opciones de instalación para los servidores de compilación de CI</span><span class="sxs-lookup"><span data-stu-id="637e1-109">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="637e1-110">Uso de instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="637e1-110">Using the native installers</span></span>

<span data-ttu-id="637e1-111">Los instaladores nativos están disponibles para macOS, Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="637e1-111">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="637e1-112">Los instaladores requieren acceso de administrador (sudo) para el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-112">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="637e1-113">El instalador nativo ofrece la ventaja de que instala todas las dependencias nativas necesarias para la ejecución de las herramientas.</span><span class="sxs-lookup"><span data-stu-id="637e1-113">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="637e1-114">Además, los instaladores nativos instalan el SDK en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="637e1-114">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="637e1-115">Los usuarios de macOS deben usar los instaladores PKG.</span><span class="sxs-lookup"><span data-stu-id="637e1-115">macOS users should use the PKG installers.</span></span> <span data-ttu-id="637e1-116">En Linux, se ofrece la posibilidad de usar un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS, o de usar los mismos paquetes (DEB o RPM).</span><span class="sxs-lookup"><span data-stu-id="637e1-116">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="637e1-117">En Windows, utilice el instalador MSI.</span><span class="sxs-lookup"><span data-stu-id="637e1-117">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="637e1-118">Los últimos archivos binarios estables se encuentran en [Get Started with .NET Core](https://aka.ms/dotnetcoregs) (Introducción a .NET Core).</span><span class="sxs-lookup"><span data-stu-id="637e1-118">The latest stable binaries are found at [Get Started with .NET Core](https://aka.ms/dotnetcoregs).</span></span> <span data-ttu-id="637e1-119">Si desea utilizar las herramientas de la última versión preliminar, que posiblemente sean inestables, use los vínculos proporcionados en el [repositorio de GitHub sobre la CLI de dotnet](https://github.com/dotnet/cli#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="637e1-119">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/cli GitHub repository](https://github.com/dotnet/cli#installers-and-binaries).</span></span> <span data-ttu-id="637e1-120">Para las distribuciones de Linux, se encuentran disponibles los archivos `tar.gz` (conocidos también como `tarballs`); use los scripts de instalación dentro de los archivos para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="637e1-120">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="637e1-121">Uso del script del instalador</span><span class="sxs-lookup"><span data-stu-id="637e1-121">Using the installer script</span></span>

<span data-ttu-id="637e1-122">El uso del script del instalador permite la instalación sin derechos administrativos en el servidor de compilación y una sencilla automatización para obtener las herramientas.</span><span class="sxs-lookup"><span data-stu-id="637e1-122">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="637e1-123">El script se encarga de descargar las herramientas y extraerlas en una ubicación predeterminada o especificada para su uso.</span><span class="sxs-lookup"><span data-stu-id="637e1-123">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="637e1-124">También puede especificar la versión de las herramientas que desea instalar y si prefiere instalar el SDK completo o solo el runtime compartido.</span><span class="sxs-lookup"><span data-stu-id="637e1-124">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="637e1-125">El script del instalador se puede automatizar para que se ejecute al principio de la compilación, a fin de obtener e instalar la versión deseada del SDK.</span><span class="sxs-lookup"><span data-stu-id="637e1-125">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="637e1-126">La *versión deseada* se corresponde con cualquier versión del SKD que los proyectos necesitan para la compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-126">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="637e1-127">El script permite instalar el SDK en un directorio local del servidor, ejecutar las herramientas desde la ubicación de instalación y limpiar después de la compilación, o bien dejar que el servicio de CI realice dicha limpieza.</span><span class="sxs-lookup"><span data-stu-id="637e1-127">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="637e1-128">Esto permite encapsular y aislar todo el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-128">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="637e1-129">La referencia del script de instalación se encuentra en el tema [dotnet-install](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="637e1-129">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="637e1-130">**Azure DevOps Services**</span><span class="sxs-lookup"><span data-stu-id="637e1-130">**Azure DevOps Services**</span></span>
>
> <span data-ttu-id="637e1-131">Cuando se utiliza el script del instalador, las dependencias nativas no se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="637e1-131">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="637e1-132">Debe instalarlas en caso de el sistema operativo no las incluya.</span><span class="sxs-lookup"><span data-stu-id="637e1-132">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="637e1-133">Vea la lista de requisitos previos en el tema [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) (Requisitos previos nativos de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="637e1-133">See the list of prerequisites in the [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) topic.</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="637e1-134">Ejemplos de configuración de CI</span><span class="sxs-lookup"><span data-stu-id="637e1-134">CI setup examples</span></span>

<span data-ttu-id="637e1-135">En esta sección se explica un procedimiento de instalación manual con un script de PowerShell o de Bash, además de incluir una descripción de varias soluciones de CI de software como servicio (SaaS).</span><span class="sxs-lookup"><span data-stu-id="637e1-135">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="637e1-136">Las soluciones de CI de SaaS tratadas son [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [ Build](https://docs.microsoft.com/azure/devops/build-release/index).</span><span class="sxs-lookup"><span data-stu-id="637e1-136">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [ Build](https://docs.microsoft.com/azure/devops/build-release/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="637e1-137">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="637e1-137">Manual setup</span></span>

<span data-ttu-id="637e1-138">Cada servicio de SaaS tiene sus propios métodos para crear y configurar un proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-138">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="637e1-139">Si usa una solución de SaaS distinta a las que indican o necesita realizar alguna personalización aparte de la compatibilidad preconfigurada, debe realizar al menos alguna configuración manual.</span><span class="sxs-lookup"><span data-stu-id="637e1-139">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="637e1-140">En general, para realizar una instalación manual, es necesario que adquiera una versión de las herramientas o las últimas compilaciones nocturnas de las herramientas y que, después, ejecute el script de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-140">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="637e1-141">Puede usar un script de PowerShell o de Bash para orquestar los comandos de .NET Core o utilizar un archivo del proyecto en el que se describa el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-141">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="637e1-142">En la [sección de orquestación](#orchestrating-the-build) se ofrece más información sobre estas opciones.</span><span class="sxs-lookup"><span data-stu-id="637e1-142">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="637e1-143">Después de crear un script que realiza una instalación manual del servidor de compilación de CI, úselo en el equipo de desarrollo para compilar el código de forma local con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="637e1-143">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="637e1-144">Cuando confirme que el script se ejecuta de forma correcta en el entorno local, impleméntelo en el servidor de compilación de CI.</span><span class="sxs-lookup"><span data-stu-id="637e1-144">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="637e1-145">Un script de PowerShell relativamente sencillo demuestra cómo obtener el SDK de NET Core e instalarlo en un servidor de compilación de Windows:</span><span class="sxs-lookup"><span data-stu-id="637e1-145">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="637e1-146">Debe proporcionar la implementación para el proceso de compilación al final del script.</span><span class="sxs-lookup"><span data-stu-id="637e1-146">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="637e1-147">El script adquiere las herramientas y, después, ejecuta el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-147">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="637e1-148">En los equipos UNIX, el siguiente script de Bash realiza las acciones descritas en el script de PowerShell de forma similar:</span><span class="sxs-lookup"><span data-stu-id="637e1-148">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="637e1-149">Travis CI</span><span class="sxs-lookup"><span data-stu-id="637e1-149">Travis CI</span></span>

<span data-ttu-id="637e1-150">Puede configurar [Travis CI](https://travis-ci.org/) para instalar el SDK de .NET Core con el lenguaje `csharp` y la clave `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="637e1-150">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="637e1-151">Vea los documentos oficiales de Travis CI en [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilación de un proyecto de C#, F# o Visual Basic) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="637e1-151">See the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) for more information.</span></span> <span data-ttu-id="637e1-152">Al acceder a la información de Travis CI, observará que el identificador de lenguaje `language: csharp` de cuyo mantenimiento se encarga la comunidad funciona con todos los lenguajes de .NET, incluidos F# y Mono.</span><span class="sxs-lookup"><span data-stu-id="637e1-152">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="637e1-153">Travis CI se ejecuta tanto en trabajos de macOS (OS X 10.11, OS X 10.12) como de Linux (Ubuntu 14.04) en una *matriz de compilación*, donde debe especificar una combinación de runtime, entorno y exclusiones/inclusiones para aceptar las combinaciones de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="637e1-153">Travis CI runs both macOS (OS X 10.11, OS X 10.12) and Linux (Ubuntu 14.04) jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="637e1-154">Vea el archivo de [ejemplo .travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml) y [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalización de la compilación) en los documentos de Travis CI para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="637e1-154">See the [.travis.yml example](https://github.com/dotnet/docs/blob/master/.travis.yml) file and [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) in the Travis CI docs for more information.</span></span> <span data-ttu-id="637e1-155">Las herramientas basadas en MSBuild incluyen los runtimes LTS (1.0.x) y Current (1.1.x) en el paquete; por tanto, cuando instala el SDK, recibe todo lo que necesita para la compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-155">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="637e1-156">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="637e1-156">AppVeyor</span></span>

<span data-ttu-id="637e1-157">[AppVeyor](https://www.appveyor.com/) instala el SDK de .NET Core 1.0.1 con la imagen de trabajo de compilación de `Visual Studio 2017`.</span><span class="sxs-lookup"><span data-stu-id="637e1-157">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="637e1-158">Se encuentran disponibles otras imágenes de compilación con diferentes versiones del SDK de .NET Core; vea el [ejemplo de appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) y el tema [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Imágenes de trabajo de compilación) de los documentos de AppVeyor para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="637e1-158">Other build images with different versions of the .NET Core SDK are available; see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) topic in the AppVeyor docs for more information.</span></span>

<span data-ttu-id="637e1-159">Los archivos binarios del SDK de .NET Core se descargan y descomprimen en un subdirectorio con la utilización del script de instalación y, después, se agregan a la variable de entorno `PATH`.</span><span class="sxs-lookup"><span data-stu-id="637e1-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="637e1-160">Agregue una matriz de compilación para ejecutar las pruebas de integración con varias versiones del SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="637e1-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a><span data-ttu-id="637e1-161">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="637e1-161">Azure DevOps Services</span></span>

<span data-ttu-id="637e1-162">Configure Azure DevOps Services para compilar proyectos de .NET Core con alguno de estos enfoques:</span><span class="sxs-lookup"><span data-stu-id="637e1-162">Configure Azure DevOps Services to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="637e1-163">Ejecute el script del [paso de instalación manual](#manual-setup) con sus comandos.</span><span class="sxs-lookup"><span data-stu-id="637e1-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="637e1-164">Cree una compilación compuesta de varias tareas de compilación integradas en Azure DevOps Services que están configuradas para usar herramientas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="637e1-164">Create a build composed of several Azure DevOps Services built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="637e1-165">Ambas soluciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="637e1-165">Both solutions are valid.</span></span> <span data-ttu-id="637e1-166">Con la utilización de un script de instalación manual, puede controlar la versión de las herramientas que recibe, ya que las descarga como parte de la compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="637e1-167">La compilación se ejecuta desde un script que debe crear.</span><span class="sxs-lookup"><span data-stu-id="637e1-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="637e1-168">En este tema solo se trata la opción manual.</span><span class="sxs-lookup"><span data-stu-id="637e1-168">This topic only covers the manual option.</span></span> <span data-ttu-id="637e1-169">Para obtener más información sobre la composición de una compilación con tareas de compilación de Azure DevOps Services, consulte el tema de [implementación e integración continuas](https://docs.microsoft.com/azure/devops/build-release/index) de Azure DevOps Services.</span><span class="sxs-lookup"><span data-stu-id="637e1-169">For more information on composing a build with Azure DevOps Services build tasks, visit the Azure DevOps Services [Continuous integration and deployment](https://docs.microsoft.com/azure/devops/build-release/index) topic.</span></span>

<span data-ttu-id="637e1-170">Para usar un script de instalación manual en Azure DevOps Services, cree una definición de compilación y especifique el script que va a ejecutar para el paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-170">To use a manual setup script in Azure DevOps Services, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="637e1-171">Esto se realiza en la interfaz de usuario de Azure DevOps Services:</span><span class="sxs-lookup"><span data-stu-id="637e1-171">This is accomplished using the Azure DevOps Services user interface:</span></span>

1. <span data-ttu-id="637e1-172">Empiece por crear una definición de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-172">Start by creating a new build definition.</span></span> <span data-ttu-id="637e1-173">Cuando llegue a la pantalla en la que se ofrece la opción de definir el tipo de compilación que desea crear, seleccione la opción **Vacío**.</span><span class="sxs-lookup"><span data-stu-id="637e1-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![Selección de una definición de compilación vacía](./media/using-ci-with-cli/screen1.png)

1. <span data-ttu-id="637e1-175">Después de configurar el repositorio que va a compilar, se le remite a las definiciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="637e1-176">Seleccione **Agregar paso de compilación**:</span><span class="sxs-lookup"><span data-stu-id="637e1-176">Select **Add build step**:</span></span>

   ![Agregar un paso de compilación](./media/using-ci-with-cli/screen2.png)

1. <span data-ttu-id="637e1-178">Se abre el **Catálogo de tareas**.</span><span class="sxs-lookup"><span data-stu-id="637e1-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="637e1-179">El catálogo contiene tareas que se utilizan en la compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="637e1-180">Como ya tiene un script, seleccione el botón **Agregar** en **PowerShell: Ejecute un script de PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="637e1-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![Paso para agregar un script de PowerShell](./media/using-ci-with-cli/screen3.png)

1. <span data-ttu-id="637e1-182">Configure el paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="637e1-182">Configure the build step.</span></span> <span data-ttu-id="637e1-183">Agregue el script desde el repositorio que se va a compilar:</span><span class="sxs-lookup"><span data-stu-id="637e1-183">Add the script from the repository that you're building:</span></span>

   ![Especificar el script de PowerShell que va a ejecutar](./media/using-ci-with-cli/screen4.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="637e1-185">Orquestación de la compilación</span><span class="sxs-lookup"><span data-stu-id="637e1-185">Orchestrating the build</span></span>

<span data-ttu-id="637e1-186">En la mayor parte de este documento se describe cómo adquirir las herramientas de .NET Core y configurar varios servicios de CI sin ofrecer información sobre cómo orquestar o *compilar realmente* el código con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="637e1-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="637e1-187">Las opciones para estructurar el proceso de compilación dependen de muchos factores que no se pueden tratar aquí en términos generales.</span><span class="sxs-lookup"><span data-stu-id="637e1-187">The choices on how to structure the build process depend on many factors that cannot be covered in a general way here.</span></span> <span data-ttu-id="637e1-188">Explore los recursos y ejemplos proporcionados en las series de documentos de [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/index) para obtener más información sobre cómo orquestar las compilaciones con cada tecnología.</span><span class="sxs-lookup"><span data-stu-id="637e1-188">Explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/index) for more information on orchestrating your builds with each technology.</span></span>

<span data-ttu-id="637e1-189">Dos enfoques generales que se aplican para estructurar el proceso de compilación del código de .NET Core con herramientas de .NET Core consisten en utilizar directamente MSBuild o en usar los comandos de la línea de comandos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="637e1-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="637e1-190">El enfoque que debe adoptar depende de lo cómo que se sienta con cada uno de ellos y de los inconvenientes que presente su complejidad.</span><span class="sxs-lookup"><span data-stu-id="637e1-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="637e1-191">MSBuild ofrece la posibilidad de expresar el proceso de compilación como tareas y objetivos, pero presenta la complejidad añadida de tener que aprender la sintaxis del archivo de proyecto de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="637e1-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="637e1-192">Quizá sea más sencillo usar las herramientas de línea de comandos de .NET Core, pero, en este caso, es necesario escribir la lógica de orquestación en un lenguaje de scripting como `bash` o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="637e1-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="637e1-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="637e1-193">See also</span></span>

* [<span data-ttu-id="637e1-194">Pasos de adquisición de Ubuntu</span><span class="sxs-lookup"><span data-stu-id="637e1-194">Ubuntu acquisition steps</span></span>](https://www.microsoft.com/net/core#linuxubuntu)
