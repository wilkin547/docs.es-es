---
title: Scripts de dotnet-install
description: Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.
ms.date: 01/16/2019
ms.openlocfilehash: 765141ae92645db448ac7c9c3448a79b895faac6
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964345"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="22ba3-103">referencia de scripts de dotnet-install</span><span class="sxs-lookup"><span data-stu-id="22ba3-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="22ba3-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="22ba3-104">Name</span></span>

<span data-ttu-id="22ba3-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="22ba3-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="22ba3-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="22ba3-106">Synopsis</span></span>

<span data-ttu-id="22ba3-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="22ba3-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="22ba3-108">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="22ba3-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="22ba3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="22ba3-109">Description</span></span>

<span data-ttu-id="22ba3-110">Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="22ba3-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="22ba3-111">Le recomendamos que use la versión estable que se hospeda en el [sitio web principal de .NET Core](https://dot.net).</span><span class="sxs-lookup"><span data-stu-id="22ba3-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="22ba3-112">Las rutas de acceso directas a los scripts son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="22ba3-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="22ba3-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="22ba3-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="22ba3-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="22ba3-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="22ba3-115">La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="22ba3-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="22ba3-116">Existen dos scripts: uno es un script de PowerShell que funciona en Windows y el otro es un script de Bash que funciona en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="22ba3-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="22ba3-117">Ambos scripts tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="22ba3-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="22ba3-118">El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="22ba3-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="22ba3-119">Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="22ba3-120">De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan.</span><span class="sxs-lookup"><span data-stu-id="22ba3-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="22ba3-121">Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="22ba3-122">De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="22ba3-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="22ba3-123">Para invalidar este comportamiento, especifique el argumento `--no-path`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="22ba3-124">Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="22ba3-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="22ba3-125">Puede instalar una versión específica mediante el argumento `--version`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="22ba3-126">La versión debe especificarse como una versión de tres partes (por ejemplo, 1.0.0-13232).</span><span class="sxs-lookup"><span data-stu-id="22ba3-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="22ba3-127">Si no se proporciona, usa la versión `latest`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="22ba3-128">Opciones</span><span class="sxs-lookup"><span data-stu-id="22ba3-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="22ba3-129">Especifica el canal de origen para la instalación.</span><span class="sxs-lookup"><span data-stu-id="22ba3-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="22ba3-130">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="22ba3-130">The possible values are:</span></span>

  - <span data-ttu-id="22ba3-131">`Current`: versión más actual.</span><span class="sxs-lookup"><span data-stu-id="22ba3-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="22ba3-132">`LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).</span><span class="sxs-lookup"><span data-stu-id="22ba3-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="22ba3-133">Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.0` o `1.0`).</span><span class="sxs-lookup"><span data-stu-id="22ba3-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="22ba3-134">Nombre de rama.</span><span class="sxs-lookup"><span data-stu-id="22ba3-134">Branch name.</span></span> <span data-ttu-id="22ba3-135">Por ejemplo, `release/2.0.0`, `release/2.0.0-preview2` o `master` (para versiones nocturnas).</span><span class="sxs-lookup"><span data-stu-id="22ba3-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="22ba3-136">El valor predeterminado es `LTS`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-136">The default value is `LTS`.</span></span> <span data-ttu-id="22ba3-137">Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="22ba3-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="22ba3-138">Representa una versión de compilación concreta.</span><span class="sxs-lookup"><span data-stu-id="22ba3-138">Represents a specific build version.</span></span> <span data-ttu-id="22ba3-139">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="22ba3-139">The possible values are:</span></span>

  - <span data-ttu-id="22ba3-140">`latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="22ba3-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="22ba3-141">`coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama).</span><span class="sxs-lookup"><span data-stu-id="22ba3-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="22ba3-142">Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="22ba3-143">Por ejemplo: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="22ba3-144">Si no se especifica, el valor predeterminado de `-Version` es `latest`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="22ba3-145">Especifica la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="22ba3-145">Specifies the installation path.</span></span> <span data-ttu-id="22ba3-146">Si no existe el directorio, se crea.</span><span class="sxs-lookup"><span data-stu-id="22ba3-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="22ba3-147">El valor predeterminado es *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="22ba3-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="22ba3-148">Los archivos binarios se colocan directamente en el directorio.</span><span class="sxs-lookup"><span data-stu-id="22ba3-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="22ba3-149">Arquitectura de los archivos binarios de .NET Core para instalar.</span><span class="sxs-lookup"><span data-stu-id="22ba3-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="22ba3-150">Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="22ba3-151">El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.</span><span class="sxs-lookup"><span data-stu-id="22ba3-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="22ba3-152">Este parámetro está obsoleto y puede quitarse en una versión futura del script.</span><span class="sxs-lookup"><span data-stu-id="22ba3-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="22ba3-153">La alternativa recomendada es la opción `Runtime`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="22ba3-154">Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="22ba3-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="22ba3-155">Es equivalente a especificar `-Runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="22ba3-156">Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="22ba3-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="22ba3-157">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="22ba3-157">The possible values are:</span></span>

  - <span data-ttu-id="22ba3-158">`dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="22ba3-159">`aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="22ba3-160">Si se establece, el script no realizará la instalación.</span><span class="sxs-lookup"><span data-stu-id="22ba3-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="22ba3-161">En su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22ba3-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="22ba3-162">Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="22ba3-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="22ba3-163">También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="22ba3-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="22ba3-164">Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="22ba3-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="22ba3-165">De manera predeterminada, el script modifica la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="22ba3-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="22ba3-166">Muestra la información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="22ba3-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="22ba3-167">Especifica la dirección URL de la fuente de Azure al instalador.</span><span class="sxs-lookup"><span data-stu-id="22ba3-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="22ba3-168">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="22ba3-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="22ba3-169">El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="22ba3-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="22ba3-170">Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza.</span><span class="sxs-lookup"><span data-stu-id="22ba3-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="22ba3-171">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="22ba3-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="22ba3-172">Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.</span><span class="sxs-lookup"><span data-stu-id="22ba3-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="22ba3-173">Se utiliza como una cadena de consulta para anexar a la fuente de Azure.</span><span class="sxs-lookup"><span data-stu-id="22ba3-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="22ba3-174">Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.</span><span class="sxs-lookup"><span data-stu-id="22ba3-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="22ba3-175">Si se establece, el instalador usa el proxy al realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="22ba3-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="22ba3-176">(Solo es válido para Windows)</span><span class="sxs-lookup"><span data-stu-id="22ba3-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="22ba3-177">Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="22ba3-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="22ba3-178">(Solo es válido para Windows)</span><span class="sxs-lookup"><span data-stu-id="22ba3-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="22ba3-179">Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.</span><span class="sxs-lookup"><span data-stu-id="22ba3-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="22ba3-180">Imprime la ayuda para el script.</span><span class="sxs-lookup"><span data-stu-id="22ba3-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="22ba3-181">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="22ba3-181">Examples</span></span>

- <span data-ttu-id="22ba3-182">Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="22ba3-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="22ba3-183">Windows:</span><span class="sxs-lookup"><span data-stu-id="22ba3-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="22ba3-184">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="22ba3-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="22ba3-185">Instale la versión más reciente del canal 2.0 en la ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="22ba3-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="22ba3-186">Windows:</span><span class="sxs-lookup"><span data-stu-id="22ba3-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="22ba3-187">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="22ba3-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="22ba3-188">Instale la versión 1.1.0 del entorno de tiempo de ejecución compartido:</span><span class="sxs-lookup"><span data-stu-id="22ba3-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="22ba3-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="22ba3-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="22ba3-190">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="22ba3-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="22ba3-191">Obtenga el script e instale la versión 2.1.2 detrás de un proxy corporativo (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="22ba3-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="22ba3-192">Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="22ba3-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="22ba3-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="22ba3-193">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="22ba3-194">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="22ba3-194">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="22ba3-195">Vea también</span><span class="sxs-lookup"><span data-stu-id="22ba3-195">See also</span></span>

- [<span data-ttu-id="22ba3-196">Versiones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="22ba3-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="22ba3-197">Archivo de descarga del SDK y .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="22ba3-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
