---
title: Integración continua (CI) con el SDK de .NET Core y herramientas
description: Aprenda a usar el SDK de .NET Core y sus herramientas en el servidor de compilación con la integración continua.
ms.date: 05/18/2017
ms.openlocfilehash: 724cc639a2588b085b31ff4590acce34d2380655
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537722"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="36069-103">Uso de .NET Core SDK y herramientas de integración continua (CI)</span><span class="sxs-lookup"><span data-stu-id="36069-103">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

<span data-ttu-id="36069-104">En este documento se describe el uso del SDK de .NET Core y sus herramientas en un servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-104">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="36069-105">El conjunto de herramientas de .NET Core funciona tanto de forma interactiva, donde un desarrollador escribe comandos en un símbolo del sistema, como de manera automática, donde un servidor de integración continua (CI) ejecuta un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-105">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="36069-106">Los comandos, las opciones, las entradas y las salidas son los mismos, y solo lo que el usuario especifica sirve para adquirir las herramientas y un sistema para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36069-106">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="36069-107">Este documento se centra en escenarios de adquisición de herramientas de integración continua, donde además se ofrecen recomendaciones sobre cómo diseñar y estructurar los scripts de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-107">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="36069-108">Opciones de instalación para los servidores de compilación de CI</span><span class="sxs-lookup"><span data-stu-id="36069-108">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="36069-109">Uso de instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="36069-109">Using the native installers</span></span>

<span data-ttu-id="36069-110">Los instaladores nativos están disponibles para macOS, Linux y Windows.</span><span class="sxs-lookup"><span data-stu-id="36069-110">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="36069-111">Los instaladores requieren acceso de administrador (sudo) para el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-111">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="36069-112">El instalador nativo ofrece la ventaja de que instala todas las dependencias nativas necesarias para la ejecución de las herramientas.</span><span class="sxs-lookup"><span data-stu-id="36069-112">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="36069-113">Además, los instaladores nativos instalan el SDK en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="36069-113">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="36069-114">Los usuarios de macOS deben usar los instaladores PKG.</span><span class="sxs-lookup"><span data-stu-id="36069-114">macOS users should use the PKG installers.</span></span> <span data-ttu-id="36069-115">En Linux, se ofrece la posibilidad de usar un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS, o de usar los mismos paquetes (DEB o RPM).</span><span class="sxs-lookup"><span data-stu-id="36069-115">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="36069-116">En Windows, utilice el instalador MSI.</span><span class="sxs-lookup"><span data-stu-id="36069-116">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="36069-117">Los archivos binarios estables más recientes se encuentran en [Descargas de .NET](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="36069-117">The latest stable binaries are found at [.NET downloads](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="36069-118">Si desea utilizar las herramientas de la última versión preliminar, que posiblemente sean inestables, use los vínculos proporcionados en el [repositorio de GitHub dotnet/core-sdk](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="36069-118">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/core-sdk GitHub repository](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span> <span data-ttu-id="36069-119">Para las distribuciones de Linux, se encuentran disponibles los archivos `tar.gz` (conocidos también como `tarballs`); use los scripts de instalación dentro de los archivos para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36069-119">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="36069-120">Uso del script del instalador</span><span class="sxs-lookup"><span data-stu-id="36069-120">Using the installer script</span></span>

<span data-ttu-id="36069-121">El uso del script del instalador permite la instalación sin derechos administrativos en el servidor de compilación y una sencilla automatización para obtener las herramientas.</span><span class="sxs-lookup"><span data-stu-id="36069-121">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="36069-122">El script se encarga de descargar las herramientas y extraerlas en una ubicación predeterminada o especificada para su uso.</span><span class="sxs-lookup"><span data-stu-id="36069-122">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="36069-123">También puede especificar la versión de las herramientas que desea instalar y si prefiere instalar el SDK completo o solo el runtime compartido.</span><span class="sxs-lookup"><span data-stu-id="36069-123">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="36069-124">El script del instalador se puede automatizar para que se ejecute al principio de la compilación, a fin de obtener e instalar la versión deseada del SDK.</span><span class="sxs-lookup"><span data-stu-id="36069-124">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="36069-125">La *versión deseada* se corresponde con cualquier versión del SKD que los proyectos necesitan para la compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-125">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="36069-126">El script permite instalar el SDK en un directorio local del servidor, ejecutar las herramientas desde la ubicación de instalación y limpiar después de la compilación, o bien dejar que el servicio de CI realice dicha limpieza.</span><span class="sxs-lookup"><span data-stu-id="36069-126">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="36069-127">Esto permite encapsular y aislar todo el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-127">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="36069-128">La referencia del script de instalación se encuentra en el artículo [dotnet-install](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="36069-128">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) article.</span></span>

> [!NOTE]
> <span data-ttu-id="36069-129">**Azure DevOps Services**</span><span class="sxs-lookup"><span data-stu-id="36069-129">**Azure DevOps Services**</span></span>
>
> <span data-ttu-id="36069-130">Cuando se utiliza el script del instalador, las dependencias nativas no se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="36069-130">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="36069-131">Debe instalarlas en caso de el sistema operativo no las incluya.</span><span class="sxs-lookup"><span data-stu-id="36069-131">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="36069-132">Para obtener más información, vea [Dependencias y requisitos de .NET Core](../install/windows.md#dependencies).</span><span class="sxs-lookup"><span data-stu-id="36069-132">For more information, see [.NET Core dependencies and requirements](../install/windows.md#dependencies).</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="36069-133">Ejemplos de configuración de CI</span><span class="sxs-lookup"><span data-stu-id="36069-133">CI setup examples</span></span>

<span data-ttu-id="36069-134">En esta sección se explica un procedimiento de instalación manual con un script de PowerShell o de Bash, además de incluir una descripción de varias soluciones de CI de software como servicio (SaaS).</span><span class="sxs-lookup"><span data-stu-id="36069-134">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="36069-135">Las soluciones de CI de SaaS tratadas son [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [ Azure Pipelines](/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="36069-135">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](/azure/devops/pipelines/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="36069-136">Instalación manual</span><span class="sxs-lookup"><span data-stu-id="36069-136">Manual setup</span></span>

<span data-ttu-id="36069-137">Cada servicio de SaaS tiene sus propios métodos para crear y configurar un proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-137">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="36069-138">Si usa una solución de SaaS distinta a las que indican o necesita realizar alguna personalización aparte de la compatibilidad preconfigurada, debe realizar al menos alguna configuración manual.</span><span class="sxs-lookup"><span data-stu-id="36069-138">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="36069-139">En general, para realizar una instalación manual, es necesario que adquiera una versión de las herramientas o las últimas compilaciones nocturnas de las herramientas y que, después, ejecute el script de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-139">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="36069-140">Puede usar un script de PowerShell o de Bash para orquestar los comandos de .NET Core o utilizar un archivo del proyecto en el que se describa el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-140">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="36069-141">En la [sección de orquestación](#orchestrating-the-build) se ofrece más información sobre estas opciones.</span><span class="sxs-lookup"><span data-stu-id="36069-141">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="36069-142">Después de crear un script que realiza una instalación manual del servidor de compilación de CI, úselo en el equipo de desarrollo para compilar el código de forma local con fines de pruebas.</span><span class="sxs-lookup"><span data-stu-id="36069-142">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="36069-143">Cuando confirme que el script se ejecuta de forma correcta en el entorno local, impleméntelo en el servidor de compilación de CI.</span><span class="sxs-lookup"><span data-stu-id="36069-143">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="36069-144">Un script de PowerShell relativamente sencillo demuestra cómo obtener el SDK de NET Core e instalarlo en un servidor de compilación de Windows:</span><span class="sxs-lookup"><span data-stu-id="36069-144">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

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

<span data-ttu-id="36069-145">Debe proporcionar la implementación para el proceso de compilación al final del script.</span><span class="sxs-lookup"><span data-stu-id="36069-145">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="36069-146">El script adquiere las herramientas y, después, ejecuta el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-146">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="36069-147">En los equipos UNIX, el siguiente script de Bash realiza las acciones descritas en el script de PowerShell de forma similar:</span><span class="sxs-lookup"><span data-stu-id="36069-147">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

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

### <a name="travis-ci"></a><span data-ttu-id="36069-148">Travis CI</span><span class="sxs-lookup"><span data-stu-id="36069-148">Travis CI</span></span>

<span data-ttu-id="36069-149">Puede configurar [Travis CI](https://travis-ci.org/) para instalar el SDK de .NET Core con el lenguaje `csharp` y la clave `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="36069-149">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="36069-150">Para más información, consulte los documentos oficiales de Travis CI en [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilación de un proyecto de C#, F# o Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="36069-150">For more information, see the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/).</span></span> <span data-ttu-id="36069-151">Al acceder a la información de Travis CI, observará que el identificador de lenguaje `language: csharp` de cuyo mantenimiento se encarga la comunidad funciona con todos los lenguajes de .NET, incluidos F# y Mono.</span><span class="sxs-lookup"><span data-stu-id="36069-151">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="36069-152">Travis CI se ejecuta tanto en trabajos de macOS como de Linux en una *matriz de compilación*, donde debe especificar una combinación de runtime, entorno y exclusiones/inclusiones para aceptar las combinaciones de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36069-152">Travis CI runs both macOS and Linux jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="36069-153">Para más información, vea el artículo [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalización de la compilación) en la documentación de Travis CI.</span><span class="sxs-lookup"><span data-stu-id="36069-153">For more information, see the [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) article in the Travis CI documentation.</span></span> <span data-ttu-id="36069-154">Las herramientas basadas en MSBuild incluyen los runtimes LTS (1.0.x) y Current (1.1.x) en el paquete; por tanto, cuando instala el SDK, recibe todo lo que necesita para la compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-154">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="36069-155">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="36069-155">AppVeyor</span></span>

<span data-ttu-id="36069-156">[AppVeyor](https://www.appveyor.com/) instala el SDK de .NET Core 1.0.1 con la imagen de trabajo de compilación de `Visual Studio 2017`.</span><span class="sxs-lookup"><span data-stu-id="36069-156">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="36069-157">Hay disponibles otras imágenes de compilación con distintas versiones del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36069-157">Other build images with different versions of the .NET Core SDK are available.</span></span> <span data-ttu-id="36069-158">Para más información, consulte el [ejemplo appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) y el artículo [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Imágenes de trabajo de compilación) en los documentos de AppVeyor.</span><span class="sxs-lookup"><span data-stu-id="36069-158">For more information, see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) article in the AppVeyor docs.</span></span>

<span data-ttu-id="36069-159">Los archivos binarios del SDK de .NET Core se descargan y descomprimen en un subdirectorio con la utilización del script de instalación y, después, se agregan a la variable de entorno `PATH`.</span><span class="sxs-lookup"><span data-stu-id="36069-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="36069-160">Agregue una matriz de compilación para ejecutar las pruebas de integración con varias versiones del SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="36069-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a><span data-ttu-id="36069-161">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="36069-161">Azure DevOps Services</span></span>

<span data-ttu-id="36069-162">Configure Azure DevOps Services para compilar proyectos de .NET Core con alguno de estos enfoques:</span><span class="sxs-lookup"><span data-stu-id="36069-162">Configure Azure DevOps Services to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="36069-163">Ejecute el script del [paso de instalación manual](#manual-setup) con sus comandos.</span><span class="sxs-lookup"><span data-stu-id="36069-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="36069-164">Cree una compilación compuesta de varias tareas de compilación integradas en Azure DevOps Services que están configuradas para usar herramientas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36069-164">Create a build composed of several Azure DevOps Services built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="36069-165">Ambas soluciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="36069-165">Both solutions are valid.</span></span> <span data-ttu-id="36069-166">Con la utilización de un script de instalación manual, puede controlar la versión de las herramientas que recibe, ya que las descarga como parte de la compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="36069-167">La compilación se ejecuta desde un script que debe crear.</span><span class="sxs-lookup"><span data-stu-id="36069-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="36069-168">En este artículo solo se trata la opción manual.</span><span class="sxs-lookup"><span data-stu-id="36069-168">This article only covers the manual option.</span></span> <span data-ttu-id="36069-169">Para más información sobre cómo elaborar una compilación con las tareas de compilación de Azure DevOps Services, consulte la documentación de [Azure Pipelines](/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="36069-169">For more information on composing a build with Azure DevOps Services build tasks, see the [Azure Pipelines](/azure/devops/pipelines/index) documentation.</span></span>

<span data-ttu-id="36069-170">Para usar un script de instalación manual en Azure DevOps Services, cree una definición de compilación y especifique el script que va a ejecutar para el paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-170">To use a manual setup script in Azure DevOps Services, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="36069-171">Esto se realiza en la interfaz de usuario de Azure DevOps Services:</span><span class="sxs-lookup"><span data-stu-id="36069-171">This is accomplished using the Azure DevOps Services user interface:</span></span>

1. <span data-ttu-id="36069-172">Empiece por crear una definición de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-172">Start by creating a new build definition.</span></span> <span data-ttu-id="36069-173">Cuando llegue a la pantalla en la que se ofrece la opción de definir el tipo de compilación que desea crear, seleccione la opción **Vacío**.</span><span class="sxs-lookup"><span data-stu-id="36069-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![Selección de una definición de compilación vacía](./media/using-ci-with-cli/select-empty-build-definition.png)

1. <span data-ttu-id="36069-175">Después de configurar el repositorio que va a compilar, se le remite a las definiciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="36069-176">Seleccione **Agregar paso de compilación**:</span><span class="sxs-lookup"><span data-stu-id="36069-176">Select **Add build step**:</span></span>

   ![Agregar un paso de compilación](./media/using-ci-with-cli/add-build-step.png)

1. <span data-ttu-id="36069-178">Se abre el **Catálogo de tareas**.</span><span class="sxs-lookup"><span data-stu-id="36069-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="36069-179">El catálogo contiene tareas que se utilizan en la compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="36069-180">Como ya tiene un script, seleccione el botón **Agregar** en **PowerShell: Ejecute un script de PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="36069-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![Paso para agregar un script de PowerShell](./media/using-ci-with-cli/add-powershell-script.png)

1. <span data-ttu-id="36069-182">Configure el paso de compilación.</span><span class="sxs-lookup"><span data-stu-id="36069-182">Configure the build step.</span></span> <span data-ttu-id="36069-183">Agregue el script desde el repositorio que se va a compilar:</span><span class="sxs-lookup"><span data-stu-id="36069-183">Add the script from the repository that you're building:</span></span>

   ![Especificar el script de PowerShell que va a ejecutar](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="36069-185">Orquestación de la compilación</span><span class="sxs-lookup"><span data-stu-id="36069-185">Orchestrating the build</span></span>

<span data-ttu-id="36069-186">En la mayor parte de este documento se describe cómo adquirir las herramientas de .NET Core y configurar varios servicios de CI sin ofrecer información sobre cómo orquestar o *compilar realmente* el código con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36069-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="36069-187">Las opciones para estructurar el proceso de compilación dependen de muchos factores que no se pueden tratar aquí en términos generales.</span><span class="sxs-lookup"><span data-stu-id="36069-187">The choices on how to structure the build process depend on many factors that can't be covered in a general way here.</span></span> <span data-ttu-id="36069-188">Para más información sobre cómo orquestar las compilaciones con cada tecnología, explore los recursos y los ejemplos que se proporciona en los conjuntos de documentación de [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [Azure Pipelines](/azure/devops/pipelines/index).</span><span class="sxs-lookup"><span data-stu-id="36069-188">For more information on orchestrating your builds with each technology, explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](/azure/devops/pipelines/index).</span></span>

<span data-ttu-id="36069-189">Dos enfoques generales que se aplican para estructurar el proceso de compilación del código de .NET Core con herramientas de .NET Core consisten en utilizar directamente MSBuild o en usar los comandos de la línea de comandos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="36069-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="36069-190">El enfoque que debe adoptar depende de lo cómo que se sienta con cada uno de ellos y de los inconvenientes que presente su complejidad.</span><span class="sxs-lookup"><span data-stu-id="36069-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="36069-191">MSBuild ofrece la posibilidad de expresar el proceso de compilación como tareas y objetivos, pero presenta la complejidad añadida de tener que aprender la sintaxis del archivo de proyecto de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="36069-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="36069-192">Quizá sea más sencillo usar las herramientas de línea de comandos de .NET Core, pero, en este caso, es necesario escribir la lógica de orquestación en un lenguaje de scripting como `bash` o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36069-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="36069-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="36069-193">See also</span></span>

- [<span data-ttu-id="36069-194">Descargas de .NET: Linux</span><span class="sxs-lookup"><span data-stu-id="36069-194">.NET downloads - Linux</span></span>](https://dotnet.microsoft.com/download?initial-os=linux)
