---
title: Scripts de dotnet-install
description: Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.openlocfilehash: 8d1c6ebb30bd45575bb61206799c9c3e5c47ff0c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44180048"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="fc89e-103">referencia de scripts de dotnet-install</span><span class="sxs-lookup"><span data-stu-id="fc89e-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="fc89e-104">nombre</span><span class="sxs-lookup"><span data-stu-id="fc89e-104">Name</span></span>

<span data-ttu-id="fc89e-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="fc89e-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fc89e-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="fc89e-106">Synopsis</span></span>

<span data-ttu-id="fc89e-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="fc89e-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

<span data-ttu-id="fc89e-108">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="fc89e-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a><span data-ttu-id="fc89e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc89e-109">Description</span></span>

<span data-ttu-id="fc89e-110">Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="fc89e-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="fc89e-111">Le recomendamos que use la versión estable que se hospeda en el [sitio web principal de .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="fc89e-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="fc89e-112">Las rutas de acceso directas a los scripts son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc89e-112">The direct paths to the scripts are:</span></span>

* <span data-ttu-id="fc89e-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="fc89e-113">https://dot.net/v1/dotnet-install.sh (bash, UNIX)</span></span>
* <span data-ttu-id="fc89e-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="fc89e-114">https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)</span></span>

<span data-ttu-id="fc89e-115">La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="fc89e-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="fc89e-116">Hay dos scripts: uno es un script de PowerShell que funciona en Windows.</span><span class="sxs-lookup"><span data-stu-id="fc89e-116">There are two scripts: One is a PowerShell script that works on Windows.</span></span> <span data-ttu-id="fc89e-117">El otro script es un script de bash que funciona en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="fc89e-117">The other script is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="fc89e-118">Ambos scripts tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fc89e-118">Both scripts have the same behavior.</span></span> <span data-ttu-id="fc89e-119">El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="fc89e-119">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="fc89e-120">Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-120">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="fc89e-121">De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan.</span><span class="sxs-lookup"><span data-stu-id="fc89e-121">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="fc89e-122">Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `--shared-runtime`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-122">If you wish to only obtain the shared runtime, specify the `--shared-runtime` argument.</span></span>

<span data-ttu-id="fc89e-123">De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="fc89e-123">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="fc89e-124">Para invalidar este comportamiento, especifique el argumento `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-124">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="fc89e-125">Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="fc89e-125">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="fc89e-126">Puede instalar una versión específica mediante el argumento `--version`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-126">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="fc89e-127">La versión debe especificarse como una versión de 3 partes (por ejemplo, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="fc89e-127">The version must be specified as a 3-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="fc89e-128">Si se omite, usa la versión `latest`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-128">If omitted, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="fc89e-129">Opciones</span><span class="sxs-lookup"><span data-stu-id="fc89e-129">Options</span></span>

`-Channel <CHANNEL>`

<span data-ttu-id="fc89e-130">Especifica el canal de origen para la instalación.</span><span class="sxs-lookup"><span data-stu-id="fc89e-130">Specifies the source channel for the installation.</span></span> <span data-ttu-id="fc89e-131">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="fc89e-131">The possible values are:</span></span>

- <span data-ttu-id="fc89e-132">`Current`: versión actual</span><span class="sxs-lookup"><span data-stu-id="fc89e-132">`Current` - Current release</span></span>
- <span data-ttu-id="fc89e-133">`LTS`: canal de soporte técnico a largo plazo (versión actual compatible)</span><span class="sxs-lookup"><span data-stu-id="fc89e-133">`LTS` - Long-Term Support channel (current supported release)</span></span>
- <span data-ttu-id="fc89e-134">Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.0` o `1.0`)</span><span class="sxs-lookup"><span data-stu-id="fc89e-134">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`)</span></span>
- <span data-ttu-id="fc89e-135">Nombre de rama [por ejemplo, `release/2.0.0`, `release/2.0.0-preview2` o `master` para la última versión de la rama `master` (versiones nocturna "experimentales")]</span><span class="sxs-lookup"><span data-stu-id="fc89e-135">Branch name [for example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` for the latest from the `master` branch ("bleeding edge" nightly releases)]</span></span>

<span data-ttu-id="fc89e-136">El valor predeterminado es `LTS`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-136">The default value is `LTS`.</span></span> <span data-ttu-id="fc89e-137">Para más información sobre los canales de soporte técnico de .NET, vea el tema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Ciclo de vida de soporte técnico de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="fc89e-137">For more information on .NET support channels, see the [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) topic.</span></span>

`-Version <VERSION>`

<span data-ttu-id="fc89e-138">Representa una versión de compilación concreta.</span><span class="sxs-lookup"><span data-stu-id="fc89e-138">Represents a specific build version.</span></span> <span data-ttu-id="fc89e-139">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="fc89e-139">The possible values are:</span></span>

- <span data-ttu-id="fc89e-140">`latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`)</span><span class="sxs-lookup"><span data-stu-id="fc89e-140">`latest` - Latest build on the channel (used with the `-Channel` option)</span></span>
- <span data-ttu-id="fc89e-141">`coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama)</span><span class="sxs-lookup"><span data-stu-id="fc89e-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options)</span></span>
- <span data-ttu-id="fc89e-142">Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="fc89e-143">Por ejemplo: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-143">For example: `2.0.0-preview2-006120`</span></span>

<span data-ttu-id="fc89e-144">Si se omite, el valor predeterminado de `-Version` es `latest`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-144">If omitted, `-Version` defaults to `latest`.</span></span>

`-InstallDir <DIRECTORY>`

<span data-ttu-id="fc89e-145">Especifica la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="fc89e-145">Specifies the installation path.</span></span> <span data-ttu-id="fc89e-146">Si no existe el directorio, se crea.</span><span class="sxs-lookup"><span data-stu-id="fc89e-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="fc89e-147">El valor predeterminado es *% LocalAppData %\.dotnet*.</span><span class="sxs-lookup"><span data-stu-id="fc89e-147">The default value is *%LocalAppData%\.dotnet*.</span></span> <span data-ttu-id="fc89e-148">Tenga en cuenta que los archivos binarios se colocan directamente en el directorio.</span><span class="sxs-lookup"><span data-stu-id="fc89e-148">Note that binaries are placed directly in the directory.</span></span>

`-Architecture <ARCHITECTURE>`

<span data-ttu-id="fc89e-149">Arquitectura de los archivos binarios de .NET Core para instalar.</span><span class="sxs-lookup"><span data-stu-id="fc89e-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="fc89e-150">Los valores posibles son `auto`, `x64`, y `x86`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-150">Possible values are `auto`, `x64`, and `x86`.</span></span> <span data-ttu-id="fc89e-151">El valor predeterminado es `auto`, que representa la arquitectura de SO que se ejecuta en ese momento.</span><span class="sxs-lookup"><span data-stu-id="fc89e-151">The default value is `auto`, which represents the currently running OS architecture.</span></span>

`-SharedRuntime`

<span data-ttu-id="fc89e-152">Si se establece, este modificador limita la instalación al entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="fc89e-152">If set, this switch limits installation to the shared runtime.</span></span> <span data-ttu-id="fc89e-153">No está instalado el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="fc89e-153">The entire SDK isn't installed.</span></span>

`-DryRun`

<span data-ttu-id="fc89e-154">Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc89e-154">If set, the script won't perform the installation; but instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="fc89e-155">Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="fc89e-155">For example if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="fc89e-156">También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="fc89e-156">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

`-NoPath`

<span data-ttu-id="fc89e-157">Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="fc89e-157">If set, the prefix/installdir are not exported to the path for the current session.</span></span> <span data-ttu-id="fc89e-158">De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="fc89e-158">By default, the script will modify the PATH, which makes the CLI tools available immediately after install.</span></span>

`-AzureFeed`

<span data-ttu-id="fc89e-159">Especifica la dirección URL de la fuente de Azure al instalador.</span><span class="sxs-lookup"><span data-stu-id="fc89e-159">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="fc89e-160">No se recomienda cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="fc89e-160">It isn't recommended that you change this value.</span></span> <span data-ttu-id="fc89e-161">De manera predeterminada, es `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="fc89e-161">The default is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

`-ProxyAddress`

<span data-ttu-id="fc89e-162">Si se establece, el instalador usa el proxy al realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="fc89e-162">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="fc89e-163">(Solo es válido para Windows)</span><span class="sxs-lookup"><span data-stu-id="fc89e-163">(Only valid for Windows)</span></span>

`--verbose`

<span data-ttu-id="fc89e-164">Muestra la información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fc89e-164">Display diagnostics information.</span></span>

`--help`

<span data-ttu-id="fc89e-165">Imprime la ayuda para el script.</span><span class="sxs-lookup"><span data-stu-id="fc89e-165">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="fc89e-166">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fc89e-166">Examples</span></span>

<span data-ttu-id="fc89e-167">Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="fc89e-167">Install the latest long-term supported (LTS) version to the default location:</span></span>

<span data-ttu-id="fc89e-168">Windows:</span><span class="sxs-lookup"><span data-stu-id="fc89e-168">Windows:</span></span>

`./dotnet-install.ps1 -Channel LTS`

<span data-ttu-id="fc89e-169">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="fc89e-169">macOS/Linux:</span></span>

`./dotnet-install.sh --channel LTS`

<span data-ttu-id="fc89e-170">Instale la versión más reciente del canal 2.0 en la ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="fc89e-170">Install the latest version from 2.0 channel to the specified location:</span></span>

<span data-ttu-id="fc89e-171">Windows:</span><span class="sxs-lookup"><span data-stu-id="fc89e-171">Windows:</span></span>

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

<span data-ttu-id="fc89e-172">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="fc89e-172">macOS/Linux:</span></span>

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

<span data-ttu-id="fc89e-173">Instale la versión 1.1.0 del entorno de tiempo de ejecución compartido:</span><span class="sxs-lookup"><span data-stu-id="fc89e-173">Install the 1.1.0 version of the shared runtime:</span></span>

<span data-ttu-id="fc89e-174">Windows:</span><span class="sxs-lookup"><span data-stu-id="fc89e-174">Windows:</span></span>

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

<span data-ttu-id="fc89e-175">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="fc89e-175">macOS/Linux:</span></span>

`./dotnet-install.sh --shared-runtime --version 1.1.0`

<span data-ttu-id="fc89e-176">Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="fc89e-176">Obtain script and install .NET Core CLI one-liner examples:</span></span>

<span data-ttu-id="fc89e-177">Windows:</span><span class="sxs-lookup"><span data-stu-id="fc89e-177">Windows:</span></span>

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

<span data-ttu-id="fc89e-178">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="fc89e-178">macOS/Linux:</span></span>

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a><span data-ttu-id="fc89e-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc89e-179">See also</span></span>

* [<span data-ttu-id="fc89e-180">Versiones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc89e-180">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
* [<span data-ttu-id="fc89e-181">Archivo de descarga del SDK y .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="fc89e-181">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
