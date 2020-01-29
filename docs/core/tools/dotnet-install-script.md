---
title: Scripts de dotnet-install
description: Obtenga información sobre los scripts de dotnet-install para instalar el SDK de .NET Core y el entorno de ejecución compartido.
ms.date: 01/23/2020
ms.openlocfilehash: 169991ac4cd24ccab90634ff265c3ae5b603f8e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734206"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="7b90f-103">referencia de scripts de dotnet-install</span><span class="sxs-lookup"><span data-stu-id="7b90f-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="7b90f-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7b90f-104">Name</span></span>

<span data-ttu-id="7b90f-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar el SDK de .NET Core y el entorno de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="7b90f-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7b90f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7b90f-106">Synopsis</span></span>

<span data-ttu-id="7b90f-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="7b90f-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

<span data-ttu-id="7b90f-108">Linux/macOs:</span><span class="sxs-lookup"><span data-stu-id="7b90f-108">Linux/macOs:</span></span>

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a><span data-ttu-id="7b90f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b90f-109">Description</span></span>

<span data-ttu-id="7b90f-110">Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="7b90f-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="7b90f-111">Se recomienda usar la versión estable de los scripts:</span><span class="sxs-lookup"><span data-stu-id="7b90f-111">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="7b90f-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="7b90f-112">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="7b90f-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="7b90f-113">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

<span data-ttu-id="7b90f-114">La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="7b90f-114">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="7b90f-115">Existen dos scripts: uno es un script de PowerShell que funciona en Windows y el otro es un script de Bash que funciona en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="7b90f-115">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="7b90f-116">Ambos scripts tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7b90f-116">Both scripts have the same behavior.</span></span> <span data-ttu-id="7b90f-117">El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="7b90f-117">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="7b90f-118">Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-118">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="7b90f-119">De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan.</span><span class="sxs-lookup"><span data-stu-id="7b90f-119">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="7b90f-120">Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-120">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="7b90f-121">De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="7b90f-121">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="7b90f-122">Para invalidar este comportamiento, especifique el argumento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-122">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span>

<span data-ttu-id="7b90f-123">Antes de ejecutar el script, instale las [dependencias](../install/dependencies.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="7b90f-123">Before running the script, install the required [dependencies](../install/dependencies.md).</span></span>

<span data-ttu-id="7b90f-124">Puede instalar una versión específica mediante el argumento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-124">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="7b90f-125">La versión debe especificarse como una versión de tres partes (por ejemplo, `2.1.0`).</span><span class="sxs-lookup"><span data-stu-id="7b90f-125">The version must be specified as a three-part version (for example, `2.1.0`).</span></span> <span data-ttu-id="7b90f-126">Si no se proporciona, usa la versión `latest`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-126">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="7b90f-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="7b90f-127">Options</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="7b90f-128">Especifica el canal de origen para la instalación.</span><span class="sxs-lookup"><span data-stu-id="7b90f-128">Specifies the source channel for the installation.</span></span> <span data-ttu-id="7b90f-129">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7b90f-129">The possible values are:</span></span>

  - <span data-ttu-id="7b90f-130">`Current`: versión más actual.</span><span class="sxs-lookup"><span data-stu-id="7b90f-130">`Current` - Most current release.</span></span>
  - <span data-ttu-id="7b90f-131">`LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).</span><span class="sxs-lookup"><span data-stu-id="7b90f-131">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="7b90f-132">Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.1` o `3.0`).</span><span class="sxs-lookup"><span data-stu-id="7b90f-132">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="7b90f-133">Nombre de rama: por ejemplo, `release/3.1.1xx` o `master` (para versiones nocturnas).</span><span class="sxs-lookup"><span data-stu-id="7b90f-133">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="7b90f-134">Use esta opción para instalar una versión de un canal de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="7b90f-134">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="7b90f-135">Use el nombre del canal como aparece en [Instaladores y binarios](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="7b90f-135">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="7b90f-136">El valor predeterminado es `LTS`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-136">The default value is `LTS`.</span></span> <span data-ttu-id="7b90f-137">Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="7b90f-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="7b90f-138">Representa una versión de compilación concreta.</span><span class="sxs-lookup"><span data-stu-id="7b90f-138">Represents a specific build version.</span></span> <span data-ttu-id="7b90f-139">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7b90f-139">The possible values are:</span></span>

  - <span data-ttu-id="7b90f-140">`latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="7b90f-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="7b90f-141">`coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama).</span><span class="sxs-lookup"><span data-stu-id="7b90f-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="7b90f-142">Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="7b90f-143">Por ejemplo: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="7b90f-144">Si no se especifica, el valor predeterminado de `-Version` es `latest`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="7b90f-145">Especifica una ruta de acceso a un archivo [global.json](global-json.md) que se va a usar para determinar la versión del SDK.</span><span class="sxs-lookup"><span data-stu-id="7b90f-145">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="7b90f-146">El archivo *global.json* debe tener un valor para `sdk:version`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-146">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="7b90f-147">Especifica la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="7b90f-147">Specifies the installation path.</span></span> <span data-ttu-id="7b90f-148">Si no existe el directorio, se crea.</span><span class="sxs-lookup"><span data-stu-id="7b90f-148">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="7b90f-149">El valor predeterminado es *%LocalAppData%\Microsoft\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="7b90f-149">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="7b90f-150">Los archivos binarios se colocan directamente en el directorio.</span><span class="sxs-lookup"><span data-stu-id="7b90f-150">Binaries are placed directly in this directory.</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="7b90f-151">Arquitectura de los archivos binarios de .NET Core para instalar.</span><span class="sxs-lookup"><span data-stu-id="7b90f-151">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="7b90f-152">Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-152">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="7b90f-153">El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.</span><span class="sxs-lookup"><span data-stu-id="7b90f-153">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="7b90f-154">Este parámetro está obsoleto y puede quitarse en una versión futura del script.</span><span class="sxs-lookup"><span data-stu-id="7b90f-154">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="7b90f-155">La alternativa recomendada es la opción `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-155">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="7b90f-156">Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="7b90f-156">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="7b90f-157">Esta opción equivale a especificar `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-157">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="7b90f-158">Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="7b90f-158">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="7b90f-159">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7b90f-159">The possible values are:</span></span>

  - <span data-ttu-id="7b90f-160">`dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-160">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="7b90f-161">`aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-161">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="7b90f-162">`windowsdesktop`: el entorno de tiempo de ejecución compartido `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-162">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="7b90f-163">Si se establece, el script no realizará la instalación.</span><span class="sxs-lookup"><span data-stu-id="7b90f-163">If set, the script won't perform the installation.</span></span> <span data-ttu-id="7b90f-164">En su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b90f-164">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="7b90f-165">Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="7b90f-165">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="7b90f-166">También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="7b90f-166">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="7b90f-167">Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="7b90f-167">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="7b90f-168">De manera predeterminada, el script modifica la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="7b90f-168">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="7b90f-169">Muestra la información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="7b90f-169">Displays diagnostics information.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="7b90f-170">Especifica la dirección URL de la fuente de Azure al instalador.</span><span class="sxs-lookup"><span data-stu-id="7b90f-170">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="7b90f-171">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="7b90f-171">We recommended that you don't change this value.</span></span> <span data-ttu-id="7b90f-172">El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="7b90f-172">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="7b90f-173">Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza.</span><span class="sxs-lookup"><span data-stu-id="7b90f-173">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="7b90f-174">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="7b90f-174">We recommended that you don't change this value.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="7b90f-175">Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.</span><span class="sxs-lookup"><span data-stu-id="7b90f-175">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="7b90f-176">Se utiliza como una cadena de consulta para anexar a la fuente de Azure.</span><span class="sxs-lookup"><span data-stu-id="7b90f-176">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="7b90f-177">Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.</span><span class="sxs-lookup"><span data-stu-id="7b90f-177">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--runtime-id`**

  <span data-ttu-id="7b90f-178">Especifica el [identificador de entorno de ejecución](../rid-catalog.md) para el que se van a instalar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="7b90f-178">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="7b90f-179">Use `linux-x64` para Linux portátil.</span><span class="sxs-lookup"><span data-stu-id="7b90f-179">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="7b90f-180">(Solo válido para Linux/macOS)</span><span class="sxs-lookup"><span data-stu-id="7b90f-180">(Only valid for Linux/macOS)</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="7b90f-181">Si se establece, el instalador usa el proxy al realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="7b90f-181">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="7b90f-182">(Solo es válido para Windows)</span><span class="sxs-lookup"><span data-stu-id="7b90f-182">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="7b90f-183">Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="7b90f-183">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="7b90f-184">(Solo es válido para Windows)</span><span class="sxs-lookup"><span data-stu-id="7b90f-184">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="7b90f-185">Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.</span><span class="sxs-lookup"><span data-stu-id="7b90f-185">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help|--help`**

  <span data-ttu-id="7b90f-186">Imprime la ayuda para el script.</span><span class="sxs-lookup"><span data-stu-id="7b90f-186">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="7b90f-187">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7b90f-187">Examples</span></span>

- <span data-ttu-id="7b90f-188">Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="7b90f-188">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="7b90f-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="7b90f-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="7b90f-190">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="7b90f-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="7b90f-191">Instale la versión más reciente del canal 3.1 en la ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="7b90f-191">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="7b90f-192">Windows:</span><span class="sxs-lookup"><span data-stu-id="7b90f-192">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="7b90f-193">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="7b90f-193">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="7b90f-194">Instale la versión 3.0.0 del entorno de ejecución compartido:</span><span class="sxs-lookup"><span data-stu-id="7b90f-194">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="7b90f-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="7b90f-195">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="7b90f-196">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="7b90f-196">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="7b90f-197">Obtenga el script e instale la versión 2.1.2 detrás de un proxy corporativo (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="7b90f-197">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="7b90f-198">Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="7b90f-198">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="7b90f-199">Windows:</span><span class="sxs-lookup"><span data-stu-id="7b90f-199">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="7b90f-200">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="7b90f-200">macOS/Linux:</span></span>

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="7b90f-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b90f-201">See also</span></span>

- [<span data-ttu-id="7b90f-202">Versiones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7b90f-202">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="7b90f-203">Archivo de descarga del SDK y .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="7b90f-203">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
