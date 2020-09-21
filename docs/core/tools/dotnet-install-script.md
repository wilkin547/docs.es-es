---
title: Scripts de dotnet-install
description: Obtenga información sobre los scripts de dotnet-install para instalar el SDK de .NET Core y el entorno de ejecución compartido.
ms.date: 04/30/2020
ms.openlocfilehash: 8f27b8a7794e84e6e2b288d6cc2ec33ffcb7600f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538047"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="c103a-103">referencia de scripts de dotnet-install</span><span class="sxs-lookup"><span data-stu-id="c103a-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="c103a-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c103a-104">Name</span></span>

<span data-ttu-id="c103a-105">`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar el SDK de .NET Core y el entorno de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="c103a-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c103a-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c103a-106">Synopsis</span></span>

<span data-ttu-id="c103a-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="c103a-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress] [-ProxyBypassList <LIST_OF_URLS>]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

<span data-ttu-id="c103a-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="c103a-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

<span data-ttu-id="c103a-109">El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="c103a-109">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

## <a name="description"></a><span data-ttu-id="c103a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c103a-110">Description</span></span>

<span data-ttu-id="c103a-111">Los scripts `dotnet-install` realizan una instalación sin derechos administrativos del SDK de .NET Core, que incluye la CLI de .NET Core y el entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="c103a-111">The `dotnet-install` scripts perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI and the shared runtime.</span></span> <span data-ttu-id="c103a-112">Hay dos scripts:</span><span class="sxs-lookup"><span data-stu-id="c103a-112">There are two scripts:</span></span>

* <span data-ttu-id="c103a-113">un script de PowerShell que funciona en Windows;</span><span class="sxs-lookup"><span data-stu-id="c103a-113">A PowerShell script that works on Windows.</span></span>
* <span data-ttu-id="c103a-114">un script de Bash que funciona en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="c103a-114">A bash script that works on Linux/macOS.</span></span>

### <a name="purpose"></a><span data-ttu-id="c103a-115">Propósito</span><span class="sxs-lookup"><span data-stu-id="c103a-115">Purpose</span></span>

 <span data-ttu-id="c103a-116">El uso previsto de los scripts es en escenarios de integración continua (CI), donde:</span><span class="sxs-lookup"><span data-stu-id="c103a-116">The intended use of the scripts is for Continuous Integration (CI) scenarios, where:</span></span>

* <span data-ttu-id="c103a-117">el SDK debe instalarse sin interacción del usuario y sin derechos de administrador;</span><span class="sxs-lookup"><span data-stu-id="c103a-117">The SDK needs to be installed without user interaction and without admin rights.</span></span>
* <span data-ttu-id="c103a-118">no es necesario que la instalación del SDK se mantenga en varias ejecuciones de CI.</span><span class="sxs-lookup"><span data-stu-id="c103a-118">The SDK installation doesn't need to persist across multiple CI runs.</span></span>

  <span data-ttu-id="c103a-119">Esta es la secuencia típica de eventos:</span><span class="sxs-lookup"><span data-stu-id="c103a-119">The typical sequence of events:</span></span>
  * <span data-ttu-id="c103a-120">Se desencadena la CI.</span><span class="sxs-lookup"><span data-stu-id="c103a-120">CI is triggered.</span></span>
  * <span data-ttu-id="c103a-121">CI instala el SDK mediante uno de estos scripts.</span><span class="sxs-lookup"><span data-stu-id="c103a-121">CI installs the SDK using one of these scripts.</span></span>
  * <span data-ttu-id="c103a-122">CI finaliza su trabajo y borra los datos temporales, incluida la instalación del SDK.</span><span class="sxs-lookup"><span data-stu-id="c103a-122">CI finishes its work and clears temporary data including the SDK installation.</span></span>

<span data-ttu-id="c103a-123">Para configurar un entorno de desarrollo o ejecutar aplicaciones, use los instaladores en lugar de estos scripts.</span><span class="sxs-lookup"><span data-stu-id="c103a-123">To set up a development environment or to run apps, use the installers rather than these scripts.</span></span>

### <a name="recommended-version"></a><span data-ttu-id="c103a-124">Versión recomendada</span><span class="sxs-lookup"><span data-stu-id="c103a-124">Recommended version</span></span>

<span data-ttu-id="c103a-125">Se recomienda usar la versión estable de los scripts:</span><span class="sxs-lookup"><span data-stu-id="c103a-125">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="c103a-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="c103a-126">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="c103a-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="c103a-127">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

### <a name="script-behavior"></a><span data-ttu-id="c103a-128">Comportamiento de los scripts</span><span class="sxs-lookup"><span data-stu-id="c103a-128">Script behavior</span></span>

<span data-ttu-id="c103a-129">Ambos scripts tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c103a-129">Both scripts have the same behavior.</span></span> <span data-ttu-id="c103a-130">Descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.</span><span class="sxs-lookup"><span data-stu-id="c103a-130">They download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span>

<span data-ttu-id="c103a-131">De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan.</span><span class="sxs-lookup"><span data-stu-id="c103a-131">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="c103a-132">Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="c103a-132">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="c103a-133">De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="c103a-133">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="c103a-134">Para invalidar este comportamiento, especifique el argumento `-NoPath|--no-path`.</span><span class="sxs-lookup"><span data-stu-id="c103a-134">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span> <span data-ttu-id="c103a-135">El script no establece la variable de entorno `DOTNET_ROOT`.</span><span class="sxs-lookup"><span data-stu-id="c103a-135">The script doesn't set the `DOTNET_ROOT` environment variable.</span></span>

<span data-ttu-id="c103a-136">Antes de ejecutar el script, instale las [dependencias](../install/windows.md#dependencies) necesarias.</span><span class="sxs-lookup"><span data-stu-id="c103a-136">Before running the script, install the required [dependencies](../install/windows.md#dependencies).</span></span>

<span data-ttu-id="c103a-137">Puede instalar una versión específica mediante el argumento `-Version|--version`.</span><span class="sxs-lookup"><span data-stu-id="c103a-137">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="c103a-138">La versión debe especificarse como un número de versión de tres partes, por ejemplo, `2.1.0`.</span><span class="sxs-lookup"><span data-stu-id="c103a-138">The version must be specified as a three-part version number, such as `2.1.0`.</span></span> <span data-ttu-id="c103a-139">Si no se especifica la versión, el script instala la versión `latest`.</span><span class="sxs-lookup"><span data-stu-id="c103a-139">If the version isn't specified, the script installs the `latest` version.</span></span>

<span data-ttu-id="c103a-140">Los scripts de instalación no actualizan el Registro en Windows.</span><span class="sxs-lookup"><span data-stu-id="c103a-140">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="c103a-141">Solo descargan los archivos binarios comprimidos y los copian en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="c103a-141">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="c103a-142">Si desea que se actualicen los valores de las claves del Registro, use los instaladores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c103a-142">If you want registry key values to be updated, use the .NET Core installers.</span></span>

## <a name="options"></a><span data-ttu-id="c103a-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="c103a-143">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="c103a-144">Arquitectura de los archivos binarios de .NET Core para instalar.</span><span class="sxs-lookup"><span data-stu-id="c103a-144">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="c103a-145">Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`.</span><span class="sxs-lookup"><span data-stu-id="c103a-145">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="c103a-146">El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.</span><span class="sxs-lookup"><span data-stu-id="c103a-146">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="c103a-147">Especifica la dirección URL de la fuente de Azure al instalador.</span><span class="sxs-lookup"><span data-stu-id="c103a-147">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="c103a-148">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="c103a-148">We recommended that you don't change this value.</span></span> <span data-ttu-id="c103a-149">El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="c103a-149">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="c103a-150">Especifica el canal de origen para la instalación.</span><span class="sxs-lookup"><span data-stu-id="c103a-150">Specifies the source channel for the installation.</span></span> <span data-ttu-id="c103a-151">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c103a-151">The possible values are:</span></span>

  - <span data-ttu-id="c103a-152">`Current`: versión más actual.</span><span class="sxs-lookup"><span data-stu-id="c103a-152">`Current` - Most current release.</span></span>
  - <span data-ttu-id="c103a-153">`LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).</span><span class="sxs-lookup"><span data-stu-id="c103a-153">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="c103a-154">Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.1` o `3.0`).</span><span class="sxs-lookup"><span data-stu-id="c103a-154">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="c103a-155">Nombre de rama: por ejemplo, `release/3.1.1xx` o `master` (para versiones nocturnas).</span><span class="sxs-lookup"><span data-stu-id="c103a-155">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="c103a-156">Use esta opción para instalar una versión de un canal de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="c103a-156">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="c103a-157">Use el nombre del canal como aparece en [Instaladores y binarios](https://github.com/dotnet/core-sdk#installers-and-binaries).</span><span class="sxs-lookup"><span data-stu-id="c103a-157">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="c103a-158">El valor predeterminado es `LTS`.</span><span class="sxs-lookup"><span data-stu-id="c103a-158">The default value is `LTS`.</span></span> <span data-ttu-id="c103a-159">Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="c103a-159">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="c103a-160">Si se establece, el script no realizará la instalación.</span><span class="sxs-lookup"><span data-stu-id="c103a-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="c103a-161">En su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c103a-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="c103a-162">Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación.</span><span class="sxs-lookup"><span data-stu-id="c103a-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="c103a-163">También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c103a-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="c103a-164">Se utiliza como una cadena de consulta para anexar a la fuente de Azure.</span><span class="sxs-lookup"><span data-stu-id="c103a-164">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="c103a-165">Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.</span><span class="sxs-lookup"><span data-stu-id="c103a-165">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="c103a-166">Imprime la ayuda para el script.</span><span class="sxs-lookup"><span data-stu-id="c103a-166">Prints out help for the script.</span></span> <span data-ttu-id="c103a-167">Solo se aplica al script de Bash.</span><span class="sxs-lookup"><span data-stu-id="c103a-167">Applies only to bash script.</span></span> <span data-ttu-id="c103a-168">Para PowerShell, use `Get-Help ./dotnet-install.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c103a-168">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="c103a-169">Especifica la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="c103a-169">Specifies the installation path.</span></span> <span data-ttu-id="c103a-170">Si no existe el directorio, se crea.</span><span class="sxs-lookup"><span data-stu-id="c103a-170">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="c103a-171">El valor predeterminado es *%LocalAppData%\Microsoft\dotnet* en Windows y */usr/share/dotnet* en Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="c103a-171">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="c103a-172">Los archivos binarios se colocan directamente en el directorio.</span><span class="sxs-lookup"><span data-stu-id="c103a-172">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="c103a-173">Especifica una ruta de acceso a un archivo [global.json](global-json.md) que se va a usar para determinar la versión del SDK.</span><span class="sxs-lookup"><span data-stu-id="c103a-173">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="c103a-174">El archivo *global.json* debe tener un valor para `sdk:version`.</span><span class="sxs-lookup"><span data-stu-id="c103a-174">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="c103a-175">Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.</span><span class="sxs-lookup"><span data-stu-id="c103a-175">Disables downloading from the [Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="c103a-176">Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="c103a-176">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="c103a-177">De manera predeterminada, el script modifica la variable de entorno PATH, que hace que la CLI esté disponible inmediatamente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="c103a-177">By default, the script modifies the PATH, which makes the .NET Core CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="c103a-178">Si se establece, el instalador usa el proxy al realizar solicitudes web.</span><span class="sxs-lookup"><span data-stu-id="c103a-178">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="c103a-179">(Solo es válido para Windows).</span><span class="sxs-lookup"><span data-stu-id="c103a-179">(Only valid for Windows.)</span></span>

- **`-ProxyBypassList <LIST_OF_URLS>`**

  <span data-ttu-id="c103a-180">Si se establece con `ProxyAddress`, proporciona una lista de direcciones URL separadas por comas que omiten el proxy.</span><span class="sxs-lookup"><span data-stu-id="c103a-180">If set with `ProxyAddress`, provides a list of comma-separated urls that will bypass the proxy.</span></span> <span data-ttu-id="c103a-181">(Solo es válido para Windows).</span><span class="sxs-lookup"><span data-stu-id="c103a-181">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="c103a-182">Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="c103a-182">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="c103a-183">(Solo es válido para Windows).</span><span class="sxs-lookup"><span data-stu-id="c103a-183">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="c103a-184">Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="c103a-184">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="c103a-185">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c103a-185">The possible values are:</span></span>

  - <span data-ttu-id="c103a-186">`dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.</span><span class="sxs-lookup"><span data-stu-id="c103a-186">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="c103a-187">`aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="c103a-187">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="c103a-188">`windowsdesktop`: el entorno de tiempo de ejecución compartido `Microsoft.WindowsDesktop.App`.</span><span class="sxs-lookup"><span data-stu-id="c103a-188">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- **`--runtime-id <RID>`**

  <span data-ttu-id="c103a-189">Especifica el [identificador de entorno de ejecución](../rid-catalog.md) para el que se van a instalar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="c103a-189">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="c103a-190">Use `linux-x64` para Linux portátil.</span><span class="sxs-lookup"><span data-stu-id="c103a-190">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="c103a-191">(Solo es válido para Linux/macOS).</span><span class="sxs-lookup"><span data-stu-id="c103a-191">(Only valid for Linux/macOS.)</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="c103a-192">Este parámetro está obsoleto y puede quitarse en una versión futura del script.</span><span class="sxs-lookup"><span data-stu-id="c103a-192">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="c103a-193">La alternativa recomendada es la opción `-Runtime|--runtime`.</span><span class="sxs-lookup"><span data-stu-id="c103a-193">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="c103a-194">Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.</span><span class="sxs-lookup"><span data-stu-id="c103a-194">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="c103a-195">Esta opción equivale a especificar `-Runtime|--runtime dotnet`.</span><span class="sxs-lookup"><span data-stu-id="c103a-195">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="c103a-196">Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.</span><span class="sxs-lookup"><span data-stu-id="c103a-196">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="c103a-197">Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza.</span><span class="sxs-lookup"><span data-stu-id="c103a-197">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="c103a-198">Le recomendamos que no cambie este valor.</span><span class="sxs-lookup"><span data-stu-id="c103a-198">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="c103a-199">Muestra la información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c103a-199">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="c103a-200">Representa una versión de compilación concreta.</span><span class="sxs-lookup"><span data-stu-id="c103a-200">Represents a specific build version.</span></span> <span data-ttu-id="c103a-201">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c103a-201">The possible values are:</span></span>

  - <span data-ttu-id="c103a-202">`latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).</span><span class="sxs-lookup"><span data-stu-id="c103a-202">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="c103a-203">`coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama).</span><span class="sxs-lookup"><span data-stu-id="c103a-203">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="c103a-204">Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`.</span><span class="sxs-lookup"><span data-stu-id="c103a-204">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="c103a-205">Por ejemplo: `2.0.0-preview2-006120`.</span><span class="sxs-lookup"><span data-stu-id="c103a-205">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="c103a-206">Si no se especifica, el valor predeterminado de `-Version` es `latest`.</span><span class="sxs-lookup"><span data-stu-id="c103a-206">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="c103a-207">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c103a-207">Examples</span></span>

- <span data-ttu-id="c103a-208">Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c103a-208">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="c103a-209">Windows:</span><span class="sxs-lookup"><span data-stu-id="c103a-209">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="c103a-210">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="c103a-210">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="c103a-211">Instale la versión más reciente del canal 3.1 en la ubicación especificada:</span><span class="sxs-lookup"><span data-stu-id="c103a-211">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="c103a-212">Windows:</span><span class="sxs-lookup"><span data-stu-id="c103a-212">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="c103a-213">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="c103a-213">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="c103a-214">Instale la versión 3.0.0 del entorno de ejecución compartido:</span><span class="sxs-lookup"><span data-stu-id="c103a-214">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="c103a-215">Windows:</span><span class="sxs-lookup"><span data-stu-id="c103a-215">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="c103a-216">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="c103a-216">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="c103a-217">Obtenga el script e instale la versión 2.1.2 detrás de un proxy corporativo (solo Windows):</span><span class="sxs-lookup"><span data-stu-id="c103a-217">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="c103a-218">Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c103a-218">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="c103a-219">Windows:</span><span class="sxs-lookup"><span data-stu-id="c103a-219">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="c103a-220">macOS y Linux:</span><span class="sxs-lookup"><span data-stu-id="c103a-220">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="c103a-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="c103a-221">See also</span></span>

- [<span data-ttu-id="c103a-222">Versiones de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c103a-222">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="c103a-223">Archivo de descarga del SDK y .NET Core Runtime</span><span class="sxs-lookup"><span data-stu-id="c103a-223">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
